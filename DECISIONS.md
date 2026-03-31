# DECISIONS.md

Design history and rationale for the Adaptive Conformance Specification (ACS).
Records why the skill is the way it is for contributors, future maintainers,
and dependent skills.

## Decision 1. Scope boundary: foundational only

ACS covers observation and conformance only.
It does not cover tool capability mapping,
team onboarding context, or post-conformance verification.

### Rationale 1

These are distinct concerns with distinct workflows.
Merging them into ACS would make it too large to invoke cleanly
and too broad to test precisely.
Tool capability mapping is the responsibility of Adaptive Tool
Discovery (ATD).
Team and project onboarding context is the responsibility of
Adaptive Onboarding (AO).
Verification of agent understanding is deferred to a
future skill.
ACS is the foundational layer all three depend on.
Its scope must stay narrow enough to be reusable.

## Decision 2. License: MIT

MIT across all `adaptive-interfaces` repos.

### Rationale 2

Organizations need to be able to use and adapt skills
internally without legal friction.
MIT is OSI-approved, universally recognized by legal teams, and
imposes no obligations on derivative works.

## Decision 3. MANIFEST.toml: adaptive-interfaces schema

Uses `schema = "adaptive-interfaces-manifest-1"`, defined in
[adaptive-interfaces-manifest-1.md](https://github.com/adaptive-interfaces/.github/blob/main/schemas/adaptive-interfaces-manifest-1.md),
an adaptation of
[SE_MANIFEST.toml](https://github.com/structural-explainability/spec-se/blob/main/manifests/se-manifest-1.md).

### Rationale 3

The adaptive-interfaces manifest borrows the pattern
(explicit includes/excludes, declarative intent) without the schema binding.

## See Also

- [Markdown Architectural Decision Records](https://adr.github.io/madr/)
