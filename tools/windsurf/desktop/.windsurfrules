# Skill: usability-heuristics-desktop

# Usability Heuristics Evaluation — Desktop (macOS/Windows/Linux)

Evaluates a desktop application's user interface against [Jakob Nielsen's 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/). The agent inspects every window, dialog, panel, and menu, scoring each heuristic and producing a structured report.

## When to use

- Before a desktop UI redesign.
- After shipping new features or windows.
- As part of QA for native (WinUI, Cocoa, GTK) or cross-platform (Electron, Tauri, Qt) apps.
- When preparing for platform store submission (Microsoft Store, Mac App Store).

## When NOT to use

- For web or mobile interfaces (use the platform-specific variant).
- For CLI/TUI applications.
- When you need a full accessibility audit (WCAG).

## Heuristics

Scoring: ✅ Pass | ⚠️ Minor | 🔴 Major | ❌ Critical

---

### H1 — Visibility of System Status

**Checklist:**
- [ ] Loading states exist for every async operation (spinner, progress bar, indeterminate progress)
- [ ] Window title reflects current document/view context
- [ ] Menu bar highlights active menu
- [ ] Status bar shows progress or current state
- [ ] Button clicks provide visual feedback (hover, pressed, disabled states)
- [ ] Long operations (>3s) show progress bar with cancel option
- [ ] System tray / dock notifications for background operations
- [ ] Save indicator (e.g., "Unsaved changes" dot in title bar)
- [ ] Taskbar progress indicator for long operations (Windows)

---

### H2 — Match Between System and the Real World

**Checklist:**
- [ ] Labels use familiar terms (no technical jargon)
- [ ] Icons have tooltips (no icon-only menu items without context)
- [ ] Date/time formats match OS locale settings
- [ ] Currency and number formats match locale
- [ ] Error messages in plain language, not codes
- [ ] Menu labels follow OS conventions (File, Edit, View, Help)
- [ ] Keyboard shortcuts shown in menus (consistent with OS standard)
- [ ] Platform-native file dialogs used (not custom ones)
- [ ] Drag-drop behavior matches OS conventions

---

### H3 — User Control and Freedom

**Checklist:**
- [ ] Undo/Redo support (Ctrl+Z / Cmd+Z)
- [ ] Confirmation dialog before destructive actions
- [ ] Close button on all dialogs, panels, popovers
- [ ] Escape key dismisses dialogs and dropdowns
- [ ] Cancel button in multi-step wizards
- [ ] "Cancel" returns to previous state, not a dead end
- [ ] Window close button asks to save if unsaved changes
- [ ] Ability to resize/reposition windows freely
- [ ] Task switching preserves state (no data loss on alt+tab)

---

### H4 — Consistency and Standards

