# Publishing

## Checking the manifests

Claude Code can validate the plugin before a release:

```sh
claude plugin validate --strict claude
claude plugin validate --strict .claude-plugin/marketplace.json
```

## Publishing to the MCP Registry

`server.json` lists the server as `ai.restless/restless`. The registry checks that you own `restless.ai` with a DNS TXT record on that apex domain. Install [`mcp-publisher`](https://github.com/modelcontextprotocol/registry), then:

```sh
MY_DOMAIN="restless.ai"
openssl genpkey -algorithm Ed25519 -out key.pem
PUBLIC_KEY="$(openssl pkey -in key.pem -pubout -outform DER | tail -c 32 | base64)"
echo "${MY_DOMAIN}. IN TXT \"v=MCPv1; k=ed25519; p=${PUBLIC_KEY}\""

# Add that TXT record at your DNS provider, wait for it to propagate, then:
PRIVATE_KEY="$(openssl pkey -in key.pem -noout -text | grep -A3 "priv:" | tail -n +2 | tr -d ' :\n')"
mcp-publisher login dns --domain "${MY_DOMAIN}" --private-key "${PRIVATE_KEY}"
mcp-publisher publish
```

Ed25519 needs OpenSSL 3 (on macOS, `brew install openssl@3`). Keep `key.pem` out of this repository.

## Releasing an update

Publish updates from Restless (MCP Server, then Marketplaces): edit the listing, raise the version, and publish. Restless rewrites the files it manages on every publish, so make changes there rather than in this repository. Claude picks up new versions automatically; check each other directory's rules for updates.
