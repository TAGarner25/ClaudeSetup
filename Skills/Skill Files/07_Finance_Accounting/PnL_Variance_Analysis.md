---
name: variance-analysis
description: Decompose portfolio and fund P&L variances into drivers with narrative explanations, attribution analysis, and waterfall breakdowns. Use when analyzing period-over-period performance, budget vs actual comparisons, strategy-level attribution, factor decomposition, or preparing variance commentary for investors and internal review at a multi-strategy quantitative hedge fund.
---

# Variance Analysis — Quantitative Hedge Fund

**Important**: This skill assists with performance attribution and variance analysis workflows but does not provide investment advice. All analyses should be reviewed by qualified investment professionals.

Techniques for decomposing fund P&L variances, strategy attribution, risk factor decomposition, materiality thresholds, narrative generation, and waterfall chart methodology for a multi-strategy quantitative hedge fund.

## Fund-Level Variance Decomposition

### Total Fund Return Decomposition

Break total fund return variance into its component drivers:

```
FUND RETURN VARIANCE DECOMPOSITION
Period: [Current] vs [Prior / Budget / Benchmark]

Total Return Variance:  X.XX pp (percentage points)

Decomposition:
  1. Alpha (strategy-specific P&L)          X.XX pp
  2. Beta (systematic/market exposure)      X.XX pp
  3. Factor exposures (style, sector)       X.XX pp
  4. Carry / yield                          X.XX pp
  5. Financing / borrow cost drag           X.XX pp
  6. Fee drag (mgmt + perf fee)             X.XX pp
  7. FX effect                              X.XX pp
  8. AUM / leverage change effect           X.XX pp
  9. One-time items                         X.XX pp
                                            -------
  Total                                     X.XX pp  (must reconcile)
```

### Price / Volume Decomposition for Fund P&L

For gross trading P&L variance:

```
Total P&L Variance = Actual P&L - Budget (or Prior Period) P&L

AUM Effect     = (Actual AUM - Budget AUM) x Budget Return %
                 (How much of the P&L change is due to AUM size change)

Return Effect  = (Actual Return % - Budget Return %) x Budget AUM
                 (How much is due to return performance change, holding AUM constant)

Cross Term     = (Actual AUM - Budget AUM) x (Actual Return % - Budget Return %)
                 (Small interaction term — can be allocated proportionally)

Verification:  AUM Effect + Return Effect + Cross Term = Total P&L Variance
```

### Strategy Attribution (Multi-Strategy)

Decompose total fund return into per-strategy contributions:

```
Strategy Attribution Table
Period: [Period]

Strategy          AUM Alloc  Gross Rtn  Net Rtn  Contribution  % of Total P&L
----------------  ---------  ---------  -------  ------------  --------------
Equity L/S        XX%        X.XX%      X.XX%    X.XX pp       XX%
Systematic/Quant  XX%        X.XX%      X.XX%    X.XX pp       XX%
Fixed Income Arb  XX%        X.XX%      X.XX%    X.XX pp       XX%
Macro / FX        XX%        X.XX%      X.XX%    X.XX pp       XX%
Cash              XX%        X.XX%      X.XX%    X.XX pp       XX%
----------------  ---------  ---------  -------  ------------  ------
TOTAL FUND        100%       X.XX%      X.XX%    X.XX pp       100%

Note: Contribution = Strategy AUM Weight x Strategy Net Return
      Fund return verification: Sum of contributions = Fund total net return
```

### Long/Short Book Attribution

For equity strategies, decompose P&L between long and short books:

```
Long/Short Attribution
Period: [Period]

               Gross Exposure  Gross P&L  Return   Attribution
Long Book      $XX,XXX,XXX    $XX,XXX    X.XX%    X.XX pp
Short Book     $XX,XXX,XXX    $XX,XXX    X.XX%    X.XX pp
               -----------    -------    -----    --------
Net            $XX,XXX,XXX    $XX,XXX    X.XX%    X.XX pp

Gross Leverage:  X.XXx NAV
Net Leverage:    X.XXx NAV
Long/Short Ratio: X.XXx
```

## Risk Factor Decomposition

### Factor Attribution Framework

Decompose strategy P&L into systematic factor exposures and residual alpha:

