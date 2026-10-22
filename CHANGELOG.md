# Changelog

All notable changes to this template are documented here.
The format follows [Keep a Changelog 1.1.0](https://keepachangelog.com/en/1.1.0/), and versions follow [SemVer 2.0.0](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

- `AGENTS.md` in the open AGENTS.md format, with rules for session start, finishing a task, drift between documents and files, larger changes, and concurrent agents.
- Boundaries as Always / Ask first / Never: atomic commits, diff checks for secrets, approval for dependencies, destructive commands, outward-facing actions, history rewrites and checks with effects beyond the local machine, reporting of blockers instead of claiming completion, and a prompt-injection boundary that keeps documented project commands usable.
- Pinned standards (Conventional Commits, SemVer, Keep a Changelog, GitHub flow, 12-Factor III, AGENTS.md) with "Last checked" and "Re-check every" columns; existing project conventions take precedence.
- Agents add a `Co-authored-by` trailer when their tool does not.
- Rule for writing step-by-step docs: goal and reasons first, fact and safety steps stated as required, other steps written as conditions for when they apply.
- Template section linking each project back to the template commit it was applied from.
- One-time bootstrap section that merges rules into existing projects without copying the template's own text, records setup, run and check commands for software, handles non-git projects with a decision log, and waits for user approval before deleting itself.
- `HANDOFF.md` skeleton: goals, state, verification, recent changes, next steps, open questions, and an "Updated" time. The last commit that changed it marks what it covers, so no commit hash is written by hand.
- `README.md` with a copyable bootstrap prompt, design choices, and a full review every 6 months or when switching to a new generation of main model.
- `.gitattributes` (LF), `.editorconfig` and `.gitignore`.
- MIT license.
