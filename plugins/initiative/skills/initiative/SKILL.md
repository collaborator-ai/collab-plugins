---
name: initiative
description: >
  Run the full Initiative pipeline against a notes collection.
  Scans the vault, infers goals, identifies blockers, derives actions,
  then synthesizes a brief. Writes all outputs to a timestamped subdirectory.
argument-hint: <path-to-notes-directory>
---

# Initiative

Run the full Initiative pipeline against a collection of personal notes to infer goals, identify blockers, derive actions, and produce a synthesis brief.

## Input

A directory path containing markdown files. This is the **target directory** — the notes collection to analyze.

The skill instruction files (1-scan.md through 5-brief.md) live alongside this file. Find them relative to this file's location.

## Pipeline

Execute these 4 stages in order, then run the synthesis.

### Setup

1. Locate the skill instruction files. They are in the same directory as this file: `1-scan.md`, `2-goals.md`, `3-blockers.md`, `4-actions.md`, `5-brief.md`.
2. Create an output directory inside the target directory: `_initiative_YYYY-MM-DD/` (using today's date). If it already exists, overwrite the files inside it.
3. Check if a previous brief exists from an earlier run. Look for other `_initiative_*/initiative_brief.md` files in the target directory, picking the most recent one that isn't today's. If found, copy it to the new output directory as `_previous_brief.md` so the brief stage can diff against it.

### Stage 1: Scan

Read `1-scan.md` from the skill directory. Follow its instructions against the target directory. Write output to `_initiative_YYYY-MM-DD/initiative_scan.md` inside the target directory.

### Stage 2: Goals

Read `2-goals.md`. Follow its instructions. Read the scan output before starting. Write output to `_initiative_YYYY-MM-DD/initiative_goals.md`.

### Stage 3: Blockers

Read `3-blockers.md`. Follow its instructions. Read the scan and goals outputs before starting. Write output to `_initiative_YYYY-MM-DD/initiative_blockers.md`.

### Stage 4: Actions

Read `4-actions.md`. Follow its instructions. Read the goals and blockers outputs before starting. Write output to `_initiative_YYYY-MM-DD/initiative_actions.md`.

### Synthesis: Brief

Read `5-brief.md`. Follow its instructions. Read all 4 pipeline outputs and the previous brief (if it exists) before starting. Write output to `_initiative_YYYY-MM-DD/initiative_brief.md`.

## After the pipeline

Print a short summary to the user:
- Which directory the outputs were written to
- How many notes were sampled out of the total
- The "Where you are" section from the brief
- The critical path from the brief
- A pointer to the full brief and actions files for details

## Constraints

- Do NOT modify any existing notes in the target directory. Only write to the `_initiative_YYYY-MM-DD/` output directory.
- Do NOT skip stages. The pipeline is sequential — each stage depends on the previous ones.
- Do NOT combine stages. Each stage has its own instructions and should be followed independently.
- If a stage's instructions say to sample N notes, respect that — do not read the entire vault.
