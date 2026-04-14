# RunDiff Users And Use Cases

Visibility: Public

Date: 2026-04-14

## Primary Users

### AI Platform Engineer

Owns shared model choices, prompt defaults, or rollout safety for one or more AI-backed features.

Needs:

- a repeatable way to compare candidate changes
- a report that is useful in rollout review
- a path that works before full observability or experiment infrastructure is in place

### Backend Or Product Engineer Owning An LLM Feature

Owns a feature that depends on model behavior and needs to change provider, prompt, or settings safely.

Needs:

- application-specific workloads instead of generic benchmarks
- deterministic checks for structure or contract behavior
- a small enough workflow to run before shipping

### Technical Lead Or Manager Reviewing Rollouts

Needs:

- a compact summary of what changed
- evidence for blocking or approving a rollout
- enough cost and latency signal to make tradeoffs visible

## Primary ICP

The best first customers are teams that:

- already ship at least one LLM-backed product feature
- change model, prompt, or provider configurations regularly
- have outgrown ad hoc spot checks or one-off notebooks
- can assemble representative workloads from fixtures, logs, or traces
- want a narrower tool than a full eval platform
- care about rollout confidence more than generalized research benchmarking

This is a medium-maturity evaluation workflow. These teams feel real regression risk, but do not yet have a mature evaluation platform they trust and use for every rollout decision.

## Secondary ICP

Teams with a mature eval platform can still be a good fit when they need a narrower rollout-decision layer on top of their existing stack.

The strongest secondary fit is a team that:

- already has datasets, traces, or scorers in Braintrust, LangSmith, Langfuse, OpenAI Evals, or an internal equivalent
- does not want to rebuild those assets
- still lacks a compact baseline-versus-candidate gate for one concrete rollout
- wants a local or CI-friendly artifact that answers ship, investigate, or block

In this mode, RunDiff complements the eval platform rather than replacing it.

## Anti-ICP

RunDiff is not optimized first for:

- research groups trying to publish benchmark leaderboards
- hobby prompt tinkering without representative workloads
- teams with no meaningful baseline cases to compare against
- organizations looking first for a hosted experiment collaboration suite
- teams already satisfied with a mature eval platform and rollout-gating workflow

## Early Adopter Profile

The best first adopters are teams that:

- already ship LLM-backed product behavior
- are changing model or prompt configurations regularly
- have representative workloads or can assemble them
- want a narrower tool than a full eval platform
- care about rollout confidence more than generalized research benchmarking

The ideal customer role inside those teams is usually:

- a senior backend engineer, AI engineer, or platform-minded product engineer as the primary user
- an engineering manager or tech lead as the economic buyer
- a tech lead, staff engineer, or manager as the final rollout reviewer

## Core Use Cases

### Use Case 1: Model Or Provider Migration

A team wants to compare a baseline model/provider against a cheaper, faster, or newer candidate.

### Use Case 2: Prompt Or System Message Revision

A team wants to tighten instructions or add behavior without regressing existing outcomes.

### Use Case 3: Structured Output Regression Check

A team wants to confirm that a candidate still satisfies schema or contract expectations across representative cases.

### Use Case 4: Rollout Review Artifact

A team wants one report that summarizes:

- what regressed
- what improved
- what needs manual investigation
- whether the candidate should be blocked

### Use Case 5: Last-Mile Gate On Top Of An Eval Platform

A team already has datasets or experiments in an existing eval system, but still wants a narrow baseline-versus-candidate workflow that emits a rollout decision artifact for PR review or CI.

## Nice-To-Have Use Cases

- CI-oriented gate commands
- importing workload cases from trace exports later
- comparing multiple candidates against one baseline

## Non-Goals For The First User

The first user is not looking for:

- a broad hosted experimentation workspace
- a benchmark leaderboard product
- a general research environment
- an observability backend
