# Contributing to Cormorant Foraging Framework

Thank you for your interest in contributing to the Cormorant Foraging Framework! This document provides guidelines for different types of contributions.

---

## Ways to Contribute

### 1. Share Your Implementation

Have you built a system using the framework? We'd love to hear about it.

**What to include:**
- Domain and use case
- Which dimension(s) you used (Sound, Space, Time, or hybrid)
- Observable signals and scoring formulas
- Performance metrics (if available)
- What worked well and what didn't

**How to share:**
- Open an issue with the label `implementation-showcase`
- Include enough detail for others to learn from your experience
- We may feature notable implementations in [APPLICATIONS.md](APPLICATIONS.md)

---

### 2. Report Issues or Suggest Improvements

Found something unclear, incorrect, or missing?

**Before submitting:**
- Check existing issues to avoid duplicates
- Provide specific examples when possible
- Reference specific files and sections

**Issue labels:**
- `documentation`: Unclear or incorrect documentation
- `question`: Need clarification on framework concepts
- `enhancement`: Suggestion for improvement
- `validation-data`: Challenges or questions about empirical claims

---

### 3. Contribute Documentation Improvements

**Types of documentation contributions:**
- Clarifying existing explanations
- Adding examples or use cases
- Fixing typos or formatting
- Improving diagrams or visual aids

**Process:**
1. Fork the repository
2. Make your changes
3. Submit a pull request with:
   - Clear description of what you changed and why
   - Reference to any related issues
   - Confirmation that you've reviewed the Design Principles below

---

### 4. Contribute Validation Data

Have you tested the framework claims in your environment?

**We welcome:**
- Replication studies of ChirpIQX, PerchIQX, or WakeIQX performance
- Cross-domain validation (applying framework to new domains)
- Ablation studies (testing component contributions)
- Comparative studies (framework vs. alternatives)

**Requirements:**
- Clear methodology description
- Observable, measurable results
- Honest reporting (including negative results)
- Sufficient detail for reproducibility

---

## Design Principles for Contributors

When contributing, please respect these core framework principles:

### 1. Observable Anchoring
**Every signal must tie to something measurable:**
- ✅ Timestamps, counts, percentages, presence/absence
- ❌ Intent, predictions, normative judgments, speculation

**Example:**
- ✅ "File was modified 3 days ago" (observable)
- ❌ "User probably wants to work on this file" (speculation)

### 2. No Speculation
**The framework describes what is, not what should be or might be:**
- ✅ "DRIFT = 35 indicates a gap between methodology and performance"
- ❌ "Team is lazy" or "Will improve next quarter"

### 3. Clean Layering
**Each layer has a single responsibility:**
- Layer 0: Sensing (Sound, Space, Time)
- Layer 1: Measurement (DRIFT)
- Layer 2: Action (Fetch)

**Dependencies flow one direction:** Layer 2 → Layer 1 → Layer 0

**Feedback returns to Layer 0** for re-sensing (no circular loops)

### 4. Dimensional Purity
**Keep scoring methods pure within a component:**
- Sound systems use additive scoring only
- Space systems use multiplicative scoring only
- Time systems use exponential decay only
- Hybrid systems compose pure dimensions at higher layers

### 5. Emergent Discovery
**The framework emerged from production systems, not theory:**
- Respect patterns that emerged empirically
- Avoid forcing theoretical constructs
- Validate changes with real-world data

---

## Pull Request Guidelines

### Documentation Changes

**Format:**
- Use Markdown formatting consistent with existing docs
- Follow the emoji convention (🐦 at the end of files)
- Maintain the existing structure and hierarchy
- Use backticks for code, formulas, and technical terms

**Content:**
- Keep language clear and concise
- Provide examples where helpful
- Link to related sections for context
- Cite sources for empirical claims

**Before submitting:**
- Read through your changes for clarity
- Check links to ensure they work
- Verify any code snippets or formulas
- Run a spell-checker

### Code or Data Contributions

**If contributing validation data or code:**
- Include clear documentation of methodology
- Provide reproducible examples
- Follow observable anchoring principles
- Include tests if applicable

---

## Review Process

1. **Initial review** (1-3 days): Maintainer reviews for alignment with framework principles
2. **Feedback**: Requests for changes or clarifications if needed
3. **Approval**: Once aligned with principles and quality standards
4. **Merge**: Changes incorporated into main branch

**Note:** Significant changes may require more discussion and iteration.

---

## Recognition

Contributors who make significant improvements will be recognized in:
- Repository contributors list
- Documentation acknowledgments section (if added in future releases)
- Release notes for the version including their contribution

---

## Questions?

Not sure if something fits? Open an issue with the `question` label and we'll help clarify.

---

## Code of Conduct

### Our Standards

- **Respectful**: Treat all contributors with respect
- **Constructive**: Provide helpful, actionable feedback
- **Empirical**: Ground discussions in observable data
- **Honest**: Report both successes and failures
- **Open**: Welcome diverse perspectives and use cases

### Unacceptable Behavior

- Personal attacks or harassment
- Speculation presented as fact
- Dismissing empirical evidence without data
- Promotion of unrelated products/services

### Enforcement

Violations of these standards may result in:
1. Warning from maintainers
2. Temporary ban from contributing
3. Permanent ban for repeated or severe violations

Report concerns to the repository maintainer.

---

## License

By contributing to this project, you agree that your contributions will be licensed under the same [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) license that covers the project.

You retain copyright to your contributions but grant permission for them to be used under this license.

---

## Attribution

When contributing significant content (examples, case studies, validation data), you may include attribution:

**Format:**
```markdown
**Contributed by:** [Your Name]
**Organization:** [Optional]
**Date:** YYYY-MM-DD
```

This appears in the specific section you contributed to, not as a general credit.

---

## Release Process

Significant updates trigger new releases:

1. **Version bump** following semantic versioning
2. **CHANGELOG.md update** documenting changes
3. **GitHub release** with tag (e.g., v1.1.0)
4. **Zenodo archiving** with new DOI
5. **Documentation updates** with new DOI references

Contributors will be notified when their changes are included in a release.

---

## Getting Started

Ready to contribute?

1. **Fork** the repository
2. **Create a branch** for your changes
3. **Make your edits** following these guidelines
4. **Submit a pull request** with clear description
5. **Respond to feedback** during review

Thank you for helping improve the Cormorant Foraging Framework!

---

*"Natural metaphors, collaborative refinement, measurable impact."* 🐦
