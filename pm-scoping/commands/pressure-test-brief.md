---
description: Quick gap analysis on a client brief — generates the scoping questions a senior PM would ask before committing to a scope
argument-hint: "<path to brief file, or paste the brief>"
---

# /pressure-test-brief — Quick Gap Analysis

Run a fast pressure-test on a client brief and produce the scoping questions a senior PM would ask before committing to a scope of work. Use this when you've just received a brief and want to prepare for the kick-off call without committing to the full scoping cycle.

This is the short version. For the full cycle (questions → SoW → WBS → time plan → risks), use `/scope-a-project`.

## Invocation

```
/pressure-test-brief                              # asks for the brief
/pressure-test-brief path/to/client-brief.md      # reads the file
/pressure-test-brief                              # paste the brief when prompted
```

## Workflow

### Step 1 — Gather the brief and minimal context

Ask the user for:

- The client brief (paste or file path)
- Optional: project type, services being offered, estimated duration, known client context

Keep the context gathering light — the point of this command is speed. If the user doesn't know something, treat it as a gap to ask about.

### Step 2 — Run the scoping-questions skill

Apply the **scoping-questions** skill. Output:

1. Brief summary (3–5 bullets)
2. Key assumptions being made
3. Full scoping questions, grouped by category
4. Top 5 questions to ask first
5. Red flags and watch-outs

Save as `scoping-questions.md` in the current working directory.

### Step 3 — Wrap

Summarise for the user:

- Number of questions generated
- The Top 5 in priority order
- Any red flags that deserve an internal chat before the client call
- Offer next steps:
  - "Want to run `/scope-a-project` once you've got the answers back?"
  - "Want me to stress-test the Assumptions section of a draft SoW instead?"
  - "Want me to produce these questions in a different format (Notion, Confluence, email)?"

## Notes

- This is a 5–10 minute workflow. No checkpoints — just one pass and done.
- Output is designed to be sent to the client (Top 5) and circulated internally (full list + red flags).
- Never invent client context. Flag gaps as questions, not assumptions.
- Use UK English and DD/MM/YYYY dates.

## Related commands

- `/scope-a-project` — full five-step scoping cycle (questions → SoW → WBS → time plan → risks)

## Related skills

- **scoping-questions** — the skill this command invokes
- **scope-of-work** — the natural next step once answers are back
