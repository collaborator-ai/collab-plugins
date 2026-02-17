---
name: initiative-brief
description: >
  Synthesize the Initiative pipeline outputs into a single living document.
  Not a pipeline stage — a higher-level integrator that reads all 4 stages
  and produces the cross-cutting analysis that no individual stage can.
argument-hint: <path-to-notes-directory>
---

# Initiative: Brief

You are writing a synthesis document that sits above the Initiative pipeline. The pipeline has 4 stages (scan, goals, blockers, actions) that each do focused analytical work. Your job is different: you read all 4 outputs together and produce the cross-cutting insights that none of them can see individually.

The brief is not a summary of the other files. The author can read those. The brief exists to answer: **"Given everything the pipeline found, what's the single most important thing to understand right now, and why?"**

## Input

- `_initiative_scan.md` (terrain map)
- `_initiative_goals.md` (goal tree + motivations)
- `_initiative_blockers.md` (what's stuck + meta-insights)
- `_initiative_actions.md` (prioritized next steps)
- The previous `_initiative_brief.md` (if it exists from a prior run)

Read all four pipeline outputs before writing anything.

## What to do

### 1. If a previous brief exists, diff first

Read the prior brief. Before writing the new one, understand what changed *in the vault* since the prior brief was written — not what changed between pipeline runs. Look for:
- Goals that were achieved, abandoned, or newly appeared
- Blockers that resolved or got worse
- Actions from the prior "do now" that were completed (check for evidence in the notes)
- Actions that are newly urgent due to changed circumstances

### 2. Find the critical path

This is the core job of the brief. Read across goals, blockers, and actions to find:

- **The keystone blocker** — the one blocker that, if resolved, would unblock the most other things. There is usually one. Name it.
- **The dependency chain** — trace the sequence: "Resolving A enables B, which enables C, which enables D." Make the causal chain explicit.
- **The highest-leverage action** — the action from the actions stage that sits at the root of the dependency chain. Explain *why* it's highest-leverage by showing what it unblocks downstream.

The critical path is the thing the pipeline outputs don't say on their own. Each stage looks at its own domain (goals, blockers, actions). Only the brief can connect them into a chain.

### 3. Write the brief

Structure:

```markdown
# Initiative Brief

**Collection:** [name]
**Updated:** [date]
**Previous brief:** [date, or "first run"]

## What changed since last brief
[Skip this section on first run. Compare against the PRIOR BRIEF's assessment of the vault, not against another pipeline run.]
- [Goal added/achieved/abandoned]
- [Blocker resolved/escalated]
- [Action completed/reprioritized]

## Where you are

[2-3 sentences. The honest, high-level summary. What phase is this project/thinking in? Early exploration, mid-build, pre-launch, stuck, thriving? Don't editorialize — describe.]

## The critical path

[The synthesis. Name the keystone blocker. Trace the dependency chain. Identify the highest-leverage action and explain why it's highest-leverage by showing what it unblocks. This section should make the reader think "I couldn't have seen that just by reading the goals and blockers separately."]

## Active goals

[Only the goals with current momentum or critical blockers. One line each: the goal and its status. Reference the goals file for details — don't repeat the tree.]

1. **[Strategic goal]** — [status]
2. ...

## Critical blockers

[Only critical and moderate. One line each: what it is and what resolves it. Reference the blockers file for evidence — don't repeat it.]

1. **[Blocker]** — [what resolves it]

## Observations

[2-4 bullets. Cross-cutting patterns that no single pipeline stage captured. This is where you surface things like:
- Structural ironies (the product is about X but the vault does the opposite of X)
- Behavioral patterns (deciding, then undeciding, then leaving both unresolved)
- Emergent signals (a theme appearing in recent notes that isn't yet in the goal tree)
- Quality-of-attention observations (where the author's energy actually goes vs. where they say it should go)

These are observations, not advice. Describe the pattern; let the author decide what to do about it.]
```

### 4. Replace the previous brief

Write the new brief to `_initiative_brief.md`, overwriting the previous one. The diff is captured within the "What changed" section, so history is preserved.

### 5. Leave the pipeline outputs in place

The pipeline files are the detailed evidence behind the brief's synthesis. The brief references them; it doesn't replace them.

## Constraints

- The brief should be readable in under 2 minutes. If it's longer, you haven't synthesized enough.
- Use the author's own language where possible. Pull phrases from their notes.
- Do NOT duplicate the actions list. The actions file owns the prioritized list. The brief identifies the critical path through it — the one action that matters most and why. Point the reader to the actions file for the full list.
- Do NOT add recommendations the pipeline didn't produce. The brief synthesizes; it doesn't advise.
- The "Where you are" section must be honest. If the project is stuck, say it's stuck.
- The observations section is for patterns, not advice. "Three notes this month revisited the pricing model without settling it" not "You should decide on pricing."
