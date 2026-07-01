# Usability Heuristics Evaluation Skill

UI/UX evaluation based on [Nielsen's 10 Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/) — available for **4 platforms** in **11 AI coding tool formats**.

## Platform

| Platform | Folder | Target |
|----------|--------|--------|
| Web | `web/` | Website, web app, dashboard |
| Mobile | `mobile/` | iOS, Android, cross-platform apps |
| Desktop | `desktop/` | macOS, Windows, Linux apps |
| CLI | `cli/` | CLI tools, TUI, terminal apps |

## Tool Format

Each platform has a variant for every AI tool:

| Tool | File | Folder |
|------|------|--------|
| OpenCode | `SKILL.md` | `{platform}/SKILL.md` |
| Claude Code | `CLAUDE.md` | `tools/claude-code/{platform}/` |
| Cursor | `.cursorrules` | `tools/cursor/{platform}/` |
| Windsurf | `.windsurfrules` | `tools/windsurf/{platform}/` |
| GitHub Copilot | `.github/copilot-instructions.md` | `tools/github-copilot/{platform}/` |
| Aider | `CONVENTIONS.md` | `tools/aider/{platform}/` |
| Continue | `.continuerc.md` | `tools/continue/{platform}/` |
| Codex CLI | `CODEX.md` | `tools/codex-cli/{platform}/` |
| Augment | `AUGMENT.md` | `tools/augment/{platform}/` |
| PearAI | `.pearai/instructions.md` | `tools/pearai/{platform}/` |
| Cody | `.cody/instructions.md` | `tools/cody/{platform}/` |

## Installation

### OpenCode (Built-in)

Already in skill format — load by name:

```bash
# The skill is auto-discovered when placed under .agents/skills/
skill load usability-heuristics
```

Copy entire skill directory (includes `references/` for supplementary modules):

```bash
cp -r . /project/.opencode/skills/usability-heuristics/
```

---

### Claude Code

Place `CLAUDE.md` at your project root, and optionally copy `references/` for supplementary module support:

```bash
cp tools/claude-code/web/CLAUDE.md /project/CLAUDE.md
cp -r references/ /project/references/   # optional, enables Data Viz + Accessibility modules
```

Claude Code reads `CLAUDE.md` automatically — no config needed. Supported locations (highest priority first):
1. `{project}/CLAUDE.md`
2. `{project}/.claude/CLAUDE.md`
3. `~/CLAUDE.md` (global, all projects)

The `references/` folder is optional but recommended — it enables the supplementary Data Visualization and Accessibility modules.

---

### Cursor

Place `.cursorrules` at your project root:

```bash
cp tools/cursor/web/.cursorrules /project/.cursorrules
```

For Cursor 0.45+ with rule scoping, use the `.cursor/rules/` directory:

```bash
cp tools/cursor/web/.cursorrules /project/.cursor/rules/usability-heuristics.mdc
```

---

### Windsurf

Place `.windsurfrules` at your project root:

```bash
cp tools/windsurf/web/.windsurfrules /project/.windsurfrules
```

Windsurf reads it automatically. For scoped rules, see Windsurf's `.windsurf/rules/` directory.

---

### GitHub Copilot

Place `copilot-instructions.md` under `.github/`:

```bash
cp "tools/github-copilot/web/.github/copilot-instructions.md" "/project/.github/copilot-instructions.md"
```

Copilot reads it automatically when editing files matching the scope in the YAML frontmatter. No extension needed.

---

### Aider

Place `CONVENTIONS.md` at your project root:

```bash
cp tools/aider/web/CONVENTIONS.md /project/CONVENTIONS.md
```

Aider reads conventions from `CONVENTIONS.md` automatically when present in the repo. Also supported: `.aider.conf.yml`.

---

### Continue

Place `.continuerc.md` at your project root:

```bash
cp tools/continue/web/.continuerc.md /project/.continuerc.md
```

Continue reads `.continuerc.md` automatically. Also supported: `.continuerc.json` (JSON format).

---

### Codex CLI

Place `CODEX.md` at your project root:

```bash
cp tools/codex-cli/web/CODEX.md /project/CODEX.md
```

Codex CLI reads `CODEX.md` automatically for project-level instructions.

---

### Augment Code

Place `AUGMENT.md` at your project root:

```bash
cp tools/augment/web/AUGMENT.md /project/AUGMENT.md
```

Augment reads `AUGMENT.md` automatically. Also supported: `INSTRUCTIONS.md`.

---

### PearAI

Place `instructions.md` under `.pearai/`:

```bash
cp "tools/pearai/web/.pearai/instructions.md" "/project/.pearai/instructions.md"
```

PearAI reads instructions from `.pearai/instructions.md` automatically.

---

### Cody (Sourcegraph)

Place `instructions.md` under `.cody/`:

```bash
cp "tools/cody/web/.cody/instructions.md" "/project/.cody/instructions.md"
```

Cody reads `.cody/instructions.md` automatically. Also supported: `.cody/instructions/` directory for multiple files.

## Features

| Feature | Description |
|---------|-------------|
| **4 Platforms** | Web, Mobile, Desktop, CLI — platform-specific checklists |
| **11 Tool Formats** | OpenCode, Claude Code, Cursor, Windsurf, GitHub Copilot, Aider, Continue, Codex CLI, Augment, PearAI, Cody |
| **Input Detection** | Auto-detects screenshot, code, Figma URL, or text description |
| **Supplementary Modules** | Data Visualization + Accessibility modules, auto-enabled when relevant |
| **Evaluation Guidelines** | Detailed rules for consistent, evidence-based findings |
| **6-Level Rating Scale** | Critical / Major / Minor / Good / Needs Manual Review / N/A |
| **Comparative Mode** | Side-by-side A/B evaluation |
| **Reference Library** | Detailed checklists with platform-specific notes in `references/` |

## References

Detailed reference files in `references/` provide deeper checklists with per-platform guidance. These are automatically referenced by the SKILL.md files during evaluation:

| File | Contents |
|------|----------|
| `references/nielsen-10-heuristics.md` | Detailed per-heuristic checklists with platform notes for Web, Mobile, Desktop, CLI |
| `references/data-viz-heuristics.md` | Data visualization module (DV-1 through DV-6) for charts, dashboards, KPIs |
| `references/accessibility-heuristics.md` | Accessibility module (A11Y-1 through A11Y-5) — always active, WCAG AA default |
| `references/severity-scale.md` | Full 6-level severity scale with assignment guidelines |

## 10 Heuristics

| # | Heuristic | Focus |
|---|-----------|-------|
| H1 | Visibility of System Status | Loading, feedback, notifications |
| H2 | Match System & Real World | User language, familiar icons |
| H3 | User Control & Freedom | Undo, cancel, back |
| H4 | Consistency & Standards | Consistent UI, platform conventions |
| H5 | Error Prevention | Validation, confirmation, auto-save |
| H6 | Recognition vs Recall | Visible navigation, search, history |
| H7 | Flexibility & Efficiency | Shortcuts, bulk actions, filters |
| H8 | Aesthetic & Minimalist | No clutter, whitespace, hierarchy |
| H9 | Error Recovery | Clear messages, fix suggestions |
| H10 | Help & Documentation | Empty states, tooltips, onboarding |

## Scoring

| Score | Meaning | Action |
|-------|---------|--------|
| ❌ Critical | Prevents task completion or causes serious data misunderstanding | Must fix before release |
| 🔴 Major | Significant friction or confusion | Should fix — high priority |
| ⚠️ Minor | Noticeable annoyance but users can complete task | Fix when possible |
| ✅ Good | Heuristic is well-handled | No action needed |
| 👁️ Manual Review | Cannot verify from provided input | Verify in live product |
| — N/A | Heuristic does not apply | No action needed |
