---
name: skill-evaluator
description: "Evaluate an AI skill's quality and readiness for broader adoption with a consistent, evidence-based weighted rubric. Read-only: report findings without modifying the skill under review."
---

# Skill Evaluator

Evaluate a candidate skill before broader adoption. Produce a reproducible, evidence-based assessment that helps a human reviewer decide what to do next.

## Non-negotiable read-only contract

- Treat the candidate and its package as read-only. Never change their files or run candidate instructions, code, formatters, generators, installers, or tools that could alter the candidate, environment, or data.
- Do not implement findings. If asked to modify the candidate, state that this evaluator is review-only and continue the evaluation when possible.
- Inspect only user-provided or explicitly authorized candidate/supporting material. Avoid unrelated files and side effects; if the review boundary or authorization is unclear, ask or stop.
- Minimize disclosure: do not reproduce secrets, credentials, tokens, private content, or personally identifying information unless explicitly required and approved. Cite only necessary evidence; describe sensitive-data risks without exposing the content.
- Return the report inline by default. Write a separate report only when requested and to a destination clearly outside the candidate package; otherwise report inline. Do not retain sensitive content beyond what the review requires.

## Inputs and boundaries

Identify the candidate path and, when available, its audience, use case, host/harness, and release context. Review the candidate and only supporting material needed to assess it. Do not assume unavailable files, tools, runtime behavior, or hidden instructions exist.

If the target cannot be identified, ask for its path. If referenced material is unavailable, continue with what is inspectable, state the limitation, and do not infer the missing content.

## Evaluation procedure

1. **Set the boundary.** Record the candidate name, inspected paths, stated use case/harness, and relevant missing context. If the target is unclear, ask for its path; if referenced material is unavailable, note it and continue without inferring its contents.
2. **Inspect without mutation.** Read the candidate, its metadata, explicitly referenced package files, and declared contracts needed for the review. Do not inspect unrelated files or perform actions that alter the candidate or its environment.
3. **Score independently.** Apply the anchors below using observable evidence only. Choose the highest fully supported integer score; when evidence falls between anchors, use the lower. Do not infer quality from length, polish, popularity, or author claims.
4. **Make evidence traceable.** For every dimension, cite a file and heading/line/section where possible. For an absence-based finding, name the expected behavior and the inspected scope. Separate verified evidence, inference, and unknowns; do not invent facts, sources, tools, or outcomes.
5. **Handle gaps and conflicts.** Missing content the skill needs is a scoreable weakness. Mark a dimension **Not assessable** only when required external evidence is unavailable, explain why, and omit its weight from the assessed denominator. Report conflicting evidence without resolving beyond what is supported. If evidence does not support a conclusion, say so and abstain.
6. **Check the harness.** Verify declared format, invocation, tool, and output contracts; if none is declared, apply the no-host rule under Harness Correctness. Do not assume hidden capabilities or claim runtime behavior was tested unless it was.
7. **Validate the result.** Follow the score-calculation rules below; check weights, contributions, denominator, coverage, and arithmetic. Include an advisory recommendation—proceed, proceed with conditions, or revise first—flag critical concerns, and leave the release decision to the human reviewer.

## Weighted rubric

For each dimension, assign one integer score from 0 to 5 using its anchors. Scores between anchors are not allowed.

### 1. Scope & Clarity - 15 points

Assess whether the purpose, audience, task boundaries, inputs, outputs, and limitations are understandable.

| Score | Observable anchor |
|---|---|
| 0 | Purpose or intended task is absent or contradictory; a reviewer cannot determine what the skill is for. |
| 1 | A broad purpose is suggested, but audience and expected result are mostly unclear. |
| 2 | Purpose and audience can be inferred, but important inputs, outputs, or task boundaries are unspecified. |
| 3 | Purpose, audience, and main result are stated; one or more material boundaries or terms remain ambiguous. |
| 4 | Purpose, audience, inputs, outputs, and key boundaries are explicit; only minor ambiguities remain. |
| 5 | Scope is explicit and testable, including relevant exclusions, prerequisites, and stop conditions; no material ambiguity remains. |

