# Paper Plan — IEEE Standard

**Proposed Title:** A Multi-Platform Usability Heuristic Evaluation Framework for AI-Assisted Development

**Target Venue:** IEEE Conference (e.g., IEEE SSCI, IEEE VIS, IEEE CHI workshop track) or IEEE Access

---

## Abstract (150–250 words)

- Problem: UI evaluation remains manual, inconsistent, and platform-specific
- What we built: An AI-driven framework that operationalizes Nielsen's 10 usability heuristics
- Key contributions:
  - Multi-platform support (web, mobile, desktop, CLI)
  - Multi-LLM-tool compatibility (11 AI coding assistant formats)
  - Modular architecture with auto-detected supplementary modules (Data Visualization, Accessibility)
  - Standardized 6-level severity scale and evaluation guidelines
- Validation: Case studies across 4 platforms demonstrating coverage, consistency, and time savings
- Conclusion: Reproducible, extensible framework bridges heuristic evaluation with AI-assisted development workflows

---

## I. Introduction (~1.5 pages)

### Context
- Rise of AI coding assistants: Claude Code, Cursor, GitHub Copilot, Windsurf, Aider, Continue, Codex CLI, Augment, PearAI, Cody
- These tools accept structured instructions (skill files, rules, conventions) that shape agent behavior
- Growing opportunity to encode UX expertise into these instruction files

### Problem
- Heuristic evaluation is labor-intensive and requires UX expertise
- Existing evaluation tools (WAVE, Lighthouse, axe-core) are automated but limited to specific heuristics (mostly accessibility)
- LLM-based evaluation exists but lacks:
  - Standardized, reusable instruction sets
  - Platform-specific adaptation
  - Multi-tool interoperability
  - Supplementary domain modules

### Proposed Solution
- A configurable skill framework that encodes Nielsen's 10 heuristics with platform-specific checklists
- Published in 11 AI coding tool formats
- Modular architecture with auto-detectable supplementary modules
- Open-source repository with CI, templates, and documentation

### Contributions
1. Platform-agnostic heuristic checklists adapted for Web, Mobile, Desktop, and CLI
2. Interoperable format mapping across 11 AI coding tools
3. Modular auto-detection system (core + Data Visualization + Accessibility)
4. Standardized 6-level severity scale with evaluation guidelines
5. Open-source reference implementation with 44+ platform-tool combinations

### Paper Organization
Section II discusses related work. Section III presents methodology. Section IV describes architecture. Section V covers implementation. Section VI evaluates the framework. Section VII discusses limitations. Section VIII concludes.

---

## II. Related Work (~2 pages)

### 2.1 Heuristic Evaluation Foundations
- Nielsen's 10 Usability Heuristics (Nielsen, 1994)
- Severity ratings for usability problems (Nielsen, 1994)
- Comparison with other frameworks:
  - Shneiderman's 8 Golden Rules
  - Benyon's 14 Principles
  - Gerhardt-Powals' Cognitive Engineering Principles
- Table: Framework comparison matrix

### 2.2 Automated UI Evaluation Tools
| Tool | Scope | Heuristics | Platform | LLM-based |
|------|-------|------------|----------|-----------|
| WAVE | Accessibility | WCAG | Web | No |
| Lighthouse | Performance + A11y | WCAG | Web | No |
| axe-core | Accessibility | WCAG | Web | No |
| UX Check (Chrome ext) | Nielsen 10 | Manual checklist | Web | No |
| This work | Nielsen 10 + modules | All 10 + DV + A11Y | Web/Mobile/Desktop/CLI | Yes |

### 2.3 LLM-Based UX Evaluation
- Prior work on using GPT/Claude for heuristic evaluation
- Strengths: contextual understanding, free-text reasoning
- Limitations: hallucination, no standardized prompt, platform-blind
- Gap: No existing work provides structured, platform-adapted, multi-tool heuristic skill

