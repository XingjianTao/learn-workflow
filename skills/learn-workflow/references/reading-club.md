# A small feature, from idea to evidence

- ID: reading-club-delivery
- Version: 1.0.0
- Status: author-approved bundled example
- Approval scope: this fictional teaching path; no real implementation is approved or verified by this label
- Reviewed: 2026-10-19
- Mode: simulation

## Purpose and entry

For someone who can converse with an AI assistant, including a non-programmer. Learn to clarify a material uncertainty, turn decisions into a specification, split coherent tasks, request evidence, review it, and leave a useful handoff. No coding, accounts, installation or command execution is required.

The role map is `clarify → specify → split → implement/check → review → record`. This is a deliberately small path, not a requirement to run every skill on every change.

## Source register

These sources were read on the review date. They are role references, not bundled dependencies, proof of installation or proof of current compatibility. This lesson freezes the contracts below; upstream changes do not silently change it.

| Role | Source | Relevant contract and effects |
| --- | --- | --- |
| Clarify | [grill-me](https://github.com/mattpocock/skills/blob/main/skills/productivity/grill-me/SKILL.md) and its `grilling` dependency | Resolve important decisions; do not implement during the interview |
| Specify | [to-spec](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-spec/SKILL.md) | Settled conversation → problem, behavior, scope and test decisions; real usage writes to a configured tracker |
| Split | [to-tickets](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md) | Specification → demonstrable slices with acceptance criteria and blocking dependencies |
| Implement/check | [implement](https://github.com/mattpocock/skills/blob/main/skills/engineering/implement/SKILL.md), [tdd](https://github.com/mattpocock/skills/blob/main/skills/engineering/tdd/SKILL.md) | Task → implementation and behavior checks; real use can change files, run tools, review and commit |
| Review | [code-review](https://github.com/mattpocock/skills/blob/main/skills/engineering/code-review/SKILL.md) | Compare actual changes against scope and repository standards; this lesson simulates that review, not its Git commands |
| Record | Generic progress-record role, not an installed skill claim | Evidence → accurate completion state and next task |

## Fictional case and artifacts

The fictional Elm Reading Club wants a signup page. The confirmed facts in **A0** are: at most 12 members, email only, each email counts once, registrations survive restart, no accounts, payment or automatic email. The one open decision is what to do when all 12 places are occupied. For this fixed case, the fictional organizer's answer, revealed after stage C, is **reject further signups with a clear full message; no waitlist**. This is case data, not an answer supplied by the learner.

Artifacts: A0 brief; A1 resolved brief; A2 specification; T1/T2 tasks; A3 implementation evidence packet; A4 review; A5 handoff. All application code/logs/results are SIMULATED.

## Contracts and routes

| ID | Role | Requires / input | Output and acceptance | Route |
| --- | --- | --- | --- | --- |
| C | Clarify | A0 | A1 resolves full-capacity behavior and preserves known constraints | S; retry C if question repeats a known fact |
| S | Specify | A1 | A2 states visible signup, uniqueness, persistence and full behavior with checks | T; retry S for vague or contradictory claims |
| T | Split | A2 | T1/T2 each deliver a testable behavior; dependencies reflect needed inputs | I; retry T for only UI/database/testing layers |
| I | Implement/check | Ready task plus A2 | A3 links acceptance criteria to behavioral evidence, with simulated status | R; retry I for unsupported claims |
| R | Review | A2, tasks, A3 | A4 identifies missing evidence or accepts scope/evidence | P if ready; I for repair R1 |
| P | Record | A4 and artifacts | A5 distinguishes rehearsal completion from real implementation and preserves next work | X transfer |

Wrong or partial answers stay at the current exercise. A requested skip uses its reference artifact and records `skipped`, not demonstrated. If the input is already a confirmed specification, enter at T; if it is a small, unambiguous correction, use I/R/P. These alternate entries do not waive their required inputs. No component skill is actually invoked in this lesson.

## C — Ask the missing question

Example: for a fictional delivery form, a decision about supported regions matters more than asking the user to choose a button color.

Exercise: **What one question about A0 must be answered before implementation, and why does it change the behavior?**

Rubric: identifies reject-versus-waitlist behavior at capacity and its effect on the product. Repeating the known limit of 12 is not enough. Then reveal the organizer's fixed answer above and form A1 with the learner's question and the supplied case answer.

Reference A1: at capacity, reject with a full message; otherwise accept one stored record per email; keep the 12-member cap and all A0 exclusions.

## S — Turn a decision into a check

Example: “search is fast” is vague; “searching for a known item returns that item” states an observable result.

Exercise: **Write one acceptance criterion for the full-capacity rule in A1, including the starting state and observable outcome.**

Rubric: starts with 12 accepted members, submits a new email, expects rejection/full feedback and an unchanged count of 12. A criterion that allows a waitlist contradicts A1. Carry the accepted criterion into A2, supplementing the other already-fixed constraints explicitly from A1.

Reference A2: accept a valid new email when there is space; one email counts once; at 12 reject a different email with count unchanged; saved registrations survive restart; no accounts/payment/automatic email/waitlist.

## T — Split into useful tasks

Example: a parcel tool's first slice could create one parcel record and display its tracking ID; a separate “database layer” alone is not that user-visible behavior.

Exercise: **Propose two tasks from A2, stating what each demonstrates and whether one blocks the other.**

Rubric: each task is a complete behavioral slice, together preserve A2, and dependencies are justified rather than every layer becoming a task. Equivalent sound splits are accepted and their IDs are carried forward. If using different IDs, map the later fixture's T1/T2 labels explicitly.

Reference: T1 accepts, stores and displays one registration, rejects a duplicate email and preserves records across restart. T2 builds on T1 to enforce the 12-member limit and full feedback. T2 is blocked by T1. Both have their respective acceptance checks.

## I — Ask for evidence

Example: “I changed the sorting code” reports an action; a known unsorted input and its checked sorted output provide behavioral evidence.

Exercise: **What before/after observation would show that retrying an existing email does not consume another place?**

Rubric: identifies a known starting unique-member count, repeats an existing email, expects the same count and no second stored registration. Does not rely only on a code screenshot or a success claim.

After acceptance, supply A3 as a fixed SIMULATED packet: adding a new email changes 11 to 12; repeating an existing email leaves 12; another new email is rejected at 12. Restart persistence has **not** been checked. These are fictional fixtures, not real tool results.

Reference A3 includes that packet and a clear `restart check missing` entry. Never silently fill that gap with a pass.

## R — Review what is missing

Example: a screenshot can demonstrate appearance, but it cannot alone establish what happens after a restart.

Exercise: **Can A3 close the work described by A2? Identify the evidence that determines your answer.**

Rubric: no; persistence across restart remains unverified. Preserve the other simulated observations without treating them as real tests. Route to repair I-R1.

Reference A4: block completion until a restart check verifies that registrations and duplicate handling persist.

### I-R1 — Repair the evidence gap

Example: a useful regression check recreates the boundary that previously failed or was missing.

Exercise: **Describe the restart check's setup, action and expected result.**

Rubric: create known registrations, restart, verify the same records/count remain, and retry an existing email without adding a duplicate. Then reveal this fixed SIMULATED repair fixture: records remain after restart and the duplicate is rejected. Re-review A3 plus this fixture against A2; the fictional evidence packet is now complete. Continue to P. If skipped, use this reference and retain the skipped status.

## P — Leave a truthful handoff

Example: “finished” loses context; a record naming the accepted behavior, its evidence and any unfinished task can be resumed.

Exercise: **Write a two-sentence handoff that reports this rehearsal accurately and tells a real implementer what remains.**

Rubric: states that the workflow/application evidence was simulated, links the decisions/tasks/evidence, and does not claim a real application was built or tested. Real implementation and actual validation remain.

Reference A5: “SIMULATED: A1/A2, T1/T2 and the reviewed A3 packet preserve the capacity, uniqueness and restart requirements. A real implementer still needs to build the feature and run those checks; learning gaps remain recorded separately.”

## X — Transfer to a new case

Case: a fictional museum already approved a specification for equipment loans: no more than 5 concurrent loans, each item can be on loan only once, and records survive restart. Nothing has been implemented.

Challenge: **Choose the next skill/role and describe the artifact it should receive and produce, including one constraint that must survive the handoff.**

Rubric: start with task splitting from the approved specification, not another broad interview or a completion report. Produce demonstrable tasks with dependencies and preserve at least one stated constraint, while recognizing that all three belong to the specification. Accept a justified small single-task implementation path if the learner explains its scope and verification inputs. Record demonstrated transfer separately from any skipped stages.

## Revisions

This version stays fixed during a lesson. Equivalent phrasing and sound task splits within its constraints are allowed. Changes to case rules, role contracts or exercise goals require a new definition version; do not change the rules to make an incorrect answer pass.
