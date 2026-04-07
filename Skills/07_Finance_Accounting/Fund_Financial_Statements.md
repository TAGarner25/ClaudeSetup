---
name: financial-statements
description: Generate fund-level financial statements including NAV, P&L attribution, and fee schedules with period-over-period comparison. Use when preparing fund P&L reports, NAV calculations, investor statements, or performance summaries for a multi-strategy quantitative hedge fund.
---

# Financial Statements — Quantitative Hedge Fund

**Important**: This skill assists with fund financial reporting workflows but does not provide financial, tax, or legal advice. All statements should be reviewed by qualified financial professionals and your fund administrator before distribution to investors or regulators.

Fund-level P&L formats, NAV calculation methodology, management and performance fee calculations, and period-over-period flux analysis for a multi-strategy quantitative hedge fund.

## Fund P&L Statement (Management Accounts)

### Standard Hedge Fund P&L Format

```
FUND P&L STATEMENT
Period: [Period description]
(USD, unless otherwise noted)

                                    Current    Prior      Variance   Variance
                                    Period     Period     ($)        (%)
                                    ---------  ---------  ---------  --------
TRADING P&L
  Realized gains / (losses)         $XX,XXX    $XX,XXX    $X,XXX     X.X%
  Unrealized gains / (losses)       $XX,XXX    $XX,XXX    $X,XXX     X.X%
                                    ---------  ---------
GROSS TRADING P&L                   $XX,XXX    $XX,XXX    $X,XXX     X.X%

INTEREST & DIVIDEND INCOME
  Dividend income                   $XX,XXX    $XX,XXX    $X,XXX     X.X%
  Interest income (long)            $XX,XXX    $XX,XXX    $X,XXX     X.X%
  Short rebate income               $XX,XXX    $XX,XXX    $X,XXX     X.X%
                                    ---------  ---------
TOTAL INCOME                        $XX,XXX    $XX,XXX    $X,XXX     X.X%

FINANCING & BORROW COSTS
  Margin interest / financing       ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
  Short stock borrow cost           ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
                                    ---------  ---------
TOTAL FINANCING COSTS               ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%

TRANSACTION COSTS
  Commissions & execution fees      ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
  Slippage / market impact          ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
                                    ---------  ---------
TOTAL TRANSACTION COSTS             ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%

NET TRADING P&L                     $XX,XXX    $XX,XXX    $X,XXX     X.X%

FUND OPERATING EXPENSES
  Management fees                   ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
  Fund administration               ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
  Legal & compliance                ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
  Technology & data (TradingView, TradeStation, Robinhood) ($X,XXX) ($X,XXX) $X,XXX X.X%
  Research & subscriptions          ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
  Other operating expenses          ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
                                    ---------  ---------
TOTAL FUND EXPENSES                 ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%

NET INCOME BEFORE PERFORMANCE FEE   $XX,XXX    $XX,XXX    $X,XXX     X.X%

  Performance fee accrual           ($XX,XXX)  ($XX,XXX)  $X,XXX     X.X%
                                    ---------  ---------

NET INCOME (LOSS)                   $XX,XXX    $XX,XXX    $X,XXX     X.X%
```

### Strategy-Level Attribution (Multi-Strategy)

Break the trading P&L down by sub-strategy:

```
STRATEGY P&L ATTRIBUTION
Period: [Period]

Strategy              Gross P&L   Costs    Net P&L   % of NAV   Sharpe (Annlzd)
--------------------  ---------  --------  --------  ---------  ---------------
Equity Long/Short     $XX,XXX    ($X,XXX)  $XX,XXX   X.XX%      X.XX
Systematic/Quant      $XX,XXX    ($X,XXX)  $XX,XXX   X.XX%      X.XX
Fixed Income Arb      $XX,XXX    ($X,XXX)  $XX,XXX   X.XX%      X.XX
Macro / FX            $XX,XXX    ($X,XXX)  $XX,XXX   X.XX%      X.XX
Cash/Other            $XX,XXX    ($X,XXX)  $XX,XXX   X.XX%      X.XX
--------------------  ---------  --------  --------  ---------  ---------------
TOTAL FUND            $XX,XXX    ($X,XXX)  $XX,XXX   X.XX%      X.XX
```

## NAV Calculation

### NAV Statement Format

```
NET ASSET VALUE (NAV) STATEMENT
As of: [Date]
Fund: [Fund name]

BEGINNING NAV                                   $XX,XXX,XXX
  Beginning NAV per share                       $X,XXX.XX
  Shares outstanding (beginning)                XXX,XXX

CHANGES IN NAV
  Net income (loss) for period                  $XX,XXX,XXX
  Subscriptions received                        $XX,XXX,XXX
  Redemptions paid                              ($XX,XXX,XXX)
  Performance fee crystallization               ($XX,XXX,XXX)
                                                ----------
NET CHANGE IN NAV                               $XX,XXX,XXX

ENDING NAV                                      $XX,XXX,XXX
  Ending NAV per share                          $X,XXX.XX
  Shares outstanding (ending)                   XXX,XXX

PERIOD RETURN
  Gross return (before fees)                    X.XX%
  Net return (after all fees)                   X.XX%
  Month-to-date                                 X.XX%
  Year-to-date                                  X.XX%
  Since inception                               X.XX%
```

### NAV Calculation Steps

1. **Start with prior period ending NAV**
2. **Mark all positions to market** — Use closing prices from TradeStation or TradingView
3. **Add interest and dividend income accruals**
4. **Deduct financing costs** — margin interest, borrow costs
5. **Deduct transaction costs** — commissions, fees
6. **Accrue management fee** (see fee schedule below)
7. **Calculate performance fee accrual** (see HWM method below)
8. **Process subscriptions and redemptions** (at NAV per unit)
9. **Reconcile to prime broker/custodian cash and position values**

