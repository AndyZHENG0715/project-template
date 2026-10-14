# Agent Instructions

This file follows the open [AGENTS.md](https://agents.md/) format and is the single entry point for agent rules in this project. Keep it short and specific; every rule should change what an agent does.

These rules reflect the best information available when they were written. If you find evidence that a rule is outdated or a better practice exists, tell the user and propose an update; do not ignore the rule or change it silently.

## Files

- `README.md`: what the project is, its long-term goals and how to use it. Written for humans.
- `AGENTS.md`: stable rules (this file).
- `HANDOFF.md`: current state only. Overwrite stale content; never turn it into a log. History lives in git and `CHANGELOG.md`.

## Session start

1. Read `README.md` and `HANDOFF.md`.
2. Compare the "Checked at" commit in `HANDOFF.md` with `git log` (or the date, in non-git projects). Read any later changes before trusting the handoff.
3. If documents and files disagree, follow [Drift](#drift).

## Before finishing

- When a task changed files or project state, update `HANDOFF.md`: state, recent changes, next steps and "Checked at". Record notable changes under `Unreleased` in `CHANGELOG.md` in the same commit.
- Purely informational replies need no update. Do not announce routine handoff updates.

## Drift

- Code and files are the default source of truth, but never revert a document or spec to match the code on your own. Ask the user which side is wrong.
- When the user changes a document or spec before the code, write "Spec ahead: <what changed>, code pending" under Next steps in `HANDOFF.md`. Treat such items as code that is behind, not as a wrong document.
- When a small change alters behavior that a spec describes, update that spec line in the same commit. No proposal is needed.

## Big features

- Small changes need no spec; `HANDOFF.md` is enough.
- A big feature (several days, many files, or a new subsystem) uses a spec-driven tool. The first time, research the best current option for this project, explain the choice and wait for approval, then record it under [Standards](#standards). Do not switch tools mid-project without approval.
- Before starting a new big feature, reconcile existing specs with the code first.
- When a feature is done, move lasting decisions into this file, or into an ADR under `docs/adr/` for major decisions.

## Boundaries

Always:

- Follow the standards below when they apply. If one does not fit, say so instead of inventing an ad-hoc format.
- Use ISO 8601 dates (`YYYY-MM-DD`), with the timezone when it matters.
- Fetch and inspect remote changes before editing when another agent may be pushing.

Ask first:

- Adding a dependency, deleting files, changing the spec tool or a pinned standard version, tagging a release, and anything external or hard to undo.

Never:

- Commit secrets, credentials, `.env` files or personal data such as ID numbers and phone numbers.
- Rewrite published git history.
- Revert a document or spec only because the code differs.

## Standards

Versions are pinned so upgrades are deliberate. Re-check the official page only when working in that area and "Last checked" is more than 3 months old; then update the date and tell the user what changed. Never switch versions silently.

| Area | Standard | Version | Last checked |
| --- | --- | --- | --- |
| Commit messages and PR titles | [Conventional Commits](https://www.conventionalcommits.org/) | 1.0.0 | 2026-10-14 |
| Version numbers | [Semantic Versioning](https://semver.org/) | 2.0.0 | 2026-10-14 |
| Changelog | [Keep a Changelog](https://keepachangelog.com/) | 1.1.0 | 2026-10-14 |
| Branching | [GitHub flow](https://docs.github.com/en/get-started/using-github/github-flow) | n/a | 2026-10-14 |
| Config and secrets | [12-Factor III](https://12factor.net/config): environment variables, commit `.env.example` only | n/a | 2026-10-14 |
| Spec-driven tool | Chosen at the first big feature | | |

Commits made by an AI agent carry a `Co-authored-by` trailer naming the agent when the tool supports it.

## Project-specific rules

<!-- Add only rules this project needs. Keep them short and verifiable. -->

<!-- BOOTSTRAP START -->
## Bootstrap (one-time)

Template last reviewed: 2026-10-14. If that is more than 6 months ago, tell the user the template is due for a review before continuing.

When this template is applied to a new or existing project:

1. Establish the real project root and read existing documents and agent instructions. Keep what is useful.
2. Rewrite `README.md` for this project: what it is, why it exists, how to use it. Do not invent unknown details; mark them `TODO` for the user. For software, use the [Standard Readme](https://github.com/RichardLitt/standard-readme) sections that apply.
3. Fill `HANDOFF.md` from current evidence.
4. Draft project-specific rules: minimal, only what the user stated or the project clearly needs. Adapt proven examples rather than generating from scratch. Show the draft to the user for review.
5. Non-git projects (study, documents): drop the git-only parts (commit checkpoint, `CHANGELOG.md`, SemVer, Conventional Commits, `.gitattributes`) and use dates in `HANDOFF.md`.
6. Delete this Bootstrap section, including its markers.
<!-- BOOTSTRAP END -->
