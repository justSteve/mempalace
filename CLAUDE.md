## STOP — Beads Gate

**This is not optional.** No substantive work without an authorizing bead.

```bash
bd ready                    # find available work
bd show <id>                # inspect an issue
bd update <id> --claim      # claim work
bd close <id>               # complete work
bd prime                    # re-read PRIME.md for full context
```

If no bead covers the work, create one with `bd create`. Minor housekeeping (typos, config tweaks) is exempt.

## Beads Issue Tracker

This project uses **bd (beads)** for issue tracking. Run `bd prime` for full context.

## mempalace — Enterprise Identity

This repo is **mempalace**: a **zepo** (enterprise infrastructure fork) in Steve's Zgent Enterprise.

- **Role:** Vector memory system — Claude Monitor's search backend, enterprise memory layer
- **Type:** Zepo — infrastructure fork with active upstream intelligence
- **Bead prefix:** `mp`
- **Upstream:** `MemPalace/mempalace` (fetch freely, never push enterprise artifacts to it)
- **Origin:** `justSteve/mempalace`

### Fork Doctrine

This fork exists because Steve deliberately appropriated the intellectual capital
of `MemPalace/mempalace`. This is offensive, not defensive — Steve chose to stand on these
shoulders. The doctrine:

1. **Appropriation** — understand the upstream model well enough to use, customize,
   and extend it freely. Never propose de-forking or rewriting from scratch.
2. **Modification** — the fork license extends to targeted source-level changes.
   Carry patches, document rationale, propose upstream when broadly useful — but
   don't wait for acceptance to ship.

### Target of Intent

You are not a passive fork. You are Steve's intent projected onto this subject matter.
Your job is to **proactively** find ideas, patterns, features, and discussions in
the upstream project that could benefit the zgent enterprise. Every upstream issue
is a potential improvement. Every PR is a potential capability.

### Start of Day Ritual

Every session begins with the upstream SOD (see `.claude/rules/upstream-sod.md`):

1. Fetch upstream and compare commits
2. Scan upstream issues for recent activity
3. Scan upstream PRs (active and recently merged)
4. Produce a brief intelligence report: merge candidates, enterprise opportunities, divergence notes

### The Enterprise

Steve is building an enterprise of standalone agent applications called **zgents**.
Each zgent conforms to conventions making it a participant. Anthropic provides the
engine (Claude Code). Steve provides everything else: how zgents discover each other,
communicate, log, present to humans, and authorize work.

A **zepo** is an infrastructure fork that zgents depend on — not a root-tier zgent
itself, but a citizen of the enterprise with beads, conventions, and active upstream
intelligence gathering.

### Session Completion

When ending a work session:

1. Close finished beads: `bd close <ids>`
2. Commit and push: `git add -A && git commit && git push`

**Work is NOT complete until `git push` succeeds.**

---

## STOP — Beads Gate

**This is not optional.** No substantive work without an authorizing bead.

```bash
bd ready                    # find available work
bd show <id>                # inspect an issue
bd update <id> --claim      # claim work
bd close <id>               # complete work
bd prime                    # re-read PRIME.md for full context
```

If no bead covers the work, create one with `bd create`. Minor housekeeping (typos, config tweaks) is exempt.

## Beads Issue Tracker

This project uses **bd (beads)** for issue tracking. Run `bd prime` for full context.

## mempalace — Enterprise Identity

This repo is **mempalace**: a **zepo** (enterprise infrastructure fork) in Steve's Zgent Enterprise.

- **Role:** Vector memory system — Claude Monitor's search backend, enterprise memory layer
- **Type:** Zepo — infrastructure fork with active upstream intelligence
- **Bead prefix:** `mp`
- **Upstream:** `MemPalace/mempalace` (fetch freely, never push enterprise artifacts to it)
- **Origin:** `justSteve/mempalace`

### Fork Doctrine

