# Connection guide

The project-designated server URL is:

```text
https://ai.primesync.me/mcp/v1
```

Use a client that supports remote MCP connections. In that client's connector configuration, supply the URL above and complete any authorization flow it presents. Interface names and account eligibility depend on the client; this guide does not assert a tested client-specific setup.

After connecting, inspect the tools your client exposes. The documentation session exposed `primesync_research_builder`. If the client exposes a different contract, use its current schema instead of assuming older examples are compatible.

Start with an explicit request such as:

> Use PrimeSync AI Studio to design a new Pine Script v6 indicator from the rules I provide. List any missing rules before implementation. Do not import a previous strategy or create a profile.

## Troubleshooting

- Connection failure: record the client name, time, and redacted error. Verify the configured URL.
- Authorization failure: reconnect through the client's supported authorization flow. Never paste tokens into a public issue.
- Missing tool: inspect the current tool list and record which names are available.
- Incompatible parameters: compare the current client schema against this repository's dated declaration.
- Missing results: distinguish a proposed workflow from a computed result. Supply the data needed for the requested analysis.

Endpoint reachability and authorization were not successfully tested while preparing this repository.

