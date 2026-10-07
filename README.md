# Restless agent plugins

Read and manage your API's observability and documentation: request logs, end-user error rates, top endpoints, time-series metrics, docs content, use cases, context items, recovery messages, GitHub data sources, and agent feedback. An agent can trace a spike in failed requests to the log that proves it, find users whose error rates are climbing, turn confused-agent feedback into a docs edit and close it out, and attach recovery guidance to recurring errors. Writes are refused for read-only keys.

Each plugin connects an AI coding agent to the Restless MCP server at `https://build.restless.ai/mcp`. Sign-in happens in the browser the first time an agent makes a real call, so there are no API keys to configure.

| Client | Plugin | Install |
| --- | --- | --- |
| Claude Code | [`claude/`](claude/) | `/plugin marketplace add restlesshq/agent-plugins`, then `/plugin install restless@restless` |
| Claude Desktop, claude.ai | [`claude/`](claude/) | **Customize → Plugins → + → Add marketplace**, enter `restlesshq/agent-plugins` |
| Cursor | [`cursor/`](cursor/) | **Dashboard → Plugins → Team Marketplaces → Add Marketplace → Import from Repo** |
| Codex, ChatGPT | [`codex/`](codex/) | `codex plugin marketplace add restlesshq/agent-plugins` |

Questions or problems: support@restless.ai
