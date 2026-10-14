# Captured tool declaration

Captured from the connected integration on 2026-09-12. The connector wrapper name in this snapshot is client-specific; it is not a server URL or standalone SDK.

Tools for working with PrimeSync AI Studio.

Primary current-request-first action for an entirely new strategy, a new indicator, trading experiments and models, isolated code repair without logic changes, indicator/strategy conversion with optional identical-arrow-and-level preservation, PnL/win-rate/drawdown/robustness optimization, universal cross-asset research, standalone Monte Carlo, and validation of fresh TradingView results. Profiles are created only when explicitly requested. The tool never forces old PrimeSync versions into a new request, stores strategy code, executes submitted code, contacts brokers, or places trades. This tool is part of plugin `PrimeSync AI Studio`.

exec tool declaration:
```ts
declare const tools: { mcp__codex_apps__primesync_studio_primesync_research_builder(args: {
  allowedEntryFeatures?: Array<"direction" | "time" | "weekday" | "session" | "setup_class" | "entry_regime">;
  baseCode?: string;
  candidateCode?: string;
  datasets?: Array<{
  asset: string;
  // TradingView List of Trades CSV text.
  csvText: string;
  filename?: string;
  mappingConfidence?: "confirmed" | "inferred";
  researchTimezone?: string;
  sourceTimezone?: string;
  symbol?: string;
  timeframe: string;
}>;
  // The exact current goal. Work only from this request and relevant supplied files.
  goal: string;
  objective?: "highest_pnl" | "best_winrate" | "lowest_drawdown" | "balanced" | "robustness";
  output?: { includeFullCode?: boolean; includeMachineReadableRules?: boolean; includePineFilterBlock?: boolean; includeReport?: boolean; pineVersion?: "preserve" | "v5" | "v6"; };
  preservation?: { allowedChangeScope?: Array<string>; preserveEntireBase?: boolean; preserveLogic?: boolean; preserveOrderBehavior?: boolean; preserveVisualSetups?: boolean; protectedSections?: Array<{ endMarker: string; name: string; startMarker: string; }>; };
  specification?: string;
  taskMode?: "auto" | "analyze" | "monte_carlo" | "optimize_existing" | "cross_asset_research" | "design_experiment" | "build_strategy" | "build_indicator" | "convert_indicator_to_strategy" | "convert_strategy_to_indicator" | "validate_code";
  validation?: { blockLength?: number; bootstrapMethod?: "circular_block" | "moving_block" | "independent"; bucketMinutes?: number; holdoutFraction?: number; minimumProfitFactor?: number; minimumTradesPerFold?: number; minimumTradesTotal?: number; randomSeed?: number; requirePositiveHoldout?: boolean; simulations?: number; validationFolds?: number; };
  visualReference?: string;
}): Promise<CallToolResult>; };
```

