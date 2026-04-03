---
name: journal-entry-prep
description: Prepare hedge fund journal entries with proper debits, credits, and supporting documentation. Use when booking trade P&L, management fee accruals, performance fee crystallization, dividend and interest income, financing cost accruals, NAV adjustments, or any fund-level accounting entries for a multi-strategy quantitative hedge fund.
---

# Journal Entry Preparation — Quantitative Hedge Fund

**Important**: This skill assists with fund accounting journal entry workflows but does not provide financial, tax, or legal advice. All entries should be reviewed by qualified fund accountants and your fund administrator before posting.

Fund-specific journal entry types, debit/credit treatments, supporting documentation requirements, and review checklists for a multi-strategy quantitative hedge fund.

## Journal Entry Types

### 1. Trade Settlement — Realized P&L

**Trigger:** Position closed (full or partial) during the period.

**Supporting data source:** TradeStation or Robinhood trade history export.

```
Journal Entry: Realized P&L — Trade Settlement
Date: [Trade settle date]

| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Cash / Margin Account | X,XXX | | Proceeds from sale of [ticker] |
| 2 | Investment — [Ticker] (Cost Basis) | | X,XXX | Close position at cost |
| 3 | Realized Gain/(Loss) | X,XXX OR | | Net gain: Proceeds minus Cost |
|   | OR Realized Gain/(Loss) | | X,XXX | Net loss: Cost minus Proceeds |

Supporting detail:
- Trade date: [Date]
- Settle date: [Date]
- Ticker: [Symbol]
- Quantity: [Shares/contracts]
- Proceeds: $[Amount]
- Cost basis: $[Amount] (using [FIFO/Average Cost/Specific Lot])
- Realized gain/(loss): $[Amount]
```

### 2. Mark-to-Market — Unrealized P&L

**Trigger:** Period-end mark of all open positions to closing prices.

**Supporting data source:** Position file from TradeStation/Robinhood; closing prices from TradingView or TradeStation.

```
Journal Entry: Mark-to-Market — Unrealized P&L
Date: [Period end date]

Step 1: Reverse prior period unrealized P&L
| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Unrealized Gain/(Loss) — Prior | X,XXX | | Reverse prior MTM |
| 2 | Investment — Fair Value Adjustment | | X,XXX | Reverse prior MTM |

Step 2: Record current period unrealized P&L
| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Investment — Fair Value Adjustment | X,XXX | | MTM to [Date] close |
| 2 | Unrealized Gain/(Loss) — Current | | X,XXX | MTM to [Date] close |

Supporting detail:
- Position file as of: [Date]
- Pricing source: [TradeStation / TradingView closing prices]
- Total long book fair value: $[Amount]
- Total short book fair value: ($[Amount])
- Net unrealized P&L change for period: $[Amount]
```

### 3. Management Fee Accrual

**Trigger:** Monthly (or as per fund LPA schedule).

```
Journal Entry: Management Fee Accrual
Date: [Period end date]

| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Management Fee Expense | X,XXX | | [Month/Year] mgmt fee accrual |
| 2 | Management Fee Payable | | X,XXX | Payable to GP / Manager |

Calculation:
  Average NAV for period: $[Amount]
  Annual fee rate: X.XX%
  Days in period: [N]
  Fee = $[AUM] x X.XX% x ([N] / 365) = $[Amount]

Reversal: No (management fee does not reverse — cumulative payable)
Reference: Fund LPA Section [X.X] — Management Fee
```

### 4. Performance Fee Accrual / Crystallization

**Trigger:** Monthly accrual; crystallization on redemption or at year-end (per LPA).

```
Journal Entry: Performance Fee Accrual
Date: [Period end date]

Scenario A — Accrual (NAV above HWM, not yet crystallized):
| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Performance Fee Expense | X,XXX | | [Month/Year] perf fee accrual |
| 2 | Performance Fee Payable — Accrued | | X,XXX | Provisional; subject to HWM reset |

Scenario B — Crystallization (year-end or on redemption):
| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Performance Fee Payable — Accrued | X,XXX | | Transfer to payable upon crystallization |
| 2 | Performance Fee Payable — Crystallized | | X,XXX | Firm obligation per LPA |

Scenario C — Reversal (NAV drops below HWM during period):
| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Performance Fee Payable — Accrued | X,XXX | | Reverse excess accrual per HWM calc |
| 2 | Performance Fee Expense | | X,XXX | Credit to reverse prior over-accrual |

Calculation (attach HWM schedule):
  Current NAV per unit (pre-perf):  $X,XXX.XX
  High Water Mark:                  $X,XXX.XX
  Gain above HWM:                   $X,XXX.XX
  Performance fee rate:             XX%
  Performance fee per unit:         $X.XX
  Units outstanding:                XXX,XXX
  Total performance fee:            $[Amount]
```

