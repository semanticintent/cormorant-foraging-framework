# The Three Dimensions

A deep dive into the Sound, Space, and Time dimensions of the Cormorant Foraging Framework.

---

## Overview

The framework maps three observable physical dimensions to information processing paradigms:

| Dimension | Physical Basis | Scoring Method | Key Property |
|-----------|---------------|----------------|--------------|
| **Sound** | Acoustic superposition | Additive | Non-reversible propagation |
| **Space** | Cartesian coordinates | Multiplicative | Static snapshots |
| **Time** | Temporal flow | Exponential decay | Irreversible history |

Each dimension emerged independently through production systems before the underlying pattern was recognized.

---

## Sound (ChirpIQX)

### Physical Foundation

Sound waves combine through **superposition**—multiple acoustic signals add together linearly. When two sound waves meet, their amplitudes sum at each point in space and time. This additive property maps directly to urgency assessment.

**Key Properties:**
- **Linear combination** - Effects sum independently
- **Non-reversible** - Sound propagates forward in time
- **Attention-grabbing** - Louder signals dominate awareness

### Mathematical Model

```
Score = Σ(Factor_i × Weight_i) - Σ(Risk_j × Weight_j)
```

Where:
- Factors contribute positively (opportunity signals)
- Risks contribute negatively (warning signals)
- Weights modulate importance

### Real-World Implementation: ChirpIQX

**Domain:** Fantasy sports player intelligence

**Formula:**
```
ChirpScore = (RecentPerformance × 0.4) +
             (OpportunityScore × 0.3) +
             (ScheduleDifficulty × 0.2) +
             (VolumeTrend × 0.1) -
             (InjuryRisk × 0.3)
```

**Performance:**
- 78% accuracy predicting breakout players
- Processes real-time game data
- Deployed as MCP server

**Observable Anchoring:**
- Recent stats (last 3 games)
- Opponent defensive rankings
- Injury reports
- Target share percentages

### When to Use Sound Dimension

Use additive scoring when:
- **Partial information has value** - Incomplete data still provides signal
- **Speed matters** - Fast decisions needed
- **Multiple independent factors** - No single factor should block action
- **Communication urgency** - Alerting, warnings, notifications

**Examples:**
- Risk assessment dashboards
- Alert prioritization systems
- Real-time opportunity detection
- Urgency scoring for support tickets

---

## Space (PerchIQX)

### Physical Foundation

Three-dimensional space uses **Cartesian coordinates** (x, y, z) where each dimension is **independent but multiplicative** in volume calculation. Volume = length × width × height. If any dimension is zero, the entire volume collapses to zero.

**Key Properties:**
- **Multiplicative relationships** - Dimensions scale each other
- **Zero collapse** - Missing one dimension eliminates the whole
- **Static snapshots** - Spatial relationships at a point in time
- **Structural mapping** - Reveals organization and hierarchy

### Mathematical Model

```
Score = Factor_1 × Factor_2 × Factor_3 × ... × Factor_n
```

Where:
- Each factor represents an independent dimension
- Zero in any factor reduces score to zero
- Higher values in any dimension amplify the total

### Real-World Implementation: PerchIQX

**Domain:** Database schema intelligence

**Formula:**
```
ICE Score = (Insight × Context × Execution) / 100
```

Where:
- **Insight** (0-10): Value of optimizing this query/schema
- **Context** (0-10): Understanding of relationships and dependencies
- **Execution** (0-10): Feasibility and effort estimate

**Performance:**
- 398 passing automated tests
- Analyzes Cloudflare D1 databases
- Identifies optimization opportunities

**Observable Anchoring:**
- Table cardinalities (row counts)
- Foreign key relationships
- Index presence/absence
- Query patterns in schema

