# Learn Workflow

[简体中文](README.zh-CN.md)

Learn how skills work together by practicing with a fictional case. This repository contains two portable, instruction-based agent skills:

| Skill | What it does |
| --- | --- |
| **build-workflow** | Interviews you, checks the selected skills' actual contracts, and authors a confirmed workflow with a fictional case and exercises. |
| **learn-workflow** | Teaches that fixed workflow one step at a time, evaluates your answers, and carries each accepted artifact into the next step. |

The builder defines the process. The teacher follows a versioned definition. Neither is an automatic workflow execution engine.

## Quick start

Install both skills with the [Skills CLI](https://github.com/vercel-labs/skills) (requires Node.js/npm):

```sh
npx skills add XingjianTao/learn-workflow --skill build-workflow --skill learn-workflow
```

Alternatively, copy `skills/build-workflow/` and `skills/learn-workflow/`, including their resources, into your agent's supported skills directory. For a Codex project, that can be `.agents/skills/`. Beyond your existing AI host, the lessons require no additional API key, Python package, external account or separate application. Your host must support reading skill instructions and conversational interaction; persistence also needs a writable workspace.

Start with the bundled example:

> Use $learn-workflow to teach me the bundled reading-club workflow in English. Start with the first exercise and wait for my answer.

Or build your own:

> Use $build-workflow to help me design a workflow for turning research notes into a reviewed report. Read the skills I provide, grill the unresolved decisions, and save a fixed workflow with a fictional case and exercises to workflows/research-report.md.

Then:

> Use $learn-workflow to teach workflows/research-report.md, one exercise at a time.

Invocation syntax differs by host; explicitly asking the agent to read the selected `SKILL.md` is also possible. Reading a skill file does not prove that a host has registered it.

## How the lesson works

1. Load an author-approved bundled lesson or a user-confirmed workflow definition.
2. See a short example and the current input artifact.
3. Choose the next action or produce a small artifact yourself.
4. Receive specific feedback. Repair a missing constraint before proceeding.
5. Reuse the accepted artifact in the next stage.
6. Try a new fictional case to check whether the workflow transfers.

The bundled [reading-club lesson](skills/learn-workflow/references/reading-club.md) walks through clarification, specification, task splitting, implementation evidence, review and progress recording. It includes a missing restart check so the learner practices returning for evidence rather than declaring success early.

The teacher distinguishes demonstrated understanding, self-report, skipped material and remaining practice. A local or in-chat checkpoint preserves the exact pending exercise and accepted artifacts. It does not treat “lesson shown” as “skill learned.” Lessons can be explained in the learner's language without changing the case rules.

## Simulation and real work

Practice is explicitly **SIMULATED**. The teacher does not invoke implementation skills, install packages, create real issues, commit, publish or send messages to demonstrate a workflow. It may maintain a learning checkpoint in a designated folder. A request for hands-on execution is handled separately with a concrete target and the normal authorized tools.

`build-workflow` reads supplied/local skill definitions or authoritative sources when available. It records source limitations and does not install missing skills. `grilling` is an optional interview aid; a self-contained interview pattern is included. `learn-workflow` consumes the resulting fixed definition and does not dynamically assemble a new workflow from installed skills.

## Repository map

```text
skills/
  build-workflow/
    SKILL.md
    agents/openai.yaml
    assets/workflow-template.md
    references/workflow-format.md
  learn-workflow/
    SKILL.md
    agents/openai.yaml
    references/checkpoint.md
    references/reading-club.md
evals/scenarios.md
```

Each skill's required resources live inside its own directory so it can be installed separately. Workflow definitions may live anywhere the host can read; the builder's [format guide](skills/build-workflow/references/workflow-format.md) describes the contract.

## Verification and limits

[Behavioral evaluation scenarios](evals/scenarios.md) cover initial teaching, incorrect answers, resumption, simulation boundaries and workflow authoring. These are agent-level exercises, not an automated execution engine or a guarantee of compatibility with every host. Validation results are recorded in [evals/RESULTS.md](evals/RESULTS.md).

The skills are instructions: models may still make mistakes. Check important artifacts and do not mistake fictional results for actual test evidence. Source references in a fixed lesson describe the inspected version/date, not a promise about future upstream changes.

## Credits and license

Original implementation by Xingjian Tao. The interview, artifact-driven delivery and evidence-based learning approaches were informed by [Matt Pocock's skills](https://github.com/mattpocock/skills), particularly `grilling`, `to-spec`, `to-tickets`, `teach` and `ask-matt`. Those skills are not vendored or required runtime dependencies. See [ATTRIBUTION.md](ATTRIBUTION.md).

Released under the [MIT License](LICENSE).
