# Capabilities and tool reference

## Observed interface

The connected integration exposed `primesync_research_builder`. This page summarizes its declaration; it is not a runtime test report. The [captured declaration](tool-declaration.md) contains the complete parameter types.

| Parameter | Purpose |
| --- | --- |
| `goal` | Required: exact current request |
| `taskMode` | Select design, analysis, conversion, validation, optimization, or Monte Carlo work |
| `specification` | Additional rules and requirements |
| `baseCode`, `candidateCode` | Code supplied for preservation, comparison, or review |
| `preservation` | Declare logic, order behavior, visual setups, and protected sections to preserve |
| `datasets` | TradingView List of Trades CSV text with asset and timeframe |
| `objective` | `highest_pnl`, `best_winrate`, `lowest_drawdown`, `balanced`, or `robustness` |
| `validation` | Bootstrap method, simulations, seed, holdout, folds, and trade-count settings |
| `output` | Code, report, machine-readable rules, Pine filter block, and Pine version preferences |
| `allowedEntryFeatures` | Allowed entry dimensions for research |
| `visualReference` | Supplied visual reference |

## Task modes

`auto`, `analyze`, `monte_carlo`, `optimize_existing`, `cross_asset_research`, `design_experiment`, `build_strategy`, `build_indicator`, `convert_indicator_to_strategy`, `convert_strategy_to_indicator`, `validate_code`.

## Declared behavior

- Work from the current request and relevant supplied files.
- Support entirely new designs without forcing previous PrimeSync versions into them.
- Support code repair and conversion with requested logic or visual preservation.
- Support PnL, win-rate, drawdown, and robustness objectives.
- Create profiles only when explicitly requested.
- Do not store strategy code, execute submitted code, contact brokers, or place trades.

The last points describe the tool's declared contract. Retention, access isolation, and runtime enforcement were not audited.

The declaration does not provide a stable typed response schema. Consumers must inspect actual results and must not assume numeric results or complete executable code will always be returned.

## Alerts

Specify desired alert conditions, timing, and message fields in the request specification when relevant to generated code. A dedicated alert delivery or notification service is not exposed by this tool declaration. Generated alert code was not tested in this documentation task.

## Older tool names

Previous project discussions referenced separate builder, audit, import, and Monte Carlo tools. They were not exposed in this session and are not presented here as verified current interfaces.

