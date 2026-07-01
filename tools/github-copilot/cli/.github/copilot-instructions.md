---
scope: '**/*.{sh,py,rs,go,zig,js}'
---

# Skill: usability-heuristics-cli

# Usability Heuristics Evaluation — CLI / TUI

Evaluates a command-line interface or terminal UI application against [Jakob Nielsen's 10 Usability Heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/). The agent inspects every command, flag, subcommand, TUI screen, and output format, scoring each heuristic and producing a structured report.

## When to use

- Before releasing a CLI tool or TUI application.
- After adding new commands or flags.
- For developer tools, build scripts, or terminal-based applications.
- When designing CLI DX (Developer Experience).

## When NOT to use

- For GUI applications of any kind (use web/mobile/desktop variants).
- For visual UI design evaluation.

## Heuristics

Scoring: ✅ Pass | ⚠️ Minor | 🔴 Major | ❌ Critical

---

### H1 — Visibility of System Status

**Checklist:**
- [ ] Spinner / progress bar for long-running operations
- [ ] `--verbose` / `--debug` flag provides detailed progress
- [ ] Exit code is set correctly (0 for success, non-zero for error)
- [ ] Subcommand completion message on success
- [ ] Real-time output for streaming operations (tail, watch)
- [ ] Estimated time remaining for very long operations
- [ ] "Working..." indicator when output is delayed
- [ ] Current step displayed in multi-step processes

---

### H2 — Match Between System and the Real World

**Checklist:**
- [ ] Command and flag names use familiar terms (not internal jargon)
- [ ] `--help` uses plain language, not developer jargon
- [ ] Error messages are human-readable, not stack traces
- [ ] Output formatting follows conventions (JSON, table, plain text)
- [ ] Short flag conventions followed (`-v` for verbose, `-h` for help)
- [ ] Arguments use standard naming patterns
- [ ] Yes/no prompts use `[y/N]` or `[Y/n]` conventions

---

### H3 — User Control and Freedom

**Checklist:**
- [ ] `Ctrl+C` gracefully interrupts long operations
- [ ] Confirmation prompt before destructive operations ("Are you sure?")
- [ ] `--dry-run` flag to preview without side effects
- [ ] `--yes` / `-y` to skip confirmation (non-interactive mode)
- [ ] `--undo` or rollback capability for state-changing commands
- [ ] Ability to cancel multi-step wizards with `Ctrl+C` or `q`
- [ ] Shell tab-completion does not auto-execute destructive actions

---

### H4 — Consistency and Standards

**Checklist:**
- [ ] All subcommands use same flag style (`--flag` vs `-flag` consistently)
- [ ] `--help` and `--version` exist on every command
- [ ] Output format is consistent across subcommands (same columns, same order)
- [ ] Naming conventions follow POSIX/GNU standards
- [ ] Exit codes follow conventions (0=success, 1=general error, 2=misuse)
- [ ] Color coding consistent (red=error, yellow=warning, green=success)
- [ ] Tab completion follows same pattern across all subcommands
- [ ] Error output goes to stderr, normal output to stdout

---

### H5 — Error Prevention

**Checklist:**
- [ ] Argument validation before execution (missing required args caught early)
- [ ] Type validation for arguments (number vs string)
- [ ] File validation before processing (file exists, is readable)
- [ ] Confirmation before destructive actions (overwrite, delete, reset)
- [ ] Auto-save config before applying changes
- [ ] Input sanitization to prevent injection
- [ ] Mutex/lock to prevent concurrent destructive operations
- [ ] Dry-run mode to preview changes before applying

---

### H6 — Recognition Rather Than Recall

**Checklist:**
- [ ] `--help` output lists all flags with descriptions
- [ ] Tab completion available for commands, subcommands, flags, and arguments
- [ ] Usage examples in `--help` output
- [ ] Default values shown in `--help`
- [ ] Shell prompt integration (e.g., shows current context)
- [ ] History of recent commands available (shell history)
- [ ] `--list` or `ls` subcommand to enumerate available options
- [ ] Aliases for commonly used commands

---

### H7 — Flexibility and Efficiency of Use

**Checklist:**
- [ ] Short flags for common options (`-v`, `-q`, `-f`)
- [ ] Piping output to other commands works (stdout/stderr separation)
- [ ] Output format flags (`--json`, `--yaml`, `--table`, `--plain`)
- [ ] `--quiet` / `--silent` for script usage
- [ ] Configuration file support (`.rc` file or `--config`)
- [ ] Environment variable support for flags
- [ ] Batch processing mode (file glob, stdin input)
- [ ] Shell completions (bash, zsh, fish)
- [ ] Man page generation from `--help`

---

### H8 — Aesthetic and Minimalist Design

**Checklist:**
- [ ] `--help` is not overly long or cluttered (grouped, sectioned)
- [ ] Default output shows only essential information
- [ ] `--verbose` adds detail for those who need it
- [ ] No redundant output (no duplicate log lines)
- [ ] Output is well-formatted (aligned columns, no orphaned text)
- [ ] Error output is concise and actionable
- [ ] Progress output can be suppressed (`--quiet`)
- [ ] Color is used sparingly and meaningfully

---

### H9 — Help Users Recognize, Diagnose, and Recover from Errors

**Checklist:**
- [ ] Error messages are in plain language (no raw stack traces)
- [ ] Error message identifies the exact problem and suggests a fix
- [ ] Invalid flags show closest match ("did you mean --recursive?")
- [ ] Validation errors point to the specific argument
- [ ] Network errors show retry suggestion
- [ ] Error messages go to stderr, not stdout
- [ ] `--help` is suggested when invalid usage is detected
- [ ] Exit code distinguishes error types (documented)

---

### H10 — Help and Documentation

**Checklist:**
- [ ] `--help` output exists and is comprehensive
- [ ] Man page (`man <tool>`) is available
- [ ] `--help` includes usage examples
- [ ] Online documentation is linked in `--help` or man page
- [ ] Error messages can include "See --help for more info"
- [ ] Tutorial / README exists for first-time users
- [ ] Shell completions are documented
- [ ] Changelog / version history accessible (`--version`)

---

## Execution

1. **Discover all commands/surfaces.** Run `<tool> --help` recursively for all subcommands. List every TUI screen, wizard, interactive prompt, and config file.

2. **For each command/surface**, evaluate all 10 heuristics. Test with `--help`, `--dry-run`, error scenarios, and piping output.

3. **Score each heuristic per command/surface** (✅ / ⚠️ / 🔴 / ❌).

4. **Produce a report** with summary table, per-command breakdown, top issues, and recommendations.

## Report Format

```
# Usability Heuristic Evaluation — [Tool Name] (CLI)

## Summary

| Severity    | Count |
|-------------|-------|
| ✅ Pass     | XX    |
| ⚠️ Minor    | XX    |
| 🔴 Major    | XX    |
| ❌ Critical | XX    |

## Per-Command Results

### `deploy init`
| Heuristic | Score | Finding |
|-----------|-------|---------|
| H1 Visibility | ✅ | Progress spinner shown during init |
| H2 Real world | ⚠️ | Flag `--cfg` should be `--config` |
| ... | | |

## Top 5 Issues
...

## Recommendations by Heuristic
```
