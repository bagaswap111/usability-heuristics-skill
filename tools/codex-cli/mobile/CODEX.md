# Skill: usability-heuristics-mobile

# Usability Heuristics Evaluation — Mobile (iOS/Android)

Evaluates a mobile application's user interface against [Jakob Nielsen's 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/). The agent inspects every screen, modal, bottom sheet, and overlay, scoring each heuristic and producing a structured report.

## When to use

- Before a mobile UI redesign or visual refresh.
- After shipping new features or screens.
- As part of QA, app store review preparation, or accessibility audit.
- For both native (Swift/Kotlin) and cross-platform (Flutter/React Native) apps.

## When NOT to use

- For web-only or desktop-only interfaces (use the platform-specific variant).
- When you need a full WCAG accessibility audit.
- For backend or API-only reviews.

## Heuristics

Scoring: ✅ Pass | ⚠️ Minor | 🔴 Major | ❌ Critical

---

### H1 — Visibility of System Status

**Checklist:**
- [ ] Loading states exist for every async operation (spinner, shimmer, pull-to-refresh)
- [ ] Screen titles clearly indicate current location
- [ ] Tab bar / bottom nav highlights active tab
- [ ] Form submissions show a saving/processing state
- [ ] Button taps provide visual feedback (ripple, highlight, disabled state)
- [ ] Long operations (>3s) show progress bar or estimated time
- [ ] Push/in-app notifications for background operations
- [ ] Network connectivity indicator (offline banner or toast)
- [ ] Pull-to-refresh with appropriate feedback
- [ ] Success confirmation (snackbar, toast) after create/update/delete

---

### H2 — Match Between System and the Real World

**Checklist:**
- [ ] Labels use familiar terms (no internal/technical jargon)
- [ ] Icons have text labels or are universally understood (e.g., magnifying glass = search)
- [ ] Date/time formats match device locale (region-aware)
- [ ] Currency and number formats match locale conventions
- [ ] Error messages are in plain language, not codes
- [ ] Navigation labels match user mental model
- [ ] Gestures match platform conventions (swipe to delete, swipe back, long-press for context menu)
- [ ] Haptic feedback is used meaningfully, not excessively
- [ ] Platform-specific design language followed (Material Design on Android, HIG on iOS)

---

### H3 — User Control and Freedom

**Checklist:**
- [ ] System back gesture/button goes to previous screen (not exits app)
- [ ] Confirmation dialog before destructive actions (delete, discard)
- [ ] Undo support (snackbar with "Undo" action)
- [ ] Close/dismiss button on modals, bottom sheets, dialogs
- [ ] Swipe to go back works consistently (iOS)
- [ ] Cancel button in multi-step flows
- [ ] "Cancel" returns user to previous state, not a dead end
- [ ] Drag handle on bottom sheets for interactive dismiss

---

### H4 — Consistency and Standards

