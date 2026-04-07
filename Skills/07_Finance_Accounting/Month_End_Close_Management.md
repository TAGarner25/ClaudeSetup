---
name: close-management
description: Manage the hedge fund month-end close process including NAV finalization, prime broker reconciliation, position verification, and investor reporting. Use when planning the close calendar, tracking close progress, coordinating with fund administrators, or sequencing close activities by day.
---

# Close Management — Quantitative Hedge Fund

**Important**: This skill assists with fund close management workflows but does not provide financial advice. All NAV calculations and financial reports should be reviewed by your fund administrator and qualified financial professionals before investor distribution.

Hedge fund month-end close checklist, task sequencing and dependencies, status tracking, and common close activities organized by day for a multi-strategy quantitative fund using TradeStation, TradingView, and Robinhood.

## Month-End Close Checklist

### Pre-Close (Last 2-3 Trading Days of the Month)

- [ ] Send close calendar and deadline reminders to all contributors (fund admin, prime broker, compliance)
- [ ] Confirm all open orders are closed or intentionally carried in TradeStation/Robinhood
- [ ] Review upcoming corporate actions (dividends, splits, mergers) that affect month-end positions
- [ ] Confirm strategy-level position limits and risk limits are current
- [ ] Pull preliminary position report from TradeStation/Robinhood and verify against expected holdings
- [ ] Flag any illiquid or hard-to-price positions that may require special valuation treatment
- [ ] Collect information on any pending subscriptions or redemptions

### Close Day 1 (T+1: First Business Day After Month-End)

- [ ] Pull final trade confirmations and executions from TradeStation and Robinhood for last trading day
- [ ] Reconcile trade blotter to exchange confirms — confirm all trades settled or are in settlement
- [ ] Pull end-of-month position file and mark all positions to closing prices (via TradingView or TradeStation)
- [ ] Compute realized P&L for all closed positions during the month
- [ ] Compute unrealized P&L on all open positions at month-end closing prices
- [ ] Record dividend income, interest income, and short rebate income
- [ ] Accrue margin interest and short borrow costs through month-end
- [ ] Calculate and record management fee accrual
- [ ] Begin performance fee HWM calculation

### Close Day 2 (T+2)

- [ ] Complete performance fee HWM calculation and accrue/reverse performance fee
- [ ] Reconcile cash balances across all accounts (TradeStation, Robinhood, custodian)
- [ ] Reconcile prime broker / custodian position statements to internal records
- [ ] Identify and resolve any position breaks or cash discrepancies
- [ ] Allocate P&L and costs to sub-strategies per allocation methodology
- [ ] Complete strategy-level attribution table
- [ ] Record all period-end journal entries (see journal-entry-prep skill)

### Close Day 3 (T+3)

- [ ] Complete NAV calculation and prepare draft NAV statement
- [ ] Process subscription and redemption activity at month-end NAV per unit
- [ ] Update investor capital account balances
- [ ] Compute per-unit returns (gross and net of all fees)
- [ ] Complete balance sheet reconciliation (cash, positions, accrued fees, investor capital)
- [ ] Run preliminary performance metrics (Sharpe, drawdown, vol, beta, correlation)
- [ ] Conduct internal review of all figures — compare to prior month for reasonableness

### Close Day 4 (T+4)

- [ ] Submit preliminary NAV and performance figures to fund administrator for independent verification
- [ ] Provide trade details and position file to fund admin as supporting documentation
- [ ] Respond to fund admin queries; resolve any discrepancies
- [ ] Update YTD and since-inception performance calculations
- [ ] Prepare investor monthly report (performance summary, strategy attribution, risk metrics)
- [ ] Internal management review and sign-off on financials and performance report

### Close Day 5 (T+5)

- [ ] Receive fund administrator NAV confirmation
- [ ] Reconcile GP-calculated NAV to fund admin NAV — resolve any differences
- [ ] Finalize monthly performance figures — hard close
- [ ] Distribute investor monthly letter / performance report
- [ ] Update fund track record and performance database
- [ ] Conduct close retrospective — identify process improvements

## Task Sequencing and Dependencies

### Dependency Map

