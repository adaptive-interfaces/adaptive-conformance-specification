# adaptive-conformance-specification

[![CI Status](https://github.com/adaptive-interfaces/adaptive-conformance-specification/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/adaptive-interfaces/adaptive-conformance-specification/actions/workflows/ci.yml)
[![Link Check](https://github.com/adaptive-interfaces/adaptive-conformance-specification/actions/workflows/links.yml/badge.svg?branch=main)](https://github.com/adaptive-interfaces/adaptive-conformance-specification/actions/workflows/links.yml)
[![MIT](https://img.shields.io/badge/license-see%20LICENSE-yellow.svg)](./LICENSE)

> Adaptive Conformance Specification (ACS) Skill

A foundational behavioral protocol for agents working within unfamiliar
codebases or tool surfaces.
ACS defines _how_ an agent must observe, infer, and conform to a system
before generating any artifact within it.

ACS produces no artifact of its own.
It produces disciplined behavior that shapes whatever the invoking skill
produces.

## Motivation

Two downstream skills motivated this specification:

**[Adaptive Tool Discovery (ATD)](https://github.com/adaptive-interfaces/adaptive-tool-discovery)**
maps the capabilities of an external tool set:
what tools exist, what each does, how to call them correctly, and what their
failure modes are.
The output is a tool capability map the agent can act on.

**[Adaptive Onboarding (AO)](https://github.com/adaptive-interfaces/adaptive-onboarding)**
builds the context needed to work as a member of a specific team or project —
conventions, ownership, local definition of done, and norms not written down
anywhere.
The output is team-member-level working context.

Both skills require the same foundational discipline:
observe before acting, infer from evidence, conform to local patterns, stop
rather than guess.
ACS extracts that shared layer so it is defined once, maintained once, and
invoked consistently by both.

## Scope: Included

- The evidentiary standard an agent must meet before generating output
- A six-step workflow: Discover → Interpret → Select → Execute → Validate → Conclude
- Principles for conforming to local patterns, including when outside conventions are permitted
- Error detection and structured reporting
- Stopping conditions for insufficient evidence
- An invocation protocol for dependent skills

## Scope: Excluded

- Which concerns to extract and where to find them (defined by the invoking skill)
- Tool capability mapping → see [adaptive-tool-discovery](https://github.com/adaptive-interfaces/adaptive-tool-discovery)
- Team and project onboarding context → see [adaptive-onboarding](https://github.com/adaptive-interfaces/adaptive-onboarding)
- Post-conformance verification of agent understanding

## Using ACS

ACS is not invoked directly by users.
It is invoked by skills that need its observation and conformance layer.

Skills that depend on ACS include this in their preamble:

> This skill operates under the Adaptive Conformance Specification (ACS).
> Apply ACS discovery and conformance steps before executing any
> domain-specific actions below.

If you are building a skill that requires an agent to work within an unfamiliar
system, ACS is the correct foundation.
Read [`SKILL.md`](./SKILL.md) for the full specification.

## Testing ACS on your own codebase

Clone the repo and add your own private scenarios under `evaluation/local/`.
That directory is gitignored and will never be committed or pushed.
Your proprietary test cases stay local while you pull upstream updates freely.

```shell
git clone https://github.com/adaptive-interfaces/adaptive-conformance-specification
cd adaptive-conformance-specification
mkdir -p evaluation/local/my-scenario
```

See [`evaluation/scenarios/`](./evaluation/scenarios/) for examples of how
scenarios are structured.

## Repository contents

```text
adaptive-conformance-specification/
  SKILL.md              the specification itself
  MANIFEST.toml         repository intent, scope, and role
  DECISIONS.md          design history and rationale
  LICENSE               MIT
  evaluation/
    rubric.md           grading criteria for conformance quality
    scenarios/          public test cases
    local/              gitignored, private test cases
```

## Developer

Format Markdown files with Prettier extension.
Then run:

```shell
npx markdownlint-cli2 "**/*.md"

uvx skillcheck SKILL.md --min-desc-score 75
```

## License

MIT © 2026 [Adaptive Interfaces](https://github.com/adaptive-interfaces)
