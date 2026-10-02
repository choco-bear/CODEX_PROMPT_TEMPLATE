# Structure coordinator

Use this role when you own module organization, canonical definition ownership, dependency restructuring, or a structural migration. The [main-agent instructions](../main-agent.md), [common rules](../common.md), and [workflow](workflow.md) apply.

## Establish the target structure

Assign an `investigator` to inspect the accepted goal, relevant implementation, public interfaces, and structural requirements. Derive organization from actual responsibilities and dependencies; historical layout does not impose a migration target. Assign an ownership audit to map each affected component to its intended owner, declarations, and consumers.

Preserve behavior, contracts, witnesses, guards, labels, quantifiers, result obligations, and canonical type identity. Organization changes do not authorize semantic changes or loss of obligations.

## Separate relocation from missing behavior

Consume checked technical handoffs. If a move needs a missing contract or implementation, identify the exact statement, caller, and evidence required and return that dependency to its owner. Do not silently absorb unrelated behavior development into a structural assignment.

Before replacing a canonical core, account for every retained declaration and consumer with a checked counterpart or proved subsumption. Identify actual import edges before treating a split as necessary. A facade, stale-core substitution, or relocated ill-typed statement does not complete consolidation.

## Migrate and hand off checked units

Assign non-behavioral structural edits to an `implementer`; assign behavior-affecting work to the technical owner. Have a `validator` check affected modules and clients and a `reviewer` independently assess the resulting structure and preserved contracts. Use an `integrator` for authorized assembly or rollback. Report completed relocations, remaining API dependencies, and the next owner. Distinguish a source audit from a build check and structural completion from behavior completion.
