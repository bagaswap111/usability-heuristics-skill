# Nielsen's 10 Usability Heuristics — Evaluation Checklist

For each heuristic, use the checklist questions to guide your evaluation. Not every question applies to every UI — skip irrelevant ones and mark the heuristic N/A if none apply.

---

## H1 — Visibility of System Status

The system should keep users informed about what is going on through timely, appropriate feedback.

### Checklist
- Does the UI show the current state clearly? (selected filters, active tab, applied settings)
- When a user action triggers data loading, is there a loading indicator?
- After an action completes, is there confirmation or visible change?
- Are there stale-state risks? (e.g. UI shows old data after a filter change)
- Do controls reflect their current value at all times?

### Platform notes
- **Web:** Browser title/ tab should reflect page context
- **Mobile:** Pull-to-refresh feedback, push notifications
- **Desktop:** Status bar, window title, system tray notifications
- **CLI:** Exit codes, spinner/progress bar, verbose output

---

## H2 — Match Between System and Real World

Use language and concepts familiar to the target user. Information should appear in a natural, logical order.

### Checklist
- Are labels and terms in the user's vocabulary, not developer jargon?
- Is the order of controls and information natural to the user's mental model and task flow?
- Do icons and visual metaphors align with their real-world meaning?
- Are units and formats appropriate? (dates, numbers, percentages)
- Would a first-time user of this domain understand the terminology without external help?

### Platform notes
- **Web:** URL slugs, breadcrumbs, link text
- **Mobile:** Gesture conventions (swipe, long-press), platform HIG
- **Desktop:** Menu bar conventions (File, Edit, View, Help)
- **CLI:** POSIX conventions, `--help` language, shorthand flags

---

## H3 — User Control and Freedom

Users need a clear "emergency exit" to leave unwanted states without extended effort.

### Checklist
- Can users undo or revert filter/control changes easily?
- Is there a "reset to defaults" option if multiple controls exist?
- Can users navigate away and return without losing context?
- Are there dead-end states where the user gets stuck?
- Do modal dialogs have clear close/cancel actions?

### Platform notes
- **Web:** Browser back button, escape key
- **Mobile:** System back gesture, swipe to dismiss
- **Desktop:** Window close, Ctrl+Z / Cmd+Z undo
- **CLI:** Ctrl+C graceful interrupt, `--dry-run`, confirmation prompts

---

## H4 — Consistency and Standards

Users should not wonder whether different words, situations, or actions mean the same thing.

### Internal Consistency (always evaluate)
- Are similar controls styled and behaved consistently across the UI?
- Is terminology consistent? (same concept always uses the same word)
- Do similar interactions produce similar results?
- Are spacing, typography, and color usage systematic or ad-hoc?
- Are control types consistent for similar functions?
- For repeated components: consistency means following the same structural pattern, not identical appearance. Flag only when an instance breaks the shared structural pattern.

### External Consistency (evaluate only if platform context provided)
- Does the UI follow the platform's established design system?
- Are common patterns consistent with sibling products?
- Does the UI follow widely-adopted industry conventions?

### Platform notes
- **Web:** Browser conventions, URL structure, open graph
- **Mobile:** Material Design / HIG guidelines, platform-specific patterns
- **Desktop:** OS-native widgets, menu bar layout, keyboard shortcuts
- **CLI:** POSIX/GNU flag conventions, exit codes, stderr/stdout

---

## H5 — Error Prevention

Good design prevents problems before they occur, rather than relying on error messages.

### Checklist
- Do interdependent controls constrain each other? (e.g. invalid options disabled when a parent control changes)
- Are sensible defaults provided to reduce the chance of misconfiguration?
- Are destructive or irreversible actions guarded with confirmation?
- Does the UI prevent invalid input rather than accepting and then showing an error?
- Are there edge cases where controls can reach an impossible or meaningless combination?

