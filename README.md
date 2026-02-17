# Collaborator

Reflection and ontology pipelines for collections of user notes. Turn any folder of markdown into actionable insight.

## Skills

### `/collaborator:initiative`

Run the Initiative pipeline against a notes collection — an Obsidian vault, a Seedvault collection, or any folder of markdown. The pipeline surveys your notes, infers your goals, identifies what's stuck, derives prioritized actions, synthesizes a cross-cutting brief, and proposes concrete work to do next.

**Pipeline:** Scan → Goals → Blockers → Actions → Brief → Proposals

Point it at a directory of markdown files and it produces:
- A **goal tree** grounded in your actual notes, not assumptions
- **Blockers** with severity ratings and meta-insights about patterns of change
- **Prioritized actions** scored by leverage and momentum
- A **brief** identifying the critical path — the one thing that unblocks everything else
- **Proposals** for work an AI agent can do immediately (research, drafts, analysis)

### `/collaborator:ontology`

Run the Ontology pipeline against a notes collection. Extracts a three-layer knowledge structure that maps where your thinking is coherent and where unresolved tensions live.

**Pipeline:** Extract → Relations → Alignments → Synthesis

This is not a classical knowledge graph. The value is in the third layer:

- **Entities** — concepts, decisions, products, people, principles, goals, and problems extracted from your notes
- **Relations** — directed connections between entities (enables, blocks, contradicts, replaced, depends-on, etc.)
- **Alignments** — edges between *relations* that reveal whether two connections confirm each other (positive) or pull against each other (negative/tension)

The synthesis identifies:
- **Load-bearing beliefs** — the strongest positive alignments, where conviction is highest
- **Active tensions** — unresolved negative alignments that demand decisions
- **Implications for action** — where the ontology suggests you need to act

## Install

```bash
# Add the marketplace
/plugin marketplace add collaborator-ai/collab-plugins

# Install the plugin
/plugin install collaborator@collab-plugins
```

Then use in Claude Code:
- `/collaborator:initiative <path-to-notes>`
- `/collaborator:ontology <path-to-notes>`

## Examples

See the [examples/](examples/) directory for sample pipeline outputs from three different use cases:
- **Solo founder** — 500+ product notes over 7 months
- **Research lead** — 200+ notes across a multi-year project
- **Engineering manager** — 300+ docs inherited from a new team

## What is Collaborator?

A set of tools that turn an OpenClaw agent into a thinking partner. [Learn more](https://collaborator.bot).

## License

MIT
