# Publication Strategy

**Paper:** A Multi-Platform Usability Heuristic Evaluation Framework for AI-Assisted Development

This document outlines a phased strategy for publishing this work — first in conferences (for rapid peer feedback, visibility, and CV building), then extended into a full journal article.

---

## Phase 0: Pre-Submission Preparation (Now)

| Task | Why | Timeline |
|------|-----|----------|
| Complete the evaluation section with real case studies | Conferences and journals reject papers with "evaluation pending" | Before first submission |
| Run 4 case studies (web, mobile, desktop, CLI) and collect metrics | Evidence is required at every level | 2–4 weeks |
| Create clear architecture diagram (e.g., Figma, draw.io, or mermaid) | Most venues require a visual system overview | 1 week |
| Define a consistent author list and affiliation | Changes after submission are problematic | Now |
| Register for ORCID if not already done | Required by IEEE, ACM, Springer | Now |

---

## Phase 1: Conference Submissions (6–12 months)

The goal is to **publish 1–2 conference papers** to validate the work, gather reviewer feedback, and build publication history before submitting the journal version.

### Recommended Conference Targets (ranked by fit + timeline)

| # | Conference | Tier | Topic Fit | Deadline (typical) | Conference | Notes |
|---|------------|------|-----------|-------------------|------------|-------|
| 1 | **HCII (HCI International)** | Tier 2 | ⭐⭐⭐⭐⭐ | ~Oct (for following Jul) | Jul | Highly accessible, large HCI conference. Accepts work-in-progress. Good first target. |
| 2 | **IEEE SSCI (Symp. Series on Computational Intelligence)** | Tier 2 | ⭐⭐⭐⭐ | ~Mar (for Nov-Dec) | Nov–Dec | Has a Human-Computer Interaction track. Good for the LLM/ML angle. |
| 3 | **ACM CHI (late-breaking work / alt.chi)** | Tier 1 | ⭐⭐⭐⭐⭐ | ~Jan (for Apr-May) | Apr–May | Extremely competitive but prestigious. Aim for **LBW (Late-Breaking Work)** track - shorter papers (4 pages), higher acceptance (~45%). |
| 4 | **IEEE/ACM ASE (Tools & Demos track)** | Tier 1 | ⭐⭐⭐ | ~May (for Sep) | Sep | Focused on automated software engineering. The skill/tool angle fits the "Tools" track. |
| 5 | **INTERACT (IFIP TC13)** | Tier 2 | ⭐⭐⭐⭐⭐ | ~Feb (for Aug-Sep) | Aug–Sep | Strong HCI conference, smaller than CHI but well-regarded. |
| 6 | **ACM ISS (Interactive Surfaces and Spaces)** | Tier 2 | ⭐⭐⭐ | ~Apr (for Oct-Nov) | Oct–Nov | Broad "interactive systems" scope. |

### Recommended Strategy

**Option A — HCII first (safest path)**

```
HCII (Oct deadline) → Present Jul → Use feedback → Submit journal (Aug)
```
- Advantage: High acceptance rate (~45%), very accessible for first-time authors
- Disadvantage: HCII proceedings are less prestigious than CHI

**Option B — CHI LBW first (ambitious path)**

```
CHI LBW (Jan deadline) → Present May → INTERACT (Feb deadline) → Present Aug → Submit journal (Sep)
```
- Advantage: CHI even on CV is valuable; LBW track is achievable
- Disadvantage: Tight timeline with overlapping deadlines

**Option C — Balanced path (recommended)**

```
INTERACT (Feb deadline) → Present Aug → Use feedback → HCII next cycle (Oct) → Present Jul → Submit journal
```
- Advantage: Two conference papers, iterative feedback
- Disadvantage: Takes 18+ months

**My recommendation: Option A** — HCII first. It's achievable, gives you a publication within 9 months, and the feedback will strengthen the journal version.

### Timeline: Option A (HCII → Journal)

```
Month 0: Paper draft complete, evaluation done
Month 1: Submit to HCII (Oct deadline)
Month 4: Receive HCII decision (Jan)
Month 6: Camera-ready + register (Mar)
Month 9: Present at HCII (Jul)
Month 9–10: Incorporate feedback, extend paper
Month 10: Submit to journal (Aug)
```

---

## Phase 2: Journal Submission (after 1+ conference paper)

### Target Journals (ranked by fit + prestige)

| # | Journal | Impact Factor | Topic Fit | Review Cycle | Notes |
|---|---------|:------------:|:---------:|:------------:|-------|
| 1 | **IEEE Access** | ~3.4 | ⭐⭐⭐⭐ | ~4–6 weeks | Open access, fast review, good for systems/engineering work. Requires APC (~$1,995). |
| 2 | **IJHCS (Int. J. Human-Computer Studies)** | ~4.1 | ⭐⭐⭐⭐⭐ | ~4–6 months | Strong HCI journal, accepts novel frameworks. No open access required. |
| 3 | **Interacting with Computers** | ~2.0 | ⭐⭐⭐⭐⭐ | ~6 months | Oxford journal, BCS HCI group. Good fit for heuristic evaluation work. |
| 4 | **ACM Transactions on CHI (TOCHI)** | ~5.0 | ⭐⭐⭐⭐⭐ | ~6–12 months | Top-tier HCI journal. Very competitive. Needs substantial evaluation. |
| 5 | **JMIR Human Factors** | ~2.6 | ⭐⭐⭐ | ~3–4 months | If you evaluate on healthcare/accessibility use cases. |
| 6 | **Software: Practice and Experience (SPE)** | ~2.0 | ⭐⭐⭐⭐ | ~3–6 months | Good fit for the multi-tool, multi-format engineering aspect. |

