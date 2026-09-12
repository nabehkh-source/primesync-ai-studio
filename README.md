# PrimeSync Studio MCP

Documentation and example requests for PrimeSync Studio's hosted Model Context Protocol (MCP) integration.

- Studio: [ai.primesync.me](https://ai.primesync.me)
- Project: [primesync.me](https://primesync.me)
- Project-designated MCP endpoint: `https://ai.primesync.me/mcp/v1`

PrimeSync Studio helps a connected AI work on strategy and indicator design, preservation of existing logic, TradingView trade-export analysis, optimization, and Monte Carlo research.

This repository contains documentation only. It does not contain the hosted server implementation or proprietary PrimeSync trading scripts.

## Start here

1. Follow the [connection guide](docs/connection.md).
2. Read the [capabilities and tool reference](docs/tools.md).
3. Choose an [example request](examples/README.md).
4. Follow the [research workflow](docs/workflow.md).
5. Review [privacy and security](SECURITY.md) and [verification status](docs/verification.md).

## Scope and limitations

The connected tool declaration says it does not execute submitted code, contact brokers, place trades, or store strategy code. These are interface declarations, not independently audited guarantees.

Backtests must be run in a suitable external environment. Generated code and proposed improvements need validation before use. Research results do not guarantee future trading performance.

## Documentation status

Prepared on 2026-09-12 from the PrimeSync Studio tool declaration exposed to the documentation session. Endpoint availability, OAuth behavior, runtime outputs, and the server implementation were not verified. See the verification record for the exact evidence boundary.

No open-source license is granted by this documentation repository. No server source release is implied.

