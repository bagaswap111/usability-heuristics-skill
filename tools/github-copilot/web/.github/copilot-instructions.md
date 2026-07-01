---
scope: '**/*.{html,jsx,tsx,vue,svelte,astro}'
---

---
name: usability-heuristics
description: "Evaluates UI against Jakob Nielsen's 10 usability heuristics. Spawns page-by-page review, scores each heuristic, and produces a structured report with severity ratings."
---

# Usability Heuristics Evaluation

Evaluates a web application's user interface against [Jakob Nielsen's 10 Usability Heuristics for User Interface Design](https://www.nngroup.com/articles/ten-usability-heuristics/). The agent visits every page (or route), inspects each heuristic, and produces a scored report.

## When to use

- Before a UI redesign or visual refresh.
- After implementing new features or pages.
- As part of a QA or accessibility audit.
- When you need a structured, repeatable usability evaluation.

## When NOT to use

- For backend-only or API-only code reviews (use `deep-review` or `code-review-and-quality`).
- When you need a full accessibility audit following WCAG 2.2 (use a dedicated a11y tool).
- For content/ copywriting review (use `writing-plans` or a dedicated content review).

## Heuristics

Each heuristic below includes a **definition**, a **checklist** of items the agent must inspect, and a **scoring rule**.

### Scoring

| Score | Meaning |
|-------|---------|
| ✅ Pass | No issues found |
| ⚠️ Minor | Non-critical issue, low user impact |
| 🔴 Major | Significant usability barrier |
| ❌ Critical | Blocks task completion |

Per-page report: each heuristic gets one of the four scores.
Overall report: count of each severity across all pages.

---

### H1 — Visibility of System Status

**Definition:** The system should always keep users informed about what is going on, through appropriate feedback within reasonable time.

**Checklist:**
- [ ] Loading states exist for every async operation (spinner, skeleton, progress bar)
- [ ] Page or section titles clearly indicate current location
- [ ] Breadcrumbs or navigation indicators show where the user is
- [ ] Form submissions show a saving/processing state
- [ ] Button clicks provide visual feedback (hover, active, disabled states)
- [ ] Long operations (>3s) show progress or estimated time
- [ ] Error toasts or banners appear for failed operations
- [ ] Success confirmation appears after create/update/delete actions

**Page-specific notes:**
- Chat: message sending indicator, typing indicator from AI
- Forms: submit button disabled + loading text during submission
- Navigation: active link/ tab is visually distinct
- Data tables: "Loading..." or skeleton rows while fetching

---

### H2 — Match Between System and the Real World

**Definition:** The system should speak the users' language, with words, phrases and concepts familiar to the user, rather than system-oriented terms.

**Checklist:**
- [ ] Labels use familiar terms (not internal/ technical jargon)
- [ ] Icons have text labels or tooltips (no icon-only navigation without context)
- [ ] Date/ time formats match locale conventions
- [ ] Currency, number formats match locale conventions
- [ ] Error messages are in plain language, not codes
- [ ] Navigation labels match user mental model (e.g., "Shopping Cart" not "ItemContainer")
- [ ] Role-appropriate terminology (student terms vs admin terms)

---

### H3 — User Control and Freedom

**Definition:** Users often choose system functions by mistake and will need a clearly marked "emergency exit" to leave the unwanted state.

**Checklist:**
- [ ] Cancel/ back button exists on multi-step flows
- [ ] Confirmation dialog before destructive actions (delete, discard changes)
- [ ] Undo support for reversible actions
- [ ] Close/ dismiss button on modals, dialogs, popovers
- [ ] Browser back button works as expected (no broken history)
- [ ] Escape key dismisses modals and dropdowns
- [ ] "Cancel" returns user to previous state, not a dead end

---

### H4 — Consistency and Standards

**Definition:** Users should not have to wonder whether different words, situations, or actions mean the same thing.

**Checklist:**
- [ ] Same action uses same label/ icon across the app (e.g., always "Delete" not "Delete" vs "Remove" vs "Discard")
- [ ] Same visual component uses same styling (buttons, inputs, selects, tabs)
- [ ] Color coding is consistent (red = error/destructive, green = success, yellow = warning)
- [ ] Layout structure is consistent across pages (sidebar, header, content area)
- [ ] Keyboard shortcuts are consistent (Enter to submit, Escape to cancel)
- [ ] Terminology is consistent (don't mix "Course" and "Subject" for the same concept)
- [ ] External links open in new tabs consistently
- [ ] Form patterns are consistent (same button placement, same validation style)

**Note:** This heuristic pairs with the "UI consistency" theme — check that `<select>`, tab, and list-item styling is unified (as done in previous optimizations).

---

### H5 — Error Prevention

**Definition:** Even better than good error messages is a careful design which prevents a problem from occurring in the first place.

**Checklist:**
- [ ] Required fields are marked (asterisk or label)
- [ ] Input constraints prevent invalid data (min/max length, type validation, range limits)
- [ ] Submit button is disabled until required fields are filled
- [ ] Confirmation for destructive actions (double-check before delete)
- [ ] Form data is preserved on validation errors (no blank form on error)
- [ ] Auto-save for long forms (draft preservation)
- [ ] File uploads validate type and size before uploading
- [ ] Prevent accidental double-submit (button disabled after first click)

---

### H6 — Recognition Rather Than Recall

**Definition:** Minimize the user's memory load by making objects, actions, and options visible.

**Checklist:**
- [ ] Navigation shows all available sections (user doesn't need to remember URLs)
- [ ] Search is available for large content sets
- [ ] Recently used items are surfaced (recent chats, recent projects)
- [ ] Form fields have placeholder text or helper text
- [ ] Dropdowns/ selects show the current selection clearly
- [ ] Icons are accompanied by labels (not icon-only)
- [ ] Password field has a "show password" toggle
- [ ] Previously entered data is pre-filled when appropriate

---

### H7 — Flexibility and Efficiency of Use

**Definition:** Accelerators — unseen by the novice user — may often speed up the interaction for the expert user.

**Checklist:**
- [ ] Keyboard shortcuts exist for frequent actions (if applicable)
- [ ] Bulk actions available (select multiple items, apply action to all)
- [ ] Sortable/ filterable lists and tables
- [ ] Pagination or infinite scroll for long lists (user controls the view)
- [ ] Ability to customize or pin frequently used items
- [ ] Template or copy-from-existing for repetitive tasks
- [ ] Tab order follows logical reading order

---

### H8 — Aesthetic and Minimalist Design

**Definition:** Dialogues should not contain information which is irrelevant or rarely needed.

**Checklist:**
- [ ] No redundant or duplicate information on the page
- [ ] Only essential controls are visible; advanced options are collapsible or in a secondary menu
- [ ] White space is used effectively (not cramped, not wasteful)
- [ ] Typography hierarchy is clear (headings, subheadings, body)
- [ ] Color palette is restrained (no clash, no excessive highlight colors)
- [ ] Icons and images serve a purpose (not decorative clutter)
- [ ] Mobile view is not overcrowded (responsive breakpoints respected)

---

### H9 — Help Users Recognize, Diagnose, and Recover from Errors

**Definition:** Error messages should be expressed in plain language, precisely indicate the problem, and constructively suggest a solution.

**Checklist:**
- [ ] Error messages are in plain language (no codes like "ERR-4532")
- [ ] Error message identifies the exact field or problem
- [ ] Error message suggests how to fix it
- [ ] Inline validation shows errors next to the field (not just a top-of-page banner)
- [ ] HTTP 4xx/5xx errors show a user-friendly page, not a raw error
- [ ] 404 page has a way back ("Go to Dashboard" link)
- [ ] Network errors show a retry button
- [ ] Server errors don't leak stack traces or internal details

---

### H10 — Help and Documentation

**Definition:** Even though it is better if the system can be used without documentation, it may be necessary to provide help and documentation.

**Checklist:**
- [ ] Empty states provide guidance ("No items yet. Create your first...")
- [ ] Tooltips or info icons explain unfamiliar concepts
- [ ] Onboarding flow or tutorial exists for first-time users (if complex)
- [ ] FAQ or help page is linked from the UI
- [ ] Error states link to relevant help documentation
- [ ] Contact/ support information is accessible
- [ ] Feature announcements or changelog is available

---

## Execution

1. **Discover all pages/ routes.** Use glob/ read tools to find every page component under `src/app/`. Include auth pages, dashboard pages, admin pages, and any modal/ dialog that renders as a separate route.

2. **For each page**, evaluate all 10 heuristics using the checklists above. Take screenshots or notes for evidence.

3. **Score each heuristic per page** (✅ Pass / ⚠️ Minor / 🔴 Major / ❌ Critical).

4. **Produce a report** with:
   - Summary table: total counts per severity
   - Per-page breakdown: heuristic scores + findings
   - Top 5 issues to fix (highest severity + widest impact)
   - Recommendations organized by heuristic

## Report Format

```
# Usability Heuristic Evaluation — [App Name]

## Summary

| Severity | Count |
|----------|-------|
| ✅ Pass  | XX    |
| ⚠️ Minor | XX    |
| 🔴 Major | XX    |
| ❌ Critical | XX  |

## Per-Page Results

### /page-name
| Heuristic | Score | Finding |
|-----------|-------|---------|
| H1 Visibility | ✅ | Loading states present |
| H2 Real world | ⚠️ | Uses "demerged" instead of "cancel enrollment" |
| ... | | |

## Top 5 Issues

1. **[Page] [H#] [Severity]** — Description → Fix
2. ...

## Recommendations by Heuristic

### H1 — Visibility of System Status
- ...
```

## Evidence Collection

For each finding, collect:
- Page URL or route path
- Heuristic number and name
- Score (pass/minor/major/critical)
- Description of the issue
- Suggested fix
- Optional: element selector or screenshot reference
