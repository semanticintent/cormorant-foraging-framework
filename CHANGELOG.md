# Changelog

All notable changes to the Cormorant Foraging Framework will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

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

### Documentation Structure
```
cormorant-foraging-framework/
├── README.md                 # Framework overview
├── DIMENSIONS.md             # Deep dive on Sound, Space, Time
├── DERIVED-LAYERS.md         # DRIFT and Fetch extensions
├── APPLICATIONS.md           # Real-world implementations
├── EMPIRICAL-VALIDATION.md   # Performance data and testing
├── CITATION.cff              # Machine-readable citation metadata
├── CHANGELOG.md              # This file
├── CONTRIBUTING.md           # Contribution guidelines
└── LICENSE                   # CC BY 4.0 license
```

---

## Future Releases

Future versions will be documented here as the framework evolves through:
- Additional production implementations
- Cross-domain validation studies
- Community contributions
- Extensions to derived layers

Each significant update will receive a new version number and DOI on Zenodo.

---

*For the latest version, visit [cormorantforaging.dev](https://cormorantforaging.dev)*
