# Accessibility Heuristics

Always applied as a supplementary module for every evaluation. These are lightweight, high-impact checks — not a full WCAG audit. Focus on issues detectable from screenshots and code inspection.

---

## A11Y-1 Color Contrast

Sufficient contrast ensures readability for users with low vision or in bright environments.

### Checklist
- Does body text meet a 4.5:1 contrast ratio against its background?
- Do large headings (18px+ bold or 24px+ regular) meet a 3:1 ratio?
- Are interactive elements (buttons, links, form controls) visually distinguishable from surrounding content?
- Is color used as the sole means of conveying information? (e.g. red = error with no icon or text label)

### Platform notes
- **Web/Desktop:** CSS `currentColor` inheritance, forced colors mode, OS high-contrast mode
- **Mobile:** Dark/light mode, accessibility zoom, reduced transparency setting
- **CLI:** N/A — color in terminal output should use NO_COLOR convention and never be the only differentiator

---

## A11Y-2 Text and Target Sizing

Adequate sizing prevents misclicks and improves readability across devices and abilities.

### Checklist
- Is body text at least 14px (or equivalent rem/em)?
- Are clickable/tappable targets at least 24×24 CSS pixels? (WCAG 2.5.8, Level AA)
  - When evaluating at AAA: targets should be at least 44×44px (WCAG 2.5.5)
- Is there adequate spacing between adjacent interactive elements to prevent accidental activation?
- Are small labels and secondary text still legible? (minimum ~11px with sufficient contrast)

### Platform notes
- **Mobile:** Touch targets minimum 44pt (iOS) / 48dp (Android)
- **Desktop:** Minimum click targets 24×24px, dense layouts may need larger
- **CLI:** Output not truncated, line wrapping handled, minimum terminal width documented

---

## A11Y-3 Keyboard Navigation

All functionality should be operable via keyboard for users who cannot use a mouse.

### Checklist
- Are focus indicators visible on interactive elements? (outline, ring, highlight)
- Does tab order follow a logical reading sequence?
- Are there keyboard traps? (focus enters a component but cannot leave via Tab or Escape)
- Can all interactive controls be activated with Enter or Space?
- Are custom components (dropdowns, modals, tabs) keyboard-accessible?

### Platform notes
- **Web/Desktop:** Tab order, focus trapping in modals, aria roles
- **Mobile:** VoiceOver / TalkBack navigation, focus management
- **CLI:** Tab completion, arrow key navigation in TUI, --non-interactive mode

---

## A11Y-4 Labels and Descriptions

Every interactive element needs an accessible name so assistive technology can announce it.

### Checklist
- Do all form inputs have visible labels? (not just placeholder text)
- Do images and icons have alt text or aria-labels?
- Do icon-only buttons have accessible names? (aria-label, sr-only text, or tooltip)
- Are form groups and fieldsets labeled for context? (e.g. "Filter options", "Date range")
- Are decorative images marked as presentational? (alt="", role="presentation")

### Platform notes
- **Web:** Aria attributes, semantic HTML, alt text
- **Mobile:** accessibilityLabel (iOS), contentDescription (Android)
- **Desktop:** Tooltip text, accessibility name property, labelled-by
- **CLI:** Help text, usage output, error descriptions, man page sections

---

## A11Y-5 State Communication

Users relying on assistive technology need state changes conveyed beyond just visual appearance.

### Checklist
- Are selected/active states communicated via aria-selected, aria-current, or equivalent?
- Are disabled elements marked with the disabled attribute or aria-disabled?
- Are expanded/collapsed states communicated via aria-expanded?
- Do loading or dynamic content regions use aria-live or role="status"?
- Is state conveyed by more than color alone? (icons, text labels, patterns, borders)

### Platform notes
- **Web:** Aria attributes, role mapping, focus management
- **Mobile:** UIAccessibility (iOS), AccessibilityNodeInfo (Android)
- **Desktop:** UI Automation (Windows), NSAccessibility (macOS)
- **CLI:** Exit codes, exit code documentation, stderr differentiation
