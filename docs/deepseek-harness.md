# PrimeSync AI Studio for DeepSeek Harness

Status: experimental preview, 2026-10-23. Full customer sign-in and tool execution are pending verification.

This bundle connects DeepSeek Harness to the existing hosted Studio MCP service. It contains no proprietary strategy or server code. It does not change Studio subscriptions, quotas, or the separate website assistant credit balance.

## Requirements

- DeepSeek Harness 0.2.1-rc.2 (the configured compatibility target; see verification below).
- Node.js 22 or newer with `npx` available to Harness.
- A browser on the same computer and an eligible PrimeSync Studio account.
- Network access to the npm registry and ai.primesync.me.

## Installation

```sh
dsh plugin --profile web add github:nabehkh-source/primesync-ai-studio
```

The package is distributed through GitHub; it is not published to npm. It contains a configuration patch only and requires no build script. The patch uses the official `@deepseek-ai/dsh-mcp-client` and invokes the third-party `mcp-remote` bridge pinned to 0.15.2. On first launch, npx downloads that bridge and its dependencies. Review those dependencies before installing.

## First sign-in

Before starting Harness, complete OAuth on the same computer:

```sh
npx --yes mcp-remote@0.15.2 https://ai.primesync.me/mcp/v1 --transport http-only --resource https://ai.primesync.me/mcp/v1 --auth-timeout 300 --static-oauth-client-metadata '{"client_name":"PrimeSync AI Studio for DeepSeek Harness","token_endpoint_auth_method":"none"}'
```

Open the authorization link shown by the bridge if the browser does not open. Sign in using the Whop account that owns your Studio access and approve the displayed permissions. Once connection succeeds, stop that command with Ctrl+C and start/restart Harness with the `web` profile. Completing sign-in first avoids spending the Harness MCP startup timeout waiting for a browser approval.

The bridge manages OAuth credentials locally (its default cache is `~/.mcp-auth`). Do not copy credentials into this repository, a prompt, or a support ticket. The browser callback is on localhost; this walkthrough is for a local desktop, not an unattended remote container. A Whop password is never a configuration value.

## Verify before use

1. Confirm the `primesync` connection loads and its tools appear.
2. Inspect the live tool list; use each tool's current schema.
3. If a read-only account/status operation is exposed, check that the expected account is connected. Do not use an analysis job just to test discovery.
4. Run one explicitly chosen synthetic analysis and verify the returned result and account usage.
5. Restart Harness and verify reconnection. Check expired-token refresh and logout/reconnect before calling the integration production-ready.

## Troubleshooting

- No tools after startup: finish the standalone sign-in above, then restart Harness. A failed optional connection does not stop the rest of Harness.
- Whop access error: check that the purchase and Studio account use the same identity.
- Callback refused: record the redacted error. Do not weaken redirect URI validation or disable OAuth.
- `npx` missing: restart Harness after installing Node.js and ensure it can find Node/npm on PATH.
- Wrong account: revoke this connection in Studio if available, then follow mcp-remote's account/cache guidance for this server only. Do not delete all other MCP connections' credentials.
- Version mismatch: this preview targets the version above. Do not bypass compatibility checks; retest and update the manifest first.

## Verification record

- Live unauthenticated Studio endpoint returned HTTP 401 with an OAuth protected-resource metadata challenge.
- Authorization metadata advertises authorization-code/refresh grants, S256 PKCE, dynamic registration, and public-client token authentication.
- The patch follows the official Harness bundle and MCP-client configuration documentation.
- Harness 0.2.1-rc.2 successfully installed the local bundle into an isolated profile; its composed configuration contains the PrimeSync MCP entry. Package dry-run and YAML/JSON parsing passed.
- The OAuth bridge version was resolved from the npm registry and pinned in the patch.
- Running that bridge against the live endpoint completed discovery and dynamic client registration and generated a PKCE authorization request with the correct resource and localhost callback. The run stopped before customer consent.
- Customer consent, token exchange, tool discovery, tool results, refresh, and full Harness runtime compatibility are not yet verified.

A public repository or directory entry is not DeepSeek review or endorsement. The normal DeepSeek chat/mobile app is outside this preview's scope. A directory can index this repository, but installation does not guarantee inclusion in every Harness user's Discover tab.

## References

- https://www.deepseek.com/en/harness/
- https://github.com/deepseek-ai/deepseek-harness/blob/master/docs/user/develop/basic/publish.md
- https://github.com/deepseek-ai/deepseek-harness/blob/master/packages/mcp/mcp-client/README.md
- https://github.com/punkpeye/mcp-remote
