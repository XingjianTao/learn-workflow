# Fixed workflow definition, format 1

This is a readable authoring contract, not a runtime language. No parser or execution engine is required. `learn-workflow` consumes a complete definition, not a list of skill names.

Required content:

| Part | What it must establish |
| --- | --- |
| Identity | Stable ID, version, title, author-approved bundled lesson or user-confirmed custom workflow, approval scope/date |
| Purpose | Learner outcome, intended audience, entry conditions, completion evidence |
| Source register | Role/skill, source location, inspected/version/date status, actual inputs/outputs and relevant side effects; distinguish source availability from installed capability |
| Fictional case | Small scenario, stable facts/constraints, explicit non-goals, initial artifact |
| Stage contracts | Stable stage ID, skill/role, prerequisites, input artifact, output artifact, acceptance criteria, next/repair/skip routes |
| Teaching material | For each stage: short non-answer example, one exercise, evaluation rubric, reference artifact for a learner-requested skip |
| Branches | Explicit guards, alternate path and rejoin/exit; for parallel branches, a join requires their necessary outputs |
| Transfer | A new fictional scenario, one final challenge and a rubric testing selection and handoffs |
| Revision policy | Who confirms material changes; what is immutable while a lesson is active |

Roles can be general concepts or concrete agent skills. Label that distinction. Never claim generic role descriptions prove tool compatibility.

An approval means the intended behavior and teaching path are accepted, not that the underlying software has run or passed tests. For a shipped example, `author-approved example` is sufficient; for a custom definition, record the user's confirmation accurately. A date alone does not create approval.

For simple workflows, keep the contracts in a table and exercises in short sections. Split long workflows into named learning paths, preserving necessary gates and dependencies. Avoid copying entire upstream skills: capture the relevant contract and link the inspected source. Respect licenses when reusing actual text.
