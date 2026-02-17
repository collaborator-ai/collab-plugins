# Stage 1: Extract Entities

Extract the named things that matter from the notes collection. These are the nodes of the ontology.

## What counts as an entity

An entity is anything that:
- Has a name or can be given one
- Appears across multiple notes or is central to a single important note
- Plays a role in decisions, goals, or the author's thinking

### Entity types

- **Concept** — an idea, framework, or mental model (e.g., "judgment product," "agent-first editor," "compound memory")
- **Product** — a named thing being built (e.g., "Seedvault," "Collaborator," "Vibevault")
- **Decision** — a choice that was made or is pending (e.g., "lead with Collaborator over Seedvault," "park ontology")
- **Person** — someone who appears in the notes (e.g., a collaborator, investor, user)
- **Principle** — a stated rule or value (e.g., "composable, standalone, open-source")
- **Goal** — something being worked toward (e.g., "raise pre-seed," "ship v1")
- **Problem** — a named difficulty or blocker (e.g., "scope creep," "positioning instability")

## Process

1. **Sample the notes.** Read up to 100 notes from the target directory. Prioritize recent notes and longer notes (which tend to contain more substance). If there are fewer than 100, read them all.

2. **Extract entities.** For each note, identify entities that appear. For each entity, record:
   - **Name**: a short, canonical name
   - **Type**: one of the types above
   - **First seen**: which note(s) it appeared in
   - **Description**: 1-2 sentences capturing what this entity is, in the author's framing

3. **Deduplicate and merge.** The same entity may appear under different names across notes. Merge them, keeping the most descriptive name. Note aliases.

4. **Rank by centrality.** Which entities appear most often? Which are connected to the most other entities? Rank them. The top entities are the load-bearing concepts in the author's thinking.

## Output format

Write to `ontology_entities.md`:

```markdown
# Ontology: Entities

**Source:** [target directory name]
**Date:** YYYY-MM-DD
**Notes sampled:** N of M total

## Entities (ranked by centrality)

### 1. [Entity Name]
- **Type:** Concept | Product | Decision | Person | Principle | Goal | Problem
- **Aliases:** [other names used]
- **Description:** [1-2 sentences]
- **Appears in:** [list of note titles, up to 5]

### 2. [Entity Name]
...
```

## Constraints

- Extract 20-60 entities. Fewer is better if it means higher quality.
- Be conservative. If you're unsure whether something is a distinct entity, leave it out.
- Use the author's language, not your own abstractions.
- Don't invent entities that aren't in the notes — extract, don't infer.
