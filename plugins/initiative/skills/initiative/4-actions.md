---
name: initiative-actions
description: >
  Derive concrete, prioritized next actions from goals and blockers.
  Requires initiative-goals and initiative-blockers to have run first.
argument-hint: <path-to-notes-directory>
---

# Initiative: Actions

You are translating goals and blockers into a prioritized list of concrete actions. Each action should be something a person can sit down and do in a single focused session.

## Input

- The goals output from Stage 2 (goal tree with confidence levels)
- The blockers output from Stage 3 (blockers with severity and meta-insights)
- The notes themselves (for reference when actions need grounding)

## What to do

### 1. Derive actions from three sources

**From concrete steps in the goal tree:** The leaf nodes of the goal tree are already action-shaped. Pull them in. But evaluate: are they still the right next steps given what the blockers reveal?

**From blockers:** Every blocker implies an action to unblock it. An unresolved question implies "make a decision about X." A contradiction implies "reconcile notes A and B." Stalled work implies "resume or explicitly abandon Y."

**From meta-insights:** The meta-insight layer suggests *types* of action, not specific ones. Translate them:
- "Needs a forcing function" → schedule a deadline, write a one-pager, or commit to a specific audience
- "Needs reactivation" → re-read the relevant notes and write a fresh take
- "Needs scoping" → write a scope document that explicitly excludes things
- "Needs a different input" → identify who to talk to, what data to gather, or what experiment to run

### 2. Filter and deduplicate

Remove actions that are:
- Already done (check the notes — was there a follow-up that completed this?)
- Redundant (two actions that accomplish the same thing)
- Premature (depends on another action being done first — mark as blocked instead)

### 3. Prioritize

Score each action on two axes:

**Leverage** — How many goals does this unblock? An action that resolves a critical blocker affecting 3 strategic goals ranks higher than one that advances a single tactical goal.

**Momentum** — Is this in an area where the author has recent energy? Actions aligned with current activity are more likely to get done than actions in dormant areas, regardless of importance.

Combine into a priority tier:
- **Do now** — High leverage AND high momentum. These are the most impactful actions the author is already positioned to take.
- **Do next** — High leverage but low momentum (important but needs ramp-up), or low leverage but high momentum (easy wins in active areas).
- **Backlog** — Low leverage and low momentum. Real actions, but not urgent.

### 4. Sequence within tiers

Within "do now," order by dependencies. If action B depends on action A, A comes first. If no dependencies, order by effort — smallest first (build momentum with quick wins).

### 5. Phrase actions concretely

Each action must be:
- **Verb-first** — "Write...", "Decide...", "Read...", "Talk to...", "Delete..."
- **Specific** — names the artifact, the decision, or the deliverable
- **Bounded** — achievable in one session (if not, decompose further)
- **Connected** — references which goal it serves and which blocker it addresses

Bad: "Work on positioning"
Good: "Write a one-paragraph positioning statement that distinguishes the product from [competitor], resolving the tension between notes X and Y"

## Output

Write the actions output to the location specified by the orchestrator. If running standalone, write `initiative_actions.md` in the output directory. Structure it as:

```markdown
# Initiative Actions

**Last updated:** [date]
**Derived from:** [N] goals, [N] blockers, [N] meta-insights

## Do now
1. **[Action]**
   - Serves: [goal reference]
   - Unblocks: [blocker reference, if any]
   - Why now: [momentum/leverage reasoning in one sentence]

2. ...

## Do next
1. **[Action]**
   - Serves: [goal reference]
   - Unblocks: [blocker reference, if any]
   - Why not now: [what needs to happen first, or why momentum is lower]

2. ...

## Backlog
1. **[Action]** — [goal reference]
2. ...

## Deferred / explicitly not doing
[Actions that were considered but filtered out, and why. This prevents them from being re-derived in future runs.]
```

## Constraints

- Every action must trace back to a goal or blocker. No free-floating advice.
- Do NOT add actions the author hasn't implicitly asked for. You're operationalizing their goals, not yours.
- "Do now" should have 3-7 items. If you have more, you haven't prioritized hard enough. If you have fewer, the vault may be in good shape.
- Do NOT modify any existing notes. Only write to the output location.
- If two actions conflict (doing A makes B irrelevant), note the conflict and let the author choose.
