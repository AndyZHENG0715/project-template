# project-template

A small, tool-agnostic starting point for projects worked on with AI agents, in any tool. It keeps three files in sync so any agent, in any tool, can pick up where the last one stopped.

Last full review: 2026-10-14

## What is inside

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Stable rules for agents, pinned standards, and a one-time bootstrap section |
| `HANDOFF.md` | Current state only: goals, state, recent changes, next steps, open questions |
| `CHANGELOG.md` | Notable changes ([Keep a Changelog](https://keepachangelog.com/)) |
| `.gitattributes`, `.editorconfig`, `.gitignore` | LF line endings, default formatting, and ignore patterns for common secret and scratch files (a convenience; agents still check each diff) |

## Usage

For a new or existing project, give your agent this prompt:

```
Apply the template at https://github.com/AndyZHENG0715/project-template to this project by following the Bootstrap section in its AGENTS.md. Merge with existing files; never overwrite them.
```

The agent shows you the merged files and draft rules before finishing. Review them.

If your tool does not load `AGENTS.md` automatically, start each session with "Read AGENTS.md first", or add a one-line tool-specific file that points to it.

Keep your tool's sandbox and approval settings on. Written rules guide an agent; they do not stop one.

## Design choices

These choices were made on 2026-10-14 from the information available then. AI tooling changes fast, so each full review re-examines this list.

- **No separate TODO file.** "Next steps" in `HANDOFF.md` is the task list.
- **Handoff is overwritten, not appended.** History belongs in git and `CHANGELOG.md`, so the handoff stays short and current.
- **No spec tool by default.** Small changes need no spec. A plan or spec is required only when a change involves design decisions, dependent steps or is hard to undo, and its format is chosen from what is best at that time.
- **Standards are defaults.** Existing project conventions win over template defaults.
- **Pinned standard versions with a "last checked" date.** Agents re-check a standard only when they work in that area: every 12 months for stable specs, every 3 months for fast-moving agent tooling. They report changes instead of switching silently.
- **Non-git projects keep a decision log** in `README.md` instead of ADRs.
- **Boundaries as Always / Ask first / Never**, following GitHub's [analysis of 2,500+ agents.md files](https://github.blog/ai-and-ml/github-copilot/how-to-write-a-great-agents-md-lessons-from-over-2500-repositories/).
- **Minimal, reviewed rules.** Research on AGENTS.md files ([Gloaguen et al., 2026](https://arxiv.org/abs/2602.11988)) found that generated context files add cost without helping, so the bootstrap drafts few rules for the user to review.

## Maintaining this template

Review the whole template, including every design choice above, when "Last full review" is more than 6 months old. Agents applying the bootstrap remind the user when it is due. Record changes in `CHANGELOG.md`.
