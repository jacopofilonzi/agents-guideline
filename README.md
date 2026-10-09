# Agent guidelines

My personal guidelines for AI coding agents (Claude Code, Codex, …), as a template to drop into any project.

| File | Content |
| --- | --- |
| [`AGENTS.md`](AGENTS.md) | How to work in the repo: workflow, commits, code style, testing, releases, invariants and pitfalls. The generic sections are my default style; the `<PLACEHOLDER>` sections are filled in per project. |
| [`STRUCTURE.md`](STRUCTURE.md) | What lives where: folder tree, API, data, configuration. Filled in once the structure is agreed on, then kept up to date as the project changes. |
| [`CLAUDE.md`](CLAUDE.md) | Only imports the other two (`@AGENTS.md`, `@STRUCTURE.md`), so Claude Code always loads them. |

## Use it in a project

Run this from the project root. It downloads the three files into the current folder:

```sh
curl -fsSL --remote-name-all "https://raw.githubusercontent.com/jacopofilonzi/agent-guidelines/main/{AGENTS,CLAUDE,STRUCTURE}.md"
```

On Windows PowerShell write `curl.exe` instead of `curl` (in Windows PowerShell 5.1 `curl` is an alias for `Invoke-WebRequest`). Keep the quotes: curl expands the `{…}` itself.

The command **overwrites** existing files with the same name. To keep them and save the downloads as `AGENTS.md.1`, … instead, add `--no-clobber`.

Then:

1. Fill in the `<PLACEHOLDER>` sections of `AGENTS.md` and delete the ones that don't apply (UI, versions, recipes…).
2. Fill in `STRUCTURE.md` once the structure has been discussed, or let the agent write it from the code.
3. Delete the template comments (`<!-- … -->`).

The files must stay in the project root: Claude Code and other agents only pick up `CLAUDE.md` / `AGENTS.md` from there.
