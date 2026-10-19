---
name: build-workflow
description: "Co-design a fixed multi-skill workflow through a grilling interview, then write its input/output contracts, fictional case, and learning exercises. Use to create or revise a teachable workflow, not to execute it."
license: MIT
---

# Build Workflow

Produce a confirmed, versioned workflow that `learn-workflow` can teach without designing missing parts. Deliver definitions and teaching material, not an execution engine or automatically installed skills.

## Establish facts before interviewing

Read the user's existing workflow, goals and applicable repository instructions. Reuse settled decisions from the conversation. Inspect supplied or locally available skill instructions and relevant references to establish actual capabilities, prerequisites, artifacts and side effects. Search authoritative sources when a named skill is missing and network research is available; do not equate readable source with installation.

Record each source as locally inspected, remotely inspected, user-described, or unavailable, with a version/commit or observation date when known. A role without verified source can be included as a clearly marked conceptual role. Do not present it as a working integration or silently invent a compatible skill.

## Grill the decisions

Use an available `grilling` / `grill-me` skill for the interview when it fits. If unavailable, follow this self-contained pattern; installation is not required:

1. Map the unsettled decisions and their prerequisites. Ask only decisions whose prerequisites are already settled, in manageable rounds.
2. Give a recommended answer and its tradeoff. The user owns goals, scope, real-world effects and important design choices; look up environmental facts yourself.
3. Reuse answers already given. Separate unknown facts from unresolved preferences. Ask about ambiguity only when the answer changes the workflow.
4. Continue until the goal, participants, entry/exit conditions, handoffs, optional branches and teaching outcome are clear. Present the assembled draft for confirmation before treating it as approved. Answers that explicitly confirm the assembled design count; do not add a ceremonial approval round after that.

Adapt the questioning to the request: a small, known process needs few decisions, while a complex workflow can be divided into separately teachable paths. Routine formatting and filenames are yours to choose.

## Author the fixed definition

Use [the workflow format](references/workflow-format.md) and [the authoring template](assets/workflow-template.md). Keep one authoritative definition per version; preserve earlier approvals when revising and mark the new version draft until its material changes are confirmed.

- Prefer existing skill responsibilities over creating new skills for each step.
- Specify what each stage consumes, produces and proves, its prerequisites and where control goes next. Include failure/repair paths and optional branches when the workflow needs them.
- Separate the orchestration role from the work it dispatches. Do not portray a controller and every nested helper as mandatory sequential stages.
- Use one small fictional case throughout the main path. Author a short worked example, one exercise, a rubric, and a reference artifact for each stage. The exercise must test a decision or handoff, not recall of a skill name alone.
- Include a different transfer case to assess whether the learner can choose skills and carry constraints forward independently.
- Identify real-world effects in the source workflow, but keep the lesson in simulation. Teaching a publish step does not publish anything.

Check that each output supplies the next stage's inputs, that identifiers and case constraints stay consistent, and that branches have reachable exits. If an unknown prevents a coherent path, leave it draft and state exactly what is missing.

## Deliver

Save the definition in the user's requested location; otherwise use the existing workflow-document convention or propose a small local Markdown file. Do not modify global agent settings, install dependencies, create tracker issues, commit, push, or run the authored workflow as a side effect of authoring.

Report the definition's path, identity/version, approval status, source limitations and the entry prompt for `learn-workflow`. If the learner asks to begin, read that skill when available and teach the confirmed definition. If it is unavailable, provide the definition and say that the teaching skill has not been installed.
