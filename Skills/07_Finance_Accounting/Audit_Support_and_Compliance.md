---
name: audit-support
description: Support hedge fund compliance, internal controls, and audit workflows including investment adviser compliance (Form ADV, Form PF), LP audit preparation, internal control documentation, and annual audit support. Use when preparing for annual audits, testing internal controls, documenting compliance procedures, or generating sample selections and workpapers for a multi-strategy quantitative hedge fund.
---

# Audit & Compliance Support — Quantitative Hedge Fund

**Important**: This skill assists with compliance and audit workflows but does not provide legal, regulatory, or audit advice. All compliance materials and audit workpapers should be reviewed by qualified legal and compliance professionals. Hedge fund regulatory requirements vary significantly by AUM, investor type, jurisdiction, and fund structure.

Compliance framework for a registered investment adviser (RIA) hedge fund structure, internal control documentation, annual audit preparation, LP audit support, and common control areas for a multi-strategy quantitative fund using TradeStation, TradingView, and Robinhood.

## Hedge Fund Compliance Framework

### Regulatory Obligations Overview

| Requirement | Who it applies to | Key deadline |
|------------|------------------|--------------|
| Form ADV (Parts 1, 2A, 2B) | SEC-registered RIAs (generally $100M+ AUM) | Annual amendment within 90 days of fiscal year-end; promptly update material changes |
| Form PF | Large hedge fund advisers ($1.5B+ AUM); all registered advisers with private fund AUM | Quarterly (large) or annual (others) |
| Annual audit | Funds claiming custody of client assets (Custody Rule) | Audited financials within 120 days of fiscal year-end |
| Annual compliance review | All registered RIAs | Annual review of compliance program effectiveness |
| Blue sky / state registration | Advisers below SEC threshold | Varies by state |
| CFTC / NFA registration | Funds trading futures or swaps (CTAs, CPOs) | Required if applicable |

**Important**: Verify current applicability and deadlines with your compliance counsel. This table is a general guide and not a substitute for legal advice.

### Annual Compliance Calendar

```
MONTH 1 (January):
  - Begin year-end audit preparation
  - Pull final December NAV and performance figures
  - Begin ADV Part 1 and 2A updates (if calendar year-end)
  - Review and update compliance policies and procedures manual
  - Confirm fund administrator has all year-end data

MONTH 2 (February):
  - Finalize ADV update; file with SEC by March 31 (for Dec 31 fiscal year-end)
  - Distribute audited financials to LPs (within 120 days of year-end)
  - Complete annual compliance review
  - Update Form PF if applicable
  - Renew any expiring software/data subscriptions (TradeStation, TradingView)

MONTH 3 (March):
  - ADV annual amendment deadline (March 31 for Dec 31 fiscal year-end)
  - LP K-1 or tax document distribution
  - Conduct annual employee compliance training
  - Review and update investment management agreement and LPA for changes

ONGOING (Monthly/Quarterly):
  - NAV calculation and investor reporting
  - Trade reconciliation and position reporting
  - Review of new investment strategies for compliance approval
  - Personal account trading pre-clearance review (Code of Ethics)
  - Review for any reportable events (material changes requiring ADV amendment)
```

## Internal Controls — Hedge Fund

### Investment Process Controls

**Pre-Trade Controls:**
| Control | Description | Frequency | Evidence |
|---------|-------------|-----------|---------|
| Position limit check | Verify new trade does not exceed per-position, sector, or strategy concentration limits | Pre-trade | Trade approval log; system limit alerts |
| Risk/leverage check | Confirm gross and net leverage within agreed fund parameters after trade | Pre-trade / real-time | Risk report; trading platform position monitor |
| Restricted list check | Confirm security is not on compliance restricted list (MNPI, regulatory restrictions) | Pre-trade | Restricted list review sign-off |
| Strategy consistency | Confirm trade is consistent with strategy mandate described in LPA/DDQ | Pre-trade | PM sign-off |

**Trade Execution Controls:**
| Control | Description | Frequency | Evidence |
|---------|-------------|-----------|---------|
| Best execution review | Review execution quality (price, timing, platform selection) | Monthly/Quarterly | TCA report; execution quality review memo |
| Commission tracking | Monitor commissions paid vs expected rates | Monthly | Brokerage statement vs fee schedule |
| Order confirmation | Match trade confirms from TradeStation/Robinhood to internal order blotter | Daily | Trade blotter reconciliation |

**Post-Trade Controls:**
| Control | Description | Frequency | Evidence |
|---------|-------------|-----------|---------|
| Trade settlement monitoring | Track all trades through settlement; flag fails | Daily | Settlement report; fail log |
| Position reconciliation | Reconcile positions to TradeStation/Robinhood | Daily | Reconciliation report |
| P&L attribution | Allocate P&L to strategies and verify attribution | Daily/Monthly | P&L attribution report |

### Valuation Controls

| Control | Description | Frequency | Evidence |
|---------|-------------|-----------|---------|
| Price sourcing | Pull closing prices from TradeStation or TradingView; document source | Daily (MTM), Month-end | Price file with source notation |
| Price override review | Any manually overridden price requires PM + compliance sign-off | As needed | Override approval log |
| Stale price check | Flag positions with prices unchanged for > 1 business day | Daily | Stale price exception report |
| Fair value policy | Apply fair value policy for illiquid/hard-to-price positions | As needed | Fair value committee memo |
| Fund admin price comparison | Compare internal prices to fund administrator's pricing | Month-end | NAV reconciliation |

### Fund Accounting Controls

