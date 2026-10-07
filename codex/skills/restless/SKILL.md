---
name: restless
description: "Use for any task involving the Restless API: monitor API usage, fix docs. Includes finding endpoints, debugging failed requests, reading the user's own request logs, and making real calls. Use when the user says things like \"Use Restless to find what is behind the jump in failed requests and read the log that proves it.\", \"Use Restless to list end-users whose error rate is climbing and show what is failing for them.\", \"Use Restless to update the getting started page for my project.\", \"Why is my Restless API request failing?\", \"Why did Restless errors spike today?\", \"Which users are getting errors from Restless?\", \"Which Restless endpoint do I use to do this?\", \"Call the Restless API for me\"."
---

# Restless

See how your API behaves in production and fix what's breaking, without leaving your agent. Trace a spike in failed requests to the exact log behind it, find the users hitting the most errors, and turn feedback from confused agents into docs fixes. Keep your docs and recovery guidance current as you go.

The `restless` MCP server bundled with this plugin is the source of truth for this API. Answer from it, not from memory: endpoint shapes, docs, and the user's own traffic all come from its tools.

## When to use

- "Use Restless to find what is behind the jump in failed requests and read the log that proves it."
- "Use Restless to list end-users whose error rate is climbing and show what is failing for them."
- "Use Restless to update the getting started page for my project."
- "Why is my Restless API request failing?"
- "Why did Restless errors spike today?"
- "Which users are getting errors from Restless?"
- "Which Restless endpoint do I use to do this?"
- "Call the Restless API for me"

## Tools

The server's tools change with the API and with whether the user has signed in, so read its tool list rather than assuming one. Signing in adds tools for the user's own request logs and account. Use the docs and endpoint tools to find the right operation and read its full definition before calling it.

## Making real calls

Use `call_endpoint`, never a hand-built curl command, and never read API keys from the environment or the filesystem. The first call asks the user to sign in and connect their key in the browser. Surface that prompt to them instead of looking for a key elsewhere.

## More

- Docs: https://build.restless.ai
- Index for agents: https://build.restless.ai/llms.txt
- Support: support@restless.ai