### 2.4 AI Coding Tool Instruction Formats
- Survey of tool instruction mechanisms:
  - Claude Code: `CLAUDE.md`, `~/.claude/skills/`
  - Cursor: `.cursorrules`, `.cursor/rules/`
  - GitHub Copilot: `.github/copilot-instructions.md`
  - Windsurf: `.windsurfrules`
  - Aider: `CONVENTIONS.md`
  - Continue: `.continuerc.md`
  - Codex CLI: `CODEX.md`
  - Augment: `AUGMENT.md`
  - PearAI: `.pearai/instructions.md`
  - Cody: `.cody/instructions.md`
  - OpenCode: `SKILL.md`
- Key observation: All are markdown-based; content is portable

---

## III. Methodology (~3 pages)

### 3.1 Heuristic Selection and Adaptation
- Why Nielsen's 10: most widely cited, platform-agnostic foundation
- Adaptation process per platform:

| Heuristic | Web | Mobile | Desktop | CLI |
|-----------|-----|--------|---------|-----|
| H1 Status Visibility | Browser title, HTTP loading | Pull-to-refresh, push notifications | Status bar, system tray | Exit codes, spinner, verbose |
| H2 Real World Match | URL slugs, breadcrumbs | Gesture conventions, HIG | Menu conventions (File/Edit) | POSIX conventions, --help |
| H3 User Control | Browser back, Escape | System back gesture, swipe | Ctrl+Z, window close | Ctrl+C, --dry-run |
| H4 Consistency | CSS design system, URL structure | Material/HIG guidelines | OS-native widgets | POSIX/GNU flags |
| H5 Error Prevention | Form validation, double-submit | Keyboard type, biometric | File overwrite, unsaved changes | Arg validation, dry-run |
| H6 Recognition | Nav menu, breadcrumbs, search | Tab bar, search bar | Menu bar, toolbar, recent files | Tab completion, --help |
| H7 Flexibility | Keyboard shortcuts, bulk actions | 3D Touch, widgets | Custom toolbar, macros | Short flags, piping |
| H8 Minimalist | Above-fold, responsive, no CLS | Touch targets, safe areas | Window chrome, high-DPI | Output formatting, --quiet |
| H9 Error Recovery | HTTP error pages, inline validation | Offline banner, snackbar | Crash reporter, session restore | Stderr, "did you mean?" |
| H10 Help/Docs | Empty states, tooltips, onboarding | Coach marks, in-app help | Menu help, built-in manual | Man pages, --help, examples |

### 3.2 Tool Format Mapping
- Content is authored once as `{platform}/SKILL.md`
- Automated transformation to target format:
  - Plain copy for most tools (same markdown)
  - YAML frontmatter injection for GitHub Copilot (`scope:` field)
- File structure:
  ```
  {platform}/SKILL.md              → tools/{tool}/{platform}/{filename}
  references/nielsen-10-heuristics.md  → shared reference (cloned when needed)
  ```

### 3.3 Supplementary Module System
- Core (always active): Nielsen's 10 heuristics
- Module detection logic:

| Module | Trigger Pattern | Reference File |
|--------|----------------|----------------|
| Data Visualization (DV-1–6) | Charts, graphs, KPIs, dashboards, data tables, progress bars, sparklines, gauges | `references/data-viz-heuristics.md` |
| Accessibility (A11Y-1–5) | Always active (WCAG AA default, escalates to AAA) | `references/accessibility-heuristics.md` |

### 3.4 Input Detection
- Type detection priority:
  1. Screenshot/image → visual analysis
  2. Code file → interaction/state/accessibility analysis
  3. Both → combined (code primary for interaction, screenshot for visual)
  4. Figma URL → parse and retrieve via MCP
  5. Text-only → informal suggestions, request screenshot/code
  6. None → prompt user

### 3.5 Severity Scale
| Level | Definition | Action |
|-------|------------|--------|
| Critical | Prevents task completion | Must fix |
| Major | Significant friction | High priority |
| Minor | Noticeable annoyance | Fix when possible |
| Good | Well-handled | Preserve |
| Manual Review | Cannot verify | Check in live product |
| N/A | Does not apply | Skip |

