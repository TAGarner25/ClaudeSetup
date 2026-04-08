---
name: reconciliation
description: Reconcile fund positions, cash balances, and NAV across trading platforms and fund records. Use when performing prime broker reconciliations, position reconciliations between TradeStation/Robinhood and internal records, cash reconciliations, fund administrator NAV reconciliations, or P&L reconciliations for a multi-strategy quantitative hedge fund.
---

# Reconciliation — Quantitative Hedge Fund

**Important**: This skill assists with fund reconciliation workflows but does not provide financial advice. All reconciliations should be reviewed by qualified fund accountants and your fund administrator before NAV finalization.

Position reconciliation methodology, cash reconciliation procedures, fund administrator NAV reconciliation, and P&L reconciliation for a multi-strategy quantitative hedge fund using TradeStation, TradingView, and Robinhood.

## Reconciliation Types

### 1. Position Reconciliation (Internal vs Broker)

Compare internal position records to positions held at broker/custodian (TradeStation, Robinhood).

**Frequency:** Daily (intraday for active strategies), mandatory at month-end.

```
POSITION RECONCILIATION
As of: [Date]  |  Prepared by: [Name]  |  Reviewed by: [Name]

Ticker    Internal Qty  TradeStation Qty  Robinhood Qty  Break?  Break ($)  Resolution
-------   ------------  ----------------  -------------  ------  ---------  ----------
AAPL      +1,000        +1,000            --             No      --
TSLA      -500          -500              --             No      --
SPY       +200          +200              --             No      --
AMZN      +100          +150              --             YES     $5,000     Investigate T+1 settle
[...]

Position Breaks Summary:
  Total positions:         [N]
  Positions in agreement:  [N]
  Breaks identified:       [N]
  Total dollar value of breaks: $[Amount]
  Breaks resolved:         [N]
  Breaks outstanding:      [N]
```

**Common causes of position breaks:**
- Trade confirmation delay (T+1 or T+2 settlement still pending)
- Corporate action (split, dividend, merger) not yet reflected in internal system
- Erroneous trade entry in internal records
- Platform data sync lag (common with Robinhood API exports)
- Options exercise/assignment processing
- Short position reporting timing differences

### 2. Cash Reconciliation (Internal vs Broker)

Reconcile cash and margin account balances across all platforms.

**Frequency:** Daily; mandatory at month-end.

```
CASH RECONCILIATION
As of: [Date]

                          Internal     TradeStation  Robinhood   Difference
                          Records      Statement     Statement
--------------------------  -----------  ------------  ----------  ----------
Cash / Free Balance         $XX,XXX      $XX,XXX       $XX,XXX     $0 / $Break
Margin Balance (borrowed)   ($XX,XXX)    ($XX,XXX)     --          $0 / $Break
Short Proceeds Held         $XX,XXX      $XX,XXX       --          $0 / $Break
Dividends Receivable        $XX,XXX      $XX,XXX       $XX,XXX     $0 / $Break
Interest Receivable         $XX,XXX      $XX,XXX       --          $0 / $Break
--------------------------  -----------  ------------  ----------  ----------
TOTAL NET CASH              $XX,XXX      $XX,XXX       $XX,XXX     $0 / $Break

RECONCILING ITEMS (if any):
  [Description of each item, amount, expected resolution date]
```

**How to pull cash data:**
- TradeStation: Account > Balance Report > Export
- Robinhood: Account > Portfolio > Brokerage Cash (or download statement)
- Cross-reference: Daily P&L report showing beginning cash + trade activity + fees = ending cash

### 3. Trade Blotter Reconciliation

Confirm all trades captured in internal records match platform trade confirms.

**Frequency:** Daily after market close; complete review at month-end.

```
TRADE BLOTTER RECONCILIATION
Period: [Date range]  |  Platforms: TradeStation, Robinhood

Step 1: Export trade history from each platform
  - TradeStation: Reports > Transaction History (export to CSV)
  - Robinhood: Account > History > Export

Step 2: Compare against internal trade log

Trade #  Date       Ticker  Side   Qty    Price   Platform     Internal Match  Break?
-------  ---------  ------  ----  -----  ------  -----------  --------------  ------
001      [Date]     AAPL    BUY   1,000  $180.00  TradeStation  YES            No
002      [Date]     TSLA    SELL    500  $250.00  Robinhood     YES            No
003      [Date]     SPY     BUY     200  $450.00  TradeStation  NO             YES — Missing from internal log

Breaks: [N]  |  Dollar value: $[Amount]  |  Resolution: [Action required]
```

**Break resolution hierarchy:**
1. Check if trade was entered in wrong account or with wrong ticker in internal records
2. Confirm platform trade confirm (check for partial fills, amended executions)
3. Verify settlement status (T+2 equities; may not be reflected same day)
4. If unresolved after 24 hours, escalate to broker/platform support