```
LEVEL 1 (No dependencies — start immediately at T+1):
├── Pull final trade confirms from TradeStation/Robinhood
├── Pull end-of-month position file
├── Pull closing prices from TradingView/TradeStation
├── Accrue interest income, dividends, financing costs
└── Begin management fee accrual

LEVEL 2 (Depends on Level 1):
├── Compute realized P&L (needs: trade confirms + closing prices)
├── Compute unrealized P&L (needs: open positions + closing prices)
├── Complete cash reconciliation (needs: all trade activity + bank feeds)
├── Performance fee HWM calculation (needs: gross P&L)
└── Strategy P&L allocation (needs: gross P&L by trade)

LEVEL 3 (Depends on Level 2):
├── Prime broker / custodian reconciliation (needs: all trade + cash entries)
├── Record all period-end journal entries (needs: all accruals computed)
├── Complete fee crystallization (needs: HWM calc finalized)
└── Subscription/redemption processing (needs: preliminary NAV)

LEVEL 4 (Depends on Level 3):
├── NAV calculation and statement (needs: all JEs posted, all recons clean)
├── Investor capital account updates (needs: final NAV + sub/red activity)
├── Performance metrics calculation (needs: final NAV series)
└── Fund admin submission (needs: NAV + trade/position file)

LEVEL 5 (Depends on Level 4):
├── Fund admin reconciliation and sign-off
├── Hard close / period lock
├── Investor report distribution
└── Track record update
```

### Critical Path

```
Pull trades/positions → Mark to market → Compute P&L →
  Accrue fees → NAV calculation → Prime broker recon →
    Fund admin verification → Hard close → Investor reporting
```

## Status Tracking and Reporting

### Close Status Dashboard

Track each close task with the following attributes:

| Task | Owner | Deadline | Status | Blocker | Notes |
|------|-------|----------|--------|---------|-------|
| Trade confirms pulled | Ops | T+1 AM | Not Started / In Progress / Complete / Blocked | | |
| Mark-to-market complete | PM / Ops | T+1 EOD | | | |
| P&L calculated | PM | T+1 EOD | | | |
| Cash reconciled | Ops | T+2 | | | |
| Prime broker recon | Ops | T+2 | | | |
| Fee accruals complete | Finance | T+2 EOD | | | |
| NAV draft complete | Finance | T+3 | | | |
| Internal review | PM / Finance | T+3 EOD | | | |
| Fund admin submission | Finance | T+4 AM | | | |
| Fund admin confirmed | Fund Admin | T+4-5 | | | |
| Investor report sent | PM | T+5 | | | |

### Status Definitions

- **Not Started:** Task has not begun
- **In Progress:** Actively being worked
- **Complete:** Finished and reviewed/approved
- **Blocked:** Cannot proceed due to missing data, platform issue, or counterparty delay
- **At Risk:** In progress but may miss deadline

## Common Close Activities by Day

### Typical 5-Day Hedge Fund Close Calendar

| Day | Key Activities | Responsible |
|-----|---------------|-------------|
| **T+1** | Pull final trade files from TradeStation/Robinhood, mark positions to market (TradingView/TradeStation), compute realized/unrealized P&L, accrue income and costs, begin fee calculations | PM, Ops |
| **T+2** | Complete fee accruals (mgmt + performance HWM), reconcile cash across all accounts, prime broker position reconciliation, allocate P&L by strategy, post journal entries | Finance, Ops |
| **T+3** | Compute NAV and draft NAV statement, process subscriptions/redemptions, update investor capital, compute performance metrics, internal management review | Finance, PM |
| **T+4** | Submit to fund admin with trade/position support, respond to admin queries, resolve discrepancies, prepare investor report | Finance, PM |
| **T+5** | Fund admin NAV confirmation, reconcile to admin NAV, hard close, distribute investor report, update track record | Finance, PM |

## Close Process Improvement

### Common Hedge Fund Close Bottlenecks

| Bottleneck | Root Cause | Solution |
|-----------|-----------|---------|
| Late trade confirmations | Manual export from Robinhood/TradeStation | Automate daily trade file exports; schedule end-of-day pulls |
| Pricing delays for illiquid positions | No automated price feed | Identify illiquid positions pre-close; source prices proactively |
| Cash reconciliation breaks | Multiple accounts across platforms | Implement daily cash reconciliation; don't let breaks accumulate |
| Fund admin discrepancies | Different pricing sources or fee calc methods | Align pricing and fee methodology with fund admin in advance |
| Performance fee disputes | HWM calculation methodology questions | Document HWM methodology in LPA; maintain clear waterfall records |
| Investor report delays | Manual formatting and data aggregation | Templatize investor report; automate data population from spreadsheets |

### Close Retrospective Questions

1. Were all trade files received from TradeStation/Robinhood on time and complete?
2. Were there any pricing challenges or disputes with the fund admin on month-end marks?
3. Did any prime broker reconciliation breaks require significant investigation time?
4. Were performance fee calculations reviewed and confirmed before investor distribution?
5. Were there any investor subscription/redemption processing issues?
6. What can be automated or streamlined for next month?