### 3.6 Evaluation Guidelines
- Be specific (reference exact controls)
- Cite evidence (not generic statements)
- Acknowledge strengths (mark Good, don't manufacture problems)
- Respect incompleteness (placeholders ≠ flaws)
- Screenshot artifacts ≠ findings (tooltips on hover, focus rings)
- WCAG: AA default, AAA on request or public-sector/healthcare context
- Use Manual Review honestly
- Internal consistency first, external only if context provided

---

## IV. System Architecture (~2 pages)

### 4.1 Overview Diagram
```
[Input]
  ├── Screenshot
  ├── Code File
  ├── Figma URL
  └── Text Description
       │
       ▼
[Input Detection Layer]
       │
       ▼
[Module Activator]
  ├── Core: Nielsen 10 (always)
  ├── Data Visualization (conditional)
  └── Accessibility (always)
       │
       ▼
[Evaluation Engine]
  ├── Read platform-specific checklists
  ├── Apply evaluation guidelines
  ├── Score with severity scale
  └── Generate report
       │
       ▼
[Output]
  ├── Report file ({platform}-eval-{name}.md)
  ├── Inline summary (ratings + priority actions)
  └── Comparative mode (optional A/B table)
```

### 4.2 Module Interaction
- Core module provides baseline evaluation across 10 heuristics
- Supplementary modules extend specific heuristics:
  - DV module adds 6 heuristics for data-display contexts
  - A11Y module adds 5 heuristics for accessibility
- Modules share severity scale and guidelines
- Report consolidates all active modules

### 4.3 File Organization
```
usability-heuristics/
├── web/SKILL.md                     # Platform-specific skill
├── mobile/SKILL.md
├── desktop/SKILL.md
├── cli/SKILL.md
├── references/
│   ├── nielsen-10-heuristics.md     # Detailed checklists + platform notes
│   ├── data-viz-heuristics.md       # DV module
│   ├── accessibility-heuristics.md  # A11Y module
│   └── severity-scale.md           # Rating definitions
├── tools/
│   ├── claude-code/{platform}/CLAUDE.md
│   ├── cursor/{platform}/.cursorrules
│   ├── ... (11 tools × 4 platforms)
├── .github/
│   ├── ISSUE_TEMPLATE/
│   ├── pull_request_template.md
│   └── workflows/validate.yml
└── README.md
```

### 4.4 Tool Format Mapping
- Each tool file is an exact copy of `{platform}/SKILL.md`
- Exception: GitHub Copilot adds YAML frontmatter with `scope:`
- Future: other tools may require format-specific wrappers

---

## V. Implementation (~2 pages)

### 5.1 Repository
- Open-source on GitHub: `bagaswap111/usability-heuristics-skill`
- 44+ platform-tool file combinations
- Continuous integration validates file structure on PR
- Issue templates for bug reports and feature requests
- PR template with platform/tool checklist

### 5.2 Reference Library
- 4 reference files with 100+ total checklist items
- Platform-specific annotations for all 10 heuristics
- Color contrast thresholds, touch target sizes (WCAG AA/AAA)
- Chart type appropriateness guidelines

### 5.3 Platform-Specific Checklist Differences (sample)
- H1 Web: "Does browser title reflect page context?" — not applicable to CLI
- H5 Mobile: "Biometric confirmation for sensitive actions" — not applicable to Desktop
- H7 CLI: "Shell tab completion available" — not applicable to Mobile
- H8 Desktop: "High-DPI/Retina assets used" — not applicable to CLI

### 5.4 Versioning and Maintenance
- Semantic versioning for skill releases
- CHANGELOG for breaking changes (heuristic additions, platform changes)
- Community contributions via PR template

---

## VI. Evaluation (~3 pages)

### 6.1 Evaluation Methodology
- Select 4 applications (one per platform)
- Run framework evaluation via Claude Code and Cursor
- Compare with manual expert evaluation
- Metrics:
  - **Coverage:** % of applicable heuristics with valid findings
  - **Precision:** % of findings confirmed by expert
  - **Recall:** % of expert-identified issues found by framework
  - **Time:** minutes to complete evaluation vs manual

### 6.2 Case Study 1: Web (e.g., OpenDashboard)
- Platform: Web
- Tool: Claude Code, Cursor
- Screenshots provided + code access
- Active modules: Core + Data Visualization + Accessibility
- Results: X findings (Y Critical, Z Major, ...)
- Expert agreement: %

### 6.3 Case Study 2: Mobile (e.g., FitTrack iOS App)
- Platform: Mobile
- Tool: GitHub Copilot
- Screenshots provided
- Active modules: Core + Accessibility
- Results: ...

### 6.4 Case Study 3: Desktop (e.g., CodeEditor App)
- Platform: Desktop
- Tool: Cursor
- Code provided
- Results: ...

### 6.5 Case Study 4: CLI (e.g., Deploy CLI tool)
- Platform: CLI
- Tool: Claude Code
- Code provided
- Results: ...

### 6.6 Comparative Analysis
| Metric | Web | Mobile | Desktop | CLI |
|--------|-----|--------|---------|-----|
| Coverage | % | % | % | % |
| Precision | % | % | % | % |
| Recall | % | % | % | % |
| Time (min) | min | min | min | min |
| Manual Time (min) | min | min | min | min |

### 6.7 Inter-Tool Consistency
- Run same platform evaluation across 3 different tools
- Measure finding agreement (Cohen's kappa or similar)

---

## VII. Discussion (~1.5 pages)

### 7.1 Strengths
- Multi-platform coverage: first framework to adapt Nielsen's heuristics for 4 platforms
- Interoperability: same content works across 11 AI tools
- Modularity: extensible to new domains (e-commerce, gaming, IoT)
- Reproducibility: open-source, versioned, community-contributable

### 7.2 Limitations
- **LLM dependency:** Quality varies by model; framework provides structure but cannot guarantee LLM adherence
- **Not a full WCAG audit:** Accessibility module covers 5 high-impact checks; full WCAG 2.2 has 50+ success criteria
- **Screenshot blind spots:** Animations, hover states, focus order, screen reader output not fully observable
- **Platform coverage:** 4 platforms cover majority of UI development but not all (wearables, AR/VR, voice)
- **CLI limitations:** Terminal screenshot analysis is less mature than GUI screenshot analysis

### 7.3 Threats to Validity
- **Internal:** LLM hallucination may produce non-existent findings; mitigated by evaluation guidelines and severity scale
- **External:** Case studies limited to 4 applications; may not generalize
- **Construct:** Severity ratings are inherently subjective; manual review label handles uncertain cases

### 7.4 Comparison with Prior Work
- vs manual expert evaluation: faster but less nuanced
- vs automated tools (Lighthouse, axe): broader heuristic coverage but less reliable for visual judgment
- vs prior LLM evaluation: more structured, platform-aware, reproducible

---

## VIII. Conclusion and Future Work (~1 page)

### 8.1 Summary of Contributions
- First multi-platform, multi-tool heuristic evaluation framework for AI coding assistants
- 44+ platform-tool file combinations in open-source repository
- Modular architecture with auto-detected supplementary modules
- Standardized severity scale and evaluation guidelines
- Demonstrated feasibility across 4 platforms

### 8.2 Future Work
- **Additional supplementary modules:**
  - E-commerce heuristics (cart, checkout, product discovery)
  - Gaming UI heuristics (immersion, feedback loops, tutorialization)
  - IoT/embedded heuristics (constrained displays, physical interaction)
  - Voice UI heuristics (VUIs, conversational interfaces)
- **Automated test generation:** Translate heuristic findings into Playwright/Cypress tests
- **Figma plugin:** Direct evaluation from design files via plugin API
- **User study:** Controlled experiment with UX professionals measuring time savings, finding quality, and workflow integration
- **Cross-model comparison:** GPT-4o vs Claude 3.5 Opus vs Gemini — which produces better heuristic evaluations with the same skill

---

## References (IEEE Format)

[1] J. Nielsen, "Enhancing the explanatory power of usability heuristics," in *Proc. SIGCHI Conf. Human Factors in Computing Systems (CHI '94)*, 1994, pp. 152–158.

[2] J. Nielsen, "Heuristic evaluation," in *Usability Inspection Methods*. New York, NY, USA: Wiley, 1994, pp. 25–62.

[3] B. Shneiderman and C. Plaisant, *Designing the User Interface: Strategies for Effective Human-Computer Interaction*, 6th ed. Boston, MA, USA: Addison-Wesley, 2016.

[4] D. Benyon, *Designing Interactive Systems: A Comprehensive Guide to HCI, UX and Interaction Design*, 3rd ed. London, UK: Pearson, 2014.

[5] W3C, "Web Content Accessibility Guidelines (WCAG) 2.2," W3C Recommendation, 2023. [Online]. Available: https://www.w3.org/TR/WCAG22/

[6] P. Gerhardt-Powals, "Cognitive engineering principles for enhancing human-computer performance," *Int. J. Human-Computer Interaction*, vol. 8, no. 2, pp. 189–211, 1996.

[7] Google, "Lighthouse," 2023. [Online]. Available: https://developer.chrome.com/docs/lighthouse/

[8] Deque Systems, "axe-core," 2023. [Online]. Available: https://github.com/dequelabs/axe-core

[9] WebAIM, "WAVE Web Accessibility Evaluation Tool," 2023. [Online]. Available: https://wave.webaim.org/

[10] Anthropic, "Claude Code," 2025. [Online]. Available: https://docs.anthropic.com/en/docs/claude-code/

[11] Cursor, "Cursor Editor — Rules for AI," 2025. [Online]. Available: https://cursor.sh

[12] GitHub, "GitHub Copilot — Custom Instructions," 2025. [Online]. Available: https://docs.github.com/en/copilot/

[13] A. Sweller et al., "Evaluating LLMs for UX Heuristic Evaluation," *arXiv preprint*, 2024.

[14] M. F. Zaman et al., "Automated Usability Evaluation Using Machine Learning: A Systematic Literature Review," *IEEE Access*, vol. 11, 2023.

[15] J. Sauro and J. R. Lewis, *Quantifying the User Experience: Practical Statistics for User Research*, 2nd ed. Cambridge, MA, USA: Morgan Kaufmann, 2016.

---

## Estimated Page Count

| Section | Pages | Notes |
|---------|-------|-------|
| Abstract | 0.3 | Single paragraph |
| I. Introduction | 1.5 | 3–4 paragraphs |
| II. Related Work | 2.0 | 4 subsections + table |
| III. Methodology | 3.0 | 6 subsections + 2 tables |
| IV. Architecture | 2.0 | 4 subsections + diagram |
| V. Implementation | 2.0 | 4 subsections |
| VI. Evaluation | 3.0 | 7 subsections + 2 tables |
| VII. Discussion | 1.5 | 4 subsections |
| VIII. Conclusion | 1.0 | 2 subsections |
| References | 1.0 | ~15 references |
| **Total** | **~17** | Within IEEE 8–20 page range |

---

## Diagram Suggestions

1. **Fig 1 — System Architecture** (Section IV): Input → Detection → Module Activator → Evaluation Engine → Output
2. **Fig 2 — Module Interaction** (Section IV): Core + DV + A11Y with shared severity scale
3. **Fig 3 — Tool Format Mapping** (Section V): SKILL.md → 11 tool formats
4. **Fig 4 — Platform Adaptation** (Section III): H1 example across 4 platforms
5. **Table I — Platform Adaptation Matrix** (Section III): 10 heuristics × 4 platforms
6. **Table II — Tool Feature Comparison** (Section II): Related work vs this work
7. **Table III — Case Study Results** (Section VI): Coverage, precision, recall, time
8. **Table IV — Inter-Tool Consistency** (Section VI): Agreement across Claude Code, Cursor, Copilot
