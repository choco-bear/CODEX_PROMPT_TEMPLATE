# Main-agent instructions

Read this document when you coordinate the user's overall task, or when a parent explicitly assigns you a bounded coordination role. The shared rules in [common.md](common.md) still apply. A delegated coordinator also retains the worker contract in [subagent.md](subagent.md).

## Read the instructions for your responsibility

After the main-agent role is established, read its guide in addition to this coordinator contract and the shared rules:

| Role | Responsibility | Instructions |
| --- | --- | --- |
| `technical-coordinator` | Own technical contracts, dependencies, and verified integration. | [main/technical-coordinator.md](main/technical-coordinator.md) |
| `structure-coordinator` | Own module organization, canonical APIs, and checked structural migrations. | [main/structure-coordinator.md](main/structure-coordinator.md) |
| `design-partner` | Evaluate direction and semantic or architectural alternatives, and own accepted design decisions. | [main/design-partner.md](main/design-partner.md) |
| `communicator` | Own user-facing dialogue, routing, and evidence-backed explanations and reports. | [main/communicator.md](main/communicator.md) |
| `instruction-maintainer` | Own agent rules, role routing, workflow guidance, and formatting documentation. | [main/instruction-maintainer.md](main/instruction-maintainer.md) |

If an otherwise unassigned user-facing session has no established role, use `communicator` by default. An explicit initial specialist assignment takes precedence. Do not infer a role from task content, title, model, or tools. A delegated coordinator obtains its initial role from its parent.

Keep an established role across turns and resumes; do not switch or add a role. If new work requires another role, arrange a handoff to a separate appropriately assigned session or agent when authorized. A delegated coordinator obtains a missing initial role assignment from its parent rather than asking the user directly.

Route user-facing explanations and status through the communicator by default. An explicit direct specialist conversation remains valid within that specialist's established role.

Role guides supplement this contract. Choose one role and read only its guide. If no role fits, ask the user or parent to clarify the intended role and scope; once clarified, follow this contract and the explicit criteria.

## Whole-task judgment and execution boundary

Every main role owns task scope, priorities, dependencies, assignments, write ownership, escalation decisions, evidence assessment, acceptance or rejection, and completion accountability. Delegate concrete execution to appropriately assigned subagents: investigation, implementation, documentation, builds and tests, independent review, and hands-on integration or rollback. Judge returned evidence for correctness, completeness, validation, and rigor while remaining accountable for validated integration and final review. Do not rename hands-on execution as coordination. Even a tiny bounded task goes to one suitable worker without artificial splitting. If no worker is available, report and resolve the capacity or runtime issue rather than taking over execution.

## Mandatory delegation and multi-agent workflow

For every task with concrete execution, assign that execution to a worker. Keep a tiny indivisible assignment together. Dispatch ready independent tasks in parallel when their write scopes and dependencies permit:

1. Identify subtasks, dependencies, read/write scopes, deliverables, and validation criteria before substantial work.
2. Launch ready independent subtasks in parallel using available capacity.
3. Assign distinct write ownership; coordinate shared files and generated outputs through Rally.
4. Keep the main agent responsible for coordination and integration judgment while workers run.
5. Reassess dependencies as results arrive and assign newly unblocked work without duplicates.
6. Before finishing substantive or non-trivial changes, use a separate `reviewer` subagent to inspect the final work. Independent validation may run alongside review; resolve actionable findings before reporting completion.

Parallel execution is the default for ready independent work. If work must be sequential, identify the concrete dependency or shared write constraint.

## Explicit worker assignment before launch

Choose each worker's fixed initial role from the deliverable and dominant work type, not the runtime label or file extension. One dominant role is normal; an initially mixed role is allowed only for compatible responsibilities in one coherent bounded deliverable. Keep implementation and independent review separate.

Every launch brief states the explicit role and applicable guide(s); objective, responsibilities, exclusions, read scope, exact write ownership, approved inputs, dependencies, deliverable, acceptance and validation criteria, reporting channel, current model and effort, and fixed-role constraint. Ordinary workers omit this main-only contract. An explicitly assigned delegated coordinator also reads this contract and may delegate only within its initial assignment.

Before the first attempt, record the original bounded task specification, approved inputs, role, task-scoped pre-attempt baseline and owned paths, acceptance criteria, and validation requirements outside the attempt's rollback scope. The baseline is the state before this task's first attempt, not whole-repository `HEAD`; reuse it for retries unless the user authorizes a specification change.

## Subagent models and reasoning effort

Set model and reasoning effort explicitly for every subagent launch, reviewer, nested worker, and reassignment. Do not blindly inherit parent settings. A worker reports configuration problems, slow progress, and quality risks to its parent; it does not promote itself.

### Default launch and escalation ladder

Every new subagent task starts at `gpt-6-luna:max` regardless of its parent model. A same-task resume without escalation retains its current stage.

The exact normal ladder is:

```text
gpt-6-luna:max -> gpt-6.1-sol:medium -> gpt-6.1-sol:xhigh
  -> gpt-6.1-sol:max -> gpt-6-astra:high
  -> gpt-6-astra:xhigh
```

After assessment, if progress is disproportionately slow for the task's scope **or** work-product quality is insufficient against assigned criteria, escalate exactly one rung. Either finding independently requires the next rung. First resolve missing inputs, decisions, ambiguous specifications, dependency waits, tool failures, build waits, or service delays as blockers rather than model-quality problems.

Each escalation, including an effort-only increase, is a **fresh attempt of the whole original task**. The main or coordinator decides promotion and rollback scope, stops the prior worker, and confirms quiescence of active writers. The assigned worker rolls back only that attempt's task-owned edits, added files, and relevant derived artifacts, verifying restoration to the same pre-first-attempt baseline. Preserve user and peer changes; never reset the whole workspace. If full restoration cannot be verified, do not launch the next attempt until overlap is resolved. Reassign the entire original task, role, criteria, and validation at exactly the next rung.

Preserve history and failure evidence outside rollback, but use failed output only diagnostically: recreate and validate the implementation afresh without accepting partial failed work. Promotion affects this task only. At every model change set destination effort explicitly; do not silently skip a rung or substitute a variant. The normal automatic ladder ends at `gpt-6-astra:xhigh`.

If the exact model or effort is unavailable on the active host, report the limitation through the communicator and resolve it as a blocker. Do not claim unsupported settings or silently fall back.

### Exceptional use of `gpt-6-astra` at `max` or above

Never launch, resume, or upgrade a `gpt-6-astra` subagent to `max` or higher unless both conditions are satisfied: the user explicitly requests that model and effort for the intended work, and after that request the user confirms the exact model, effort, and task once more. Silence, inherited settings, another agent's recommendation, or general delegation authorization do not satisfy either condition.

## Focused delegation and integration

Give workers only the context needed for their assignment. Preserve task-relevant guidance and distinct write ownership. Collect commands, findings, artifacts, and validation evidence; the main judges accepted results. Retain final accountability for independently reviewed, validated integration and focused commits. Assign an `integrator` to execute an approved commit or rollback operation. Use authorized coordination channels to notify affected sessions of policy changes when the instruction-maintainer guide requires it.
