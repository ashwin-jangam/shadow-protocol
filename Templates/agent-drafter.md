---
name: "[agent-name]"
description: "[What this agent does and when to use it.]"
---

# [Agent title]

## Purpose and scope

[Who the agent is for, what it does, and what result it should produce.]
- **Use for:** [Tasks or goals it should help with.]
- **Exclude:** [Tasks it must not do.]
- **Prerequisites/completion:** [What it needs to start; how to tell it is done.]

## Inputs and context

- **Inputs/context:** [What information it needs and what optional details may help.]
- **Authorized sources:** [Information and files it is allowed to use.]
- **Boundaries:** [What it must not access or assume.]
- **If unclear:** [When it should ask, pause, or stop.]

## Instructions

1. **Establish:** [Confirm the goal, scope, inputs, and permission.]
2. **Gather:** [Review relevant information and check it.]
3. **Act:** [Complete the task in clear, repeatable steps.]
4. **Validate:** [Check the result against the request and done criteria.]
5. **Report/handoff:** [Summarize the result, evidence, limits, and decisions for the user.]

- **Decision rules:** [What to do when important conditions occur.]
- **Stop when:** [The request is unclear, permission is missing, work is unsafe, or a blocker cannot be resolved.]

## Tools and integrations

[For each tool or integration, explain what it does, how to use it, when it is available, its permissions, inputs, outputs, and limits. Write "None" if there are no tools. Don't claim a tool was tested without evidence.]

- **Host/harness:** [Platform and version, or "Unspecified."]
- **Tools/integrations:** [List tools and explain their use, or link to documentation.]

## Authorization and side effects

- **Allowed actions/authority:** [What it may read, change, run, or do externally; what permission it needs.]
- **Confirmation/bounds:** [What needs approval, what the approval covers, and how to undo it if possible.]
- **Recovery/handoff:** [How to undo permitted changes or safely hand work to a person.]

## Grounding and uncertainty

- **Sources/verification:** [What information to use, how to check it, and how to show where conclusions came from.]
- **Gaps/conflicts:** [How to report missing or conflicting information; don't resolve conflicts without evidence.]
- **Certainty:** [How to distinguish facts, conclusions, and unknowns; when to qualify or decline to answer.]
- **Never assume:** [Facts, permissions, abilities, or results that must be checked.]

## Safety and privacy

[How to limit and handle data, protect private information, treat untrusted content, and refuse or escalate unsafe or unauthorized requests.]

## Failure handling and handoff

[How to explain errors or unavailable tools, limit recovery attempts, label unfinished work, and identify when to stop or ask a person.]

## Output contract

[Format and level of detail. Include the result, supporting evidence, limits or unknowns, unfinished work, risks, and any needed user action. Say work is complete only when checked.]

## Testability and maintenance

[Checks that show the agent works as intended; tools, versions, permissions, and assumptions to review when things change; terms to use consistently.]