### Platform notes
- **Web:** Form validation, double-submit prevention, auto-save
- **Mobile:** Keyboard type matching input, biometric confirmation
- **Desktop:** File overwrite warnings, unsaved changes prompt
- **CLI:** Argument validation, dry-run mode, lock files

---

## H6 — Recognition Rather Than Recall

Minimize the user's memory load by making elements, actions, and options visible.

### Checklist
- Are all available options visible or easily accessible? (no hidden functionality)
- Do users need to remember information from one part of the UI to use another part?
- Are labels present on all controls, or do some rely on positional memory?
- Is the current context (page, section, applied filters) always visible?
- Are tooltips or inline descriptions available for non-obvious concepts?

### Platform notes
- **Web:** Nav menu, breadcrumbs, search, recent items
- **Mobile:** Tab bar, bottom sheet, search bar
- **Desktop:** Menu bar, toolbar, side panel, recent files
- **CLI:** Tab completion, `--help`, history, aliases

---

## H7 — Flexibility and Efficiency of Use

Shortcuts and accelerators should be available for expert users without cluttering the novice experience.

### Checklist
- Are there shortcuts for frequent actions? (keyboard shortcuts, quick filters)
- Can expert users bypass or skip steps that novices need?
- Are there power-user features that don't interfere with the basic experience?
- Can users customize or save preferred configurations?
- Is the UI efficient for the user's most common task?

### Platform notes
- **Web:** Keyboard shortcuts, bulk actions, sortable tables
- **Mobile:** 3D Touch / long-press, widgets, share sheet
- **Desktop:** Customizable toolbar, macros, split pane, command palette
- **CLI:** Short flags, piping, `--quiet`, `--json` output, shell completions

---

## H8 — Aesthetic and Minimalist Design

Every extra element competes with relevant content and diminishes its relative visibility.

### Checklist
- Does every visible element serve a purpose? Are there decorative-only elements that add noise?
- Is the visual hierarchy clear? (most important information is most prominent)
- Is the information density appropriate — not too sparse, not overwhelming?
- Are controls grouped logically, or scattered without clear organization?
- Does whitespace guide the eye effectively?

### Platform notes
- **Web:** Above the fold, responsive breakpoints, no layout shift
- **Mobile:** Touch targets (44pt/48dp), safe areas, no crowding
- **Desktop:** Window chrome, high-DPI assets, dark mode
- **CLI:** Output formatting, aligned columns, `--verbose`/`--quiet`

---

## H9 — Help Users Recognize, Diagnose, and Recover from Errors

Error messages should be in plain language, indicate the problem precisely, and suggest a solution.

### Checklist
- When something goes wrong (no data, failed load, invalid state), is the error message clear and helpful?
- Are error states visually distinct from normal states?
- Do error messages suggest what to do next?
- Are empty states handled gracefully? (no data available, no results matching filter)
- Are errors expressed in user language, not technical codes or stack traces?

### Platform notes
- **Web:** HTTP error pages, inline validation, retry button
- **Mobile:** Offline banner, snackbar with action, retry on network error
- **Desktop:** Crash reporter, session restore, log file reference
- **CLI:** Stderr output, exit codes, "did you mean?" suggestions

---

## H10 — Help and Documentation

Even if the system can be used without documentation, it may be necessary to provide help.

### Checklist
- Are complex or domain-specific concepts explained? (tooltips, descriptions, info icons)
- Is contextual help available near the elements that need it?
- Are descriptions concise and task-oriented?
- For multi-step workflows, is there guidance on what to do next?
- Placeholders that indicate intent to add help should be noted, not penalized as design flaws.

### Platform notes
- **Web:** Empty states, tooltips, FAQ link, onboarding
- **Mobile:** Coach marks, onboarding flow, in-app help
- **Desktop:** Menu help, tooltips, "What's This?" mode, built-in manual
- **CLI:** `--help`, man pages, usage examples, shell completions