### Conference-to-Journal Extension Ratio

Journals require **30–50% new content** beyond the conference version. Plan these extensions:

| Extension | Description | Effort |
|-----------|-------------|--------|
| More case studies | Expand from 2 to 6–8 (add e-commerce, healthcare, education) | 2–4 weeks |
| User study | Recruit 10–20 UX professionals, measure time savings | 4–6 weeks |
| Cross-model comparison | Claude vs GPT-4o vs Gemini with same skill | 2 weeks |
| Statistical analysis | Inter-rater agreement (Cohen's kappa), effect sizes | 1 week |
| Longitudinal analysis | Does the skill improve findings over repeated use? | 4 weeks |
| Related work expansion | Full 3+ pages vs the conference's 1–2 pages | 1 week |

### Recommended Journal Target: IJHCS

- Strong fit (HCI journal, publishes evaluation frameworks)
- No open access fee (compared to IEEE Access)
- Good review cycle (4–6 months)
- Well-regarded in HCI community
- Threshold: need 6+ case studies or a user study + comparison

### Journal Extension Checklist

Before journal submission, ensure you have added:

- [ ] 6+ case studies (vs 2–3 for conference)
- [ ] User study with 10+ participants
- [ ] Cross-model comparison (if applicable)
- [ ] Statistical analysis
- [ ] Expanded related work (2x the conference version)
- [ ] Full author bios
- [ ] Compliance with journal format template
- [ ] Cover letter stating how this extends prior conference publication

---

## Phase 3: After Publication

| Activity | Why |
|----------|-----|
| Post on arXiv.org (if allowed by venue) | Increases visibility and citations |
| Share on Twitter/X, LinkedIn, Hacker News | Community engagement |
| Add a "Cite this" badge to the repo README | Makes it easy for others to cite |
| Submit to ACM SIGCHI (if significant HCI component) | Indexing in ACM DL requires at least one author with SIGCHI membership |
| Track citations with Google Scholar | Monitor impact |

---

## Venue-Specific Adaptation Notes

### For HCII
- Format: Springer LNCS (LaTeX or Word)
- Length: 10–12 pages (long paper) or 6–8 pages (short paper)
- Review: Single-blind
- Key sections to emphasize: practical contribution, evaluation, tool interoperability
- Tone: HCI audience — explain the AI/tool aspects clearly

### For INTERACT
- Format: Springer LNCS
- Length: 12–14 pages (full paper) or 6–8 pages (short paper)
- Review: Double-blind (anonymize paper!)
- Key sections to emphasize: user-centered design, evaluation methodology
- Tone: Academic HCI — rigorous methodology, citation-heavy

### For IJHCS (Journal)
- Format: Elsevier — LaTeX or Word template
- Length: 10,000–15,000 words (no strict page limit)
- Review: Double-blind
- Key sections to emphasize: contribution to HCI theory, rigorous evaluation
- Tone: Scholarly, comprehensive, self-contained (readers should not need to read the conference paper)

### For IEEE Access (Journal)
- Format: IEEE double-column
- Length: 8–12 pages
- Review: Single-blind
- Key sections to emphasize: engineering contribution, system design, reproducibility
- Tone: Technical, systems-oriented

---

## Cost Estimate

| Venue | Submission Fee | Registration (early) | Travel | Total (approx) |
|-------|:-------------:|:--------------------:|:------:|:--------------:|
| HCII | ~$100 | ~$600 | ~$1,500 | ~$2,200 |
| INTERACT | ~$150 | ~$700 | ~$2,000 | ~$2,850 |
| CHI LBW | ~$150 | ~$800 | ~$2,000 | ~$2,950 |
| IEEE Access (journal) | ~$1,995 (APC) | — | — | ~$1,995 |
| IJHCS (journal) | $0 (subscription) or ~$3,000 (OA option) | — | — | $0–$3,000 |

---

## Summary: Recommended Path

```
Year 1:
  Oct: Submit to HCII                        (conference #1)
  Jan: Decision — likely accepted
  Jul: Present at HCII
  Jul–Aug: Extend paper with feedback + more case studies

Year 2:
  Aug: Submit to IJHCS                       (journal)
  Dec–Feb: Decision — revise or accept
  Mar–May: Final version published
```

This path produces **1 conference paper + 1 journal paper** within ~18 months, with minimal financial risk.

---

## Appendix: Rejected Contingency Plans

| If HCII rejects... | If IJHCS rejects... |
|--------------------|---------------------|
| Submit to INTERACT (Feb deadline) | Revise and submit to IEEE Access |
| Or submit to IEEE SSCI (Mar deadline) | Or submit to Interacting with Computers |
| Or submit to ASE Tools (May deadline) | Or submit to Software: Practice and Experience |
| Worst case: present as poster at local/regional HCI symposium | | 

