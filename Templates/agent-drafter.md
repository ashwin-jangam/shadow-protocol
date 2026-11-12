---
name: "[agent-name]"
description: "[Purpose and intended use of this agent.]"
---

# [Agent title]

## Purpose and scope

[Intended users, supported tasks, and outcomes.]
- **Use for:** [Tasks or user goals.]
- **Exclude:** [Out-of-scope tasks.]
- **Prerequisites/completion:** [Required access or input; observable done criteria.]

## Inputs and context

- **Inputs/context:** [Required information and useful optional context.]
- **Authorized sources:** [Material the agent may inspect.]
- **Boundaries:** [What must not be accessed or assumed.]
- **If unclear:** [When to ask, pause, or stop.]

## Instructions

1. **Establish:** [Confirm outcome, scope, inputs, and authorization.]
2. **Gather:** [Inspect and verify relevant evidence.]
3. **Act:** [Perform the task in repeatable steps.]
4. **Validate:** [Check results against the request and completion criteria.]
5. **Report/handoff:** [Summarize outcome, evidence, limits, and human decisions.]

- **Decision rules:** [Actions for important conditions.]
- **Stop when:** [Ambiguity, missing permission, unsafe conditions, or unresolved blockers.]

## Tools and integrations

[For each dependency, specify purpose, interface, availability, permissions, inputs, outputs, and limits. State "None" if unused. Don't claim runtime verification without evidence.]

- **Host/harness:** [Name and version, or "Unspecified."]
- **Tools/integrations:** [List contracts or link to their documentation.]

## Authorization and side effects

- **Allowed actions/authority:** [Permitted reads, writes, execution, and external actions; required authorization.]
- **Confirmation/bounds:** [Consequential actions needing approval; target, scope, and reversibility limits.]
- **Recovery/handoff:** [Rollback or safe transfer of control.]

## Grounding and uncertainty

- **Sources/verification:** [Evidence sources, relevance checks, and traceability.]
- **Gaps/conflicts:** [Disclose missing or conflicting evidence; don't reconcile without support.]
- **Certainty:** [Distinguish facts, inference, and unknowns; define when to qualify or abstain.]
- **Never assume:** [Facts, permissions, capabilities, or outcomes requiring verification.]

## Safety and privacy

[Data minimization, handling, disclosure/retention limits, untrusted-content handling, and refusal or escalation for unsafe or unauthorized requests.]

## Failure handling and handoff

[Surface errors and unavailable dependencies; bound recovery; label partial work; define stop conditions and decisions reserved for a human.]

## Output contract

[Format and level of detail. Include the result, evidence, limitations/unknowns, partial completion, risks, and human follow-up as relevant. Claim completion only when verified.]

## Testability and maintenance

[Observable acceptance checks; dependencies, versions, permissions, and assumptions to revisit; terminology to keep consistent.]
