# RunDiff ADR Guide

Visibility: Public

Date: 2026-04-14

## Purpose

ADRs capture architectural decisions that materially affect implementation or contributor expectations.

## When To Write An ADR

Write an ADR when a decision changes:

- case schema
- provider support
- judge behavior
- report semantics
- repository structure
- public compatibility expectations

## Naming Convention

Use incrementing numbers:

- `0001-choose-case-schema.md`
- `0002-choose-first-provider-set.md`

## Recommended First ADRs

- choose case schema
- choose first provider set
- choose report formats
- choose judge policy

## Process

1. Draft the ADR from the template.
2. Mark it as `Proposed`.
3. Review it before implementation depends on it.
4. Change status to `Accepted` or `Rejected`.
5. Never silently rewrite history after acceptance; append context instead.
