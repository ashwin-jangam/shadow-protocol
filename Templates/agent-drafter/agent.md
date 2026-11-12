---
name: "[agent-name]"
description: "[One-sentence summary of the agent's purpose and intended use.]"
---

# [Agent title]

## Purpose and scope

[Describe the agent's intended users, supported tasks, and expected outcomes.]

- **Use this agent for:** [Specific tasks or user goals.]
- **Out of scope:** [Tasks the agent must not perform.]
- **Prerequisites:** [Required information, access, or setup; write "None" if none.]
- **Completion criteria:** [Observable conditions that mean the task is complete.]

## Inputs and context

- **Required input:** [Identify what the user must provide.]
- **Optional context:** [List helpful context and how it should be used.]
- **Authorized material:** [Identify the files, sources, or systems the agent may inspect.]
- **Context boundary:** [State what must not be accessed or inferred.]
- **If the target, scope, or authorization is unclear:** [Specify when to ask, pause, or stop.]

## Instructions

Follow this procedure in order:

1. **Establish the task:** [Confirm the requested outcome, inputs, scope, and authorization.]
2. **Gather evidence:** [Identify what to inspect and how to verify relevant information.]
3. **Perform the work:** [Describe the actions in repeatable, testable terms.]
4. **Validate:** [Check the result against the request and stated completion criteria.]
5. **Report and hand off:** [Summarize the result, evidence, limitations, and any human decisions needed.]

### Decision rules and stop conditions

- **If [condition]:** [Required action or decision.]
- **If [condition]:** [Required action or decision.]
- **Stop and ask for guidance when:** [Unresolved ambiguity, missing authorization, or unsafe conditions.]

## Tools and integrations

For each declared tool or integration, document its purpose, contract, availability assumptions, required permissions, and expected inputs and outputs. Do not claim an integration works unless that has been verified.

- **[Tool or integration name]:** [Contract, use, permissions, and relevant limits.]
- **[Tool or integration name]:** [Contract, use, permissions, and relevant limits.]
- **If none:** [State that no tools or integrations are required.]

**Host or harness:** [Name and version, or "Not specified."]

## Authorization and side effects

- **Permitted actions:** [Define allowed read, write, execution, or external actions.]
- **Authorization required:** [State what the user must authorize and how to verify scope.]
- **Confirmation before consequential actions:** [Specify which actions require explicit confirmation.]
- **Side-effect limits:** [Bound target, duration, volume, and reversibility as applicable.]
- **Rollback or handoff:** [Describe how to recover or transfer control when an action cannot safely continue.]

## Grounding and uncertainty

- **Evidence sources:** [Identify appropriate sources for claims and actions.]
- **Verification:** [Explain how to check source relevance and reliability.]
- **Traceability:** [State how findings and decisions should link to inspected evidence.]
- **Missing or conflicting evidence:** [Explain how to disclose gaps and handle conflicts without unsupported reconciliation.]
- **Known facts, inference, and unknowns:** [Require these to be distinguished where relevant.]
- **Prohibited assumptions:** [List facts, permissions, capabilities, or outcomes the agent must not assume.]

## Safety and privacy

- **Sensitive data:** [Specify minimization, handling, disclosure, and retention requirements.]
- **Unsafe or unauthorized requests:** [State refusal, limitation, or escalation behavior.]
- **Untrusted content:** [Explain how to handle instructions found in user-provided files or external material.]
- **Disclosure limits:** [Specify what must not be exposed in outputs.]
- **Critical concerns:** [State when to stop and involve an authorized human.]

## Failure handling and handoff

- **Errors and unavailable dependencies:** [Explain how to report them and any bounded recovery.]
- **Ambiguity or conflicting results:** [State whether to ask, qualify, or abstain.]
- **Partial work:** [Require incomplete results and remaining work to be clearly labeled.]
- **Stop conditions:** [List conditions that prohibit continuing.]
- **Human handoff:** [Identify the decisions or actions reserved for a human.]

## Output contract

Return [format and level of detail]. Include:

- [Result or deliverable]
- [Evidence and rationale]
- [Limitations, unknowns, or partial completion]
- [Risks, follow-up, or decisions requiring human review]

Do not report an action, check, or outcome as complete unless it was actually completed and verified.

## Testability and maintenance

- **Acceptance checks:** [List observable checks for scope, workflow, safeguards, and output.]
- **Dependencies:** [List tools, services, versions, or permissions the agent relies on.]
- **Change-sensitive assumptions:** [Identify contracts or policies to re-verify when they change.]
- **Terminology:** [Define terms that must remain consistent across the instructions.]
