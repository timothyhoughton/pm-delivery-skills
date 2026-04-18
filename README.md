# pm-delivery-skills

**Open-source delivery skills for project managers.** Practitioner-written AI workflows for scoping, planning, and running digital projects — starting with the five-prompt framework that turns a vague client brief into a full scope of work, time plan, and risk register in under an hour.

Works with Claude Code, Claude Cowork, and any AI assistant that supports the universal `SKILL.md` format.

---

## Who it's for

Digital project managers, account managers, and delivery leads at marketing, advertising, and digital agencies. Specifically:

- PMs who want structured, battle-tested frameworks — not generic ChatGPT prompts
- Account managers who keep getting vague briefs and don't have time to reinvent scoping every time
- Delivery leads who want their team using consistent, commercially defensible processes
- Operators who are told "use AI" and need something more useful than "try ChatGPT"

This isn't theory. Every skill is adapted from the delivery patterns that hold up in real agency work — clients with unclear briefs, tight launch dates, thin margins, and high stakes.

---

## What's included (v1)

### Plugin: `pm-scoping`

Seven skills and two chained commands covering the full pre-delivery scoping cycle for any digital project — websites, apps, campaigns, content, data, internal tools.

**Skills:**

| Skill | What it does |
|---|---|
| `scoping-questions` | Generate brief-specific questions to ask before committing to a scope |
| `scope-of-work` | Write a tight Scope of Work under 500 words, commercially watertight |
| `work-breakdown-structure` | Decompose the SoW into phases, tasks, and dependencies |
| `project-time-plan` | Convert the WBS into a realistic time plan with critical path |
| `project-risk-register` | Identify the top 5 risks with early warnings and contingencies |
| `assumptions-and-dependencies` | Stress-test the load-bearing sections of the SoW |
| `scope-change-control` | Draft a change request when scope shifts mid-project |

**Commands:**

| Command | What it does |
|---|---|
| `/scope-a-project` | Full scoping cycle — questions → SoW → WBS → time plan → risks |
| `/pressure-test-brief` | Fast gap analysis on a client brief (15–20 minutes) |

---

## Installation

### Claude Code (CLI)

```bash
claude plugin marketplace add timothyhoughton/pm-delivery-skills
claude plugin install pm-scoping@pm-delivery-skills
```

### Claude Cowork (desktop app)

1. Open **Customize → Browse plugins → Personal**
2. **Add marketplace from GitHub**
3. Enter `timothyhoughton/pm-delivery-skills`
4. Install the `pm-scoping` plugin

### Other AI assistants (Cursor, Gemini CLI, OpenCode, Codex, Kiro)

The `SKILL.md` format is portable. Copy any skill from `pm-scoping/skills/*/SKILL.md` into the equivalent skills directory for your tool. Commands use standard YAML frontmatter and work in any assistant that reads `/`-style markdown command files.

---

## Quick start

Once installed, try:

```
/pressure-test-brief
```

Paste a real (or fictional) client brief when prompted. In 15 seconds you'll have the scoping questions a senior PM would ask — prioritised, grouped, and tied to specific delivery risks.

Then, when the answers come back:

```
/scope-a-project
```

That walks you through the full cycle — SoW, WBS, time plan, risk register — in one guided workflow with checkpoints.

---

## Roadmap

The architecture supports more plugins. Likely next additions, in rough order:

- `pm-stakeholder-comms` — status reports, steerco decks, escalation playbooks, internal comms
- `pm-discovery` — pre-brief discovery work when the client hasn't written anything yet
- `pm-retrospectives` — retros that don't waste everyone's afternoon
- `pm-reporting` — monthly reports, campaign wrap-ups, performance narratives
- `pm-risk` — deeper risk work beyond the initial register

Suggestions welcome — open an issue.

---

## About

Built by [Tim Houghton](https://thewashup.club) — twenty years of digital delivery at agencies, currently Director of Product & Services at a global healthcare marketing agency.

The patterns in these skills come from real projects. If they're useful to you, **[subscribe to The Wash-Up](https://thewashup.club)** — weekly writing on AI for agency project managers, account managers, and delivery leads.

---

## Contributing

Contributions welcome. See [CONTRIBUTING.md](CONTRIBUTING.md) for how skills are structured, naming conventions, and the validator that keeps quality consistent.

If you're submitting a new skill, the short version:

- Skills are **nouns** (frameworks, templates, deliverables)
- Commands are **verbs** (workflows that chain skills)
- Every skill needs `name` + `description` in frontmatter; `name` must match the directory
- Every command needs `description` + `argument-hint`
- Run `python3 validate_plugins.py` before opening a PR

---

## License

MIT — see [LICENSE](LICENSE). Free to use, adapt, and distribute. Attribution appreciated but not required.
