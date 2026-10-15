# Changelog

All notable changes to the Cormorant Foraging Framework will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [2.0.0] - 2026-03-07

### Added
- **GESA.md** — Full specification for Layer ∞ (Generative Episodic Simulated Annealing)
  - 8-step optimization loop: OBSERVE → RETRIEVE → GENERATE → ANNEAL → SELECT → ACT → STORE → COOL
  - Episode similarity formula with 5 weighted dimensions
  - Temperature profiles (Fast Cool, Standard, Slow, Adaptive)
  - Three loop invariants, episode schema, candidate scoring
- **PHILOSOPHICAL-FOUNDATIONS.md** — Epistemological, ontological, and information-theoretic foundations
  - Observable anchoring grounded in empiricism, logical positivism, pragmatism
  - Structural realism, natural kinds analysis, embodied cognition
  - Shannon entropy and Kolmogorov complexity perspectives
  - Ethics of transparency and autonomy
- **COMPARATIVE-ANALYSIS.md** — Cross-dimensional validation and scoring methodology comparison
  - Worked examples for additive, multiplicative, and exponential scoring
  - Design independence evidence across production systems
  - Mathematical model comparison and dimensional independence tests

### Changed
- **README.md** — Major rewrite for v2.0.0
  - Subtitle: "Three-Dimensional Taxonomy" → "Multi-Layered Architecture"
  - Abstract expanded to include GESA and the complete stack
  - Added complete ASCII stack diagram (3D → DRIFT → Fetch → GESA)
  - Added Layer ∞ GESA section
  - Updated ecosystem tree with all 5 DOIs
  - Added Project Phoenix and StratIQX to Applications
  - Updated repository structure to reflect new files
- **DERIVED-LAYERS.md** — Added GESA as Layer ∞
  - Replaced experimental "Potential Layer 3: Adapt" section with full GESA summary
  - Added dependency chain diagram showing GESA's relationship to prior layers
- **CITATION.cff** — Bumped to v2.0.0
  - Updated title and abstract to reflect multi-layered architecture
  - Added GESA-related keywords (generative-episodic-simulated-annealing, optimization, episodic-memory)
  - Added Project Phoenix and Semantic Intent SSOT references
  - Updated PACE DOI to latest version

---

## [1.0.0] - 2026-01-10

### Added
- Initial public release of the Cormorant Foraging Framework
- Complete documentation of the three-dimensional taxonomy (Sound, Space, Time)
- Derived layers documentation (DRIFT and Fetch)
- Empirical validation data from production systems:
  - ChirpIQX: 78% prediction accuracy
  - PerchIQX: 398 passing tests
  - WakeIQX: 85% context retention
- Applications documentation covering:
  - PACE Pattern (DOI: 10.5281/zenodo.18049371)
  - 6D Foraging Methodology (DOI: 10.5281/zenodo.18209946)
  - HEAT Framework
  - PlayIQX, BrowserLLM implementations
- Citation metadata (CITATION.cff) with references to related works
- Creative Commons Attribution 4.0 International license

### Design Principles
- Observable anchoring: Every measurement ties to detectable physical properties
- No speculation: Excludes predictions, intent, and normative judgments
- Clean layering: Each layer has single responsibility with clear dependencies
- No circular dependencies: Feedback returns to Layer 0 for re-sensing
- Emergent discovery: Patterns found, not forced

### Production Systems
- ChirpIQX (Sound): Fantasy sports intelligence via MCP server
- PerchIQX (Space): Database schema intelligence for Cloudflare D1
- WakeIQX (Time): Temporal context continuity management

---

*For the latest version, visit [cormorantforaging.semanticintent.dev](https://cormorantforaging.semanticintent.dev)*
