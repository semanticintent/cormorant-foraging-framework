# GESA: Generative Episodic Simulated Annealing

## Layer ∞ — The Optimization Layer

**GESA** is the optimization layer of the Cormorant Foraging Framework. Where DRIFT measures the gap and Fetch decides whether to act, GESA determines **how to act differently over time** — generating improved strategies from accumulated episode history using a simulated annealing schedule.

```
Layer 0:  Cormorant 3D (Chirp / Perch / Wake)   ->  Sense
Layer 1:  DRIFT                                  ->  Measure the gap
Layer 2:  Fetch                                  ->  Decide to act
Layer ∞:  GESA                                   ->  Optimise across episodes
```

**Without GESA, the stack is reactive. With GESA, it becomes adaptive.**

**Documentation:** [gesa.cormorantforaging.dev](https://gesa.cormorantforaging.dev)

---

## Three Core Concepts

### 1. Episodic Memory

Not *semantic* memory (general facts) but **situated experience with temporal context**:

| Memory Type | Example | What It Encodes |
|-------------|---------|-----------------|
| Semantic | "Burnout is caused by overload" | General knowledge |
| Episodic | "On March 3rd, reducing context switches for Team A resolved a pain streak within 2 sprints" | Context + action + outcome + time |

Every Fetch decision, every DRIFT measurement, every intervention outcome becomes an immutable episode stored with full context.

### 2. Simulated Annealing

Derived from metallurgy: heat metal to make it malleable, cool it slowly.

- **High temperature (early)** — Accept suboptimal moves. Explore widely. Escape local traps.
- **Low temperature (late)** — Narrow toward proven solutions. Exploit what works.

The critical insight: *deliberate acceptance of worse outcomes early prevents getting stuck in local optima*.

In GESA, temperature governs **exploration vs exploitation** across the episode timeline.

### 3. Generative Output

GESA does not retrieve cached answers. It **generates new strategies** by synthesising:

1. Relevant past episodes (retrieved by similarity)
2. Current context (DRIFT, Fetch, 3D scores)
3. Annealing temperature (how bold vs conservative to be)

The output is always a **novel hypothesis** — a candidate action that didn't necessarily exist before.

---

## The Name, Unpacked

| Word | Meaning in GESA |
|------|----------------|
| **Generative** | Produces novel strategies, not cached lookups |
| **Episodic** | Operates on situated, temporal memory — not facts |
| **Simulated** | Borrows the annealing metaphor — not real metallurgy |
| **Annealing** | The cooling schedule that governs exploration vs exploitation |

---

## The 8-Step Loop

```
OBSERVE current state -> RETRIEVE similar episodes -> GENERATE candidates
      ^                                                       |
    COOL <-- STORE new episode <-- ACT <-- SELECT <-- ANNEAL
```

| Step | Action |
|------|--------|
| **1. OBSERVE** | Read DRIFT, Fetch, and 3D scores |
| **2. RETRIEVE** | Find similar past episodes |
| **3. GENERATE** | Synthesise candidate strategies |
| **4. ANNEAL** | Filter by temperature (bold vs conservative) |
| **5. SELECT** | Pick best candidate within temperature |
| **6. ACT** | Execute selected strategy |
| **7. STORE** | Record outcome as new episode |
| **8. COOL** | Advance the temperature schedule |

---

### Step 1: OBSERVE

**Read current system state.**

Inputs:
- DRIFT gap and sign (positive/negative/zero)
- Fetch score and decision threshold
- Chirp, Perch, Wake scores
- Active domain and dimension
- Gap velocity (how DRIFT has moved across recent episodes)

This step is passive — it reads, does not modify. The observe step establishes the context fingerprint that drives retrieval.

---

### Step 2: RETRIEVE

**Search episode memory for situations with similar context fingerprint.**

Similarity is measured across five dimensions:

```
Similarity(e1, e2) =
    0.30 x DomainMatch
  + 0.25 x DriftProximity
  + 0.20 x DimensionMatch
  + 0.15 x TemperatureProximity
  + 0.10 x OutcomePolarity
```

- **DomainMatch** — Are the episodes from the same domain?
- **DriftProximity** — How close is the DRIFT magnitude? A gap of 42 is more similar to 38 than to 5.
- **DimensionMatch** — In 6D context: does the origin dimension match?
- **TemperatureProximity** — Episodes captured at similar temperatures are more relevant.
- **OutcomePolarity** — Failed episodes constrain generation; successful episodes inform it. Both are retrieved.

Retrieval also applies temporal decay (`EpisodeWeight = BaseWeight x e^(-age/tau)`) — recent episodes carry more weight.

---

### Step 3: GENERATE

**Synthesise candidate strategies from retrieved episodes + current context.**

Generation is not lookup. The generator produces *variations and combinations*, not exact replays of past episodes. A candidate strategy may combine patterns from three different historical episodes in a way that never occurred before.

At **high temperature**: the generator includes novel, less-proven candidates.
At **low temperature**: the generator is constrained to historically-validated strategies.

Output: A set of `CandidateStrategy[]` objects, each with a proposed action, confidence score, episodic support count, and reasoning trace.

---

### Step 4: ANNEAL

**Apply the temperature filter.**

| Temperature | Filter Applied |
|-------------|---------------|
| T > 70 | All candidates included — full exploration |
| 40 < T <= 70 | Candidates with episodicSupport >= 1 included |
| 20 < T <= 40 | Candidates with episodicSupport >= 3 included |
| T <= 20 | Only candidates with episodicSupport >= 5 and confidence >= 60 |

This makes GESA conservative over time without being permanently conservative from the start. Early in the system's life, weak candidates are considered. As the episode store grows and temperature drops, only proven strategies survive the filter.

---

### Step 5: SELECT

**Score remaining candidates. Pick the highest within temperature constraints.**

```
Score = confidence x episodicSupport x gapVelocityMultiplier

Where:
  gapVelocityMultiplier = 1.0 + (gapVelocity x 0.1)
```

Gap velocity adjustment: if the gap is **widening** (positive velocity), higher-confidence strategies are weighted more heavily — the situation is worsening, act decisively. If the gap is **closing**, lower-confidence exploratory strategies can be tolerated.

---

### Step 6: ACT

**Return or execute the selected strategy.**

Depending on deployment context:
- **Recommendation mode** — Return the strategy with full GESARecommendation object for human decision
- **Automatic mode** — Execute directly if Fetch score exceeds Execute threshold (>1000)
- **Hybrid mode** — Auto-execute for high-confidence low-risk strategies; recommend for others

The selected strategy always carries its full provenance: which episodes supported it, what temperature it was generated under, what alternatives were considered.

---

### Step 7: STORE

**After outcome is observable, write the new episode to memory.**

Two phases:
- **Phase A (at time of action):** Write context, action, and initial state. Mark outcome as pending.
- **Phase B (after outcome observed):** Update with `driftAfter`, `gapChange`, `success`, and `timeToResolve`.

The gap between Phase A and Phase B is domain-dependent:
- Browser automation: seconds to minutes
- Content strategy: days to weeks
- Workplace interventions: sprints to months

Incomplete episodes (Phase A only) are excluded from retrieval until Phase B completes.

---

### Step 8: COOL

**Advance the temperature schedule.**

```
T_new = T_current x alpha
```

Where `alpha` is the cooling rate from the active temperature profile.

Temperature only cools when a new episode is stored (Step 7 completes). No episode = no cooling. This prevents artificial temperature decay during inactive periods.

---

## Temperature Profiles

All profiles share the base formula: `Temperature(t) = T0 x alpha^t`

| Profile | alpha | Character | Use When |
|---------|-------|-----------|----------|
| **Fast Cool** | 0.85 | Exploitation-first | Domain well-understood, speed matters |
| **Standard Cool** | 0.95 | Balanced | Default for new deployments |
| **Slow Cool** | 0.99 | Exploration-first | Unknown problem space, premature convergence risk |
| **Adaptive Cool** | f(variance) | Self-tuning | Sufficient history (30+ episodes), variable domain |

### Adaptive Cool

The most sophisticated profile. Cooling rate adjusts dynamically:

```
If variance(recent_outcomes) > threshold:
    alpha <- max(alpha - 0.02, 0.90)   // Slow cooling: outcomes unpredictable
Else:
    alpha <- min(alpha + 0.01, 0.99)   // Speed cooling: outcomes converging
```

Also reads DRIFT trajectory:
- Negative gap velocity (gap closing) — allow faster cooling
- Positive gap velocity (gap widening) — force slower cooling, increase exploration

---

## Loop Invariants

Three invariants must hold at every cycle:

1. **Every ACT produces an episode.** No action without capture.
2. **Every episode is immutable.** No retroactive modification of what happened.
3. **Temperature only decreases.** The system earns conservatism through experience; it cannot reset to exploration without explicit intervention.

Violation of invariant 1 or 2 breaks the learning guarantee. Violation of invariant 3 means the system could oscillate between exploration and exploitation, never converging.

---

## What Makes GESA Different

| Approach | How It Learns |
|----------|--------------|
| Reinforcement Learning | Reward signal updates a value function (implicit, neural) |
| Case-Based Reasoning | Retrieve -> Adapt -> Reuse (deterministic, no temperature) |
| **GESA** | **Retrieve -> Generate -> Anneal -> Select (explicit temperature, observable)** |

GESA's novel contribution: the **integration of episodic case-based reasoning with an explicit annealing schedule inside a biomimetic sensing framework** — making the exploration/exploitation tradeoff explicit, observable, and tunable rather than implicit in a neural architecture.

---

## Episode Schema

```
Episode {
  id:              string        // Unique identifier
  timestamp:       ISO-8601      // When this episode occurred
  domain:          string        // Problem domain (Workplace, Trading, Content, etc.)
  dimension:       string        // 6D dimension if applicable (D1-D6)

  // Context (from OBSERVE)
  driftBefore:     number        // DRIFT score at time of action
  fetchScore:      number        // Fetch score that triggered action
  chirpScore:      number        // Sound dimension score
  perchScore:      number        // Space dimension score
  wakeScore:       number        // Time dimension score
  temperature:     number        // Annealing temperature at time of action

  // Action (from ACT)
  strategy:        string        // What was done
  confidence:      number        // Confidence at time of selection
  alternatives:    string[]      // What else was considered

  // Outcome (from STORE Phase B)
  driftAfter:      number        // DRIFT score after action
  gapChange:       number        // driftBefore - driftAfter
  success:         boolean       // Did the gap close?
  timeToResolve:   number        // Time between action and observable outcome
}
```

---

## The Completeness GESA Provides

| Question | Framework Layer |
|----------|----------------|
| What do I perceive? | 3D Foundation (Chirp/Perch/Wake) |
| Where is the gap? | DRIFT |
| Should I act now? | Fetch |
| **How should I act differently next time?** | **GESA** |

The first three questions make the system **capable**. The fourth makes it **intelligent**.

---

*"The cormorant doesn't retrieve a cached dive. It generates a new one — from everything it remembers, weighted by what worked."*
