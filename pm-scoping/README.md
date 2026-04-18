# pm-scoping

Turn a vague client brief into a structured scope of work, work breakdown, time plan, and risk register. Seven skills and two chained commands covering the full pre-delivery scoping cycle for any digital project — websites, apps, campaigns, content, data, internal tools.

## Overview

The projects that go wrong aren't the ones with difficult clients. They're the ones that started without a proper stake in the ground. This plugin exists to fix that.

Every skill is adapted from delivery patterns that hold up in real agency work. The prompts are specific, the outputs are structured, and nothing relies on the client being organised or the brief being complete.

## Installation

See [root README](../README.md#installation) for install instructions via Claude Code, Claude Cowork, or other AI assistants.

## Skills (7)

- **scoping-questions** — Generate brief-specific scoping questions a senior PM would ask before committing to a scope of work. Use when a client brief lands and you need to surface gaps, assumptions, and delivery risks.
- **scope-of-work** — Write a tight, commercially watertight Scope of Work under 500 words, using the client brief and scoping answers as input.
- **work-breakdown-structure** — Decompose a signed Scope of Work into phases, tasks, owners, dependencies, and critical path.
- **project-time-plan** — Turn a work breakdown into a realistic time plan with hard dependencies, genuine parallelisation, critical path, and minimum elapsed time to launch.
- **project-risk-register** — Produce a top-5 risk register with early warning signs, owners, and executable contingencies, tied to the SoW and time plan.
- **assumptions-and-dependencies** — Stress-test the Assumptions and Dependencies sections of a SoW — the load-bearing paragraphs that save the PM at week four.
- **scope-change-control** — Draft a commercial change request when scope, timeline, or budget shifts mid-project.

## Commands (2)

- `/pm-scoping:scope-a-project` — Full scoping cycle. Chains questions → SoW → WBS → time plan → risks into one guided workflow with checkpoints.
- `/pm-scoping:pressure-test-brief` — Fast gap analysis on a client brief. Produces the scoping questions a senior PM would ask before committing.

## Typical workflow

1. Client brief lands → run `/pressure-test-brief` → send Top 5 questions to the client before kick-off
2. Answers come back → run `/scope-a-project` → full scoping pack produced over 45–90 minutes with checkpoints
3. Scope changes mid-project → run the `scope-change-control` skill directly with the new ask

Or run individual skills as needed — they're all standalone.

## Author

Tim Houghton — [The Wash-Up](https://thewashup.substack.com), weekly writing on AI for agency project managers.

## License

MIT
