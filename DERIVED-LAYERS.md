# Derived Layers: DRIFT and Fetch

Building on the three-dimensional foundation to create measurement and action systems.

---

## Overview

The Cormorant Foraging Framework extends beyond sensing (Sound, Space, Time) through two additional layers:

```
Layer 2: Fetch (Action)
         ↑
Layer 1: DRIFT (Measurement)
         ↑
Layer 0: Sound, Space, Time (Sensing)
```

**Key Principle:** Each layer has a **single responsibility** with clear dependencies. No circular loops—feedback returns to Layer 0 for re-sensing.

---

## Layer 1: DRIFT — Measurement

**DRIFT** measures the gap between what someone demonstrates they know how to do (methodology) and what they actually deliver (performance).

### Formula

```
DRIFT = Methodology − Performance
```

**Positive DRIFT:** Demonstrated capability exceeds delivered results (underperformance)
**Negative DRIFT:** Delivered results exceed demonstrated methodology (overperformance or hidden capability)
**Zero DRIFT:** Performance matches methodology (alignment)

### Observable Components

#### Methodology Score
What the person/team **demonstrates** they can do:

- Documentation quality
- Process adherence
- Tool usage sophistication
- Communication patterns
- Planning artifacts

**Scoring:** 0-100 based on observable evidence of capability

#### Performance Score
What the person/team **actually delivers**:

- Output quality
- Delivery consistency
- Error rates
- Timeline adherence
- Outcome achievement

**Scoring:** 0-100 based on measurable results

### Key Constraints

**What DRIFT Measures:**
- ✅ Gap between shown capability and delivered results
- ✅ Observable patterns in behavior
- ✅ Measurable outcomes

**What DRIFT Does NOT Measure:**
- ❌ Intent or motivation
- ❌ Predictions of future performance
- ❌ Normative judgments about "should"
- ❌ Hidden knowledge or capabilities

### Real-World Example: HEAT Framework

**HEAT** (Healthy Effort Analysis Tool) uses DRIFT to detect workplace intelligence signals.

**Scenario:** Senior developer with high methodology score (writes detailed design docs, uses advanced patterns) but low performance score (frequent bugs, missed deadlines).

```
Methodology = 85 (excellent documentation, sophisticated approaches)
Performance = 45 (missed deadlines, high bug rate)
DRIFT = +40 (significant gap)
```

**Interpretation:** Large positive DRIFT suggests potential issues:
- Disengagement (knows how but not applying)
- External blockers (process/tool issues)
- Misaligned incentives
- Capacity limitations

**NOT concluded:** Laziness, bad attitude, lack of skill (these are speculative)

### DRIFT in Different Domains

#### Software Development
- **Methodology:** Code review quality, architectural decisions, documentation
- **Performance:** Bug rates, delivery speed, production incidents

#### Customer Support
- **Methodology:** Escalation protocols, knowledge base usage, ticket categorization
- **Performance:** Resolution time, customer satisfaction, first-contact resolution

#### Sales
- **Methodology:** Pipeline management, CRM hygiene, qualification process
- **Performance:** Close rates, deal size, sales cycle length

### Dependency on Layer 0

DRIFT **requires** Layer 0 sensing:

- **Sound (ChirpIQX):** Real-time signals of urgency and risk
- **Space (PerchIQX):** Structural understanding of relationships
- **Time (WakeIQX):** Historical patterns and trends

Without observable anchoring from Layer 0, DRIFT becomes speculation.

### Documentation