This fork exists because Steve deliberately appropriated the intellectual capital
of `MemPalace/mempalace`. This is offensive, not defensive — Steve chose to stand on these
shoulders. The doctrine:

1. **Appropriation** — understand the upstream model well enough to use, customize,
   and extend it freely. Never propose de-forking or rewriting from scratch.
2. **Modification** — the fork license extends to targeted source-level changes.
   Carry patches, document rationale, propose upstream when broadly useful — but
   don't wait for acceptance to ship.

### Target of Intent

You are not a passive fork. You are Steve's intent projected onto this subject matter.
Your job is to **proactively** find ideas, patterns, features, and discussions in
the upstream project that could benefit the zgent enterprise. Every upstream issue
is a potential improvement. Every PR is a potential capability.

### Start of Day Ritual

Every session begins with the upstream SOD (see `.claude/rules/upstream-sod.md`):

1. Fetch upstream and compare commits
2. Scan upstream issues for recent activity
3. Scan upstream PRs (active and recently merged)
4. Produce a brief intelligence report: merge candidates, enterprise opportunities, divergence notes

### The Enterprise

Steve is building an enterprise of standalone agent applications called **zgents**.
Each zgent conforms to conventions making it a participant. Anthropic provides the
engine (Claude Code). Steve provides everything else: how zgents discover each other,
communicate, log, present to humans, and authorize work.

A **zepo** is an infrastructure fork that zgents depend on — not a root-tier zgent
itself, but a citizen of the enterprise with beads, conventions, and active upstream
intelligence gathering.

### Session Completion

When ending a work session:

1. Close finished beads: `bd close <ids>`
2. Commit and push: `git add -A && git commit && git push`

**Work is NOT complete until `git push` succeeds.**

---

# CLAUDE.md

## The Mission

Memory is identity. When an AI forgets everything between conversations, it cannot build real understanding — of you, your work, your people, your life.

MemPalace exists to solve this. It is a memory system — not a search engine, not a RAG pipeline, not a vector database wrapper. It treats every word you have shared as sacred, stores it verbatim, and makes it instantly available. Your data never leaves your machine. We never summarize. We never paraphrase. We return your exact words.

100% recall is the design requirement — the target every search path is measured against. Anything less means forgetting, and forgetting means starting over.

The name comes from the ancient "method of loci" — the memory palace technique used for thousands of years to organize and recall vast amounts of information by placing it in imagined rooms of an imagined building. We were also inspired by the Zettelkasten method (created by German sociologist Niklas Luhmann) — small cross-referenced index cards that point to each other. We apply both ideas to AI memory:

- **Wings** for broad categories (people, projects, topics)
- **Rooms** for time-based groupings (days, sessions)
- **Drawers** for full verbatim content (your exact words)
- **AAAK compression** for the index layer — a compact symbolic format (via `dialect.py`) that lets an LLM scan thousands of entries instantly and know exactly which drawer to open

## Design Principles

These are non-negotiable. Every PR, every feature, every refactor must honor them.

- **Verbatim always** — Never summarize, paraphrase, or lossy-compress user data. The system searches the index and returns the original words. If a user said it, we store exactly what they said. This is the foundational promise.
- **Incremental only** — Append-only ingest after initial build. Never destroy existing data to rebuild. A crash mid-operation must leave the existing palace untouched.
- **Entity-first** — Everything is keyed by real names with disambiguation by DOB, ID, or context. People matter more than topics.
- **Local-first, zero API** — All extraction, chunking, and embedding happens on the user's machine. No cloud dependency for memory operations. No API keys required.
- **Performance budgets** — Hooks under 500ms. Startup injection under 100ms. Memory should feel instant.
- **Privacy by architecture** — The system physically cannot send your data because it never leaves your machine. No telemetry, no phone-home, no external service dependencies for core operations.
- **Background everything** — Filing, indexing, timestamps, and pipeline work happen via hooks in the background. Nothing interrupts the user's conversation. Zero tokens spent on bookkeeping in the chat window.