**Key Insight:** If Context = 0 (don't understand the schema), the entire ICE score becomes 0 regardless of Insight or Execution values. This prevents action without understanding.

### When to Use Space Dimension

Use multiplicative scoring when:
- **All factors required** - Missing any dimension should block action
- **Structural analysis** - Mapping relationships and hierarchies
- **Interdependencies matter** - Factors amplify or nullify each other
- **Snapshot assessment** - Static evaluation at a point in time

**Examples:**
- Prioritization frameworks (ICE, RICE)
- Database optimization
- Architecture analysis
- Relationship mapping

---

## Time (WakeIQX)

### Physical Foundation

Time flows **unidirectionally** from past to future, creating an **irreversible history**. Information relevance naturally degrades over time like a boat's wake that gradually dissipates. Recent events have stronger impact than distant ones.

**Key Properties:**
- **Exponential decay** - Relevance decreases continuously
- **Recency bias** - Recent information weighted higher
- **Irreversibility** - Cannot undo the passage of time
- **Memory persistence** - Some signals last longer than others

### Mathematical Model

```
Relevance = BaseRelevance × e^(-age/halfLife) × AccessBoost
```

Where:
- `BaseRelevance`: Initial importance of the information
- `age`: Time since creation/last modification
- `halfLife`: Time period where relevance drops to 50%
- `AccessBoost`: Multiplier for recently accessed items

### Real-World Implementation: WakeIQX

**Domain:** Context continuity management

**Formula:**
```
ContextRelevance = InitialScore × e^(-days/7) × (1 + 0.5*recentAccess)
```

**Performance:**
- 85% context maintenance across sessions
- Manages conversation history
- Temporal context protocol

**Observable Anchoring:**
- File modification timestamps
- Last access times
- Creation dates
- Logged event sequences

**Key Insight:** Information doesn't disappear—it fades. A file modified 30 days ago has lower relevance than one modified yesterday, but a 30-day-old file accessed today gets a boost.

### When to Use Time Dimension

Use exponential decay when:
- **Recency matters** - Recent information more valuable
- **Memory management** - Limited capacity requires prioritization
- **Continuity tracking** - Maintaining context over time
- **Historical patterns** - Understanding trends and sequences

**Examples:**
- Cache eviction policies
- Session management
- Document relevance ranking
- Activity feed prioritization
- Log analysis

---

## Dimensional Interactions

### Pure Dimensions vs. Hybrid Systems

Most real-world systems combine dimensions:

**Example: Task Prioritization System**

```
Priority = (Urgency + Impact) × Feasibility × e^(-age/halfLife)
           ↑                    ↑              ↑
         Sound              Space           Time
```

- **Sound (Urgency + Impact)**: Additive factors for immediate attention
- **Space (× Feasibility)**: Multiplicative gate (can't do impossible tasks)
- **Time (decay)**: Older tasks lose relevance

### Dimensional Purity

The framework intentionally keeps dimensions **pure** in their implementations:

- **ChirpIQX**: Only additive scoring
- **PerchIQX**: Only multiplicative scoring
- **WakeIQX**: Only exponential decay

This purity makes each system **easier to reason about** and **composable**.

---

## Observable Anchoring

Every dimension ties to **measurable, observable properties**:

### Sound Anchors
- Performance metrics (percentages, counts)
- Difficulty ratings (opponent strength)
- Risk indicators (injury status)
- Volume measurements (usage rates)

### Space Anchors
- Structural properties (table sizes)
- Relationships (foreign keys)
- Presence/absence (indexes, constraints)
- Cardinalities (one-to-many, many-to-many)

### Time Anchors
- Timestamps (creation, modification)
- Access logs (last opened, viewed)
- Event sequences (ordered history)
- Age calculations (duration since event)

**No speculation. No predictions. Only observable signals.**

---

## Design Constraints

### What These Dimensions DON'T Include

1. **Intent** - No mind-reading or assumption about purpose
2. **Normative judgments** - No "should" or "ought"
3. **Predictions** - No forecasting future states
4. **Hidden information** - Only what's measurable

These constraints ensure the framework stays **grounded in physics** rather than drifting into speculation.

---

## Mathematical Properties

### Sound (Additive)
- **Commutative**: A + B = B + A
- **Associative**: (A + B) + C = A + (B + C)
- **Identity**: 0 is identity element
- **Monotonic**: Adding positive values always increases score

### Space (Multiplicative)
- **Commutative**: A × B = B × A
- **Associative**: (A × B) × C = A × (B × C)
- **Identity**: 1 is identity element
- **Zero annihilator**: 0 × anything = 0

### Time (Exponential)
- **Continuous decay**: No sudden drops
- **Half-life**: Predictable degradation rate
- **Non-negative**: Relevance never goes negative
- **Asymptotic**: Approaches but never reaches zero

---

## Next Steps

- **[Derived Layers](DERIVED-LAYERS.md)** - How DRIFT and Fetch build on these dimensions
- **[Applications](APPLICATIONS.md)** - Real-world implementations
- **[Empirical Validation](EMPIRICAL-VALIDATION.md)** - Performance data

---

*"Three dimensions. Three metaphors. Three production systems."* 🐦
