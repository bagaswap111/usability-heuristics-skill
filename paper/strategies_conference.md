# Conference Publication Strategy — 4-6 Page IEEE Paper

**Paper:** A Multi-Platform Usability Heuristic Evaluation Framework for AI-Assisted Development

**Target Format:** IEEE Conference (double-column, 4-6 pages)

---

## Target Venues

| # | Conference | Tier | Fit | Deadline | Conference | Acceptance |
|---|------------|------|-----|----------|------------|------------|
| 1 | **IEEE SSCI (Symp. Series on Computational Intelligence)** | Tier 2 | ⭐⭐⭐⭐ | ~Mar (Nov-Dec) | Nov-Dec | ~40% |
| 2 | **IEEE/ACM ASE (Tools & Demos track)** | Tier 1 | ⭐⭐⭐ | ~May (Sep) | Sep | ~30% |
| 3 | **IEEE ICSE (SEIP track)** | Tier 1 | ⭐⭐⭐ | ~Oct (May) | May | ~25% |
| 4 | **IEEE VIS (Short Papers)** | Tier 1 | ⭐⭐⭐ | ~Jun (Oct) | Oct | ~35% |
| 5 | **IEEE AIxSE (AI for Software Engineering)** | Tier 2 | ⭐⭐⭐⭐⭐ | ~Feb (May) | May | ~35% |

**Recommended:** IEEE SSCI — best balance of fit, timeline, and acceptance rate.

---

## Page Budget (4-6 pages IEEE double-column)

| Section | Est. Words | Est. Pages | Notes |
|---------|-----------|------------|-------|
| Abstract | ~150 | 0.2 | 100-200 words |
| I. Introduction | ~500 | 0.5 | Problem + Contributions only |
| II. Framework Design | ~800 | 1.0 | Methodology + Architecture merged |
| III. Implementation | ~400 | 0.5 | Repository + tool formats |
| IV. Evaluation | ~1,200 | 1.5 | Case study results (core evidence) |
| V. Discussion | ~300 | 0.3 | Key findings + limitations |
| VI. Conclusion | ~200 | 0.2 | Summary + future work |
| Figures (2) | — | ~0.5 | Fig 1 (Architecture) + Fig 4 (Platform) |
| Tables (2-3) | — | ~0.5 | Results + Platform matrix |
| References | — | ~0.3 | 10-12 essential refs |
| **Total** | **~3,550** | **~5.0** | Within 4-6 page range |

---

## Condensation Strategy from draft1.md

### What to Keep (Essential)
- **Abstract:** Condensed to 150 words
- **Introduction:** Problem statement + 5 contributions (no background section)
- **Framework Design:** Platform adaptation matrix (Table I), severity scale, module system — merged from Methodology + Architecture
- **Implementation:** Repository structure + tool format mapping (1 paragraph + 1 table)
- **Evaluation:** BINUS AI case study — initial findings table, top-5 critical findings, fix batches summary, before/after results table, improvement trajectory
- **Discussion:** 2-3 key strengths + 2-3 key limitations
- **Conclusion:** 1 paragraph summary + 3 future directions

### What to Cut
- **Related Work section** → condense to 2-3 sentences in Introduction
- **Inter-rater reliability subsection** → cut entirely
- **Evaluation Guidelines** → cut (too detailed for short paper)
- **Comparative Mode** → cut or 1 sentence
- **Reference Library details** → cut (point to repo)
- **Actionability of Findings** → merge into Results
- **Threats to Validity** → cut (too detailed for short paper)
- **Supplementary Materials** → cut (point to repo)

### What to Merge
- **Methodology + Architecture** → "Framework Design" section
- **Results + Fix Batches + Trajectory** → single "Evaluation" section
- **Discussion + Conclusion** → keep separate but condensed

---

## Key Selling Points for Reviewers

1. **Novelty:** First framework to encode Nielsen's 10 heuristics into AI coding tool instruction files with platform-specific adaptation
2. **Interoperability:** 11 tool formats from a single canonical source
3. **Validation:** Real-world case study with 210 findings, 32 fixes, all Critical/Major eliminated
4. **Practical impact:** 30-50× time reduction vs manual evaluation, zero UX expertise required
5. **Open-source:** 44 pre-generated files available on GitHub

---

## Submission Checklist

- [ ] 4-6 pages IEEE double-column format
- [ ] Abstract ≤ 200 words
- [ ] 10-12 references (IEEE format)
- [ ] 2 figures (architecture diagram + platform adaptation)
- [ ] 2-3 tables (platform matrix + evaluation results)
- [ ] No supplementary materials section (point to GitHub)
- [ ] All claims backed by evidence files
- [ ] Single-blind review (include author names)
- [ ] ORCID for all authors