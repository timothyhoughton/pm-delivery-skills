# Contributing

Thanks for considering a contribution. This repo is a practitioner resource — the bar is useful, specific, and battle-tested over novel or impressive.

## How to contribute

- **Bugs, typos, small fixes** — open a PR directly.
- **New skills, new commands, or new plugins** — open an issue first. Describe the problem you're trying to solve and how the skill/command/plugin would work. Keeps wasted effort to a minimum.
- **Feedback on existing skills** — open a discussion or issue with the specific skill name in the title.

## Rules

### Structure

- **Plugin folders** are `pm-[domain]` — lowercase, hyphenated.
- **Skill directories** are lowercase-hyphenated nouns (e.g. `scope-of-work`, `project-risk-register`). Skills are nouns because they represent the framework, not the action.
- **Skill files** are always `SKILL.md` (exact filename required).
- **Command files** are lowercase-hyphenated verbs (e.g. `scope-a-project.md`, `pressure-test-brief.md`). Commands are verbs because they represent the workflow.

### Frontmatter

- Every skill needs `name` and `description` in YAML frontmatter.
- The skill's `name` field must exactly match the directory name.
- Every command needs `description` and `argument-hint` in YAML frontmatter.

### Scope of skills

- **One skill, one job.** If a skill is doing two things, split it.
- **Specific over generic.** Every prompt should be tuned to a real delivery problem — not a generic "help me do X" template.
- **Executable prompt included.** The prompt block is the executable core. The framing around it (why this exists, the framework, when to use, when not to use) is there to help the LLM and the user — not to pad the file.

### Cross-plugin references

- Commands can reference skills **in the same plugin**, using the `**skill-name**` convention.
- Commands should **not** hard-reference skills in other plugins — suggestions to other plugins go in natural language ("Next, consider `pm-planning:/kickoff-plan`").

### Voice and style

- UK English. DD/MM/YYYY dates. £ for currency.
- Plain language. No agency jargon unless it's standard client-side vocabulary.
- Active voice. Short sentences. Concrete nouns.
- No filler, no hedging, no motivational language.

### Before opening a PR

1. Run the validator: `python3 validate_plugins.py` from the repo root. It must pass with zero errors.
2. Keep PRs focused — one change per PR.
3. Update the plugin's README.md if you add or rename skills/commands.
4. If you're adding a new plugin, update `.claude-plugin/marketplace.json` at the repo root.

### Attribution

Every contributor is credited in the commit history. If you want explicit attribution in a skill's further-reading section, note it in your PR description.

## Validator

`validate_plugins.py` checks:

- Plugin manifest (`plugin.json`): required fields, semantic version, author attribution
- Skills: frontmatter present, `name` matches directory, description meets length guidelines
- Commands: frontmatter present, `description` and `argument-hint` present
- Cross-references: commands only reference skills in the same plugin
- README: exists and has the expected sections

The validator is adapted (with attribution) from Paweł Huryn's `pm-skills` repository, released under MIT.

## License

All contributions are accepted under the repo's MIT license.