### 5. Dividend and Interest Income

**Trigger:** Dividend payment date or accrual date; monthly interest income.

```
Journal Entry: Dividend Income
Date: [Payment date or ex-date for accrual]

| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Cash / Dividend Receivable | X,XXX | | Dividend: [Ticker], [Shares] x $[Rate] |
| 2 | Dividend Income | | X,XXX | [Ticker] dividend [Pay Date] |

Journal Entry: Interest / Short Rebate Income
Date: [Period end]

| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Interest Receivable | X,XXX | | Accrued interest / rebate income |
| 2 | Interest Income / Short Rebate Income | | X,XXX | [Period] accrual |
```

### 6. Financing / Borrow Cost Accrual

**Trigger:** Monthly accrual of margin interest and short stock borrow costs.

**Supporting data source:** TradeStation margin statement; Robinhood margin report.

```
Journal Entry: Financing Cost Accrual
Date: [Period end]

| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Margin Interest Expense | X,XXX | | [Period] margin interest — [TradeStation/Robinhood] |
| 2 | Short Borrow Cost Expense | X,XXX | | [Period] stock borrow cost |
| 3 | Accrued Financing Costs Payable | | X,XXX | Total financing accrual |

Margin interest calculation:
  Average margin balance: $[Amount]
  Annual margin rate (broker): X.XX%
  Days in period: [N]
  Interest = $[AUM] x X.XX% x ([N] / 365) = $[Amount]

Borrow cost:
  Short position: [Ticker], [Shares] short
  Borrow rate: X.XX% annual
  Daily cost = (Share price x Shares x Rate) / 360
```

### 7. Subscription / Redemption Processing

**Trigger:** New investor subscription or existing investor redemption.

```
Journal Entry: New Subscription
Date: [Effective date — typically month-end]

| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Cash | X,XXX,XXX | | Subscription: [LP Name], [Units] units at $[NAV/unit] |
| 2 | Partners' Capital — [LP Name] | | X,XXX,XXX | Subscription proceeds |

Journal Entry: Redemption
Date: [Effective date]

| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Partners' Capital — [LP Name] | X,XXX,XXX | | Redemption: [LP Name], [Units] units at $[NAV/unit] |
| 2 | Redemption Payable | | X,XXX,XXX | Payable within [X] business days per LPA |

[On payment:]
| Line | Account | Debit | Credit | Memo |
|------|---------|-------|--------|------|
| 1 | Redemption Payable | X,XXX,XXX | | Payment of redemption proceeds |
| 2 | Cash | | X,XXX,XXX | Wire transfer to [LP Name] |
```

## Review Checklist (All Entry Types)

Before finalizing any journal entry, verify:

- [ ] Debits equal credits
- [ ] Correct period date (check month-end vs trade date vs settle date)
- [ ] Amounts reconcile to supporting source data (TradeStation/Robinhood export, TradingView prices)
- [ ] Account codes are correct and consistent with the fund's chart of accounts
- [ ] Memo is specific enough to trace back to source transaction
- [ ] Performance fee entries reference the HWM calculation schedule
- [ ] Trade entries reference the specific trade confirmation
- [ ] Entry is consistent with prior period treatment (same methodology)
- [ ] Reversal flag set appropriately (MTM unrealized should be reversed each period; accruals typically do not reverse)
- [ ] Supporting documentation is attached or referenced
- [ ] Entry reviewed by a second person before posting to fund books

## Journal Entry Log Format

Maintain a running log for the period:

| JE # | Date | Type | Description | Debit Total | Credit Total | Preparer | Reviewer | Status |
|------|------|------|-------------|-------------|--------------|----------|----------|--------|
| 001 | [Date] | Trade P&L | Realized P&L — [Ticker] close | $X,XXX | $X,XXX | | | Draft |
| 002 | [Date] | MTM | Mark-to-market all positions | $X,XXX | $X,XXX | | | Draft |
| 003 | [Date] | Mgmt Fee | [Month] management fee accrual | $X,XXX | $X,XXX | | | Draft |