```
FACTOR ATTRIBUTION
Strategy: [Strategy Name]  Period: [Period]

Factor          Exposure   Factor Return  Attribution
--------------  ---------  -------------  -----------
Market (Beta)   X.XX       X.XX%          X.XX pp
Size            X.XX       X.XX%          X.XX pp
Value           X.XX       X.XX%          X.XX pp
Momentum        X.XX       X.XX%          X.XX pp
Quality         X.XX       X.XX%          X.XX pp
Volatility      X.XX       X.XX%          X.XX pp
Sector (GICs)   X.XX       X.XX%          X.XX pp
--------------                            -------
Systematic Total                          X.XX pp
Residual (Alpha)                          X.XX pp
--------------                            -------
Total Return                              X.XX pp
```

**Note:** Factor exposures can be estimated from TradeStation position data combined with market factor returns from data providers (Bloomberg, TradingView, academic factor libraries).

### Drawdown Attribution

When analyzing a drawdown period:

```
DRAWDOWN ANALYSIS
Period: [Start] to [End] (or ongoing)

Peak NAV per unit:     $X,XXX.XX  (achieved [Date])
Trough NAV per unit:   $X,XXX.XX  (as of [Date])
Max Drawdown:          -X.XX%

Drawdown Decomposition:
  Strategy P&L impact
    Equity L/S:           -X.XX pp
    Systematic/Quant:     -X.XX pp
    Fixed Income Arb:     -X.XX pp
    Macro / FX:           -X.XX pp
  Total strategy drag:    -X.XX pp

  Cost drag during period:
    Financing costs:      -X.XX pp
    Transaction costs:    -X.XX pp
    Management fee:       -X.XX pp
  Total cost drag:        -X.XX pp

  Total drawdown:         -X.XX pp

Recovery analysis:
  Required return to recover to HWM:  X.XX%
  Days in drawdown:                   XX
  Average drawdown recovery (historical): XX days
  Estimated recovery at current run rate: [Date estimate]
```

## Materiality Thresholds and Investigation Triggers

### Setting Thresholds for Hedge Funds

| Comparison Type | Dollar Threshold | Return Threshold | Trigger |
|----------------|-----------------|-----------------|---------|
| Actual vs Prior Month | 0.1% of NAV | 25 bps | Either |
| Actual vs Budget | 0.1% of NAV | 50 bps | Either |
| Strategy vs Alloc | 0.05% of NAV | 20 bps | Either |
| Daily P&L (intraperiod) | 0.2% of NAV | N/A | Dollar only |
| Factor exposure change | N/A | 10% change in exposure | % change |

### Investigation Priority

When multiple variances exceed thresholds, prioritize by:
1. **Largest absolute dollar impact** on NAV
2. **Unexpected direction** — variance opposite to recent trend or market
3. **Specific strategy under/overperformance** relative to its own historical volatility
4. **Factor exposure drift** — unexpected shift in beta, sector, or style exposure
5. **Cost overruns** — financing or transaction costs materially above estimates

## Narrative Generation

### Structure for Fund P&L Variance Narratives

```
[Area]: [Favorable/Unfavorable] variance of $[amount] ([bps] bps / [%]%)
vs [comparison basis] for [period]

Driver: [Primary driver description]
[2-3 sentences: business reason, market context, specific quantification of
contributing factors. Reference TradingView/TradeStation data where applicable.]

Outlook: [One-time / Expected to continue / Likely to reverse / Monitor]
Action: [None required / Rebalance / Reduce risk / Investigate model / Update forecast]
```

### Common Hedge Fund Variance Narrative Templates

**Strong alpha month:**
> Systematic strategy generated X.XX pp above its expected factor-adjusted return, driven by outperformance in the [sector/factor] book. Long positions in [theme] contributed $XX,XXX while short positions in [theme] added $XX,XXX. Momentum factor had a particularly strong month (+X.XX%), benefiting our factor tilt.

**Drawdown narrative:**
> Net return was -X.XX% for the period, X.XX pp below budget. Primary driver was the broad risk-off move in [market], which reduced the long book by $XX,XXX. Short book partially offset with +$XX,XXX. Gross leverage was X.XXx at month-end, reduced from X.XXx at start. The drawdown is within the strategy's expected volatility range (annualized vol: X.XX%); no model changes were made.