Full DRIFT specification: [drift.cormorantforaging.dev](https://drift.cormorantforaging.dev)

---

## Layer 2: Fetch — Action

**Fetch** transforms measurement into decision through multiplicative gating. Like a cormorant deciding whether to dive for a fish, it requires all factors to align.

### Formula

```
Fetch = Chirp × |DRIFT| × Confidence
```

Where:
- **Chirp:** Urgency score from Layer 0 (Sound dimension)
- **|DRIFT|:** Absolute value of DRIFT measurement from Layer 1
- **Confidence:** Certainty in the measurements (0-1)

### Component Breakdown

#### Chirp (Urgency)
From ChirpIQX additive scoring:
- How urgent is this situation?
- What's the immediate impact?
- Are there time-sensitive risks?

**Range:** 0-1000+ (typical operational range)

#### |DRIFT| (Magnitude)
Absolute value of DRIFT gap:
- How large is the methodology-performance gap?
- Positive or negative, the magnitude matters

**Range:** 0-100 (from percentage-based scoring)

#### Confidence (Certainty)
How certain are we about the measurements?
- Sample size adequate?
- Data quality sufficient?
- Time period representative?

**Range:** 0.0-1.0 (0% to 100% confidence)

### Decision Thresholds

```
Fetch > 1000  → Execute immediately
Fetch 500-1000 → Confirm before executing
Fetch 100-500  → Queue for later review
Fetch < 100    → Wait and gather more data
```

### Multiplicative Gating

**Critical property:** If **any** component is zero, Fetch = 0 (no action).

**Examples:**

1. **High urgency, no DRIFT:**
   ```
   Fetch = 800 × 0 × 0.9 = 0 (Wait)
   ```
   Urgent situation but performance matches methodology—no intervention needed.

2. **Large DRIFT, low confidence:**
   ```
   Fetch = 600 × 45 × 0.1 = 2,700 (Execute? No—low confidence)
   ```
   But note the confidence multiplier brings this below reliable threshold.

3. **Aligned signals:**
   ```
   Fetch = 750 × 35 × 0.85 = 22,312 (Execute)
   ```
   High urgency, significant DRIFT, high confidence—clear action signal.

### Real-World Example: Workplace Intervention

**Scenario:** Team lead showing concerning patterns

**Inputs:**
- **Chirp:** 720 (high urgency—critical project at risk)
- **DRIFT:** -32 (negative—delivering beyond demonstrated methodology)
- **Confidence:** 0.88 (strong signal over 6 weeks)

**Calculation:**
```
Fetch = 720 × |-32| × 0.88 = 20,275
```

**Decision:** Execute—immediate 1:1 conversation

**Why negative DRIFT matters:** Consistently delivering beyond demonstrated capability suggests:
- Hidden expertise not being leveraged
- Unsustainable effort (burnout risk)
- Process bypassing (technical debt accumulation)

### Fetch in Different Domains

#### Performance Management
- **Chirp:** Project criticality, deadline pressure
- **DRIFT:** Capability vs. delivery gap
- **Confidence:** Observation period, data completeness
- **Action:** 1:1s, interventions, resource allocation

#### System Optimization
- **Chirp:** Performance degradation urgency
- **DRIFT:** Architecture sophistication vs. actual efficiency
- **Confidence:** Profiling data quality
- **Action:** Refactoring, infrastructure changes

#### Customer Success
- **Chirp:** Churn risk, expansion opportunity
- **DRIFT:** Contracted services vs. actual usage
- **Confidence:** Usage data completeness
- **Action:** Proactive outreach, upsell conversations

### Feedback Loop

**Critical:** Fetch does **not** create a closed loop.

```
Layer 0 (Sense) → Layer 1 (Measure) → Layer 2 (Act)
                                         ↓
                                   Take Action
                                         ↓
                           Return to Layer 0 (Re-sense)
```

After action, return to sensing:
- Did the urgency change? (Sound)
- Did relationships shift? (Space)
- How has the situation evolved? (Time)
- Did DRIFT close or widen? (Measurement)

**No shortcuts.** Don't assume the action worked—measure again.

### Design Principles

1. **Multiplicative gating:** Any zero blocks action
2. **Threshold-based decisions:** Clear boundaries for action
3. **No speculation:** Only measured inputs
4. **Clean dependencies:** Fetch depends on DRIFT, DRIFT depends on Layer 0
5. **Observable outcomes:** Actions create new signals to sense

### Documentation

Full Fetch specification: [fetch.cormorantforaging.dev](https://fetch.cormorantforaging.dev)

---

## Relationship Between Layers

### Layer 0 → Layer 1
**Sound, Space, Time enable DRIFT measurement:**

- **Sound:** Real-time performance signals (bug rates, delivery speed)
- **Space:** Structural methodology signals (documentation, process adherence)
- **Time:** Historical patterns (trend analysis, degradation detection)

Without Layer 0, DRIFT has no observable foundation.

### Layer 1 → Layer 2
**DRIFT measurement enables Fetch decisions:**

- DRIFT magnitude becomes a gating factor
- Sign of DRIFT (positive/negative) informs action type
- DRIFT confidence feeds into overall certainty

Without Layer 1, Fetch has no gap to act upon.

### Layer 2 → Layer 0
**Fetch actions create new signals to sense:**

- Actions change urgency (Sound)
- Actions alter relationships (Space)
- Actions create history (Time)

Without returning to Layer 0, learning stops.

---

## Common Patterns

### Pattern 1: High Urgency, No DRIFT
```
Chirp: High | DRIFT: ~0 | Fetch: Low
```
**Interpretation:** Urgent situation but performance matches capability
**Action:** Monitor but don't intervene

### Pattern 2: Low Urgency, High DRIFT
```
Chirp: Low | DRIFT: High | Fetch: Low
```
**Interpretation:** Significant gap but not time-sensitive
**Action:** Queue for later investigation

### Pattern 3: High Urgency, High DRIFT, Low Confidence
```
Chirp: High | DRIFT: High | Confidence: Low | Fetch: Low
```
**Interpretation:** Looks urgent with big gap, but data insufficient
**Action:** Gather more data before acting

### Pattern 4: Aligned Signals
```
Chirp: High | DRIFT: High | Confidence: High | Fetch: Very High
```
**Interpretation:** Clear, confident signal requiring action
**Action:** Execute immediately

---

## Layer Infinity: GESA — Optimization

**Generative Episodic Simulated Annealing** completes the stack — transforming a reactive system into an adaptive one that learns from its own decisions.

Where DRIFT measures the gap and Fetch decides whether to act, GESA determines **how to act differently over time**.

### The 8-Step Loop

```
OBSERVE -> RETRIEVE -> GENERATE -> ANNEAL -> SELECT -> ACT -> STORE -> COOL
```

| Step | Action |
|------|--------|
| **OBSERVE** | Read DRIFT, Fetch, and 3D scores |
| **RETRIEVE** | Find similar past episodes by context fingerprint |
| **GENERATE** | Synthesise candidate strategies from episodes + context |
| **ANNEAL** | Filter candidates by temperature (bold vs conservative) |
| **SELECT** | Score and pick best candidate within temperature constraints |
| **ACT** | Execute or recommend the selected strategy |
| **STORE** | Record outcome as new immutable episode |
| **COOL** | Advance the temperature schedule |

### Three Core Concepts

1. **Episodic Memory** — Situated experience with temporal context, not general facts. Every Fetch decision, DRIFT measurement, and intervention outcome becomes an immutable episode.

2. **Simulated Annealing** — High temperature (early) accepts suboptimal moves for exploration; low temperature (late) narrows toward proven solutions. Temperature governs exploration vs exploitation across the episode timeline.

3. **Generative Output** — GESA does not retrieve cached answers. It generates new strategies by synthesising relevant past episodes, current context, and annealing temperature.

### Loop Invariants

Three invariants must hold at every cycle:

1. **Every ACT produces an episode.** No action without capture.
2. **Every episode is immutable.** No retroactive modification.
3. **Temperature only decreases.** The system earns conservatism through experience.

### Dependency Chain

```
Layer 0 (Sense) -> Layer 1 (Measure) -> Layer 2 (Act) -> Layer ∞ (Learn)
                                                              |
                                                    Store Episode
                                                              |
                                              Return to Layer 0 (Re-sense)
```

GESA depends on all prior layers: 3D scores from Layer 0, gap measurement from DRIFT, and action decisions from Fetch. Its episode store feeds back to Layer 0 through re-sensing — maintaining the no-circular-dependency principle.

**Full specification:** [GESA.md](GESA.md) | **Documentation:** [gesa.cormorantforaging.dev](https://gesa.cormorantforaging.dev)

---

## Next Steps

- **[GESA Specification](GESA.md)** - Full Layer ∞ specification with formulas and schemas
- **[Applications](APPLICATIONS.md)** - See DRIFT, Fetch, and GESA in production systems
- **[Empirical Validation](EMPIRICAL-VALIDATION.md)** - Performance data for derived layers
- **[Dimensions](DIMENSIONS.md)** - Deep dive on Layer 0 foundation

---

*"Measure the gap. Gate the action. Learn from history. The cormorant's loop, made reproducible."*
