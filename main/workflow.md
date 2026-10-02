# Shared workflow for technical and structural work

Use this workflow when coordinating implementation, migration, validation, or other repository work. It supplements [main-agent.md](../main-agent.md) and the selected role guide; it does not assign a role or expand write scope.

## Establish the contract

Identify the exact requested behavior, affected interfaces, assumptions, expected outputs, and acceptance checks before planning. Read `<goal-document>` and relevant design records. Treat accepted design references as fixed unless the user explicitly requests a change. Reuse existing definitions and contracts when they fit; record any requested deviation as a design decision.

## Plan and execute

Assign a worker to write and maintain a focused plan when the task has meaningful dependencies. Keep plans short and current; record remaining steps, owners, and open obligations. Assign implementation to the responsible worker, validation to a `validator`, and independent assessment to a `reviewer`. Coordinate ownership of shared plans, source files, and generated outputs before edits or builds.

## Handle obstacles and alternatives

Before resuming an attempt, check current plans and verified results relevant to the request. Distinguish a failed helper, witness, or route from a false requirement. Return the precise goal, assumptions, attempted reasoning, and evidence to the design partner when an obstacle affects accepted direction.

For a candidate failure or counterexample, apply `<counterexample-criteria>`: establish the requested premise, every remaining requirement, the observed behavior, and its exclusion from permitted behaviors. Separate candidates, checks, and verified results. A verified counterexample constrains work under that statement; it does not authorize changing semantics or assumptions. Hand the cause and exact scope to the design partner for a user decision.

## Integrate and report

Have the validator return exact commands, environment, exit codes, diagnostics, and what each check establishes or leaves unverified. Have the reviewer report actionable findings or a scoped no-findings result. Resolve findings before acceptance, then assign an integrator to assemble or commit the verified unit. Report completed, partial, and blocked work with file paths, evidence, and remaining dependencies.
