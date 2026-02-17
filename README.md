# Collaborator

Skills for working with collections of user notes to extract actionable insights.

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

## Install

```bash
# Add the marketplace
/plugin marketplace add collaborator-ai/collab-plugins

# Install the plugin
/plugin install collaborator@collab-plugins
```

Then use `/collaborator:initiative <path-to-notes>` in Claude Code.

## Examples

See the [examples/](examples/) directory for sample pipeline outputs from three different use cases:
- **Solo founder** — 500+ product notes over 7 months
- **Research lead** — 200+ notes across a multi-year project
- **Engineering manager** — 300+ docs inherited from a new team

## What is Collaborator?

When everything is buildable, the bottleneck becomes knowing the right thing to build. [Collaborator](https://collaborator.bot) helps AI power users decide what to build next — and why.

## License

MIT
