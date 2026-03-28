# Changelog

## v1.1.0 — 2026-03-28

### Breaking Changes
- Agents moved from `agents/` to `.claude/agents/` — required for Claude Code subagent invocation
- Agent filenames no longer have numeric prefixes (e.g. `01-strategy.md` → `strategy.md`)
- `.env.example` removed — see `docs/env-reference.md` instead

### Added
- YAML frontmatter on all 28 agent files (name, description, tools, model) — agents are now invocable as Claude Code subagents
- `LICENSE` file (MIT)
- `docs/env-reference.md` — replaces .env.example with proper context
- Automatic quality enforcement in CLAUDE.md — gates that fire silently on every page, API route, DB change, and pre-ship
- Agent Tool invocation syntax in CLAUDE.md — orchestrator now routes via `Agent(name: "...", prompt: "...")`
- Tiered agent catalog: Core (auto-invoked) / Builder / Strategic / Growth
- Solo Builder Mode: revenue-first ordering, energy-aware routing, decision journal, progress dashboard
- Slash commands: /plan, /build, /test, /review, /ship, /stuck, /missing, /blockers, /sprint, /progress, /teardown
- Spec-driven workflow: enforces spec before any feature is built
- Persistent context protocol: session state survives between sessions

### Changed
- README rewritten around quality gates positioning ("Your code ships with quality gates you'd normally skip")
- CLAUDE.md completely restructured — orchestrator-first with embedded quality enforcement
- Removed "How It Works" flowchart (aspirational, replaced with 60-second demo)
- Removed "vs. Doing It Yourself" comparison table (defensive, replaced by quality gate demonstration)
- Model assignments: opus for strategy, architecture, evaluator, devils-advocate — sonnet for all others

### Fixed
- Agents were not invocable in Claude Code format (missing frontmatter, wrong directory)
- .env.example contained placeholder keys for services not in this repo
