# Stage 3: Identify Alignments

This is the core of the ontology — the layer that makes it actionable. Alignments are edges between *relations*, revealing where the author's thinking is coherent and where it's in tension.

## What is an alignment?

An alignment connects two relations and says: these two connections either **confirm** each other (positive alignment) or **pull against** each other (negative alignment / tension).

### Positive alignment (confirming)
Two relations that reinforce the same direction. When both are true, conviction in that direction should be stronger.

**Example:**
- Relation 1: "Collaborator is a judgment product" (concept → defines → product)
- Relation 2: "Initiative pipeline produces strategic recommendations" (product → enables → goal)
- Alignment: **positive** — both point toward Collaborator's value being in judgment, not memory. The pipeline is evidence that the positioning is real.

### Negative alignment (tension)
Two relations that pull in opposite directions. Both may be true, but they create an unresolved decision or contradiction.

**Example:**
- Relation 1: "Collaborator is the product, Seedvault is infrastructure"
- Relation 2: "Borthwick responded most to Seedvault/editor"
- Alignment: **negative** — the product strategy says lead with the agent, but the market signal points at the infrastructure. This tension is unresolved and demands a decision.

## Process

1. **Read the entities and relations outputs** from Stages 1 and 2.

2. **Find alignment candidates.** Look for pairs of relations that:
   - Share an entity (two relations connected to the same node)
   - Point in the same or opposite directions regarding a decision, goal, or position
   - Create a meaningful signal when considered together (not just coincidental overlap)

3. **Classify each alignment:**
   - **Polarity**: positive (confirming) or negative (tension)
   - **Strength**: strong (clearly reinforcing/contradicting), moderate (noticeable but not decisive), or weak (suggestive)
   - **Resolution status**: resolved (a decision was made), unresolved (still open), or evolving (in process of being worked out)
   - **Implication**: what does this alignment mean for the author? What decision does it point toward, or what conviction does it strengthen?

4. **Rank by impact.** The most important alignments are:
   - Strong negative alignments that are unresolved (these are the biggest open questions)
   - Strong positive alignments (these are the areas of highest conviction)
   - Alignments that connect to active goals or decisions

## Output format

Write to `ontology_alignments.md`:

```markdown
# Ontology: Alignments

**Date:** YYYY-MM-DD
**Relations analyzed:** N
**Alignments found:** N (P positive, Q negative)

## Tensions (Negative Alignments, ranked by impact)

### 1. [Tension Name]
- **Relation A:** [Entity] → [type] → [Entity] — "[evidence]"
- **Relation B:** [Entity] → [type] → [Entity] — "[evidence]"
- **Polarity:** negative
- **Strength:** strong | moderate | weak
- **Status:** unresolved | evolving | resolved
- **Implication:** [What decision does this tension demand? What happens if it stays unresolved?]

### 2. [Tension Name]
...

## Confirmations (Positive Alignments, ranked by strength)

### 1. [Confirmation Name]
- **Relation A:** [Entity] → [type] → [Entity] — "[evidence]"
- **Relation B:** [Entity] → [type] → [Entity] — "[evidence]"
- **Polarity:** positive
- **Strength:** strong | moderate | weak
- **Implication:** [What conviction does this strengthen? What action does it support?]

### 2. [Confirmation Name]
...

## Alignment Clusters

[Group alignments that share entities or themes. These clusters reveal the fault lines and pillars in the author's thinking.]
```

## Constraints

- Find 10-30 alignments. Focus on the ones that matter.
- Every alignment must connect exactly two relations from Stage 2.
- Don't manufacture tensions — they must be grounded in the actual notes.
- Negative alignments are more valuable than positive ones. Tensions are where the action is.
- The implication field is critical — don't leave it vague. Be specific about what decision or action each alignment points toward.
