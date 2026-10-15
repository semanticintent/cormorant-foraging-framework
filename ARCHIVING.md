# Academic Archiving & Citation

This document describes how the Cormorant Foraging Framework is archived for academic citation and provides guidance for others who wish to archive similar work.

---

## Zenodo Archive

This repository will be archived on Zenodo for long-term preservation and academic citation.

**Status:** ✅ Archived

**Archive Details:**
- **Title:** Cormorant Foraging Framework: A Three-Dimensional Taxonomy for Intelligence Systems
- **Version:** 1.0.0
- **Date:** 2026-01-10
- **License:** CC BY 4.0
- **DOI:** [10.5281/zenodo.18904952](https://doi.org/10.5281/zenodo.18904952)

---

## Why Archive on Zenodo?

1. **Permanent DOI** - Persistent identifier that won't break
2. **Long-term preservation** - CERN-backed infrastructure
3. **Academic credibility** - Citable in research papers
4. **Version tracking** - Each release gets its own DOI
5. **Discoverability** - Indexed by academic search engines
6. **Citation network** - Links to related works (PACE, 6D Methodology)

---

## Preparation Checklist

Repository preparation for archiving:

- [x] Repository structure is clean and logical
- [x] All essential files at appropriate levels
- [x] CITATION.cff file with complete metadata
- [x] LICENSE file clearly specifies terms (CC BY 4.0)
- [x] CHANGELOG.md documents version history
- [x] .gitignore excludes temporary/build files
- [x] Internal links verified and working
- [x] README.md includes abstract and overview
- [x] References to related works (PACE, 6D Methodology)
- [ ] GitHub repository created and pushed
- [ ] GitHub release v1.0.0 created
- [ ] Zenodo integration enabled
- [ ] DOI received from Zenodo

---

## Zenodo Submission Guide

When submitting to Zenodo, use these details:

### Required Fields

| Field | Value |
|-------|-------|
| **Upload type** | Software (framework/methodology) |
| **Title** | Cormorant Foraging Framework: A Three-Dimensional Taxonomy for Intelligence Systems |
| **Creators** | Michael Shatny (ORCID: 0009-0006-2011-3258) |
| **Description** | Use abstract from README.md |
| **License** | Creative Commons Attribution 4.0 International |
| **Keywords** | intelligence systems, biomimetic framework, dimensional taxonomy, observable properties, additive scoring, multiplicative scoring, exponential decay, cormorant foraging, natural metaphors |
| **Version** | 1.0.0 |

### Related Identifiers

Link to related works in the ecosystem:
- **PACE Pattern:** 10.5281/zenodo.18049371 (relationship: "is referenced by")
- **6D Foraging Methodology:** 10.5281/zenodo.18209946 (relationship: "is referenced by")

### Related Documentation Sites

- **ChirpIQX:** https://chirp.semanticintent.dev
- **PerchIQX:** https://perch.semanticintent.dev
- **WakeIQX:** https://wake.semanticintent.dev
- **DRIFT:** https://drift.semanticintent.dev
- **Fetch:** https://fetch.semanticintent.dev
- **Main site:** https://cormorantforaging.semanticintent.dev

### Notes

Include trademark notice: "Cormorant Foraging Framework" is a trademark of Michael Shatny.

---

## After Receiving DOI

Once Zenodo assigns a DOI, complete these tasks:

### 1. Update Repository

- [ ] Add DOI badge to README.md: `[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXX)`
- [ ] Update citation examples in README.md with actual DOI
- [ ] Update this file (ARCHIVING.md) status from 🟡 Pending to ✅ Archived
- [ ] Add DOI to this file's archive details section
- [ ] Update CITATION.cff with DOI
- [ ] Update LICENSE with DOI in attribution section

### 2. Verify GitHub Release

- [ ] Tag: v1.0.0
- [ ] Title: "Cormorant Foraging Framework v1.0.0"
- [ ] Description: Copy from CHANGELOG.md
- [ ] Attach DOI in release notes

### 3. Enable Auto-Archiving

For future versions:
- [ ] Connect GitHub repository to Zenodo
- [ ] Enable automatic DOI generation for new releases
- [ ] Each GitHub release will automatically create a new Zenodo version

### 4. Update External References

- [ ] Add DOI to cormorantforaging.dev website
- [ ] Update component sites (chirpiqx.com, perchiqx.com, wakeiqx.com)
- [ ] Update PACE Pattern references to Cormorant Framework
- [ ] Update 6D Methodology references to Cormorant Framework
- [ ] Update Semantic Intent SSOT references

---

## For Researchers & Contributors

### How to Cite

See [README.md](README.md#citation) for citation formats, or use the metadata in [CITATION.cff](CITATION.cff).

### Version History

Each version archived on Zenodo gets its own DOI:
- **v1.0.0:** Initial release (2026-01-10) - DOI: [10.5281/zenodo.18904952](https://doi.org/10.5281/zenodo.18904952)

Concept DOI (always points to latest version): 10.5281/zenodo.18904952

### Contributing to Archived Work

See [CONTRIBUTING.md](CONTRIBUTING.md) for how to propose changes. Significant updates will be released as new versions with new DOIs.

---

## Ecosystem Integration

The Cormorant Foraging Framework is the foundational taxonomy for the entire ecosystem:

```
Semantic Intent (Philosophy)
  ↓
Cormorant Foraging (3D Framework) ← This work
  ├─ PACE Pattern (DOI: 10.5281/zenodo.18049371)
  ├─ 6D Methodology (DOI: 10.5281/zenodo.18209946)
  └─ HEAT Framework
      └─ Extensions: DRIFT, Fetch
```

Once archived, this DOI will be referenced by:
- Future releases of PACE Pattern
- Future releases of 6D Methodology
- New frameworks building on the dimensional taxonomy
- Research papers and applications

---

## Production System Documentation

The framework emerged from three production systems, each with its own documentation:

### ChirpIQX (Sound Dimension)
- **Website:** https://chirp.semanticintent.dev
- **Repository:** https://github.com/semanticintent/semantic-chirp-intelligence-mcp-docs
- **Status:** Production MCP server

### PerchIQX (Space Dimension)
- **Website:** https://perch.semanticintent.dev
- **Repository:** https://github.com/semanticintent/semantic-perch-intelligence-mcp-docs
- **Status:** Production Cloudflare D1 intelligence

### WakeIQX (Time Dimension)
- **Website:** https://wake.semanticintent.dev
- **Repository:** https://github.com/semanticintent/semantic-wake-intelligence-mcp-docs
- **Status:** Production temporal context protocol

### DRIFT (Layer 1)
- **Website:** https://drift.semanticintent.dev
- **Repository:** https://github.com/semanticintent/drift-site
- **Status:** Production measurement framework

### Fetch (Layer 2)
- **Website:** https://fetch.semanticintent.dev
- **Repository:** https://github.com/semanticintent/fetch-website
- **Status:** Production action framework

These systems provide empirical validation for the framework claims.

---

## Archiving Timeline

1. ✅ **Documentation complete** - All files created and reviewed
2. ⏳ **Push to GitHub** - Create repository and push initial commit
3. ⏳ **Create release** - Tag v1.0.0 and create GitHub release
4. ⏳ **Enable Zenodo** - Connect repository to Zenodo
5. ⏳ **Receive DOI** - Wait for Zenodo to assign DOI
6. ⏳ **Update references** - Add DOI to all relevant files
7. ⏳ **Announce** - Share with ecosystem and research community

---

*Last updated: 2026-01-10*
