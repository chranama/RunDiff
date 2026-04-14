# RunDiff Open Questions

Visibility: Public

Date: 2026-04-14

## Questions That Block v0.1

### 1. What Is The Canonical Case Schema?

Choices include:

- text-generation-first JSONL
- a schema that includes both freeform and structured-output cases
- a broader schema that anticipates tool-calling too early

Decision needed:

- choose the narrowest useful case shape for the first release

### 2. What Providers Are Supported First?

Choices include:

- OpenAI only
- OpenAI plus OpenAI-compatible endpoints
- OpenAI plus Anthropic

Decision needed:

- choose the first provider scope that is credible without overexpanding adapters

### 3. What Report Formats Are First-Class In v0.1?

Choices include:

- JSON only
- JSON plus Markdown
- JSON plus HTML

Decision needed:

- choose the smallest output set that still supports human review

### 4. What Is The Judge Policy?

Questions:

- is the LLM judge enabled by default or opt-in?
- what happens when judge calls fail?
- how should judge-derived signals be labeled versus deterministic ones?

Decision needed:

- define explicit judge behavior before implementation

## Questions That Can Wait Slightly Longer

### 5. Should Trace Exports Become An Input Source Early?

This is useful, but may expand the product before the canonical case schema is stable.

### 6. How Much Structured Output Depth Belongs In v0.1?

The project should support enough contract checking to matter without becoming a full schema-validation platform.

### 7. What CI Gate Semantics Should Exist?

Possible later paths:

- threshold-based exit codes
- required-case blockers
- budget-aware warnings

## Rule

If an open question changes user-facing semantics or the first implementation path materially, it should become an ADR before implementation proceeds.
