# OpenCode Agents

A focused collection of Markdown agent definitions for [OpenCode](https://opencode.ai/). Each file in this repository defines a specialist agent that can be delegated to during coding sessions for architecture, review, refactoring, and numerical Python work.

## What's Included

| Agent | Purpose |
| --- | --- |
| `code-architect` | Designs feature architectures by studying existing codebase patterns first. |
| `code-simplifier` | Simplifies and refines code while preserving behavior. |
| `cpp-reviewer` | Reviews C++ changes for memory safety, undefined behavior, concurrency, and performance. |
| `js-reviewer` | Reviews JavaScript and TypeScript changes for correctness, security, async behavior, typing, and tests. |
| `numpy-autist` | Refactors NumPy code toward fast, shape-safe, vectorized array operations. |
| `python-reviewer` | Reviews Python changes for correctness, security, typing, async behavior, and maintainability. |
| `rust-reviewer` | Reviews Rust changes for ownership, lifetimes, unsafe usage, error handling, and idiomatic patterns. |

## Repository Structure

```text
.
├── README.md
└── agents/
    ├── code-architect.md
    ├── code-simplifier.md
    ├── cpp-reviewer.md
    ├── js-reviewer.md
    ├── numpy-autist.md
    ├── python-reviewer.md
    └── rust-reviewer.md
```

## Installation

Install agents with [`oc-agent`](https://www.npmjs.com/package/oc-agent), a zero-dependency `npx` CLI for installing and managing OpenCode agent `.md` files.

This repository contains multiple agents, so choose the agent you want with `--agent`:

```bash
npx oc-agent add https://git.woldtech.nl/CrucifiedMidget/opencode-agents.git --agent python-reviewer
```

Install globally with `-g`:

```bash
npx oc-agent add https://git.woldtech.nl/CrucifiedMidget/opencode-agents.git --agent python-reviewer -g
```

Use `-y` for non-interactive installs in scripts or CI:

```bash
npx oc-agent add https://git.woldtech.nl/CrucifiedMidget/opencode-agents.git --agent python-reviewer -g -y
```

## Managing Agents

`oc-agent` tracks installed agents in `oc-agent-manifest.json`, which allows reliable updates and removals.

```bash
npx oc-agent list
npx oc-agent update python-reviewer
npx oc-agent remove python-reviewer
```

Use `-g` with each command when managing globally installed agents:

```bash
npx oc-agent list -g
npx oc-agent update python-reviewer -g
npx oc-agent remove python-reviewer -g
```

| Scope | Path |
| --- | --- |
| Project | `./.opencode/agents/` |
| Global | `~/.config/opencode/agents/` |
