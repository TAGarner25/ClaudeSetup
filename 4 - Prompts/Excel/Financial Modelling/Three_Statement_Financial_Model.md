# PROMPT - Copy & Paste Everything Below Into Claude Excel Plugin

Create a comprehensive three-statement financial model (Income Statement, Balance Sheet, and Cash Flow Statement) in Excel with full integration and error-checking capabilities. The model should include historical periods and multi-scenario projections.

## Historical Data Requirements

- Include 2 historical periods (e.g., 2023 and 2024)
- Keep balance sheet structures simple and clean
- Use actual or representative data for a hypothetical company
- Ensure all three statements are fully integrated for historical periods

## Cash Flow Statement Specifications

- Use the indirect method for both historical and projected periods
- Start with Net Income and adjust for:
  - Non-cash expenses (depreciation, amortization)
  - Changes in working capital (accounts receivable, inventory, accounts payable)
  - Operating, investing, and financing activities
- Ensure cash flow reconciles to the balance sheet cash position

## Projection Parameters

- Time horizon: 5 years (2025-2029)
- Project all three statements with full integration
- Build assumptions table with key drivers:
  - Revenue growth rate
  - COGS as % of revenue
  - Operating expenses as % of revenue
  - CAPEX as % of revenue
  - Depreciation method and rates
  - Working capital assumptions (DSO, DIO, DPO)
  - Tax rate
  - Debt repayment schedule
  - Dividend policy

## Scenario Analysis

Create three distinct scenarios with toggle functionality:

- **Base Case** - Moderate growth assumptions
- **Optimistic Case** - Higher revenue growth, improved margins
- **Conservative Case** - Lower growth, compressed margins

Include a scenario selector (dropdown or toggle mechanism) that dynamically updates all three statements based on selected scenario assumptions.

## Critical Accounting Equations & Checks

Implement the following validation checks with clear error indicators:

### Balance Sheet Integrity

- Assets = Liabilities + Equity (must balance for every period)
- Display check formula: IF(Total Assets = Total Liabilities + Total Equity, "BALANCED", "ERROR")

### Income Statement to Balance Sheet Links

- Current year Net Income must flow to Retained Earnings
- Calculate: Beginning Retained Earnings + Net Income - Dividends = Ending Retained Earnings

### Cash Flow to Balance Sheet Reconciliation

- Ending Cash from Cash Flow Statement = Cash on Balance Sheet
- Formula check: Beginning Cash + Net Change in Cash = Ending Cash

### Additional Validation Checks

- Revenue growth rates are reasonable and consistent
- All percentages and ratios are within logical ranges
- No negative equity or unreasonable leverage ratios
- Working capital changes reconcile between balance sheet and cash flow

## Best Practices to Implement

- **Clear Structure**: Separate sections for assumptions, historical data, and projections
- **Color Coding**:
  - Blue for inputs/assumptions
  - Black for formulas
  - Green for links from other statements
- **Circularity Management**: Handle interest expense calculations properly (interest on debt depends on debt balance)
- **Dynamic Formatting**: Use conditional formatting to highlight errors or unusual values
- **Documentation**: Include notes explaining key assumptions and methodologies
- **Flexibility**: Make the model easy to update and modify assumptions
- **Professional Layout**: Clean formatting with appropriate borders, headers, and labels

## Claude in Excel Capabilities to Leverage

- Automated formula generation for complex calculations
- Quick setup of linked financial statements
- Error-checking formulas and validation rules
- Scenario analysis structure with dropdown controls
- Working capital schedule automation
- Depreciation schedule creation
- Debt schedule with principal and interest calculations
- Conditional formatting for checks
- Professional formatting and layout

## Deliverables

- Integrated three-statement model with 2 historical + 5 projected years
- Assumptions dashboard with all key drivers
- Three scenario toggle with distinct assumption sets
- All accounting equation checks with visual error indicators
- Supporting schedules (working capital, depreciation, debt)
