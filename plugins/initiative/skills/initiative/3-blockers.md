---
name: initiative-blockers
description: >
  Identify what's stuck, stalled, or unresolved in the notes collection.
  Includes meta-insight extraction from patterns of change.
  Requires initiative-scan and initiative-goals to have run first.
argument-hint: <path-to-notes-directory>
---

# Initiative: Blockers

You are looking for what's stuck. Goals tell you where the author wants to go; blockers tell you what's in the way. This stage also performs meta-insight extraction — reasoning about what the *patterns of change* in the notes suggest.

## Input

- A directory of markdown notes (the target directory)
- The scan output from Stage 1
- The goals output from Stage 2

Read both prior outputs first. Then go back into the notes to find evidence of stuckness.

## What to do

### 1. Find unresolved questions

Search for notes that pose questions without answering them. Look for:
- Literal question marks in note titles or content
- Notes titled with "Question", "Decision", "TBD", "Open"
- Patterns like "Option A vs Option B" without a stated conclusion
- Notes that end with "need to think about this more" or equivalent

For each, check: was it answered in a later note? If yes, it's resolved. If no, it's a blocker.

### 2. Find revisited-without-resolution

This is the strongest signal of stuckness. When the same topic appears across 3+ notes and the thinking *doesn't converge* — the author keeps restating the problem differently without settling it.

Compare notes on the same topic chronologically. Are they refining toward a conclusion, or going in circles? Circling = blocker.

### 3. Find contradictions

Two notes that assert incompatible things. These may be:
- Explicit contradictions (Note A says "we should do X", Note B says "X is wrong")
- Implicit contradictions (Note A assumes one architecture, Note B assumes a different one)
- Evolved-but-not-reconciled (the author changed their mind but didn't update earlier thinking)

Contradictions aren't always blockers — sometimes the newer note simply supersedes. Only flag it as a blocker if the tension appears unresolved.

### 4. Find stalled work

Look for notes with status markers that suggest incompleteness:
- `[WIP]`, `[DRAFT]`, `[TODO]` prefixes
- Notes that describe a plan but show no follow-up
- Implementation notes that stop mid-way
- "Sprint" or "timeline" notes whose deadlines have passed

Cross-reference with the goal tree: which goals have no recent activity?

### 5. Meta-insight extraction from change patterns

This is the distinctive part. You're not just looking at what the notes say — you're looking at what the *patterns of change* suggest about what kinds of thinking are needed.

Analyze the vault's evolution and ask:

- **Rewrite clusters** — When the same concept gets rewritten 3+ times, it means the framing isn't settled. The meta-insight: "This concept needs a forcing function — a deadline, a conversation, or a concrete test that resolves the framing."
- **Burst-then-silence** — A topic gets 10 notes in a week, then nothing. The meta-insight: "Either this was resolved (check) or energy dissipated. If unresolved, it needs reactivation."
- **Broadening without deepening** — Notes keep adding new facets to a topic without resolving existing ones. The meta-insight: "Scope is expanding faster than decisions are being made. Needs scoping or decomposition."
- **Convergence** — Notes on a topic get shorter, more precise, more confident over time. The meta-insight: "This is almost resolved. One more push — probably a concrete deliverable — will close it."
- **Oscillation** — The author alternates between two positions across notes. The meta-insight: "This isn't a thinking problem, it's a values conflict or missing information. Needs a different input — data, feedback, or a decision framework."

For each meta-insight, specify: what pattern you observed, which notes exhibit it, and what kind of action it suggests.

### 6. Map blockers to goals

Every blocker should connect to one or more goals in the tree. A blocker that doesn't connect to any goal is either:
- Evidence of a goal you missed (go back and update the goal tree)
- Noise (note it but deprioritize)

## Output

Write the blockers output to the location specified by the orchestrator. If running standalone, write `initiative_blockers.md` in the output directory. Structure it as:

```markdown
# Initiative Blockers

**Last updated:** [date]

## Unresolved questions
1. **[Question]** — first raised in [note], not answered as of [latest note on topic]
   - Blocks: [goal reference]

## Revisited without resolution
1. **[Topic]** — appears in [N] notes spanning [date range]
   - Pattern: [circling / broadening / oscillating]
   - Blocks: [goal reference]

## Contradictions
1. **[Note A] vs [Note B]** — [description]
   - Status: [unresolved / newer-supersedes / needs-decision]
   - Blocks: [goal reference]

## Stalled work
1. **[Note or workstream]** — last activity [date], status markers suggest incomplete
   - Blocks: [goal reference]

## Meta-insights from change patterns
1. **[Pattern name]** — [description of the pattern observed]
   - Evidence: [which notes, what timeline]
   - Suggests: [what kind of action or thinking is needed]

## Blocker severity
| Blocker | Goals affected | Severity |
|---------|---------------|----------|
| [blocker] | [goal refs] | [critical/moderate/low] |
```

Severity:
- **Critical** — blocks a strategic goal directly, no workaround visible
- **Moderate** — blocks tactical goals, has potential workarounds
- **Low** — blocks concrete steps, can be unblocked with a single decision or action

## Constraints

- Every blocker must cite specific notes as evidence.
- Do NOT invent blockers. If the vault looks healthy and unblocked, say so.
- Meta-insights are inferences — label them as such. The user should be able to evaluate whether your reading of the pattern is correct.
- Do NOT modify any existing notes. Only write to the output location.
