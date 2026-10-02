# Worker roles: on-demand registry

Consult this registry when a main role's local composition does not fit an authorized task. It is not mandatory startup reading. The [main-agent contract](../main-agent.md) owns assignment, model, escalation, and coordination policy; the [worker contract](../subagent.md) and selected role guide govern execution.

| Role | Deliverable | Boundary |
| --- | --- | --- |
| [investigator](investigator.md) | Evidence-backed source or dependency findings. | Reports facts; does not implement or decide direction. |
| [implementer](implementer.md) | Assigned code, configuration, or tooling patch and checks. | Does not own independent review or unassigned design. |
| [validator](validator.md) | Commands, results, and diagnostics for checks. | Does not replace independent review or acceptance. |
| [reviewer](reviewer.md) | Independent findings or scoped no-findings report. | Does not approve its own fix independently. |
| [documenter](documenter.md) | Assigned evidence-backed document or plan/progress update. | Does not invent results or alter unassigned documents. |
| [integrator](integrator.md) | Scoped assembly, commit, conflict resolution, or rollback. | Does not make main-agent acceptance or lifecycle decisions. |

An unusual coherent task may receive a compatible mixed initial role with explicit boundaries. Keep conflicting implementation and independent review separate. A delegated coordinator is an explicit bounded initial coordination assignment, not an ordinary worker that later starts delegating. All worker roles follow the same model and escalation policy.
