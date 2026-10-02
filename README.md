# Repository agent template

This directory is a portable instruction set for coordinating work in an arbitrary repository. Copy it to `.codex/` (or adapt the paths for your host) and replace angle-bracket placeholders with repository facts.

Start with [AGENTS.md](AGENTS.md). Every session reads [common.md](common.md), then reads exactly one role contract: [main-agent.md](main-agent.md) for a coordinator or [subagent.md](subagent.md) plus the assigned guide for a bounded worker.

Main roles are documented in `main/`: communicator, design-partner, instruction-maintainer, project-explainer (a legacy redirect), structure-coordinator, and technical-coordinator. The shared workflow document is [`workflow.md`](main/workflow.md). On-demand worker roles are in `sub/`.

Before adapting this template, define the repository's goal and validation commands in the placeholders in `common.md` and the selected role guide. Keep user decisions, accepted design, implementation evidence, and review findings in the repository's established documents.
