# RunDiff Proof Plan

Visibility: Public

Date: 2026-04-14

## Purpose

This document defines the claims RunDiff makes and the evidence that should exist to support those claims.

## Core Claims

RunDiff v0.1 should aim to prove these claims:

1. RunDiff can execute representative workloads against a baseline and candidate configuration reproducibly.
2. RunDiff can catch seeded deterministic regressions in structured or rule-checked outputs.
3. RunDiff can summarize semantic differences separately from deterministic failures.
4. RunDiff can produce a rollout-oriented artifact that is useful for human review.

## Non-Claims

RunDiff v0.1 should not claim:

- universal model-quality ranking
- statistical rigor for every possible application
- hosted collaboration or annotation workflows
- support for every provider or framework

## Evidence By Claim

### Claim 1: Reproducible Baseline And Candidate Comparison

Evidence:

- sample workload fixtures
- baseline and candidate config fixtures
- repeat-run tests
- stable report artifacts

### Claim 2: Deterministic Regression Catching

Evidence:

- seeded fixtures where the candidate breaks schema, formatting, or rule-based expectations
- tests showing the report flags these regressions

### Claim 3: Semantic Difference Reporting

Evidence:

- cases where baseline and candidate both pass structure checks but differ meaningfully
- optional judge output captured explicitly and labeled as judge-derived

### Claim 4: Reviewable Rollout Artifact

Evidence:

- one compact Markdown or HTML report
- machine-readable JSON report
- summary buckets such as `improved`, `regressed`, `needs review`

## Fixture Strategy

Recommended fixture groups:

- freeform answer cases
- structured-output cases
- rule-checked extraction or classification cases
- seeded regression cases
- latency or cost comparison examples where provider metadata exists

## Reviewer Path

The first reviewer path should take roughly 5 to 10 minutes.

Suggested path:

1. read the short project description
2. run baseline and candidate over the example workload
3. inspect the summary report
4. inspect one or two detailed case diffs
5. run the fixture tests

## Proof Artifacts

The first proof bundle should include:

- a small example workload
- baseline and candidate config examples
- seeded regression cases
- one JSON report
- one human-readable report

## Failure Conditions

The proof plan is failing if:

- report outputs are too vague to support a rollout decision
- deterministic regressions are not caught reliably
- judge-based output is mixed with deterministic output unclearly
- reviewers cannot tell why a change was marked risky
