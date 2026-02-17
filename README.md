# collab-plugins

Plugins from the [Collaborator](https://collaborator.bot) project. Bring persistent AI judgment into your coding tools.

## Plugins

### `/initiative`

Run the Initiative pipeline against a notes collection. Surveys your vault, infers goals, identifies blockers, derives prioritized actions, synthesizes a cross-cutting brief, and proposes work the Collaborator should do next.

**Pipeline:** Scan → Goals → Blockers → Actions → Brief → Proposals

### `/collab`

Invoke the Collaborator persona in any AI coding tool. Loads identity, context, memory, and active stances — turning your AI into a creative partner with opinions about your work.

## Install

```bash
# Add the marketplace
/plugin marketplace add collaborator-ai/collab-plugins

# Install a plugin
/plugin install initiative@collab-plugins
/plugin install collab@collab-plugins
```

## What is Collaborator?

When everything is buildable, the bottleneck becomes knowing the right thing to build. Collaborator helps AI power users decide what to build next — and why.

Built on composable, standalone open-source modules:
- **[Vibevault](https://github.com/collaborator-ai/vibevault)** — Pretty markdown browser and editor
- **[Seedvault](https://github.com/collaborator-ai/seedvault)** — Markdown sync for human-agent context pooling
- **[collab-mcp](https://github.com/collaborator-ai/collab-mcp)** — Bring agent personas into any AI tool via MCP

## License

MIT
