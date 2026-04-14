# RunDiff

RunDiff is a Python-first regression gate for AI teams.

It replays representative workloads against baseline and candidate model, prompt, or provider configurations, compares deterministic and judge-based signals, and produces rollout-oriented reports.

## Why

Teams shipping LLM-backed features often need to change:

- the model
- the provider
- the system prompt
- decoding settings
- structured-output contracts

Those changes can improve latency, cost, or quality, but they can also silently break production behavior.

RunDiff is aimed at the narrower question:

`Is this change safe to ship?`

## Intended Product Shape

RunDiff is planned as:

- a local-first CLI
- Python-first and ecosystem-native
- baseline-versus-candidate first
- workload-driven rather than benchmark-driven
- rollout-oriented rather than experiment-history-oriented

RunDiff is not trying to become:

- a full eval platform
- a full observability platform
- a generic prompt playground
- a benchmark leaderboard product

## Current Status

This repository is currently in the planning stage.

The first implementation target is:

- a standalone Python CLI
- a reusable comparison engine
- deterministic checks first
- optional LLM-judge scoring second
- JSON plus human-readable report output

No production code has landed yet.

## Who It Is For

Primary fit:

- teams that already ship at least one LLM-backed product feature
- teams that have outgrown spot checks and one-off notebooks
- teams that want a narrower workflow than a full eval platform

Secondary fit:

- teams with a mature eval platform that still want a tighter rollout gate for baseline-versus-candidate decisions

## Repository Layout

- [`docs/`](./docs/) - planning docs and project definition
- [`adr/`](./adr/) - architecture decision records
- [`rfcs/`](./rfcs/) - proposals that need discussion before becoming decisions

## Start Here

Recommended reading order:

1. [`docs/problem-statement.md`](./docs/problem-statement.md)
2. [`docs/users-and-use-cases.md`](./docs/users-and-use-cases.md)
3. [`docs/competitive-analysis.md`](./docs/competitive-analysis.md)
4. [`docs/mvp-definition.md`](./docs/mvp-definition.md)
5. [`docs/architecture-overview.md`](./docs/architecture-overview.md)
6. [`docs/roadmap.md`](./docs/roadmap.md)

The full planning index lives at [`docs/planning-index.md`](./docs/planning-index.md).

## Decision Process

- Use an RFC when a meaningful design direction is still under discussion.
- Use an ADR once a material decision has been made.

Implementation should start only after the remaining blocking open questions are resolved or promoted into explicit decisions.