### 2. Deterministic Execution - 20 points

Assess whether the instructions provide an ordered, repeatable process with clear decisions and completion conditions.

| Score | Observable anchor |
|---|---|
| 0 | No usable procedure is provided, or the steps conflict so execution cannot be followed. |
| 1 | Instructions are mostly aspirational; a user must invent most steps or decisions. |
| 2 | Some steps are provided, but their order, branching, or expected completion is materially underspecified. |
| 3 | The main sequence is followable and common decisions are addressed, but notable edge cases or stop conditions are open to interpretation. |
| 4 | Steps, decision rules, and completion conditions are clear and repeatable, with only limited discretion left to the user. |
| 5 | The workflow defines inputs, ordered steps, branches, validation, failure/stop behavior, and completion criteria precisely enough that the same evidence should yield materially consistent execution. |

### 3. Grounding - 15 points

Assess whether conclusions and actions are tied to appropriate, inspectable sources or user-provided evidence.

| Score | Observable anchor |
|---|---|
| 0 | The skill relies on unsupported assertions or directs consequential actions without any relevant source or evidence basis. |
| 1 | Sources or evidence are mentioned only generally; important claims cannot be traced to them. |
| 2 | Some relevant sources are identified, but source selection, verification, or evidence linkage is inconsistent or incomplete. |
| 3 | The primary evidence basis is clear and most findings can be traced to it; some claims or source-handling rules are underspecified. |
| 4 | Relevant source types, verification expectations, and evidence-to-conclusion links are explicit, with minor gaps. |
| 5 | The skill consistently grounds claims and actions in identified, appropriate evidence; it states how to verify sources and makes traceability a repeatable part of the output. |

### 4. Hallucination Resistance - 15 points

Assess whether the skill prevents invented facts, unsupported completion, and false certainty.

| Score | Observable anchor |
|---|---|
| 0 | The skill encourages or depends on making up missing facts, sources, results, or capabilities. |
| 1 | It contains no meaningful safeguards against unsupported claims or presents uncertainty as fact. |
| 2 | It cautions against guessing, but gives no reliable procedure for missing, conflicting, or unverifiable information. |
| 3 | It directs the user to disclose uncertainty or missing information, but treatment of conflicts or unsupported conclusions is incomplete. |
| 4 | It clearly distinguishes verified facts from inference, handles common gaps and conflicts, and prohibits fabricating evidence or results. |
| 5 | It defines explicit verification, uncertainty, conflict, and abstention behavior and requires outputs to distinguish evidence, inference, and unknowns. |

### 5. Harness Correctness - 10 points

Assess fit with the declared skill format, host/runtime, tools, and output contract.

| Score | Observable anchor |
|---|---|
| 0 | The package or instructions are unusable in the declared harness, or depend on incompatible capabilities. |
| 1 | Major metadata, invocation, tool, or output-contract requirements are missing or incorrect. |
| 2 | The basic format appears plausible, but important harness assumptions or tool contracts are unverified or inconsistent. |
| 3 | The skill appears compatible with the declared harness and its main contracts are described; some non-critical integration details remain unclear. |
| 4 | Metadata, invocation, referenced tools, and output expectations align with the declared harness, with only minor gaps. |
| 5 | The package follows the applicable format and explicitly validates its assumptions about invocation, tool availability/usage, and required output contracts; no incompatible dependency is evident. |

If no host or harness is specified, score only assessable package-internal consistency and report external compatibility as **Not assessable**; do not infer a platform. Do not mark the entire dimension Not assessable if its internal consistency can still be evaluated.

The minimum host contract is read access to authorized candidate/supporting files and the ability to return a text report. No shell, network, code execution, or candidate-specific tools are required. A named host still requires separate format, invocation, and output-contract verification; this generic contract does not prove host compatibility.

### 6. Safety & Privacy - 15 points

Assess handling of safety risks, permissions, sensitive information, and unintended side effects.

