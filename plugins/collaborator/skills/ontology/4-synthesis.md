# Stage 4: Ontology Synthesis

Produce a concise synthesis of the ontology — the map of the author's thinking, where it's strong, and where it's unresolved.

## Process

1. **Read all three outputs** from Stages 1-3: entities, relations, and alignments.

2. **If a previous ontology exists** (`_previous_ontology.md`), read it and note what changed:
   - New entities that appeared
   - Entities that disappeared or lost centrality
   - Relations that flipped (e.g., "enables" became "blocks")
   - Tensions that resolved or new tensions that emerged
   - Confirmations that strengthened or weakened

3. **Write the synthesis** with these sections:

### The Landscape
A 2-3 paragraph narrative overview of the author's thinking. What are the central entities? How do they relate? Where is there coherence? Write this like a map legend — orienting someone who needs to understand the terrain quickly.

### Load-Bearing Beliefs
The 3-5 strongest positive alignments. These are the pillars — the things the author is most sure about, supported by multiple reinforcing relations. If any of these broke, it would cascade.

### Active Tensions
The 3-5 sharpest unresolved negative alignments. These are the open questions that demand decisions. For each, state:
- What the tension is
- What decision it demands
- What happens if it's not resolved (i.e., the cost of inaction)

### Evolution (if previous ontology exists)
What changed since last run? New tensions, resolved tensions, entities that gained or lost centrality. This is the "diff" that shows how the author's thinking is moving.

### Implications for Action
Based on the alignment structure, what should the author do? This isn't a to-do list — it's a set of observations about where the ontology suggests action is needed. Which tensions are most costly to leave unresolved? Which confirmations suggest doubling down?

## Output format

Write to `ontology_synthesis.md`:

```markdown
# Ontology Synthesis

**Date:** YYYY-MM-DD
**Entities:** N | **Relations:** N | **Alignments:** N (P+ / Q-)

## The Landscape

[2-3 paragraph narrative]

## Load-Bearing Beliefs

1. **[Belief name]** — [one sentence] — supported by [alignment reference]
2. ...

## Active Tensions

1. **[Tension name]** — [one sentence]
   - Demands: [what decision]
   - Cost of inaction: [what happens if unresolved]
2. ...

## Evolution

[What changed since last run, if applicable]

## Implications for Action

[3-5 observations about where the ontology suggests action]
```

## Constraints

- The synthesis should be readable in under 3 minutes.
- Write for the author, not for a general audience. Use their language.
- Don't repeat the full entity/relation/alignment lists — synthesize, don't summarize.
- Be honest about uncertainty. If the ontology reveals that the author's thinking is incoherent in a specific area, say so directly.
- The "Implications for Action" section should have opinions. This is where the ontology earns its keep.