| Control | Description | Frequency | Evidence |
|---------|-------------|-----------|---------|
| NAV calculation review | Review draft NAV; compare to prior month for reasonableness | Monthly | NAV review sign-off |
| HWM verification | Verify performance fee HWM calculation per LPA | Monthly | HWM schedule; LPA reference |
| Journal entry approval | All non-standard JEs require second-person review | Each JE | JE approval log |
| Bank/cash reconciliation | Reconcile all cash balances | Daily/Monthly | Cash recon report |
| Investor capital reconciliation | Verify LP capital accounts reconcile to NAV | Monthly | Capital account statement |

### Information Security Controls

| Control | Description | Frequency | Evidence |
|---------|-------------|-----------|---------|
| Trading platform access | Only authorized personnel have access to TradeStation, Robinhood, TradingView | Ongoing; review quarterly | Access list review |
| Password / MFA | All trading accounts use strong passwords and MFA | Ongoing | IT policy; access audit |
| Data backup | Fund records, trade data, and P&L records are backed up | Daily | Backup completion log |
| Encryption | Investor data, LP information, and financial records encrypted at rest and in transit | Ongoing | IT policy review |
| Vendor due diligence | Periodic review of third-party providers (TradeStation, Robinhood, TradingView) | Annual | Vendor due diligence file |

## Annual Audit Preparation

### LP Audit / Audited Financial Statements

Most hedge funds claiming custody must provide audited financials to LPs within 120 days of fiscal year-end. Prepare the following for your external auditor:

**Required Documentation Package:**
1. Trial balance as of year-end
2. NAV statement and NAV calculation workbook
3. Position file (all open positions at year-end closing prices)
4. Complete trade blotter for the year (TradeStation + Robinhood exports)
5. Reconciliation of internal NAV to fund administrator NAV
6. Bank and cash account statements (all accounts, year-end)
7. Management fee schedule and accrual calculation
8. Performance fee calculation and HWM schedule
9. Subscription and redemption schedule with LP confirmations
10. Auditor confirmation letters to TradeStation, Robinhood (prime broker / custodian)
11. Any related party transaction documentation
12. Copies of material agreements (LPA, investment management agreement, side letters)

### Sample Selection for Audit Testing

**Trade Population Selection (for auditor testing of trade recording):**

| Selection Method | When to Use | Sample Size |
|-----------------|-------------|-------------|
| Random (all trades) | Default for large trade populations | Per auditor guidance (typically 25-60) |
| Targeted (large trades) | Supplement to random; trades above $[threshold] | All above threshold |
| Period-end targeted | Trades in last week of fiscal year (cut-off risk) | All or judgment sample |
| Specific security | Auditor requests specific ticker or strategy | All related trades |

**Position Balance Confirmation (for auditor confirmation of positions):**
- Auditor typically sends direct confirmation requests to TradeStation, Robinhood as custodians
- Prepare position file in standard format (Ticker, CUSIP, Quantity, Price, Fair Value)
- Be prepared to provide cost basis detail for any positions selected for deeper testing

**NAV/Fee Testing:**
- Auditor typically re-computes management fee and performance fee from LPA terms
- Prepare LPA with fee sections highlighted; provide AUM history and HWM schedule
- Provide all pricing sources used for month-end NAV calculations

### Deficiency Classification for Hedge Funds

**Minor Control Deficiency:**
- A single reconciliation break that was resolved within 48 hours
- An approved pricing override with appropriate documentation
- A delayed trade confirm that settled in normal course

**Significant Deficiency:**
- Repeated reconciliation breaks in the same account or security
- Inconsistent application of valuation methodology without documentation
- Performance fee calculation error corrected before investor distribution
- Access control gap (unauthorized personnel with trading access)

**Material Control Weakness:**
- Undetected position discrepancy that affected reported NAV to investors
- Management fee or performance fee materially miscalculated and distributed
- Failure to reconcile to fund administrator for a full reporting period
- LP misallocation of realized gains/losses affecting tax reporting

## Code of Ethics — Key Compliance Points

- **Personal account trading:** All employees must pre-clear personal securities trades; log in compliance system
- **MNPI policy:** Written procedures for handling material non-public information; restricted list maintained
- **Outside business activities:** Require disclosure and approval of any outside investment activities
- **Gift and entertainment:** Log and disclose per thresholds in compliance manual
- **Annual certification:** All employees certify compliance with Code of Ethics annually

## Compliance Testing Workpaper Template

```
COMPLIANCE CONTROL TEST WORKPAPER
===================================
Control Area:          [e.g., Trade Pre-Clearance, NAV Calculation, Position Reconciliation]
Control Description:   [What the control does, who performs it, how often]
Testing Period:        [Period covered]
Test Objective:        To verify that [control] operated effectively throughout the testing period

TEST PROCEDURES:
1. [Procedure 1]
2. [Procedure 2]
3. [Procedure 3]

SAMPLE:
  Population:    [All [control type] during period — N items]
  Sample Size:   [N items]
  Method:        [Random / Targeted / All items]

RESULTS:
| Sample # | Date | Item | Expected Evidence | Evidence Found | Result | Exception? |
|----------|------|------|------------------|----------------|--------|------------|
| 1 | | | | | Pass/Fail | Y/N |
| 2 | | | | | Pass/Fail | Y/N |

EXCEPTIONS:
[If any: describe exception, root cause, severity, and remediation]

CONCLUSION:
[ ] Effective — Control operated effectively; no exceptions
[ ] Minor deficiency — Isolated exception; not expected to repeat
[ ] Significant deficiency — Pattern of exceptions; requires remediation
[ ] Material weakness — Control failed to operate; investor/regulatory impact possible

Tested by: ____________  Date: ________
Reviewed by: ___________  Date: ________
```
