# Stage 2: Map Relations

Map the connections between entities. These are the edges of the ontology.

## What counts as a relation

A relation is a directed connection between two entities that the author has stated, implied, or that clearly exists in the notes. Relations should be grounded in evidence — a specific note, a decision, a pattern across multiple notes.

### Relation types

- **enables** — A makes B possible or easier (e.g., "Seedvault enables Collaborator")
- **blocks** — A prevents or hinders B (e.g., "scope creep blocks shipping v1")
- **contradicts** — A and B are in tension or can't both be true (e.g., "Collaborator is the product" contradicts "Borthwick responded most to Seedvault")
- **replaced** — A was superseded by B (e.g., "memory product" replaced by "judgment product")
- **depends-on** — A requires B (e.g., "investor pitch depends on positioning freeze")
- **contains** — A is part of B (e.g., "initiative pipeline" is part of "Collaborator")
- **informs** — A shapes thinking about B without enabling or blocking it (e.g., "Mem0 competitor analysis informs Collaborator positioning")
- **serves** — A advances or works toward B (e.g., "MCP server serves multi-surface identity")

You may use other relation types if they fit better. The types above are suggestions, not constraints.

## Process

1. **Read the entities output** from Stage 1.

2. **Return to the notes.** Re-read the sampled notes with the entity list in mind. For each note, look for explicit or implied relations between entities.

3. **Extract relations.** For each relation, record:
   - **From → To**: the two entities (directed)
   - **Type**: the relation type
   - **Evidence**: a brief quote or reference to the note(s) where this relation is grounded
   - **Confidence**: high (explicitly stated), medium (clearly implied), or low (inferred from patterns)
   - **Status**: active (currently true), historical (was true, may not be now), or contested (debatable)

4. **Cluster by entity.** Group relations around their most-connected entities. This reveals which entities are hubs of the author's thinking.

## Output format

Write to `ontology_relations.md`:

```markdown
# Ontology: Relations

**Date:** YYYY-MM-DD
**Entities referenced:** N
**Relations extracted:** N

## Relations (grouped by source entity)

### [Entity Name] (N relations)

1. **[Entity A] → enables → [Entity B]**
   - Evidence: "[quote or note reference]"
   - Confidence: high | medium | low
   - Status: active | historical | contested

2. **[Entity A] → contradicts → [Entity C]**
   ...

### [Next Entity]
...

## Most Connected Entities

| Entity | Outgoing | Incoming | Total |
|--------|----------|----------|-------|
| ...    | ...      | ...      | ...   |
```

## Constraints

- Extract 30-100 relations. Quality over quantity.
- Every relation must have evidence — no speculative connections.
- Only include relations at confidence medium or above. Low-confidence relations go in a separate "Speculative" section at the end, if included at all.
- Historical relations matter — they show how thinking evolved. Mark them clearly.
