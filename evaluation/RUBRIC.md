# ACS Conformance Rubric

This rubric evaluates whether an agent execution conforms to the
Adaptive Conformance Specification (ACS).

Evaluation is based on the required Conformance Output Contract
and the behavioral constraints defined in `SKILL.md`.

All judgments must be grounded in the submitted conformance record.
No credit is given for implied or assumed behavior.

## Evaluation Dimensions

Each dimension is scored independently.

### 1. Evidence Quality

Question: Was sufficient, relevant evidence inspected and recorded?

Full (2)

- Clear record of inspected files, tools, or examples
- Evidence is specific and relevant to the task
- Structures (inputs, outputs, schemas, patterns) are identified

Partial (1)

- Some evidence recorded, but incomplete or weakly connected
- Key structures or sources missing

None (0)

- No meaningful evidence
- Claims made without inspection

### 2. Interpretation Accuracy

Question: Was the system correctly understood?

Full (2)

- Components correctly described
- Inputs, outputs, and constraints accurately identified
- Local patterns correctly recognized

Partial (1)

- Minor inaccuracies or omissions
- Patterns identified but not clearly justified

None (0)

- Misinterpretation of system behavior
- Incorrect assumptions about structure or constraints

### 3. Selection Rationale

Question: Is the chosen approach justified by evidence?

Full (2)

- Selection explicitly tied to observed patterns or files
- Competing options acknowledged when relevant

Partial (1)

- Selection stated but weakly justified
- Limited traceability to evidence

None (0)

- No rationale provided
- Arbitrary or unexplained selection

### 4. Conformance to Local Patterns

Question: Does the output match the system it was generated for?

Full (2)

- Naming, structure, and conventions match observed patterns
- No external conventions introduced

Partial (1)

- Minor inconsistencies or stylistic drift

None (0)

- Output does not match local structure
- External or invented patterns introduced

### 5. Minimality and Discipline

Question: Is the output limited to what is supported by evidence?

Full (2)

- No unnecessary fields, parameters, or behavior
- Output is minimal and valid

Partial (1)

- Minor overgeneration or redundancy

None (0)

- Includes unsupported or speculative content
- Adds unobserved fields or behavior

### 6. Validation Integrity

Question: Was the output checked against observed patterns?

Full (2)

- Validation explicitly performed and described
- Confirms structure, naming, and constraints
- No unobserved elements present

Partial (1)

- Validation attempted but incomplete

None (0)

- No validation step
- Errors or inconsistencies ignored

### 7. Transparency and Traceability

This dimension is cross-cutting.
It evaluates the traceable relationship between evidence and decisions
across all sections of the Conformance Output Contract (3.1–3.6),
not a single section in isolation.

Question: Can decisions be traced back to evidence?

Full (2)

- All claims and decisions are traceable to observed evidence
- Uncertainty is explicitly stated

Partial (1)

- Partial traceability
- Some assumptions not clearly justified

None (0)

- Decisions cannot be traced to evidence
- Hidden assumptions present

## Scoring

Each dimension is scored:

- 2 = Full
- 1 = Partial
- 0 = None

Maximum score: 14

## Evaluation Outcomes

- Conformant (12–14)
  - Strong evidence, correct interpretation, full conformance
  - No structural violations

- Partially Conformant (7–11)
  - Some gaps or minor inconsistencies
  - No critical violations

- Non-Conformant (0–6)
  - One or more critical failures:
    - acting without evidence
    - hallucinated structure
    - failure to validate
    - silent correction or guessing

## Critical Violations (Automatic Non-Conformance)

Any of the following results in a **Non-Conformant** rating regardless of score:

- No evidence of inspection
- Fabricated or hallucinated tools, fields, or behavior
- Output not aligned with observed system structure
- Silent correction of errors without reporting
- Omission of required Conformance Output Contract sections

## Notes

- Evaluation is based only on what is explicitly shown.
- Missing sections are treated as missing behavior.
- Partial correctness does not compensate for structural violations.
