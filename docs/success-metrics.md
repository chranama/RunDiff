# RunDiff Success Metrics

Visibility: Public

Date: 2026-04-14

## Product Success

RunDiff succeeds when teams can compare baseline and candidate AI configurations over representative workloads and make safer rollout decisions with less manual review.

## v0.1 Success Criteria

- a new user can run the example workflow in less than 10 minutes
- the tool catches seeded deterministic regressions in provided fixtures
- the report makes baseline-versus-candidate differences understandable quickly
- deterministic and judge-derived signals are clearly distinguished

## Engineering Success

- deterministic fixture-based tests for case loading, normalization, and checks
- golden output tests for reports
- explicit provider-adapter boundaries
- explicit handling of timeouts, retries, and judge failures

## Adoption Signals

Early signals worth watching:

- issues or requests from AI backend/platform teams
- requests for more provider support
- requests for CI gate integration
- evidence that teams use RunDiff before model or prompt rollouts

## Performance Targets

Initial targets should be modest but explicit:

- predictable execution on small representative workloads
- no confusing nondeterminism in the deterministic path
- clear runtime metadata capture where provider responses support it

## Risk Signals

The project is off track if:

- the case schema is too broad to explain simply
- the reports do not help a human decide whether to ship
- judge output overwhelms deterministic checks
- the project starts to look like a broad experiment platform instead of a rollout gate
