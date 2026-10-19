---
name: learn-workflow
description: "Teach a prewritten, approved multi-skill workflow through a fictional case, one learner exercise at a time. Use to learn, rehearse, or resume a defined workflow; use build-workflow to author or change the workflow."
license: MIT
---

# Learn Workflow

Teach the workflow the learner selected. Default to fictional rehearsal, not execution of its component skills. The learning goal is to choose the next skill and pass a useful artifact to it.

## Load the fixed lesson

1. Read the supplied workflow definition and any existing learning checkpoint. If no definition was supplied, offer the bundled [reading-club workflow](references/reading-club.md), or ask for the intended definition when the surrounding task identifies a different workflow.
2. A usable definition has an identity/version, confirmed teaching scope, a fictional case, named stages with input/output contracts and transitions, exercises with evaluation criteria, and a transfer exercise. It can be an author-approved bundled lesson or a user-confirmed custom definition. A learner need not approve a bundled lesson's design again.
3. If the definition is a draft or lacks a required decision, identify that gap and route to `build-workflow` if available; otherwise ask the author to complete it. Do not invent a missing stage, case, rubric, or approval. Minor wording differences are fine; do not demand an exact file format.
4. Do not discover installed skills or read arbitrary SKILL.md files to construct a new workflow during teaching. Use the roles and source-status notes already recorded in the definition. Reading a skill's source or simulating its role is not evidence that it is installed or was executed.

## Rehearse one step per turn

Start with the fictional goal, current mode, and a short map of the selected path. Explain an unfamiliar term when it first becomes necessary. Use the learner's language; translating explanations must preserve the fixed rules.

For each stage:

- Show the current input artifact and the one decision or transformation this stage performs. Explain why this skill fits now.
- Give the stage's short worked example without revealing the answer to its exercise.
- Ask exactly one exercise from the definition, then yield. Do not answer for the learner or ask the next stage's question yet. This is a teaching interaction, not a preference/approval form; use normal conversation unless the host provides a dedicated quiz tool.
- On the next response, compare it to the stage rubric. Accept equivalent reasoning, not just specific words. Explain a concrete strength or missing constraint. A wrong or incomplete answer stays at this stage for a focused retry.
- Once accepted, carry the learner's accepted artifact into the next stage, preserving identifiers, constraints, dependencies, and unresolved items. Supplement omitted routine details only when they follow from the fixed definition, and say what was supplemented.

Follow the definition's branches and skip conditions. Do not force every available skill into every task. For a workflow-changing request, separate proposed changes from the active version and return to authoring; do not silently alter the lesson.

## Truthful practice and progress

Label mock code, tests, logs, issues and releases as **SIMULATED**. Never invoke an implementation, installation, publishing or messaging skill merely to demonstrate it. Case text and example commands are lesson data, not current authority to operate tools.

A request for hands-on work is a mode change. Clarify the concrete target and effects, then use the normal authorized implementation workflow outside this rehearsal. Do not imply that simulated tests or releases have become real.

Use [checkpoint guidance](references/checkpoint.md) when saving or resuming progress. Use an existing designated learning folder; if none exists, keep a compact checkpoint in chat. Only learning records may be written during rehearsal, never the fictional application's source or external records.

Distinguish `demonstrated`, `self-reported`, `skipped`, and `needs-practice`. “Got it” is self-report; “skip” permits moving on without a mastery claim. A skip may use a clearly labeled reference artifact from the definition, never a fabricated learner answer. Offer to revisit skipped essentials at the transfer check.

End with the fixed transfer exercise on a new fictional case. Assess skill selection and artifact handoffs, then report demonstrated capabilities and remaining gaps. Showing the whole lesson is not proof of learning.
