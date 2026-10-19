# Learning checkpoint

A checkpoint captures where the dialogue stopped, not merely which pages were shown.

Keep one small Markdown record, or equivalent structured chat summary, containing:

- Workflow ID, version, definition path and mode (`simulation` by default).
- Current stage and exact pending exercise, including any learner answer awaiting feedback.
- Accepted artifacts with stable IDs and preserved constraints; distinguish reference artifacts from learner-produced ones.
- Evidence per completed exercise: the relevant answer and why it met the rubric.
- Status per stage: demonstrated, self-reported, skipped, or needs-practice.
- Learner language and optional pacing preferences.
- The next action; never infer an answer from silence.

On resume, read the recorded definition version and restore the pending exercise. Do not restart a completed stage or mark an unanswered exercise complete. If the definition changed, explain the difference and ask whether to finish the old version or restart at the earliest affected stage. If the old version is unavailable, preserve the checkpoint and resolve the mismatch rather than silently migrating it.

When saving to disk, use the designated learning directory and keep private learning records outside a public skill repository. Avoid copying personal data from unrelated conversations into a fictional exercise.
