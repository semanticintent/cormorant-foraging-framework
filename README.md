# Cormorant Foraging Framework
## A Three-Dimensional Taxonomy for Intelligence Systems

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![GitHub](https://img.shields.io/badge/GitHub-semanticintent%2Fcormorant--foraging--framework-blue)](https://github.com/semanticintent/cormorant-foraging-framework)

**A biomimetic framework mapping natural dimensions to intelligence system design.**

> *"Intelligence systems naturally align with physical dimensions when guided by natural metaphors."*

---

## Abstract

The **Cormorant Foraging Framework** presents a three-dimensional taxonomy for categorizing and designing intelligence systems using observable physical dimensions—Sound, Space, and Time. Inspired by cormorant foraging behavior, the framework demonstrates how natural metaphors map directly to information processing paradigms.

Rather than being imposed top-down, this framework emerged empirically from three independently deployed production systems (ChirpIQX, PerchIQX, WakeIQX), revealing convergent design principles aligned with fundamental physics.

**Author:** Michael Shatny
**ORCID:** [0009-0006-2011-3258](https://orcid.org/0009-0006-2011-3258)
**Date:** January 2026
**License:** [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)
**Website:** [cormorantforaging.dev](https://cormorantforaging.dev)

---

## The Three Dimensions

### Sound (ChirpIQX) — Communication & Urgency

**Physical Basis:** Acoustic waves combining through superposition; non-reversible propagation

**Scoring Method:** Additive formula
```
Score = (Factor1 × Weight1) + (Factor2 × Weight2) - (Risk × WeightRisk)
```

**Metaphor:** Cormorant chirping for coordination and warnings

**Applications:**
- Real-time urgency assessment
- Fast decisions where partial scores remain meaningful
- Communication-driven intelligence

**Observable Anchoring:** Recent performance, schedule difficulty, measurable metrics

**Documentation:** [chirpiqx.com](https://chirpiqx.com)

---

### Space (PerchIQX) — Structure & Relationships

**Physical Basis:** Three-dimensional Cartesian coordinates; static spatial snapshots

**Scoring Method:** Multiplicative formula
```
ICE Score = (Insight × Context × Execution) / 100
```

**Metaphor:** Cormorant perching to observe and map spatial relationships

**Key Insight:** Missing any dimension collapses priority entirely (zero in any factor blocks action)

**Applications:**
- Structural analysis
- Database schema intelligence
- Relationship mapping

**Observable Anchoring:** Schema relationships, cardinalities, index presence

**Documentation:** [perchiqx.com](https://perchiqx.com)

---

### Time (WakeIQX) — Memory & Continuity

**Physical Basis:** Unidirectional temporal flow creating irreversible history

**Scoring Method:** Exponential decay function
```
Relevance = BaseRelevance × e^(-age/halfLife) × AccessBoost
```

**Metaphor:** Wake trails persisting and gradually fading after passage

**Key Insight:** Information relevance degrades continuously; recent access boosts weight

**Applications:**
- Memory management
- Context continuity
- Historical pattern recognition

**Observable Anchoring:** Timestamps, file modifications, logged events

**Documentation:** [wakeiqx.com](https://wakeiqx.com)

---

## Derived Layers

The framework extends through two additional layers built on the 3D foundation:

### Layer 1: DRIFT — Measurement

Measures gap between demonstrated methodology and actual performance.

```
DRIFT = Methodology − Performance
```

**Principle:** Depends entirely on Layer 0 sensing; no speculation beyond measurement.

**Documentation:** [drift.cormorantforaging.dev](https://drift.cormorantforaging.dev)

---

### Layer 2: Fetch — Action

Transforms measurement into decision through multiplicative gating.

```
Fetch = Chirp × |DRIFT| × Confidence
```

**Decision Thresholds:**
- Execute: >1000
- Confirm: 500-1000
- Queue: 100-500
- Wait: <100

**Principle:** Any zero component blocks execution.

**Documentation:** [fetch.cormorantforaging.dev](https://fetch.cormorantforaging.dev)

---

## Empirical Validation

### ChirpIQX
- **Domain:** Fantasy sports intelligence
- **Accuracy:** 78% prediction rate for breakout players
- **Implementation:** Model Context Protocol server

### PerchIQX
- **Domain:** Database schema analysis
- **Tests:** 398 passing automated tests
- **Implementation:** Cloudflare D1 intelligence

### WakeIQX
- **Domain:** Context continuity management
- **Performance:** 85% context maintenance across sessions
- **Implementation:** Temporal context protocol

---

## Design Principles

1. **Observable Anchoring** — Every measurement ties to detectable physical properties
2. **No Speculation** — Excludes predictions, intent, and normative judgments
3. **Clean Layering** — Each layer has single responsibility with clear dependencies
4. **No Circular Dependencies** — Feedback returns to Layer 0 for re-sensing
5. **Emergent Discovery** — Patterns found, not forced

---

## Relationship to Existing Systems

The framework maps onto established decision architectures while providing unique biomimetic grounding:

- **OODA Loop** (Observe-Orient-Decide-Act)
- **PID Controllers** (Proportional-Integral-Derivative)
- **Reinforcement Learning** (Sense-Process-Act cycles)

---

## Applications

The framework has been applied in:

- **PACE Pattern** — Conversational UX using the dimensional taxonomy
- **6D Foraging Methodology** — Strategic analysis with Sound/Space/Time scoring
- **HEAT Framework** — Workplace intelligence detection
- **PlayIQX, ChirpIQX, BrowserLLM** — Production implementations

---

## Repository Structure

```
cormorant-foraging-framework/
├── README.md                 # This file - framework overview
├── DIMENSIONS.md             # Deep dive on Sound, Space, Time
├── DERIVED-LAYERS.md         # DRIFT and Fetch extensions
├── APPLICATIONS.md           # Real-world implementations
├── EMPIRICAL-VALIDATION.md   # Performance data and testing
├── CITATION.cff              # Machine-readable citation metadata
├── CHANGELOG.md              # Version history
├── CONTRIBUTING.md           # How to contribute
└── LICENSE                   # CC BY 4.0 license
```

---

## Connection to Ecosystem

Cormorant Foraging Framework is the foundational taxonomy for:

```
Semantic Intent (Philosophy)
  ↓
Cormorant Foraging (3D Framework) ← You are here
  ├─ PACE Pattern (DOI: 10.5281/zenodo.18049371)
  ├─ 6D Methodology (DOI: 10.5281/zenodo.18209946)
  └─ HEAT Framework
      └─ Extensions: DRIFT, Fetch
```

**Related Projects:**
- [Semantic Intent SSOT](https://semanticintent.dev/papers/semantic-intent-ssot)
- [PACE Pattern](https://github.com/semanticintent/pace-pattern)
- [6D Foraging Methodology](https://github.com/semanticintent/6d-foraging-methodology)

---

## Citation

If you use or reference the Cormorant Foraging Framework in your work, please cite:

### APA Style

Shatny, M. (2026). Cormorant Foraging Framework: A Three-Dimensional Taxonomy for Intelligence Systems. Zenodo. [DOI to be assigned]

### BibTeX

```bibtex
@misc{shatny2026cormorant,
  author = {Shatny, Michael},
  title = {Cormorant Foraging Framework: A Three-Dimensional Taxonomy for Intelligence Systems},
  year = {2026},
  publisher = {Zenodo},
  url = {https://github.com/semanticintent/cormorant-foraging-framework},
  note = {ORCID: 0009-0006-2011-3258}
}
```

---

## License

This work is licensed under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

You are free to:
- **Share** — copy and redistribute in any medium or format
- **Adapt** — remix, transform, and build upon for any purpose

Under the following terms:
- **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made.

---

## Author

**Michael Shatny**
Ontario, Canada
ORCID: [0009-0006-2011-3258](https://orcid.org/0009-0006-2011-3258)

---

*"Natural metaphors reveal natural structures in intelligence design."* 🐦