**Checklist:**
- [ ] Same action uses same label/icon across the app
- [ ] Same component uses same styling (buttons, inputs, trees, tables)
- [ ] Color coding consistent (red = error/destructive, green = success)
- [ ] Layout structure consistent across windows
- [ ] Platform conventions followed (menu bar at top on macOS, in-window on Windows)
- [ ] Terminology consistent (don't mix "Folder" and "Directory")
- [ ] Keyboard shortcuts consistent with OS standards
- [ ] Dialog button order follows platform convention (OK/Cancel on Windows, Cancel/OK on macOS)

---

### H5 — Error Prevention

**Checklist:**
- [ ] Required fields marked
- [ ] Input constraints prevent invalid data
- [ ] Submit button disabled until valid
- [ ] Confirmation for destructive actions
- [ ] Form data preserved on validation errors
- [ ] Auto-save for long documents
- [ ] File validation before upload (type, size)
- [ ] Prevent double-submit
- [ ] Unsaved changes prompt before close
- [ ] Read-only mode for files opened by another process

---

### H6 — Recognition Rather Than Recall

**Checklist:**
- [ ] Menu bar shows all available actions
- [ ] Recent files list in File menu or splash screen
- [ ] Search/filter in large lists and trees
- [ ] Toolbar with labeled icon buttons for common actions
- [ ] Tooltips on all toolbar and menu items
- [ ] Status bar shows contextual hints
- [ ] Auto-complete in input fields
- [ ] Breadcrumbs in file browsers
- [ ] Sidebar/panel shows navigation tree

---

### H7 — Flexibility and Efficiency of Use

**Checklist:**
- [ ] Keyboard shortcuts for frequent actions
- [ ] Customizable toolbar / quick access bar
- [ ] Bulk operations (multi-select + batch action)
- [ ] Sortable/filterable tables and lists
- [ ] Macros or scripting support for power users
- [ ] Tabbed document interface
- [ ] Split-pane views
- [ ] Configurable keyboard shortcuts
- [ ] Command palette (Ctrl+Shift+P style)

---

### H8 — Aesthetic and Minimalist Design

**Checklist:**
- [ ] No redundant or duplicate information
- [ ] Only essential controls visible; advanced options in submenus
- [ ] White space used effectively
- [ ] Typography hierarchy clear
- [ ] Color palette restrained
- [ ] Icons and images serve a purpose
- [ ] Window chrome not overly distracting
- [ ] High-DPI / Retina assets used
- [ ] Dark mode support

---

### H9 — Help Users Recognize, Diagnose, and Recover from Errors

**Checklist:**
- [ ] Error messages in plain language (no codes)
- [ ] Error identifies the exact field or problem
- [ ] Error suggests how to fix it
- [ ] Inline validation in preference dialogs
- [ ] Crash reports with "Restore previous session" option
- [ ] Network errors show retry button
- [ ] No stack traces leaked to user
- [ ] Log files accessible but not shown by default

---

### H10 — Help and Documentation

**Checklist:**
- [ ] Empty states provide guidance
- [ ] Tooltips explain unfamiliar controls
- [ ] Onboarding wizard on first launch
- [ ] Help menu with documentation link
- [ ] "What's This?" mode for controls (contextual help cursor)
- [ ] Error states link to relevant help
- [ ] About dialog with version and support links
- [ ] Built-in manual or user guide

---

## Execution

1. **Discover all windows/surfaces.** List every window, dialog, panel, popover, menu, and system tray interaction. Include preferences, about dialog, wizards, and error dialogs.

2. **For each surface**, evaluate all 10 heuristics. Test both light and dark mode, and different window sizes.

3. **Score each heuristic per surface** (✅ / ⚠️ / 🔴 / ❌).

4. **Produce a report** with summary table, per-surface breakdown, top issues, and recommendations.

## Report Format

```
# Usability Heuristic Evaluation — [App Name] (Desktop)

## Summary

| Severity    | Count |
|-------------|-------|
| ✅ Pass     | XX    |
| ⚠️ Minor    | XX    |
| 🔴 Major    | XX    |
| ❌ Critical | XX    |

## Per-Surface Results

### Preferences Window
| Heuristic | Score | Finding |
|-----------|-------|---------|
| H1 Visibility | ✅ | Changes apply instantly with feedback |
| H2 Real world | ⚠️ | Uses "daemon" instead of "background service" |
| ... | | |

## Top 5 Issues
...

## Recommendations by Heuristic

---

## Input Detection

Automatically detect what the user has provided:

| Provided | How to use |
|---|---|
| Screenshot / image | Analyze visual hierarchy, layout, labeling, control placement, window chrome |
| Code file (C#, Rust, C++, Python, Swift, etc.) | Read code to understand interaction logic, states, constraints, accessibility attributes |
| Both code + screenshot | Use both — code is primary for interaction/state analysis, screenshot for visual judgment |
| Figma / design URL | Parse fileKey and nodeId. Use available MCP tools to retrieve design context. Treat as screenshot + code context. |
| Text-only description | Do NOT produce a formal report. Give brief informal suggestions and request a screenshot, code, or design URL. |
| None of the above | Ask: "Can you provide a screenshot, design URL, or point me to the relevant code file?" |

If only one type is provided and the other would significantly improve the evaluation, note it at the end of the report — not at the beginning.

---

## Module Auto-Detection

Before running the evaluation, scan the input for domain-specific patterns and enable relevant modules:

| Module | Auto-detect when | Reference file |
|---|---|---|
| Data Visualization | Charts, graphs, KPIs, dashboards, data tables, status indicators, progress bars, sparklines, gauges, or any data-display layout | [references/data-viz-heuristics.md](references/data-viz-heuristics.md) |
| Accessibility | **ALWAYS enabled** for every evaluation. Default: WCAG AA. Escalate to AAA when the user requests it, or the product targets the general public, healthcare, government, or users with disabilities. | [references/accessibility-heuristics.md](references/accessibility-heuristics.md) |

Multiple modules can be active simultaneously. State which modules are active at the top of the report.

---

## Evaluation Guidelines

- **Be specific**: reference exact controls, labels, or layout areas by name — not generic statements.
- **Cite evidence**: "The date picker has no disabled states when the range changes" is better than "Error prevention could be improved."
- **Acknowledge strengths**: if a heuristic is well-handled, mark it as `Good` with a brief note on what works. Do not manufacture problems.
- **Respect incompleteness**: placeholder text, TODO comments, and stub components are not design flaws. Note them in the finding text and rate based on actual user impact.
- **Screenshot artifacts are not findings**: Transient states captured in a screenshot (tooltips, hover menus, focus rings) are not permanent layout problems. If a transient state reveals a real positioning issue, note it with appropriate context.
- **WCAG level**: Default to Level AA. Escalate to Level AAA when the user explicitly requests it, or when the product context implies it (public-sector, healthcare, assistive-technology products).
- **Use Needs Manual Review honestly**: When you cannot observe or verify a behavior from the provided input, rate it `Needs Manual Review`. Do not assign a severity to something you haven't confirmed.
- **Internal consistency first**: for H4 (Consistency and Standards), always evaluate internal consistency within the app first. Only evaluate external/platform consistency if context was provided.
- **Reference the detailed checklists** in `references/nielsen-10-heuristics.md` for per-heuristic platform-specific guidance.

---

## Rating Scale

Use the full 6-level scale from [references/severity-scale.md](references/severity-scale.md):

| Rating | Label | Definition | Action |
|---|---|---|---|
| ❌ | **Critical** | Prevents task completion or causes serious data misunderstanding | Must fix before release |
| 🔴 | **Major** | Significant friction or confusion; users can work around but will struggle | Should fix — high priority |
| ⚠️ | **Minor** | Noticeable annoyance but users can complete their task | Fix when possible |
| ✅ | **Good** | Heuristic is well-handled; note what works | No action needed |
| 👁️ | **Needs Manual Review** | Cannot verify from provided input | Verify in live product |
| — | **N/A** | Heuristic does not apply to this UI | No action needed |

When `Rating = N/A` or `Rating = Needs Manual Review`, there is no scored severity.

---

## Comparative Mode

Triggered when the user provides two versions (e.g., two screenshots, two design URLs, before/after code).

1. Run the standard evaluation on **both** versions
2. Produce a comparison table:

| Heuristic | Version A | Version B | Delta |
|---|---|---|---|
| H1 Visibility of System Status | Minor | Good | Improved |
| ... | ... | ... | ... |

3. Highlight **regressions** (worse in B) and **improvements** (better in B)
4. Executive summary focuses on **what changed**, not a full re-evaluation of both versions
```