**Checklist:**
- [ ] Same action uses same label/icon across the app
- [ ] Same component uses same styling (buttons, cards, inputs, dialogs)
- [ ] Color coding is consistent (red = destructive, green = success)
- [ ] Layout structure consistent across screens
- [ ] Platform conventions respected (iOS picker vs Android dropdown)
- [ ] Terminology is consistent (don't mix "Course" and "Subject")
- [ ] Navigation pattern is consistent (tabs vs drawer vs stack)
- [ ] Typography scale is consistent

---

### H5 — Error Prevention

**Checklist:**
- [ ] Required fields are marked (asterisk or label)
- [ ] Input constraints prevent invalid data (keyboard type, max length, regex)
- [ ] Submit button is disabled until required fields are valid
- [ ] Confirmation for destructive actions (double-check before delete)
- [ ] Form data preserved on validation errors
- [ ] Auto-save for long forms (draft preservation)
- [ ] File/image uploads validate type and size before uploading
- [ ] Prevent accidental double-tap (button disabled after first tap)
- [ ] Network-aware: queue or warn before submitting offline
- [ ] Biometric/passcode confirmation for sensitive actions

---

### H6 — Recognition Rather Than Recall

**Checklist:**
- [ ] Bottom tab bar / navigation shows all main sections
- [ ] Search is available for large content sets
- [ ] Recently viewed/used items are surfaced
- [ ] Form fields have placeholder text or helper text
- [ ] Current selection is clearly highlighted
- [ ] Icons are accompanied by labels (tab bar, list items)
- [ ] Password field has a "show password" toggle
- [ ] Previously entered data is pre-filled when appropriate
- [ ] Search history or recent searches shown

---

### H7 — Flexibility and Efficiency of Use

**Checklist:**
- [ ] 3D Touch / long-press shortcuts for frequent actions
- [ ] Bulk actions available (select multiple, apply action to all)
- [ ] Sortable/filterable lists
- [ ] Pagination or virtual scrolling for long lists
- [ ] Favorites / bookmarks for frequently used items
- [ ] "Copy from existing" for repetitive tasks
- [ ] Haptic touch / contextual menus (iOS) or long-press menus (Android)
- [ ] Share sheet integration
- [ ] Widget support for quick actions (iOS widgets, Android app widgets)

---

### H8 — Aesthetic and Minimalist Design

**Checklist:**
- [ ] No redundant or duplicate information
- [ ] Only essential controls visible; advanced options in secondary menus
- [ ] White space used effectively (not cramped, not wasteful)
- [ ] Typography hierarchy clear (headings, subheadings, body)
- [ ] Color palette restrained (no clash, no excessive highlights)
- [ ] Icons and images serve a purpose
- [ ] Safe areas respected (notch, status bar, home indicator)
- [ ] Touch targets meet platform minimum (44pt / 48dp)
- [ ] No visual clutter in dense screens

---

### H9 — Help Users Recognize, Diagnose, and Recover from Errors

**Checklist:**
- [ ] Error messages in plain language (no codes like "ERR-4532")
- [ ] Error identifies the exact field or problem
- [ ] Error suggests how to fix it
- [ ] Inline validation under the field (not just a top-of-screen banner)
- [ ] Network error shows retry button
- [ ] Server errors don't leak stack traces or internal details
- [ ] Empty/error states have illustration + action button
- [ ] Offline mode shows cached content with "You're offline" banner

---

### H10 — Help and Documentation

**Checklist:**
- [ ] Empty states provide guidance ("No items yet. Create your first...")
- [ ] Tooltips or coach marks explain unfamiliar features
- [ ] Onboarding flow exists for first-time users
- [ ] FAQ / help screen is linked from the UI
- [ ] Error states link to relevant help
- [ ] Contact/support is accessible (in-app chat, email, phone)
- [ ] What's New / changelog screen after app updates

---

## Execution

1. **Discover all screens.** List every screen/route: tab screens, stack screens, modals, bottom sheets, dialogs. Include auth, onboarding, empty states, error states.

2. **For each screen**, evaluate all 10 heuristics. Note orientation-specific issues (portrait vs landscape) and dark mode if applicable.

3. **Score each heuristic per screen** (✅ / ⚠️ / 🔴 / ❌).

4. **Produce a report** with summary table, per-screen breakdown, top issues, and recommendations.

## Report Format

```
# Usability Heuristic Evaluation — [App Name] (Mobile)

## Summary

| Severity    | Count |
|-------------|-------|
| ✅ Pass     | XX    |
| ⚠️ Minor    | XX    |
| 🔴 Major    | XX    |
| ❌ Critical | XX    |

## Per-Screen Results

### Login Screen
| Heuristic | Score | Finding |
|-----------|-------|---------|
| H1 Visibility | ✅ | Loading spinner on submit |
| H2 Real world | ⚠️ | Uses "ERR-001" instead of "Invalid email" |
| ... | | |

## Top 5 Issues
1. **[Screen] [H#] [Severity]** — Description → Fix
...

## Recommendations by Heuristic
### H1 — Visibility of System Status
- ...
```