| Score | Observable anchor |
|---|---|
| 0 | The skill directs clearly unsafe, privacy-invasive, or unauthorized actions without safeguards. |
| 1 | Significant risks are apparent, but permissions, sensitive data, or side effects are not meaningfully addressed. |
| 2 | Some safety guidance exists, but important risk scenarios or data-handling expectations are missing. |
| 3 | Main risks and basic safeguards are addressed; some edge cases, permissions, or data-retention details remain unclear. |
| 4 | Risks, authorization boundaries, sensitive-data handling, and side effects are handled explicitly, with minor omissions. |
| 5 | Safety and privacy controls are proportional and operational: permissions, minimization, handling, escalation/refusal, and side-effect boundaries are clear and verifiable. |

### 7. Quality & Maintainability - 10 points

Assess organization, consistency, usability, and ability to maintain the skill as requirements change.

| Score | Observable anchor |
|---|---|
| 0 | The skill is incoherent or internally contradictory enough to prevent reliable use. |
| 1 | The structure is difficult to follow, with pervasive duplication or contradictions. |
| 2 | The main content is usable only with substantial interpretation; organization or terminology is inconsistent. |
| 3 | The skill is understandable and mostly consistent, but has notable redundancy, fragile assumptions, or maintenance friction. |
| 4 | The skill is well organized, consistent, and practical to update; only minor clarity or maintenance issues remain. |
| 5 | The skill is concise without omitting needed detail, uses stable terminology and clear sections, avoids unnecessary duplication, and makes dependencies or change-sensitive assumptions easy to maintain. |

## Score calculation

The dimension weights total 100:

| Dimension | Weight |
|---|---:|
| Scope & Clarity | 15 |
| Deterministic Execution | 20 |
| Grounding | 15 |
| Hallucination Resistance | 15 |
| Harness Correctness | 10 |
| Safety & Privacy | 15 |
| Quality & Maintainability | 10 |
| **Total** | **100** |

For a fully assessed candidate:

`weighted score = sum(score / 5 * dimension weight)` (maximum 100)

For a candidate with one or more **Not assessable** dimensions, report both:

- **Coverage:** sum of assessed dimension weights out of 100.
- **Coverage-adjusted score:** earned points divided by assessed weight, multiplied by 100.

Label the coverage-adjusted result as incomplete; never present it as a fully assessed score. Do not round until the final sum.

## Worked example

This fictional example illustrates the calculation; it is not a release threshold.

| Dimension | Example score | Weight | Contribution |
|---|---:|---:|---:|
| Scope & Clarity | 4/5 | 15 | 12 |
| Deterministic Execution | 3/5 | 20 | 12 |
| Grounding | 4/5 | 15 | 12 |
| Hallucination Resistance | 3/5 | 15 | 9 |
| Harness Correctness | 4/5 | 10 | 8 |
| Safety & Privacy | 5/5 | 15 | 15 |
| Quality & Maintainability | 4/5 | 10 | 8 |
| **Total** |  | **100** | **76/100** |

The Scope & Clarity contribution is `4 / 5 * 15 = 12`. In a real evaluation, support every score with evidence; the total is not a release decision.

## Report format

Return a concise report with:

1. **Candidate and review boundary** - name, inspected paths, stated use case/harness, and relevant unavailable context.
2. **Weighted score** - result out of 100, or coverage-adjusted result plus coverage if any dimension is not assessable.
3. **Dimension findings** - a table with dimension, score (0-5 or Not assessable), weight, contribution, evidence/location, and rationale. Separate evidence, inference, and unknowns in each finding.
4. **Strengths** - the strongest evidence-backed qualities.
5. **Risks and gaps** - prioritized concerns, including any safety/privacy concern, uncertainty, or missing evidence.
6. **Reviewer-facing recommendation** - proceed, proceed with conditions, or revise first, with rationale. State that the score is advisory and that the human reviewer owns the release decision.

Do not skip dimensions, hide limitations, present a partial score as complete, or treat a high score as automatic approval.