## Contributing

We welcome bug fixes, performance improvements, new language support, better entity disambiguation, documentation, and test coverage.

We do not accept summarization of user content, cloud storage/sync features, telemetry or analytics, features requiring API keys for core memory, or shortcuts that bypass verbatim storage.

## Setup

```bash
pip install -e ".[dev]"
```

## Commands

```bash
# Run tests
python -m pytest tests/ -v --ignore=tests/benchmarks

# Run tests with coverage
python -m pytest tests/ -v --ignore=tests/benchmarks --cov=mempalace --cov-report=term-missing

# Lint
ruff check .

# Format
ruff format .

# Format check (CI mode)
ruff format --check .
```

## Project Structure

```
mempalace/
├── mcp_server.py        # MCP server — all read/write tools
├── cli.py               # CLI dispatcher
├── config.py            # Configuration + input validation
├── miner.py             # Project file miner
├── convo_miner.py       # Conversation transcript miner
├── searcher.py          # Semantic search (hybrid BM25 + vector)
├── knowledge_graph.py   # Temporal entity-relationship graph (SQLite)
├── palace.py            # Shared palace operations
├── palace_graph.py      # Room traversal + cross-wing tunnels
├── backends/            # Pluggable storage backends (ChromaDB default)
│   ├── base.py          # Abstract interface — implement this for new backends
│   └── chroma.py        # ChromaDB implementation
├── dialect.py           # AAAK compression dialect
├── normalize.py         # Transcript format detection + normalization
├── entity_detector.py   # Auto-detect people/projects from content
├── entity_registry.py   # Entity storage and disambiguation
├── layers.py            # L0-L3 memory wake-up stack
├── onboarding.py        # Interactive first-run setup
├── repair.py            # Palace repair and consistency checks
├── dedup.py             # Deduplication
├── migrate.py           # ChromaDB version migration
├── spellcheck.py        # Auto-correct user messages
├── exporter.py          # Palace data export
├── hooks_cli.py         # Hook management CLI
├── query_sanitizer.py   # Prompt contamination prevention
├── split_mega_files.py  # Split concatenated transcript files
└── version.py           # Single source of truth for version

hooks/                   # Claude Code hook scripts
├── mempal_save_hook.sh        # Stop: triggers diary save
└── mempal_precompact_hook.sh  # PreCompact: saves state before compression
```

## Conventions

- **Python style**: snake_case for functions/variables, PascalCase for classes
- **Linter**: ruff with E/F/W rules
- **Formatter**: ruff format, double quotes
- **Commits**: conventional commits (`fix:`, `feat:`, `test:`, `docs:`, `ci:`)
- **Tests**: `tests/test_*.py`, fixtures in `tests/conftest.py`
- **Coverage**: 85% threshold (80% on Windows due to ChromaDB file lock cleanup)

## Architecture

```
User → CLI / MCP Server → Storage Backend (ChromaDB default, pluggable)
                        → SQLite (knowledge graph)

Palace structure:
  WING (person/project)
    └── ROOM (day/topic)
          └── DRAWER (verbatim text chunk)

Index layer (AAAK):
  Compressed pointers → DRAWER locations
  Scanned by LLM to find relevant drawers without reading all content

Knowledge Graph:
  ENTITY → PREDICATE → ENTITY (with valid_from / valid_to dates)
```

## Key Files for Common Tasks

- **Adding an MCP tool**: `mempalace/mcp_server.py` — add handler function + TOOLS dict entry
- **Changing search**: `mempalace/searcher.py`
- **Modifying mining**: `mempalace/miner.py` (project files) or `mempalace/convo_miner.py` (transcripts)
- **Adding a storage backend**: subclass `mempalace/backends/base.py`, register in `backends/__init__.py`
- **Input validation**: `mempalace/config.py` — `sanitize_name()` / `sanitize_content()`
- **Tests**: mirror source structure in `tests/test_<module>.py`
