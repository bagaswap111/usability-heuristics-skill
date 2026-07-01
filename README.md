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

## Usage

1. Choose the **platform** (web/mobile/desktop/cli)
2. Choose your **tool**
3. Copy the file from `tools/{tool}/{platform}/` to your project root
4. The AI agent will automatically read the usability evaluation rules

Example — using Claude Code for a web app evaluation:

```bash
cp tools/claude-code/web/CLAUDE.md /path/to/project/CLAUDE.md
```

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
