# RunDiff Repository Plan

Visibility: Public

Date: 2026-04-14

## Purpose

This document proposes the repository shape needed to support planning, implementation, fixtures, and contributor workflow.

## Recommended Public Structure

- `docs/` for planning and public design docs
- `adr/` for architectural decisions
- `rfcs/` for larger proposals
- `fixtures/` for synthetic workloads and expected reports
- `schemas/` for case and config schemas
- `examples/` for runnable sample workloads and configs
- `scripts/` for development helpers
- `python/` for the first implementation

## Initial Implementation Layout

Recommended Python-first layout:

- `python/`
  - `pyproject.toml`
  - `src/rundiff/`
  - `tests/`

## First Files To Add Once Implementation Starts

- Python package manifest
- sample `rundiff.yaml`
- canonical JSONL case fixture
- baseline and candidate example configs
- golden JSON report
- first end-to-end test
- local developer quickstart

## Repository Rules

- no real production prompts or customer data
- fixtures should be synthetic or clearly sanitized
- examples should be runnable and minimal
- report artifacts should be reproducible from documented commands

## Recommended First ADRs

- choose case schema
- choose first provider set
- choose report output formats
- choose judge policy
