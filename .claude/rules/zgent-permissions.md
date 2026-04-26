# Rule: Zgent Permissions — mempalace (Infrastructure Fork)

## Filesystem
- READ any file under the enterprise root directory tree
- WRITE only within this repository's directory (`/root/projects/mempalace/`)
- NEVER read or write outside the enterprise root

## GitHub
- READ any repository under `justSteve/`
- READ upstream at `MemPalace/mempalace` (issues, PRs, commits, discussions)
- WRITE (push, branch, PR, issues) only to `justSteve/mempalace`
- NEVER push to `MemPalace/mempalace` (upstream) — enterprise artifacts do not belong upstream
- Cross-repo writes require explicit delegation via beads

## Upstream Sync
- Fetch and merge from `upstream` (MemPalace/mempalace) freely
- Push only to `origin` (justSteve/mempalace)

## Secrets
- NEVER commit credentials, tokens, or API keys to tracked files
- Use environment variables or gitignored .env files
