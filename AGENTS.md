# AGENTS.md â€” freellmapi

## Project

**freellmapi** â€” aggregates free-tier LLM providers into one OpenAI-compatible
endpoint (server, client, cli, and a desktop app). npm-workspaces monorepo.

## Scope

- In scope: `shared/`, `server/`, `client/`, `cli/` workspaces; `desktop/` (own
  lockfile, outside workspaces); provider adapters and the OpenAI-compatible API
- Out of scope: upstream provider implementations, hosted deployment config

## Setup

```bash
# Clone and enter
git clone https://github.com/hummbl-dev/freellmapi.git
cd freellmapi
npm install
```

## Testing

```bash
npm test   # bootstrap + hooks node --test, then per-workspace tests
```

### Python baseline (gap-8 fleet-wide standard)

If this repo contains Python, the fleet-wide baseline applies:

```bash
ruff check .          # lint
mypy .                # type check
pytest tests/ -v      # tests
```

Config files: `ruff.toml`, `mypy.ini`. CI runs these as advisory (Phase 1);
they will become required (Phase 2) after fleet cleanup.

## Conventions

- Commit format: Conventional Commits
- Branch naming: `type/agent/short-desc`
- License: Apache 2.0
- `.gitattributes` is required â€” the canonical fleet version normalizes text files to LF and marks binary types. Without it, Windows clones accumulate CRLF noise that pollutes diffs, blocks hooks, and creates phantom merge conflicts. Do not remove or weaken it.
- AI agents may assist with research, review, patch preparation, and operational coordination, but must not be credited in Git commit authorship metadata or commit-message trailers. Do not add `Co-authored-by`, `Generated-by`, `Authored-with`, or equivalent AI/vendor/agent attribution to commits. Agent activity belongs in internal receipts, bus messages, handoffs, or PR notes, not commit credit.

## Pre-PR-creation checklist

Before creating a PR branch, always:

1. **Fetch latest**: `git fetch origin` to ensure local refs are current
2. **Rebase on target**: `git rebase origin/main` so the PR branch starts from the latest commit
3. **Verify merge-base**: `git merge-base HEAD origin/main` should return the same SHA as `git rev-parse origin/main`
4. **Run pre-push CI check** (if available)
5. **Run local tests** (if available)

## CI

- `CI` (`.github/workflows/ci.yml`): build/test on push to `main` and PRs
- `Docker` (`.github/workflows/docker.yml`): image build
- `Security Scan` (`.github/workflows/security-scan.yml`): Gitleaks on the
  pushed/PR commit range plus `npm audit` reports (root `--omit=dev`, and the
  `desktop/` lockfile in full)
