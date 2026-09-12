# Strategy research workflow

This is a recommended user workflow, not a claim that the server automatically executes every stage.

1. **Define the request.** Supply market, timeframe, timezone, sessions, entry and exit rules, risk sizing, execution timing, and objective. Resolve unspecified rules before coding.
2. **Set preservation boundaries.** For existing code, identify protected logic, order behavior, visual setups, and allowed changes.
3. **Review the blueprint.** Check that the proposed behavior matches the requested rules.
4. **Generate and review code.** Request full code and a report; inspect assumptions and unresolved issues.
5. **Run an external backtest.** Compile and run the code in the intended environment. Record capital, order sizing, commission, slippage, margin, chart symbol, timeframe, date range, and relevant execution settings.
6. **Export trades.** Supply TradingView List of Trades CSV text with the asset, timeframe, and timezone context.
7. **Analyze candidates.** Use a consistent objective and comparable properties. Keep a holdout where appropriate and avoid selecting from in-sample results alone.
8. **Run Monte Carlo analysis.** Record simulation count, random seed, bootstrap method, return unit, and assumptions. Require numerical outputs and definitions; do not invent missing results.
9. **Validate the final candidate.** If code changes after analysis, rerun the external backtest and analysis. Results from the previous version do not validate the new code.

## Results to request

Ask for the sample size, tested period, costs, net result, drawdown definition, win rate, losing streak, holdout results, and Monte Carlo downside statistics. Each reported number should identify its dataset and method.

Trade-export analysis cannot demonstrate how a newly changed entry rule would have performed without a fresh backtest. Monte Carlo analysis estimates outcomes under its assumptions; it does not prove the strategy has an edge.

