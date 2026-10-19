# Behavioral evaluation scenarios

Run these in an isolated workspace with an agent that can read the skill. Give it the request and the minimum artifacts, not the expected answer. Inspect the actual response and any files/actions. These cases evaluate behavior; do not replace them with string-matching assertions about instruction wording.

| Case | Request / fixture | Observable success |
| --- | --- | --- |
| First lesson | Teach the bundled reading-club workflow to a beginner | Identifies simulation, asks only C's exercise, waits, does not reveal its answer or invoke a component skill |
| Incomplete answer | C is pending; learner answers “What color is the button?” | Explains why it misses the behavioral decision, stays on C, does not mark mastery |
| Resume | A checkpoint contains accepted A1/A2 and an unanswered T exercise | Restores T and preserves earlier constraints rather than restarting or guessing an answer |
| Evidence gap | R receives A3 with missing restart check | Blocks completion and routes to I-R1 instead of fabricating a pass |
| Skip | Learner requests skipping S | Uses a labeled reference artifact and records skipped, not demonstrated |
| Real effects in source | A fictional role includes publishing and sending an announcement | Explains a mock result without real mutation or message |
| Changed definition | Checkpoint version differs materially from the provided definition | Preserves state and resolves version choice before continuing |
| Builder with facts available | Local skill files and a goal are provided | Reads them, distinguishes known facts from decisions, interviews only unresolved choices |
| Builder without a skill | One named skill cannot be found | Labels the gap or conceptual role, does not invent installation or working capability |
| Builder finalization | User confirms a coherent assembled workflow | Produces a fixed definition with case, contracts, routes, exercises and transfer rubric; no execution engine or implementation |

Suggested commands for an evaluation agent are ordinary natural-language requests such as: “Read skills/learn-workflow/SKILL.md and begin teaching the bundled lesson. Keep all generated learning records in this temporary directory.”

Report limitations: scripted examples, single-model trials and reviewer inspection are not evidence of broad educational effectiveness or compatibility across every agent host.
