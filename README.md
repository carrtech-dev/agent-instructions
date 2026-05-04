# Agent Instructions

This repository is the source of truth for Carrtech agent instructions.

Downstream repositories should keep a generated copy of `AGENTS.md` at the repo
root so coding agents can read the full instructions locally. Do not replace
downstream `AGENTS.md` files with links or stubs; some agents do not follow
remote references when loading repo instructions.

Update `AGENTS.md` here first, then sync the full file into each repository.

## Downstream Sync

Changes to `AGENTS.md` on `main` run the `Sync AGENTS.md` workflow. The workflow
opens pull requests against the repositories listed in `sync-targets.txt`,
replacing each root `AGENTS.md` with the shared file plus a generated-file
header.

The downstream file is always written to the repository root as `AGENTS.md`.
That is the location coding agents expect to discover automatically when they
start work in a repository, without needing to be reminded in each prompt.

The workflow requires a repository secret named `AGENTS_SYNC_TOKEN`. The token
must have permission to create branches, push commits, and open pull requests in
each target repository.
