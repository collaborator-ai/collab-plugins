---
name: initiative-goals
description: >
  Read a notes collection deeply and infer a hierarchical goal tree.
  Requires initiative-scan to have run first.
argument-hint: <path-to-notes-directory>
---

# Initiative: Goals

You are reading a collection of personal notes to infer what the author is trying to achieve. Your job is to construct a hierarchical goal tree — strategic goals at the top, tactical goals beneath, concrete steps at the leaves.

## Input

- A directory of markdown notes (the target directory)
- The scan output from Stage 1 (provided by the orchestrator, or `initiative_scan.md` in the output directory)

Read the scan first. Use its topic clusters and activity timeline to guide where you read deeply.

## What to do

### 1. Separate motivations from goals

Before looking for goals, identify the author's **motivations** — the deep *why* behind the work. Motivations are values, missions, and beliefs that don't decompose into tasks. Examples: "keep humans meaningfully in the loop," "build something that matters," "own the category."

Motivations go in their own section. They are NOT goals. They provide context for why goals matter, but they don't have tactical sub-goals or concrete steps.

### 2. Read for stated goals

Search the notes for explicit statements of intent. These show up as:
- "The goal is...", "We need to...", "I want to..."
- Notes with titles like "Vision", "Strategy", "Roadmap", "Plan", "Goals"
- Pitch documents, position papers, planning notes
- Action items and to-do lists

Collect every stated goal verbatim with its source note.

### 3. Read for implied goals

Implied goals are things the author never explicitly states but clearly cares about, revealed by behavior:
- **Repetition** — Topics revisited across 5+ notes imply a goal the author keeps circling
- **Refinement** — When the same idea gets rewritten in progressively sharper language, the author is converging on something
- **Negative space** — What the author argues *against* implies what they're trying to achieve (e.g., arguing against "AI personalization framing" implies a goal of finding a different positioning)
- **Resource allocation** — Where the most notes concentrate (by topic cluster) reveals where the author invests thinking time

For each implied goal, cite the evidence (which notes, what pattern).

### 4. Build the goal tree

Organize into a hierarchy:

**Strategic goals** (3-5 — no more): The big things. These are directional — "launch the product", "establish technical credibility", "resolve the core positioning question." A strategic goal takes weeks or months.

If two strategic goals are really the same problem at different levels, **merge them**. Prefer fewer, sharper goals over comprehensive coverage. For example, "ship the product," "resolve the positioning," and "define the product stack" may all be facets of one goal: "ship a defined product."

**Tactical goals** (under each strategic goal): The workstreams. These are scoped — "finalize the pitch deck", "choose between architecture options", "build the demo." A tactical goal takes days to a week.

**Concrete steps** (under each tactical goal): The leaf nodes. These are actionable in a single sitting — "write the executive summary", "benchmark option A vs B", "prototype the search UI." Every concrete step must pass the "sit down and do it" test: can a person start and finish this in one focused session? If not, decompose further or move it up to a tactical goal.

### 5. Distinguish confidence levels

Not all goals are equally clear from the notes. Mark each goal:
- **Explicit** — directly stated in the notes
- **Strong inference** — heavily implied by multiple notes
- **Weak inference** — suggested by the evidence but you could be wrong

### 6. Identify goal tensions

Sometimes goals conflict. The author may want to "ship fast" and also "get the architecture right." These tensions are valuable — they reveal decisions that need to be made. List them.

## Output

Write the goals output to the location specified by the orchestrator. If running standalone, write `initiative_goals.md` in the output directory. Structure it as:

```markdown
# Initiative Goals

**Derived from:** [N notes read] / [total notes in collection]
**Last updated:** [date]

## Motivations
[The deep *why* — values, missions, beliefs. These are not goals; they don't have sub-tasks. They provide context for why the goals matter.]

1. **[Motivation]** — [evidence from notes]
2. ...

## Goal tree

### 1. [Strategic goal] [explicit|strong|weak]
> [Evidence: which notes, what pattern]

#### 1.1 [Tactical goal] [explicit|strong|weak]
- [ ] [Concrete step]
- [ ] [Concrete step]

#### 1.2 [Tactical goal]
- [ ] [Concrete step]

### 2. [Strategic goal]
...

(3-5 strategic goals max. If you have more, merge related ones.)

## Goal tensions
- **[Goal A] vs [Goal B]:** [description of the tension, where it shows up in the notes]

## Unclassified signals
[Anything that looks goal-relevant but you couldn't place in the tree]
```

## Constraints

- Ground every goal in specific notes. No free-floating inferences.
- When uncertain, say so. "Weak inference" is more useful than false confidence.
- Do NOT prescribe goals the author doesn't have. You are reading, not advising.
- Do NOT modify any existing notes. Only write to the output location.
- Concrete steps should be phrased as things a person could sit down and do, not vague directives. "Write the intro paragraph for the pitch deck" not "Work on the pitch deck."