## Fee Calculations

### Management Fee

Standard hedge fund management fee (adjust to your fund's terms):

```
Management Fee Accrual — [Period]

AUM (beginning of period):          $XX,XXX,XXX
AUM (end of period):                $XX,XXX,XXX
Average AUM:                        $XX,XXX,XXX

Annual management fee rate:         X.XX%
Daily accrual rate:                 Annual rate / 365

Period accrual (N days):
  Average AUM x Annual Rate x (N / 365)
  = $XX,XXX,XXX x X.XX% x (N / 365)
  = $XX,XXX

Management fee payable (period):    $XX,XXX
Management fee paid (period):       ($XX,XXX)
Accrued management fee (balance):   $XX,XXX
```

### Performance Fee (High Water Mark Method)

```
Performance Fee Calculation — [Period]

High Water Mark (HWM):              $X,XXX.XX per unit
Current NAV per unit (pre-perf):    $X,XXX.XX per unit

Gain above HWM per unit:            $X,XXX.XX (or $0 if below HWM)
Performance fee rate:               XX%
Performance fee per unit:           $X,XXX.XX x XX% = $X,XXX.XX

Units outstanding:                  XXX,XXX
Total performance fee accrual:      $XX,XXX,XXX

Crystallization: [Monthly / Quarterly / Annual / On redemption]

  Accrued performance fee (prior):  $XX,XXX,XXX
  + Accrual for period:             $XX,XXX,XXX
  - Crystallization (if applicable): ($XX,XXX,XXX)
  Accrued performance fee (ending): $XX,XXX,XXX

New HWM (post-crystallization):     $X,XXX.XX per unit
```

### Hurdle Rate (if applicable)

```
Hurdle Rate Adjustment

Hurdle rate (annual):               X.XX% (e.g., risk-free rate / SOFR + spread)
Hurdle for period:                  X.XX%

Beginning NAV per unit:             $X,XXX.XX
Hurdle amount per unit:             $X,XXX.XX x X.XX% x (N / 365) = $X.XX
Hurdle threshold NAV per unit:      $X,XXX.XX + $X.XX = $X,XXX.XX

Performance fee applies only on returns above hurdle threshold.
```

## Key Fund Performance Metrics

```
PERFORMANCE SUMMARY
Period: [Period]

                                    Current    Prior      Change
                                    Period     Period
AUM ($M)                            $XXX.X     $XXX.X     $XX.X
NAV per unit                        $X,XXX.XX  $X,XXX.XX  $XX.XX
Net return (%)                      X.XX%      X.XX%      X.XX pp
Gross return (%)                    X.XX%      X.XX%      X.XX pp
Annualized return (since inception) X.XX%
Sharpe ratio (annualized)           X.XX
Sortino ratio                       X.XX
Maximum drawdown (current)          X.XX%
Maximum drawdown (all-time)         X.XX%
Calmar ratio                        X.XX
Win rate (% of profitable days)     XX.X%
Average daily P&L                   $XX,XXX
Volatility (annualized)             X.XX%
Beta to S&P 500                     X.XX
Correlation to S&P 500              X.XX
Gross leverage                      X.XXx
Net leverage                        X.XXx
```

## Common Adjustments and Reclassifications

### Period-End Adjustments

1. **Mark-to-market:** Revalue all open positions at period-end closing prices (pull from TradeStation or TradingView)
2. **Dividend accruals:** Accrue dividends declared but not yet paid on long positions
3. **Borrow cost accruals:** Accrue stock borrow costs on short positions
4. **Management fee accrual:** Compute and accrue management fee for the period
5. **Performance fee accrual:** Update HWM calculation and accrue or reverse performance fee
6. **FX revaluation:** Revalue foreign-currency-denominated positions at period-end spot rates
7. **Carry/funding adjustments:** Accrue financing costs on levered positions

### Reclassifications

1. **Realized vs unrealized:** Reclassify P&L from unrealized to realized upon trade close-out
2. **Long/short P&L split:** Segregate P&L attribution between long book and short book
3. **Strategy allocation:** Allocate P&L, costs, and capital to sub-strategy buckets
4. **Fee netting:** Net management and performance fees against gross returns for net return calculation

## Flux Analysis Methodology

### Variance Calculation for Funds

For each line item, calculate:
- **Dollar variance:** Current period minus Prior period
- **Percentage variance:** (Current minus Prior) / |Prior| x 100
- **Basis point change:** For return metrics, express in basis points (1 bp = 0.01%)
- **Per-unit variance:** Variance expressed on a per-NAV-unit basis for comparability

### Materiality Thresholds for Hedge Funds

| Line Item | Dollar Threshold | Percentage Threshold |
|-----------|-----------------|---------------------|
| Gross Trading P&L | Fund-specific (e.g., 0.1% of NAV) | 10% |
| Strategy P&L (per sub-strategy) | Fund-specific | 15% |
| Fund expenses | 10% of expected line | 10% |
| NAV per unit | 0.5% of NAV/unit | N/A |
| Management fee accrual | 5% of expected fee | 5% |
| Performance fee accrual | Material any deviation | 5% |

### Variance Decomposition for Fund P&L

Break down total P&L variance into:
- **Market return effect:** Broad market move driving long/short book P&L
- **Alpha / strategy effect:** Strategy-specific P&L above/below market beta
- **AUM effect:** Change in gross P&L driven purely by change in AUM/capital deployed
- **Leverage effect:** Change in gross exposure amplifying or dampening returns
- **Fee drag:** Change in management fee and performance fee impact
- **FX effect:** Currency impact on non-USD positions
- **One-time items:** Non-recurring events (corporate actions, special distributions, strategy launches/closures)