**Variance narrative anti-patterns to avoid:**
- "Returns were lower due to negative market conditions" (vague — which positions? what conditions?)
- "Short book underperformed" without specifying which positions/themes
- Attributing everything to "market beta" without isolating the alpha component

## Waterfall Chart Methodology

### Fund Return Waterfall (Gross to Net)

Show the bridge from gross return to net return:

```
WATERFALL: Fund Return — Gross to Net ([Period])

Gross Trading Return                   X.XX%
  |
  |--[-] Financing / borrow costs     -X.XX pp
  |--[-] Transaction costs            -X.XX pp
  |--[-] Management fee drag          -X.XX pp
  |--[-] Performance fee drag         -X.XX pp
  |--[+/-] FX impact                  +/-X.XX pp
  |
Net Return                             X.XX%

Fee Total:  -X.XX pp  (Gross - Net spread)
```

### P&L Variance Waterfall (Period over Period)

```
WATERFALL: Fund Net P&L — [Current Period] vs [Prior Period]

Prior Period Net P&L                   $XX,XXX
  |
  |--[+] AUM growth effect            +$XX,XXX
  |--[+] Equity L/S alpha improvement +$XX,XXX
  |--[-] Systematic strategy decline  -$XX,XXX
  |--[+] Short book contribution      +$XX,XXX
  |--[-] Higher borrow costs          -$XX,XXX
  |--[+] Lower performance fee accrual+$XX,XXX
  |--[-] Additional tech/data spend   -$XX,XXX
  |
Current Period Net P&L                 $XX,XXX

Net Variance: +$XX,XXX (+X.X%)
```

### Bridge Reconciliation Table

| Driver | Amount | bps Impact | % of Variance | Cumulative |
|--------|--------|-----------|---------------|------------|
| AUM growth effect | +$XX,XXX | +X bps | XX% | +$XX,XXX |
| Equity L/S alpha | +$XX,XXX | +X bps | XX% | +$XX,XXX |
| Systematic decline | -$XX,XXX | -X bps | -XX% | +$XX,XXX |
| Short contribution | +$XX,XXX | +X bps | XX% | +$XX,XXX |
| Borrow cost increase | -$XX,XXX | -X bps | -XX% | +$XX,XXX |
| Performance fee | +$XX,XXX | +X bps | XX% | +$XX,XXX |
| Tech/data spend | -$XX,XXX | -X bps | -XX% | +$XX,XXX |
| **Total variance** | **+$XX,XXX** | **+X bps** | **100%** | |

## Budget vs Actual vs Forecast Comparisons

### Three-Way Comparison for Hedge Funds

| Metric | Budget | Forecast | Actual | Bud Var (bps) | Fcast Var (bps) |
|--------|--------|----------|--------|---------------|-----------------|
| Gross Return | X.XX% | X.XX% | X.XX% | +/- X bps | +/- X bps |
| Net Return | X.XX% | X.XX% | X.XX% | +/- X bps | +/- X bps |
| AUM ($M) | $XXX | $XXX | $XXX | $XX | $XX |
| Gross P&L | $XX,XXX | $XX,XXX | $XX,XXX | $X,XXX | $X,XXX |
| Mgmt Fee | $X,XXX | $X,XXX | $X,XXX | $X,XXX | $X,XXX |
| Perf Fee | $X,XXX | $X,XXX | $X,XXX | $X,XXX | $X,XXX |
| Net P&L | $XX,XXX | $XX,XXX | $XX,XXX | $X,XXX | $X,XXX |
| Sharpe (Annlzd) | X.XX | X.XX | X.XX | | |
| Max Drawdown | X.XX% | X.XX% | X.XX% | | |

### When to Use Each Comparison

- **Actual vs Budget:** Annual performance measurement, investor expectations set in DDQ/marketing materials
- **Actual vs Forecast:** Operational management, risk monitoring, fee projection updates
- **Actual vs Benchmark:** Positioning report, investor letter context (e.g., vs S&P 500, vs HFRI Multi-Strategy Index)
- **Actual vs Prior Month:** Sequential performance, drawdown monitoring, detecting regime change
- **Actual vs Prior Year (same month):** Seasonality-adjusted performance comparison
