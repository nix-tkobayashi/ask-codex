# ask-codex

> A problem shared is a problem halved.

A simple skill that guides Claude to collaborate with OpenAI Codex to solve problems.

## Install

```bash
npx skills add nix-tkobayashi/ask-codex
```

Then use `/ask-codex` in Claude Code.

### Prerequisites

- [OpenAI Codex CLI](https://github.com/openai/codex) installed and available in your PATH

## Usage

In Claude Code, use any of these triggers:

- `/ask-codex`
- "ask codex"
- "get codex opinion"
- "second opinion"

Claude will spawn a `codex exec` process, pass your question, and return the response.

## How it works

The skill runs Codex non-interactively:

```bash
codex exec --skip-git-repo-check "<prompt>"
```

## License

MIT
