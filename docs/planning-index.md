# RunDiff Planning Index

Visibility: Public

Date: 2026-04-14

## Purpose

This index is the entry point for the planning docs that should exist before implementation starts. The goal is to make the problem, user, product shape, and first implementation path legible to future contributors.

## Suggested Reading Order

1. [Problem Statement](./problem-statement.md)
2. [Users And Use Cases](./users-and-use-cases.md)
3. [Competitive Analysis](./competitive-analysis.md)
4. [MVP Definition](./mvp-definition.md)
5. [Success Metrics](./success-metrics.md)
6. [Architecture Overview](./architecture-overview.md)
7. [Proof Plan](./proof-plan.md)
8. [Repository Plan](./repository-plan.md)
9. [Roadmap](./roadmap.md)
10. [Open Questions](./open-questions.md)

## Decision Process

- [ADR Guide](../adr/README.md)
- [ADR Template](../adr/0000-template.md)
- [RFC Guide](../rfcs/README.md)
- [RFC Template](../rfcs/0000-template.md)

## Build-Ready Checklist

Implementation should not start until the project can answer these clearly:

- what exact regression-gating problem RunDiff solves first
- who the first user is
- what v0.1 includes and excludes
- what the first runnable artifact is
- how correctness and usefulness will be measured
- which provider and case formats are supported first
- which open questions must become ADRs before code lands
