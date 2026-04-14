# RunDiff Roadmap

Visibility: Public

Date: 2026-04-14

## Milestone 0: Build-Ready Planning

Goal:

- finalize problem, users, MVP, architecture, and competitive positioning
- choose the first case schema
- choose the first provider set
- record the first ADRs

Exit criteria:

- planning docs reviewed
- no blocking open questions for v0.1 scope
- first implementation path is explicit

## Milestone 1: Python Comparison Engine

Goal:

- build the core Python engine and minimal CLI

Scope:

- load cases
- resolve baseline and candidate configs
- run both paths
- normalize responses
- support first deterministic checks

Exit criteria:

- sample workloads run end to end
- fixture-based tests pass

## Milestone 2: Reporting And Diff Classification

Goal:

- make outputs useful for rollout review

Scope:

- classify differences
- emit JSON report
- emit human-readable report
- add seeded regression fixtures

Exit criteria:

- reviewer-fast artifact exists
- seeded regressions are surfaced clearly

## Milestone 3: Judge And CI Path

Goal:

- add optional semantic judging and reusable gate workflows

Scope:

- explicit judge behavior
- judge-labeled report sections
- CI-oriented command or exit behavior

Exit criteria:

- deterministic and judge-derived signals are clearly separated
- one CI-friendly usage path is documented

## Milestone 4: Hardening And Broader Evaluation

Goal:

- make the tool useful for outside teams

Scope:

- better examples
- clearer config docs
- broader provider coverage if justified
- optional adapters for importing cases from mature eval platforms if justified
- stronger failure messages

Exit criteria:

- a new user can evaluate the tool without maintainer hand-holding

## Roadmap Discipline

RunDiff should stay narrow.
New ideas should be rejected or deferred if they push the project toward becoming a general experiment platform or observability product.
