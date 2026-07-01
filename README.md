# Usability Heuristics Evaluation Skill

Evaluasi UI/UX berbasis [10 Heuristics Nielsen](https://www.nngroup.com/articles/ten-usability-heuristics/) — tersedia untuk **4 platform** dalam **11 format AI coding tools**.

## Platform

| Platform | Folder | Target |
|----------|--------|--------|
| Web | `web/` | Website, web app, dashboard |
| Mobile | `mobile/` | iOS, Android, cross-platform apps |
| Desktop | `desktop/` | macOS, Windows, Linux apps |
| CLI | `cli/` | CLI tools, TUI, terminal apps |

## Tool Format

Setiap platform punya varian untuk tiap tool AI:

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

## Cara Pakai

1. Pilih **platform** yang sesuai (web/mobile/desktop/cli)
2. Pilih **tool** yang kamu pakai
3. Copy file dari folder `tools/{tool}/{platform}/` ke root project kamu
4. Agent AI akan otomatis membaca aturan evaluasi usability

Contoh — pakai Claude Code untuk evaluasi web app:

```bash
cp tools/claude-code/web/CLAUDE.md /path/to/project/CLAUDE.md
```

## 10 Heuristics

| # | Heuristic | Fokus |
|---|-----------|-------|
| H1 | Visibility of System Status | Loading, feedback, notifikasi |
| H2 | Match System & Real World | Bahasa user, ikon familiar |
| H3 | User Control & Freedom | Undo, cancel, back |
| H4 | Consistency & Standards | UI konsisten, ikuti platform |
| H5 | Error Prevention | Validasi, konfirmasi, auto-save |
| H6 | Recognition vs Recall | Navigasi visible, search, history |
| H7 | Flexibility & Efficiency | Shortcut, bulk action, filter |
| H8 | Aesthetic & Minimalist | No clutter, whitespace, hierarki |
| H9 | Error Recovery | Pesan jelas, saran perbaikan |
| H10 | Help & Documentation | Empty state, tooltip, onboarding |

## Scoring

| Score | Arti |
|-------|------|
| ✅ Pass | No issues |
| ⚠️ Minor | Non-critical, low impact |
| 🔴 Major | Significant barrier |
| ❌ Critical | Blocks task completion |
