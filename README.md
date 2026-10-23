# PrimeSync AI Studio

<img src="primesync-ai-studio-logo.png" alt="PrimeSync AI Studio" width="128" height="128">

Documentation and example requests for PrimeSync AI Studio's hosted Model Context Protocol (MCP) integration.

- Studio: [ai.primesync.me](https://ai.primesync.me)
- Project: [primesync.me](https://primesync.me)
- Project-designated MCP endpoint: `https://ai.primesync.me/mcp/v1`

PrimeSync AI Studio helps a connected AI work on strategy and indicator design, preservation of existing logic, TradingView trade-export analysis, optimization, and Monte Carlo research.

This repository contains public documentation and an experimental DeepSeek Harness configuration bundle. It does not contain the hosted server implementation or proprietary PrimeSync trading scripts.

## Start here

1. Follow the [connection guide](docs/connection.md).
2. Read the [capabilities and tool reference](docs/tools.md).
3. Choose an [example request](examples/README.md).
4. Follow the [research workflow](docs/workflow.md).
5. Review [privacy and security](SECURITY.md) and [verification status](docs/verification.md).

## DeepSeek Harness preview

An installable preview is available for DeepSeek Harness. Read the [setup and verification guide](docs/deepseek-harness.md) before installing. Full customer OAuth sign-in and end-to-end tool execution remain unverified; this is not a DeepSeek endorsement or a production compatibility claim.

## Scope and limitations

The connected tool declaration says it does not execute submitted code, contact brokers, place trades, or store strategy code. These are interface declarations, not independently audited guarantees.

Backtests must be run in a suitable external environment. Generated code and proposed improvements need validation before use. Research results do not guarantee future trading performance.

## Documentation status

Prepared on 2026-09-12 from the PrimeSync AI Studio tool declaration exposed to the documentation session. Endpoint availability, OAuth behavior, runtime outputs, and the server implementation were not verified. See the verification record for the exact evidence boundary.

No open-source license is granted by this documentation repository. No server source release is implied.

