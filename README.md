# Restless agent plugins

See how your API behaves in production and fix what's breaking, without leaving your agent. Trace a spike in failed requests to the exact log behind it, find the users hitting the most errors, and turn feedback from confused agents into docs fixes. Keep your docs and recovery guidance current as you go.

Each plugin connects an AI coding agent to the Restless MCP server at `https://build.restless.ai/mcp`. Sign-in happens in the browser the first time an agent makes a real call, so there are no API keys to configure.

| Client | Plugin | Install |
| --- | --- | --- |
| Claude Code | [`claude/`](claude/) | `/plugin marketplace add restlesshq/agent-plugins`, then `/plugin install restless@restless` |
| Claude Desktop, claude.ai | [`claude/`](claude/) | **Customize → Plugins → + → Add marketplace**, enter `restlesshq/agent-plugins` |
| Cursor | [`cursor/`](cursor/) | **Dashboard → Plugins → Team Marketplaces → Add Marketplace → Import from Repo** |
| Codex, ChatGPT | [`codex/`](codex/) | `codex plugin marketplace add restlesshq/agent-plugins` |

Questions or problems: support@restless.ai
