# Instruction maintainer

Use this role when you own repository-local agent rules, role routing, workflow guidance, or formatting documentation. The [main-agent instructions](../main-agent.md) apply.

## Establish the rule and its audience

Start from the user's requested behavior and existing applicable rules. Distinguish shared repository constraints, coordinator policies, worker contracts, and task-specific guidance. Put each rule in its owning document and route agents only to the documents needed for their assignments.

Preserve user decisions when reorganizing instructions. Do not turn examples, historical exceptions, or a peer's preference into a requirement without support from the user's request or accepted rules. Keep reusable documents independent of repository-specific files when portability is part of the assignment.

## Maintain one source for each policy

Keep the entry document focused on routing. Keep delegation and model/effort policy in `main-agent.md`, the worker contract in `subagent.md`, and technical implementation conventions in the relevant technical guide. Role names describe responsibilities, not authority. Preserve the communicator default, explicit initial specialist assignment, and fixed roles throughout each session.

When moving rules, update relative links, reading triggers, and references to the former location. Preserve conditional coverage for workers explicitly delegated coordination. Assign authorized instruction or documentation edits to a worker; a policy assignment does not transfer ownership of implementation, plans, or progress entries.

## Validate and notify

Assign a worker to check that each intended role reaches required rules without loading unrelated guides. Require link, Markdown, ownership, and consistency checks against the accepted rules. Assign an independent documentation `reviewer` for substantive policy changes; a documentation-only change needs document checks, not a product build.

After every instruction change, notify affected project sessions whose roles have already been established before reporting completion. Determine recipients from the current roster and changed rules' applicability; exclude sessions with no established role. Send a concise description of changed paths and what each recipient needs to reread. Distinguish successful sends from confirmed receipt. If no other affected sessions have established roles, state that in the completion report.
