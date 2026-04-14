# RunDiff MVP Definition

Visibility: Public

Date: 2026-04-14

## MVP Goal

Deliver a first useful artifact that proves RunDiff can compare a baseline and candidate configuration over representative workloads and surface rollout-significant regressions.

## Recommended First Artifact

Start with a standalone Python CLI plus reusable comparison engine.

Why this should come first:

- easiest way to validate the case schema and diff semantics
- simplest path for fixture-based tests and report artifacts
- low adoption friction for early users
- naturally fits the Python model SDK ecosystem

## v0.1 Must-Haves

- load a canonical workload file format
- load baseline and candidate run configuration from file
- execute both configurations over the same cases
- capture response content plus basic runtime metadata
- support deterministic checks for:
  - schema validity
  - exact or rule-based expectations where applicable
  - parseable structured output
- support an optional LLM-judge pass for semantic comparison
- classify differences into a small number of failure buckets
- emit:
  - machine-readable JSON report
  - human-readable Markdown or HTML summary
- produce a simple rollout recommendation such as:
  - `keep`
  - `investigate`
  - `block`

## v0.1 Out Of Scope

- hosted UI or collaboration layer
- full trace-ingestion support
- every provider or framework
- annotation workflows
- broad observability features
- multi-candidate experiment management

## Expected Inputs

The implementation should choose one primary input path first:

- a canonical JSONL case schema
- plus a small run configuration file such as `rundiff.yaml`

This should become an ADR before implementation.

## Acceptance Criteria

The MVP is successful if it can:

- run sample baseline and candidate configs over provided workloads
- catch seeded deterministic regressions in sample fixtures
- generate a report that a technically capable reviewer can understand quickly
- make the deterministic-versus-judge distinction explicit
- be runnable from the README in a short setup path

## Near-Term Follow-Up

The next release after the MVP should target one or more of:

- CI-oriented gate commands
- trace-export import adapters
- broader provider coverage
- richer structured-output or tool-call case types
