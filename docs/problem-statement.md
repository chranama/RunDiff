# RunDiff Problem Statement

Visibility: Public

Date: 2026-04-14

## Problem

Teams shipping LLM-backed product features regularly want to change something important:

- the model
- the provider
- the system prompt
- the decoding configuration
- the structured-output contract

Those changes can improve latency, cost, or output quality, but they can also silently break behavior that matters in production.

## Core Tension

Users are forced into one of several bad options:

- ship the change with only ad hoc spot checks
- rely on generic benchmarks that do not reflect application behavior
- run manual review loops that are slow and expensive
- adopt a broad experiment platform when the immediate need is simply "is this change safe to ship?"

## Why Existing Options Are Not Enough

Existing eval and experiment tools are useful, but many are:

- broader than the first problem the team needs to solve
- optimized for ongoing experimentation rather than rollout decisions
- heavier to adopt than a narrow CLI-first workflow
- less focused on baseline-versus-candidate diffs over application-owned workloads

Teams with mature eval platforms are not excluded from the problem, but they are usually not the first wedge. Even well-tooled teams can still lack a narrow rollout gate that:

- works from local developer workflows
- produces one compact ship-or-block artifact
- makes baseline-versus-candidate comparison the center of the workflow
- fits naturally into CI or release review without opening the full experiment stack

Raw traces and observability data also help diagnose behavior after the fact, but they do not by themselves answer the pre-rollout question:

"What changed, and is it safe to ship?"

## RunDiff Thesis

RunDiff should provide a narrow regression-gating tool for AI product teams.

Given a representative workload and two candidate configurations, it should:

- replay both versions
- compare deterministic contract behavior
- optionally score semantic differences with an LLM judge
- summarize regressions in a rollout-oriented report

## Desired Outcome

A team should be able to say:

"Before we switch the model, prompt, or provider, we can replay representative cases and see whether quality, structure, cost, or latency regressed in a way that should block rollout."

## Non-Problem

RunDiff is not trying to become:

- a full observability platform
- a generic prompt playground
- a hosted annotation service
- a universal benchmark suite for model ranking

RunDiff is also not trying first to replace a mature eval platform. When those platforms already exist, RunDiff should act as a narrower rollout-decision layer on top of them rather than competing to become the primary experiment system.

## Constraints

The project should be:

- useful from a local CLI first
- Python-first and ecosystem-native
- explicit about deterministic versus judge-based evaluation
- artifact-oriented, not chat-oriented
- narrow enough that a small team could adopt it for one migration decision
