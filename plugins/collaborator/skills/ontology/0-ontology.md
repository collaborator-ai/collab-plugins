---
name: ontology
description: >
  Run the Ontology pipeline against a notes collection.
  Extracts entities, maps relations between them, then identifies
  alignments (confirmations and tensions) between relations.
  Writes all outputs to a timestamped subdirectory.
argument-hint: <path-to-notes-directory>
---

# Ontology

Run the Ontology pipeline against a collection of personal notes to extract a three-layer knowledge structure: entities, relations, and alignments.

This is not a classical knowledge graph. The value is in the third layer — alignments between relations — which reveals where thinking is coherent and where unresolved tensions live.

## Input

A directory path containing markdown files. This is the **target directory** — the notes collection to analyze.

The skill instruction files (1-extract.md through 4-synthesis.md) live alongside this file. Find them relative to this file's location.

## The Three Layers

1. **Entities** — concepts, decisions, people, products, principles, and other named things that appear across notes
2. **Relations** — directed connections between entities (A enables B, A contradicts B, A replaced B, A depends on B, etc.)
3. **Alignments** — edges between *relations* that indicate whether two relations point the same way (positive/confirming) or pull against each other (negative/tension)

## Pipeline

Execute these 4 stages in order.

### Setup

1. Locate the skill instruction files in the same directory as this file: `1-extract.md`, `2-relations.md`, `3-alignments.md`, `4-synthesis.md`.
2. Create an output directory inside the target directory: `_ontology_YYYY-MM-DD/` (using today's date). If it already exists, overwrite the files inside it.
3. Check if a previous ontology exists from an earlier run. Look for other `_ontology_*/ontology_synthesis.md` files in the target directory, picking the most recent one that isn't today's. If found, copy it to the new output directory as `_previous_ontology.md` so the synthesis stage can diff against it.

### Stage 1: Extract Entities

Read `1-extract.md` from the skill directory. Follow its instructions against the target directory. Write output to `_ontology_YYYY-MM-DD/ontology_entities.md`.

### Stage 2: Map Relations

Read `2-relations.md`. Follow its instructions. Read the entities output before starting. Write output to `_ontology_YYYY-MM-DD/ontology_relations.md`.

### Stage 3: Identify Alignments

Read `3-alignments.md`. Follow its instructions. Read the entities and relations outputs before starting. Write output to `_ontology_YYYY-MM-DD/ontology_alignments.md`.

### Stage 4: Synthesis

Read `4-synthesis.md`. Follow its instructions. Read all 3 pipeline outputs and the previous ontology (if it exists) before starting. Write output to `_ontology_YYYY-MM-DD/ontology_synthesis.md`.

## After the pipeline

Print a short summary to the user:
- Which directory the outputs were written to
- How many entities and relations were extracted
- The top 3-5 strongest alignments (positive)
- The top 3-5 sharpest tensions (negative)
- A pointer to the full synthesis for details

## Constraints

- Do NOT modify any existing notes in the target directory. Only write to the `_ontology_YYYY-MM-DD/` output directory.
- Do NOT skip stages. The pipeline is sequential.
- Do NOT combine stages. Each stage has its own instructions.
- If a stage's instructions say to sample N notes, respect that.
- Entity and relation extraction should be conservative — fewer high-confidence items beat many speculative ones.
