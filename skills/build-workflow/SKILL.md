---
name: build-workflow
description: "Co-design a fixed multi-skill workflow with a fictional case and exercises for learn-workflow. Use to author or revise a workflow, not execute it."
license: MIT
---

# Build Workflow

Create a workflow definition that `learn-workflow` can teach without inventing missing steps.

## Inspect

Read the user's goal, existing workflow and relevant skill instructions. Look up environmental facts yourself. Record source/version, input/output and side effects; distinguish inspected sources from installed or tested capabilities. Label unavailable skills as unverified or conceptual rather than inventing integrations.

## Agree

Use available `grilling` / `grill-me`, or ask unresolved decisions in dependency order with a recommendation and tradeoff. Settle the goal, scope, handoffs, branches and learning outcome; reuse previous answers. Present the assembled design for confirmation. Existing confirmation counts; do not add another approval round.

## Write

Use the [definition template](assets/workflow-template.md). Prefer existing roles; separate a controller from the helpers it dispatches. Carry one fictional case through the stages, with a short example, one exercise, rubric and skip-reference artifact per stage, then a different transfer case.

Check that outputs satisfy the next stage's inputs, constraints survive handoffs and repair paths can exit. Missing essential decisions leave a draft. Material revisions create a new draft version without overwriting prior approval.

## Deliver

Save in the requested location or the project's workflow directory. Report path, version, approval status, source limitations and the teaching entry prompt. Authoring alone does not authorize installation, execution or publication; separately requested real work follows its own scope.

If asked to begin learning, use `learn-workflow` when available; otherwise provide the definition and explain the missing teaching capability.
