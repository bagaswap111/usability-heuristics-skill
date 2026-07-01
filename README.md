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
# Load it in your opencode.json or via the skill command:
skill load usability-heuristics
```

Copy: `cp web/SKILL.md /project/.opencode/skills/usability-heuristics/SKILL.md`

---

### Claude Code

Place `CLAUDE.md` at your project root:

```bash
cp tools/claude-code/web/CLAUDE.md /project/CLAUDE.md
```

Claude Code reads `CLAUDE.md` automatically — no config needed. Supported locations (highest priority first):
1. `{project}/CLAUDE.md`
2. `{project}/.claude/CLAUDE.md`
3. `~/CLAUDE.md` (global, all projects)

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

| Score | Meaning |
|-------|---------|
| ✅ Pass | No issues |
| ⚠️ Minor | Non-critical, low impact |
| 🔴 Major | Significant barrier |
| ❌ Critical | Blocks task completion |
