# Evaluation record

Date: 2026-10-19. Scope: the two instruction-based skills in this repository.

## Concision revision

The entrypoints were reduced from 1,344 to 578 whitespace-separated words (57%); the duplicate format guide was merged into the existing template. The six original trials below describe the first version. Two independent trials were run against the shortened files:

- **Resume with a corrected learning status:** the learner said the specification stage had been skipped. The teacher corrected that stage to `skipped`, used a labeled reference specification, preserved its constraints and asked only the pending task-splitting exercise. It wrote a separate temporary checkpoint without changing the supplied original.
- **Author from two actual source files:** the builder inspected both files, proposed compatible inputs/outputs and a repair path, kept source conflicts unresolved, and requested confirmation of the assembled draft without claiming installation or execution.

Both passed reviewer inspection. Both shortened skills also passed `quick_validate.py`; relative links and the working diff were checked. Other original scenarios were not rerun after this wording revision.

The authoring agent inspected the responses and generated artifacts from independent agent trials. The agents received the skill, a realistic request and raw fixtures; they did not receive an expected answer. Follow-up user answers were scripted evaluation inputs, not evidence of a real learner's progress. Temporary fixtures and learning records stayed outside the public package.

## Observed behavior

| Trial | Observation | Result |
| --- | --- | --- |
| Beginner's first lesson | Started the bundled reading-club simulation in Chinese, explained A0, asked one clarification exercise, and waited without revealing the fictional owner's answer. | Pass |
| Incorrect answer | Given a question about button color, explained the missing behavioral decision and prompted a focused retry at the same stage. Did not mark it complete or execute a component skill. | Pass |
| Resume from a checkpoint | Restored the unanswered task-splitting exercise, preserved the learner's accepted capacity criterion and other A2 constraints, and did not restart earlier stages. | Pass |
| Missing acceptance evidence | Given a claim that three passing checks were enough, compared the packet with the restart requirement, kept review open for a retry, and saved `needs-practice` in the temporary checkpoint. Did not invent a restart result. | Pass |
| Builder with source files | Read two fictional note-processing skill definitions, distinguished source fidelity from external fact verification, and proposed a two-stage draft with explicit handoffs and a repair route. Requested confirmation of the assembled draft. | Pass |
| Builder after confirmation | Wrote and reread a fixed workflow in an isolated temporary folder. Reviewer inspection confirmed source-status notes, a coherent fictional case, two stage contracts, exercises/rubrics/reference artifacts, repair and skip routes, and a new transfer case. Approval was correctly attributed to the simulated user input. | Pass |

No real application, tracker issue, publication or message was created by these trials. Writes were limited to the builder's authorized temporary workflow definition and the teacher's temporary learning checkpoint.

## Packaging checks

- Both skills passed Codex's `skill-creator/scripts/quick_validate.py` frontmatter/scaffold checks.
- Reviewed English/Chinese README consistency, relative resource links, UI metadata and self-contained skill directories.
- Checked the publication contents for private local paths, credentials matching common token/private-key patterns, and unintended artifacts. This is a scoped publication check, not a general security audit.

## Limits and remaining scenarios

These are single-environment, scripted agent trials. They do not establish educational effectiveness with real learners, repeatability across models, or host compatibility beyond reading the instructions. The Skills CLI installation command follows its upstream documentation; it has not been run as a cross-host installation test.

The scenario catalog is broader than this run. Requested skips, material definition-version changes and unavailable source skills have not received independent behavioral trials. They remain documented scenarios rather than claimed passes. A full real-user lesson and transfer exercise are also still outstanding.
