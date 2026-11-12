---
name: "[skill-name]"
description: "[Purpose and when to use this skill.]"
---

# [Skill title]

## Purpose and scope

[Audience, supported task, and expected result.]
- **Use when:** [Triggers or user goals.]
- **Exclude:** [Out-of-scope tasks.]
- **Prerequisites:** [Inputs, access, or setup; "None" if none.]

## Inputs and boundaries

- **Inputs/context:** [Required information and useful optional context.]
- **Sources and access:** [Authorized material; what is out of bounds.]
- **Gaps:** [When to ask, pause, or proceed with limited scope.]

## Workflow

1. **[Step]:** [Action, decision, expected result.]
2. **[Step]:** [Action, decision, expected result.]
3. **[Step]:** [Action, decision, expected result.]
4. **Validate:** [Observable completion checks.]

- **Branches:** [Actions for important conditions.]
- **Stop/ask when:** [Ambiguity, authorization, safety, or other blockers.]

## Evidence and uncertainty

- **Grounding/traceability:** [Sources to use; how to verify and cite evidence.]
- **Gaps/conflicts:** [How to disclose and handle missing or conflicting evidence.]
- **Certainty:** [Separate facts, inference, and unknowns; state when to abstain.]
- **Never invent:** [Facts, sources, capabilities, or results that must be verified.]

## Host, tools, and integrations

- **Host/format/invocation:** [Host and version, metadata, invocation, output contract; "Unspecified" if unknown.]
- **Dependencies:** [Tools/integrations, purpose, availability, permissions, inputs, and outputs; "None" if none.]
- **Unavailable or unverified:** [Fallback/stop behavior and compatibility limits; don't claim runtime verification without evidence.]

## Safety, privacy, and side effects

- **Authorization/actions:** [Required permission and allowed reads, writes, execution, or external calls.]
- **Confirmation/limits:** [Actions needing approval; scope and side-effect bounds.]
- **Data handling:** [Minimization, disclosure, and retention.]
- **Refusal/recovery:** [Unsafe or unauthorized requests; safeguards or rollback for permitted actions.]

## Errors and handoff

[How to surface errors, bound retries, label partial work, and escalate unresolved issues without implying success.]

## Output

[Format and required content: deliverable, evidence/rationale, limitations or unknowns, and next steps.]

## Maintenance and acceptance

[Observable checks for scope, workflow, and output; dependencies or assumptions to revisit; terminology to keep consistent.]