### 4. P&L Reconciliation (Internal vs Platform)

Confirm that internal P&L calculations match platform-reported P&L.

**Frequency:** Month-end mandatory; weekly recommended.

```
P&L RECONCILIATION
Period: [Month/Year]

                          Internal Calc   TradeStation   Robinhood   Difference
                          -------------   ------------   ---------   ----------
Realized P&L              $XX,XXX         $XX,XXX        $XX,XXX     $0 / $Break
Unrealized P&L (Open)     $XX,XXX         $XX,XXX        $XX,XXX     $0 / $Break
Dividends Received        $XX,XXX         $XX,XXX        $XX,XXX     $0 / $Break
Interest / Rebates        $XX,XXX         $XX,XXX        --          $0 / $Break
Commissions / Fees        ($XX,XXX)       ($XX,XXX)      ($XX,XXX)   $0 / $Break
Margin Interest           ($XX,XXX)       ($XX,XXX)      ($XX,XXX)   $0 / $Break
                          -------------   ------------   ---------   ----------
GROSS TRADING P&L         $XX,XXX         $XX,XXX        $XX,XXX     $0 / $Break

P&L Breaks:
  [Description of each break, amount, root cause, resolution]
```

**Common P&L breaks:**
- Cost basis methodology difference (FIFO vs Average Cost vs Specific Lot)
- Dividend vs return-of-capital classification
- Corporate action treatment (different system handling of spin-offs, mergers)
- Mark-to-market timing (platform uses prior close vs real-time price)
- Accrued interest calculation methodology
- Commission and fee categorization differences

### 5. Fund Administrator NAV Reconciliation

Reconcile your internally calculated NAV to the fund administrator's independent NAV calculation.

**Frequency:** Month-end mandatory.

```
NAV RECONCILIATION — INTERNAL vs FUND ADMIN
As of: [Month-end date]

                              Internal NAV    Fund Admin NAV    Difference
                              ------------    --------------    ----------
Gross Long Market Value       $XX,XXX,XXX     $XX,XXX,XXX       $0 / $Break
Gross Short Market Value      ($XX,XXX,XXX)   ($XX,XXX,XXX)     $0 / $Break
Net Securities Value          $XX,XXX,XXX     $XX,XXX,XXX       $0 / $Break
Cash (all accounts)           $XX,XXX,XXX     $XX,XXX,XXX       $0 / $Break
Dividends Receivable          $XX,XXX         $XX,XXX           $0 / $Break
Accrued Interest Income       $XX,XXX         $XX,XXX           $0 / $Break
Management Fee Payable        ($XX,XXX)       ($XX,XXX)         $0 / $Break
Performance Fee Payable       ($XX,XXX)       ($XX,XXX)         $0 / $Break
Other Liabilities             ($XX,XXX)       ($XX,XXX)         $0 / $Break
                              ------------    --------------    ----------
NET ASSET VALUE               $XX,XXX,XXX     $XX,XXX,XXX       $0 / $Break

NAV per Unit:
  Internal:    $X,XXX.XX
  Fund Admin:  $X,XXX.XX
  Difference:  $X.XX ([X bps])

ACCEPTANCE THRESHOLD: Differences below [X bps / $X,XXX] are considered immaterial.
Any difference above threshold requires investigation and resolution before investor reporting.

NAV Break Analysis:
  [Itemize each break, dollar amount, source of difference, resolution action]
```

**Common fund admin NAV breaks:**
- Pricing source difference (TradeStation/TradingView vs fund admin pricing vendor)
- Fee calculation methodology difference (confirm formula matches LPA)
- FX rate difference (fund admin may use WM/Reuters 4pm vs platform close)
- Accrual timing difference (admin may use different accrual period)
- Subscription/redemption activity not yet reflected in one calculation

### 6. Review and Escalation

Flag reconciliation breaks that require attention:

- **Aged position breaks:** Position discrepancies outstanding more than 2 business days
- **Material cash breaks:** Cash differences exceeding $[threshold]
- **NAV break above tolerance:** Difference vs fund admin exceeding [X bps] 
- **Unexplained P&L breaks:** P&L items that cannot be traced to specific trades
- **Growing breaks:** Reconciling items accumulating period over period

Escalation path:
1. **T+0 to T+1:** Ops/Finance team attempts to resolve internally
2. **T+2:** Escalate unresolved breaks to portfolio manager
3. **T+3 (month-end):** Escalate any material unresolved breaks to fund administrator
4. **Beyond T+3:** Document break, book conservative adjustment if material, investigate root cause

## Reconciliation Output Format

For each reconciliation, provide:
1. Summary table showing all accounts in agreement and any breaks
2. Break detail list with description, amount, age, and resolution status
3. Adjusting journal entries required (if any)
4. Action items with owners and target resolution dates
5. Sign-off section (preparer + reviewer)
