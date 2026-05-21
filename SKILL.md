---
name: ask-codex
description: Asks Codex CLI for coding assistance. Use for getting a second opinion, code generation, debugging, or delegating coding tasks.
allowed-tools: Bash(codex *), Bash(npm *)
---

# Ask Codex

Executes the local `codex` CLI to get coding assistance.

**Note:** This skill requires the `codex` CLI to be installed and available in your system's PATH.

## 必須ルール

- **`--skip-git-repo-check` を常に付ける** — Claude Code から呼び出す場合、カレントディレクトリが Codex の trusted directory に登録されていないため「Not inside a trusted directory」エラーになる
- **`-m` オプションは付けない** — v0.132.0 以降はデフォルトが `gpt-5.5` になり、ChatGPT アカウント認証で正常に動作する

## Quick start

```bash
codex exec --skip-git-repo-check "Your question or task here"
```

## Common options

| Option | Description |
|--------|-------------|
| `-C DIR` | Set working directory |
| `--full-auto` | Enable automatic execution with workspace-write sandbox |

> For all available options, run `codex exec --help`

## Examples

**Ask a coding question:**

```bash
codex exec --skip-git-repo-check "How do I implement a binary search in Python?"
```

**Analyze code in a specific directory:**

```bash
codex exec --skip-git-repo-check -C /path/to/project "Explain the architecture of this codebase"
```

**Let Codex make changes automatically:**

```bash
codex exec --skip-git-repo-check --full-auto "Add error handling to all API endpoints"
```

## Notes

- Codex runs non-interactively with `exec` subcommand
- By default, output goes to stdout and no files are modified without approval
- Use `--full-auto` for automatic execution within sandbox constraints
- The command inherits the current working directory unless `-C` is specified
