# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project status

This is a new project. Technical stack, build/lint/test commands, and architecture have not been decided yet. This section should be filled in once the stack is chosen — commands for build/lint/test/dev-server, and a high-level description of the architecture (major modules, how they interact, key data flow) that isn't obvious from a single file.

## Git workflow rules

- **Push to GitHub after every code change.** After making a change and confirming it works (build/tests pass as applicable), commit it and push to the remote right away — do not batch up multiple unrelated changes into one push.
- Use clear, descriptive commit messages that explain why the change was made, not just what changed.
- Do not force-push, rewrite history, or skip commit hooks (`--no-verify`) unless explicitly instructed.
- A GitHub remote has not been configured yet. Once one is added, this rule takes effect immediately — confirm the push actually reaches the remote (e.g. `git push` output, `git log origin/<branch>..<branch>`) rather than assuming it succeeded.
