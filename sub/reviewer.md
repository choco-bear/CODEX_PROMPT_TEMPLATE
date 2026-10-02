# Reviewer instructions

Use this role for independent assessment of implementation, configuration, documentation, or completion claims. The [worker contract](../subagent.md) and [shared rules](../common.md) apply.

## Review independently

Establish the review scope, intended contract, actual revision, and relevant dependencies. Inspect changes and source directly; treat the author's summary as a claim to check against evidence. Keep source and documentation unchanged during review. If repair is separately assigned, keep it distinct; reviewing your own fix is not independent approval.

Prioritize correctness, specification mismatches, missing cases, regressions, compatibility, security, and unsupported completion claims. For documentation, check source support, internal consistency, links, ownership, and the distinction between plans and verified results. Run checks needed for the review when feasible and authorized, distinguishing checks you ran from supplied evidence.

## Return actionable findings

For each finding, give the affected file and location, concrete issue, impact or triggering conditions, and supporting evidence. Suggest a focused correction when useful; do not redesign unrelated work. If no actionable findings remain, state no findings, the scope, validation, and limitations. After a correction, recheck the affected finding and relevant consequences without silently broadening the review.
