OpenCode Agents Repository
==========================

This repository contains Markdown agent definition files for OpenCode.
OpenCode reads these files and exposes them as specialized agents that can be delegated to during coding sessions.

What This Repo Contains
-----------------------

- `architect.md` for high-level software architecture guidance
- `code-architect.md` for implementation planning and codebase-aware design
- `code-simplifier.md` for simplifying and refining existing code
- `cpp-reviewer.md` for C++ code review
- `numpy-autist.md` for NumPy refactoring and vectorization guidance
- `rust-reviewer.md` for Rust code review

How OpenCode Uses These Files
-----------------------------

- Reads agent definition files from the configured agents directory
- Uses YAML frontmatter such as `description` to summarize each agent
- Treats the Markdown body as the agent's role, process, and operating instructions
- Makes each file available as a named agent based on its filename

Recommended Use
---------------

- Keep this repo, or a symlink to it, under `~/.config/opencode/agents/`
- Add new agents as focused `.md` files with clear descriptions
- Delegate work to the most specific agent for the task

Example:

  ln -s /path/to/this/repo ~/.config/opencode/agents

Agent Design Conventions In This Repo
-------------------------------------

- Keep each agent focused on one specialist role
- Put the most important operating rules near the top of the file
- Prefer concrete review or implementation workflows over vague advice
- Avoid duplicating broad OpenCode behavior unless the agent needs stricter guidance
- Keep frontmatter minimal and useful for discovery

Current Structure
-----------------

- Architecture guidance lives in `architect.md` and `code-architect.md`
- Refactoring guidance lives in `code-simplifier.md` and `numpy-autist.md`
- Language-specific review guidance lives in `cpp-reviewer.md` and `rust-reviewer.md`

Notes
-----

- Agent files are plain Markdown with optional YAML frontmatter
- Filenames determine the agent names shown to OpenCode
- Short, precise agent descriptions make delegation easier

References
----------

- https://github.com/VoltAgent/awesome-claude-code-subagents
- https://github.com/affaan-m/everything-claude-code/tree/main/agents
- https://github.com/msitarzewski/agency-agents
