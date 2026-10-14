# project-template

A small, tool-agnostic starting point for projects worked on with AI agents (Claude, Codex, ChatGPT and others). It keeps three files in sync so any agent, in any tool, can pick up where the last one stopped.

Last full review: 2026-10-14

## What is inside

| File | Purpose |
| --- | --- |
| `AGENTS.md` | Stable rules for agents, pinned standards, and a one-time bootstrap section |
| `HANDOFF.md` | Current state only: goals, state, recent changes, next steps, open questions |
| `CHANGELOG.md` | Notable changes ([Keep a Changelog](https://keepachangelog.com/)) |
| `.gitattributes`, `.editorconfig`, `.gitignore` | LF line endings, default formatting, and ignore patterns for common secret and scratch files (a convenience; agents still check each diff) |

## Usage

New project:

1. On GitHub, choose **Use this template** and create the repository.
2. Open it with any agent and say: "Apply the bootstrap section in AGENTS.md."
3. Review the project-specific rules the agent drafts.

Existing project: do not copy files over existing ones. Tell the agent:

```
Read AGENTS.md first. Then merge https://github.com/AndyZHENG0715/project-template into this project by applying its AGENTS.md bootstrap section. Keep existing docs and conventions.
```

Non-git project (study notes, documents): same prompt. The bootstrap drops the git-only parts and uses date and time instead of commits.

Tools that do not load `AGENTS.md` automatically: start each session with "Read AGENTS.md first", or add a one-line tool-specific file that points to it.

## Design choices

These are choices made on 2026-10-14 from the information available then, not settled truths. AI tooling changes fast: if newer evidence suggests a better option, propose the change to the user instead of following these blindly. Each full review re-examines this list.

- **No separate TODO file.** "Next steps" in `HANDOFF.md` is the task list.
- **Handoff is overwritten, not appended.** History belongs in git and `CHANGELOG.md`, so the handoff stays short and current.
- **No spec tool by default.** Small changes need no spec. A plan or spec is required only when a change involves design decisions, dependent steps or is hard to undo, and its format is chosen from what is best at that time.
- **Standards are defaults.** Existing project conventions win over template defaults.
- **Pinned standard versions with a "last checked" date.** Agents re-check only when they work in that area and the date is over 3 months old, and report changes instead of switching silently.
- **Boundaries as Always / Ask first / Never**, following GitHub's [analysis of 2,500+ agents.md files](https://github.blog/ai-and-ml/github-copilot/how-to-write-a-great-agents-md-lessons-from-over-2500-repositories/).
- **Minimal, reviewed rules.** Research on AGENTS.md files ([Gloaguen et al., 2026](https://arxiv.org/abs/2602.11988)) found that generated context files add cost without helping, so the bootstrap drafts few rules for the user to review.

## Maintaining this template

Review the whole template, including every design choice above, when "Last full review" is more than 6 months old. Agents applying the bootstrap remind the user when it is due. Record changes in `CHANGELOG.md`.
