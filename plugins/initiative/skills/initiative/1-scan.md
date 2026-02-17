---
name: initiative-scan
description: >
  Survey a collection of personal notes to build a structural map.
  Run this first before other Initiative stages.
argument-hint: <path-to-notes-directory>
---

# Initiative: Scan

You are surveying a collection of personal notes to build a working map of what's here. This is the first stage of the Initiative pipeline. Your output is consumed by later stages — be thorough but concise.

## Input

A directory path containing markdown files (flat or nested). These are personal notes — think Obsidian vault, Zettelkasten, or working journal. They may have YAML frontmatter or may be plain markdown.

## What to do

### 1. Take inventory

Count total notes. Check for subdirectory structure or if it's flat. Note the file naming conventions you observe — prefixes like `[DRAFT]`, `[WIP]`, topic-based names, date-based names, or freeform titles.

### 2. Sample across time

Sort files by modification date. Read 3-5 of the oldest, 3-5 of the newest, and 3-5 from the middle. You need to understand how the collection has evolved, not just where it is now.

### 3. Identify topic clusters

After sampling, use search to probe for recurring themes. Look for:
- Words and phrases that appear across many notes
- Naming patterns that suggest intentional grouping (shared prefixes, colons as separators)
- Repeated proper nouns (product names, people, tools, frameworks)

Group what you find into 5-10 topic clusters. Name each cluster with a short phrase. Estimate how many notes belong to each.

### 4. Note the metadata patterns

If notes have frontmatter, document the schema. What fields exist? Are they consistent? Do they carry information that's useful for later stages (author, type, status, tags)?

If notes don't have frontmatter, note that too — it means structure lives in the filenames and content, not metadata.

### 5. Detect authorship patterns

Are all notes written by the same person? If there are multiple authors (common when AI assistants help take notes), note the different voices. This matters because human-written notes carry intent differently than AI-generated summaries.

### 6. Map the recency distribution

Where is the energy? Are notes concentrated in a recent burst, spread evenly, or clustered around specific periods? Identify the 2-3 most active periods and what topics dominated each.

### 7. Assess note quality distribution

Not all notes carry equal signal. Estimate what percentage of notes are:
- **High-signal** — contain decisions, original thinking, specific plans, or concrete artifacts (drafts, specs, pitches)
- **Medium-signal** — contain useful context, summaries, or explorations but no decisions
- **Low-signal** — conversation artifacts, trivial captures, duplicates, or notes that exist only because an AI generated them during a session (e.g., "Mid-conversation break" or restating what the user just said)

This calibrates how aggressively later stages should sample. A vault that's 80% high-signal can be sampled lightly; one that's 80% noise needs heavier filtering.

## Output

Write the scan output to the location specified by the orchestrator. If running standalone, write `initiative_scan.md` in the target directory. Structure it as:

```markdown
# Initiative Scan

**Collection:** [directory name]
**Total notes:** [count]
**Date range:** [oldest] to [newest]
**Structure:** [flat / nested — describe]

## Naming conventions
[What patterns you observed]

## Topic clusters
1. **[Cluster name]** (~N notes) — [one-sentence description]
2. ...

## Metadata patterns
[Frontmatter schema if present, or "no frontmatter"]

## Authorship
[Single author / multiple — describe]

## Activity timeline
[Where the energy is concentrated, what topics dominated each period]

## Note quality distribution
[Estimated percentages: high-signal / medium-signal / low-signal, with examples of each]

## Raw observations
[Anything notable that doesn't fit the above — contradictions, surprises, gaps]
```

## Constraints

- Do NOT infer goals yet. That's the next stage. You are mapping terrain, not interpreting it.
- Do NOT read every note. Sample strategically. You can always go deeper in later stages.
- Do NOT modify any existing notes. Only write to the output location.
- Keep your output factual. "There are 12 notes about pricing" not "The author is struggling with pricing."
