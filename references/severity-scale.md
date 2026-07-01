# Rating Scale

Adapted from Nielsen's severity rating for usability problems. Use this scale consistently across all findings.

| Rating | Label | Definition | Action |
|--------|-------|------------|--------|
| ❌ | **Critical** | Prevents the user from completing their task, or causes serious misunderstanding of data. Users will abandon or make consequential errors. | Must fix before release |
| 🔴 | **Major** | Causes significant friction or confusion. Users can work around it but will struggle or lose efficiency. | Should fix — high priority |
| ⚠️ | **Minor** | Noticeable annoyance but users can complete their task without significant difficulty. | Fix when possible |
| ✅ | **Good** | This heuristic is well-handled. Note what works so it is preserved in future iterations. | No action needed |
| 👁️ | **Needs Manual Review** | Evaluator cannot verify from available input. | Verify in live product |
| — | **N/A** | Heuristic does not apply to this UI. | No action needed |

When `Rating = N/A` or `Rating = Needs Manual Review`, there is no scored severity.

## Severity Assignment Guidelines

- **User impact over aesthetic preference**: A visually imperfect but functional UI is less severe than a polished UI that misleads.
- **Frequency matters**: An issue affecting every interaction is more severe than one affecting a rare edge case.
- **Consider the user profile**: What is critical for a novice may be minor for a daily expert user — and vice versa.
- **Incomplete vs. broken**: A missing feature that has a placeholder is not a design flaw. Note it in the finding text and rate based on actual user impact, not implementation completeness.
- **Compound effects**: If two minor issues together create a major workflow problem, note the compound effect and rate the combination, not each issue in isolation.
