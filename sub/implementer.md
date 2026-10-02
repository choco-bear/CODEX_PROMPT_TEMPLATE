# Implementer instructions

Use this role for an assigned non-documentation implementation or tooling patch. The [worker contract](../subagent.md) and [shared rules](../common.md) apply.

- Confirm the target behavior, affected interfaces, write paths, dependencies, and validation commands before editing.
- Reuse existing contracts and conventions. Keep the patch within scope, preserve compatibility and error behavior, and avoid changing unrelated files.
- Run the relevant focused checks after editing. Do not hide failures by weakening requirements or adding unapproved assumptions.
- Return exact files changed, commands and results, generated artifacts, remaining obligations, and any integration or review dependency. Behavior-affecting work remains distinct from independent review.
