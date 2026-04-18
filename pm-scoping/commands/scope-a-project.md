---
description: Turn a vague client brief into a full scoping pack — questions, Scope of Work, work breakdown, time plan, and risk register — in one guided workflow
argument-hint: "<path to brief file, or paste the brief>"
---

# /scope-a-project — Full Scoping Cycle

Run the end-to-end project scoping cycle for any digital project. Takes a raw client brief and walks through five checkpoints to produce scoping questions, a Scope of Work, a work breakdown, a time plan, and a risk register.

Designed to be run in one sitting (45–90 minutes depending on depth), with user checkpoints between each step so you can redirect, trim, or go deeper.

## Invocation

```
/scope-a-project                                    # asks for the brief
/scope-a-project path/to/client-brief.md            # reads the file
/scope-a-project                                    # paste the brief when prompted
```

## Workflow

### Step 1 — Gather the brief and context

Ask the user for:

- The client brief (paste or file path)
- Project type (website, app, campaign, content programme, data project, internal tool, other)
- Anything they already know that isn't in the brief: agency/client names, target dates, team structure, commercial model, known client behaviour

Accept partial context — every subsequent step handles missing information by flagging assumptions rather than inventing.

### Step 2 — Generate scoping questions

Apply the **scoping-questions** skill.

Output the full question set plus the Top 5 priority questions. Save as `01-scoping-questions.md`.

**Checkpoint:** "Here are the questions I'd ask the client. Want me to trim, reprioritise, or add anything before you take them to the kick-off call?"

Then pause for the user to bring back the answers. Options:

1. User pastes answers in the same session → continue to Step 3
2. User says "I'll come back with answers" → save progress and stop

### Step 3 — Write the Scope of Work

Once the scoping answers are available, apply the **scope-of-work** skill.

The prompt takes both the original brief and the scoping answers as inputs. Output a SoW under 500 words plus Reviewer Notes. Save as `02-scope-of-work.md`.

**Checkpoint:** "Here's the SoW, under 500 words. Check the Reviewer Notes — that's where I've flagged assumptions and things to sense-check internally. Want me to tighten any section before we move on?"

### Step 4 — Build the work breakdown

Apply the **work-breakdown-structure** skill with the draft SoW as input. Output a WBS table plus critical path summary, high-risk dependencies, and gaps. Save as `03-work-breakdown.md`.

**Checkpoint:** "Here's the work breakdown. The critical path and high-risk dependencies are what matter most. Anything I should decompose further or consolidate?"

### Step 5 — Build the time plan

Apply the **project-time-plan** skill with the WBS as input. Output a time plan table, critical path duration, resource heat map, estimation assumptions, and risks. Save as `04-time-plan.md`.

**Checkpoint:** "The minimum elapsed time to launch is **X working days**. Reality-check this against the SoW launch date and flag if there's a conflict. Want me to run through any estimation assumptions?"

### Step 6 — Flag the risks

Apply the **project-risk-register** skill with both the SoW and time plan as inputs. Output the top 5 risks with contingencies, a heat view, what's not on the list, and next actions. Save as `05-risk-register.md`.

**Checkpoint:** "Here's the risk register. The Recommended Next Actions section is what I'd take into your PM one-on-one this week."

### Step 7 — Pressure-test assumptions (optional)

Offer to run the **assumptions-and-dependencies** skill over the SoW for a deeper audit of the load-bearing sections. Save as `06-assumptions-audit.md`.

### Step 8 — Wrap

Produce a short summary:

- Files saved and what each one is for
- Top 3 things the PM should do this week (pulled from the risk register's Recommended Next Actions)
- Any conflict between the stated launch date and the minimum elapsed time
- What's still outstanding (e.g. Reviewer Notes items to sense-check)

## Notes

- This is a structured 45–90 minute workflow. Let the user know upfront.
- At every checkpoint, the user can redirect, skip, or go deeper.
- Save each output as a separate numbered file in the current working directory.
- If the brief is very thin, stop after Step 2 and send the user back to the client with the Top 5 questions before continuing.
- Never invent client names, dates, budgets, or platform access. Flag gaps as assumptions.
- Use UK English and DD/MM/YYYY dates throughout.
- If the user only wants a subset (e.g. SoW only, or WBS only), just run the relevant skill directly instead.

## Related commands

- `/pressure-test-brief` — quick gap analysis only (skill 1, no full cycle)

## Related skills

- **scoping-questions**, **scope-of-work**, **work-breakdown-structure**, **project-time-plan**, **project-risk-register**, **assumptions-and-dependencies**, **scope-change-control**
