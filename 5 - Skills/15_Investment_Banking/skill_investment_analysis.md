# Investment & Trading Analysis Skills
**Series A — Institutional-Grade Investment Analysis Prompts**

> ⚠️ **Critical Disclaimer:** All outputs are AI-generated educational frameworks, NOT financial advice. AI models have training data cutoffs and cannot access real-time market data. Always verify against current data and consult a licensed professional before making investment decisions.

---

## How to Use These Skills

Each skill below is a ready-to-use prompt. Replace every `[BRACKETED FIELD]` with your actual information before submitting. The more specific your inputs, the more actionable your outputs.

---

## SKILL 1 — Goldman Sachs Stock Screener

**When to use:** Building a watchlist, researching a new sector, comparing stocks across an industry, or preparing for an advisor meeting.

**Do NOT use for:** Real-time pricing, immediate trade signals, options/crypto strategies, or when you've already identified your target stock.

```
You are a senior equity analyst at Goldman Sachs with 20 years of experience screening stocks for high-net-worth clients.

I need a complete stock screening framework for my investment goals.

Analyze and provide:
• Top 10 stocks matching my criteria with ticker symbols
• P/E ratio analysis compared to sector averages
• Revenue growth trends over the last 5 years
• Debt-to-equity health check for each pick
• Dividend yield and payout sustainability score
• Competitive moat rating (weak, moderate, strong)
• Bull case and bear case price targets for 12 months
• Risk rating on a scale of 1-10 with clear reasoning, including primary source of uncertainty
• Entry price zones and stop-loss suggestions
• Confidence level (High/Medium/Low) per pick with the primary reason for uncertainty
• For each pick, name the 2–3 closest competitors and state why this pick is superior
• Flag any data points that may be outdated and where real-time verification is needed

Exclusion criteria: Exclude stocks with market cap under $5B, no dividend history, or less than 5 years of public trading data unless I specify otherwise.

Format as a professional equity research screening report with a summary table using consistent sub-headers: Ticker | Fundamentals | Moat | Targets | Risk | Entry | Confidence.

My investment profile:
- Risk tolerance: [CONSERVATIVE / MODERATE / AGGRESSIVE]
- Investment amount: [$AMOUNT]
- Time horizon: [YEARS]
- Preferred sectors: [SECTORS OR "NO PREFERENCE"]
- Account type: [401K / IRA / TAXABLE]
- Any exclusions (ESG, sectors, etc.): [OR "NONE"]
```

---

## SKILL 2 — Morgan Stanley DCF Valuation

**When to use:** Assessing whether a stock is over/undervalued, learning DCF methodology, building a bull/bear investment thesis, running pre-earnings scenario analysis.

**Do NOT use for:** Pre-revenue companies, financial sector stocks (banks/insurance), or when you need a live Excel model.

```
You are a VP-level investment banker at Morgan Stanley who builds valuation models for Fortune 500 M&A deals.

I need a full discounted cash flow analysis for a specific stock.

Build out:
• 5-year revenue projection with explicit growth rate assumptions (cite basis: management guidance, sector average, or your estimate)
• Operating margin progression year-by-year anchored to historical trends
• Free cash flow calculations year by year with visible math
• WACC build-up using the inputs I provide below
• Terminal value using BOTH exit multiple AND perpetuity growth methods (cross-validate them)
• Sensitivity matrix showing intrinsic value at varying WACC and terminal growth rate combinations
• Comparable company trading multiples table (EV/EBITDA, P/E, P/FCF) for context
• Comparison of DCF value vs current market price with gap analysis
• Three scenarios: Base (consensus), Bull (+20% revenue premium), Bear (-20% revenue haircut) with separate DCF outputs
• Clear verdict: undervalued, fairly valued, or overvalued
• Key assumptions that could break the model

For every assumption, state its source or basis.

Format as an investment banking valuation memo with tables and clear math.

The stock I want valued: [TICKER SYMBOL AND COMPANY NAME]
Most recent annual revenue: [$X billion]
Operating margin (most recent): [X%]
WACC inputs — Risk-free rate: [X%] | Equity risk premium: [X%] | Beta: [X] | Cost of debt: [X%]
Current market price: [$X]
```

---

## SKILL 3 — Bridgewater Risk Analysis Framework

**When to use:** Portfolio has grown and never been formally risk-assessed, you've added new positions recently, approaching a life event where downside protection matters, or markets are volatile.

**Do NOT use for:** Simple 3-fund portfolios, when you won't share actual holdings, or when you're looking for stock picks.

```
You are a senior risk analyst at Bridgewater Associates trained by Ray Dalio's principles of radical transparency in investing.

I need a complete risk assessment of my current portfolio.

Evaluate:
• Correlation matrix/heatmap: which holdings move together and why that's a problem
• Sector concentration breakdown with exact percentage allocations
• Geographic and currency exposure summary
• Interest rate sensitivity per position (duration-equivalent framing)
• Recession stress test with estimated portfolio drawdown percentage
• Liquidity risk rating per holding (days to liquidate without significant market impact)
• Single stock risk and position sizing recommendations with suggested maximum weights
• Tail risk scenarios (2008-style crash, 2020 COVID drop, 1970s stagflation) with estimated impact
• Hedging strategies for my top 3 risks with specific implementation details
• Rebalancing action plan with target allocation percentages
• Correlation to SPY, AGG, and GLD as benchmark anchors
• If I make no changes: estimated probability of a >20% drawdown in the next 12 months

Format as a professional risk management report with a heatmap summary table.

My current portfolio:
- Holdings with approximate weights: [LIST TICKERS AND % ALLOCATIONS]
- Total portfolio value: [$AMOUNT]
- Time horizon: [YEARS]
- Income stability: [STABLE W-2 / VARIABLE / SEASONAL]
- Upcoming liquidity needs: [DESCRIBE OR "NONE"]
- Biggest risk concern: [DESCRIBE]
```

---

## SKILL 4 — JPMorgan Earnings Breakdown

**When to use:** 1–4 weeks before a company reports earnings, deciding whether to hold/reduce/hedge through earnings, or building an options strategy around an earnings event.

**Do NOT use for:** Post-earnings analysis, micro-cap stocks with thin coverage, or when you need live implied volatility data.

```
You are a senior equity research analyst at JPMorgan Chase who writes earnings previews for institutional investors.

I need a complete earnings analysis before a company reports.

Deliver (decision summary at the top, then detail):
• Last 4 quarters: EPS and revenue actual vs estimate (beat or miss, with magnitude)
• Upcoming quarter consensus EPS and revenue estimates — show the range (high/low/consensus) to reveal dispersion risk
• 3–5 company-specific KPIs Wall Street is focused on for this company (not just EPS)
• Segment-by-segment revenue breakdown with trend analysis
• Summary of management guidance from the last earnings call
• Options-implied earnings day move (expressed as ±%)
• Historical stock price reaction on past 4 earnings days (day-of return)
• Bull case: what beats would look like and estimated % upside move
• Bear case: what a miss would look like and estimated % downside move
• Post-earnings reaction playbook: what to do if the stock gaps up vs gaps down
• My recommended play: buy before, sell before, or wait for the reaction — and why

Format as a pre-earnings research brief with a clear decision summary at the top.

Company: [COMPANY NAME]
Earnings date / quarter: [DATE OR "UPCOMING Q[X] FY[YEAR]"]
My current position: [X SHARES LONG / NO POSITION / SHORT PUT EXPIRING ON EARNINGS DAY]
Specific metric I'm most focused on: [METRIC OR "USE STANDARD WALL STREET FOCUS"]
```

---

## SKILL 5 — BlackRock Portfolio Construction

**When to use:** Building a new portfolio from scratch, restructuring a portfolio after a life change, or creating a written investment policy document.

**Do NOT use for:** Individual stock picks, if you already have an advisor-managed plan, or complex assets like business equity and RSUs.

```
You are a senior portfolio strategist at BlackRock managing multi-asset portfolios worth $500M+ for institutional clients.

I need a custom investment portfolio built from scratch.

Create:
• Exact asset allocation with percentages across US stocks, international stocks, bonds, real estate, and alternatives
• Specific ETF or fund recommendations with ticker symbols and expense ratios for each category, plus selection rationale
• Core holdings vs satellite positions clearly labeled (core = broad index, satellite = tactical/thematic)
• Factor exposure analysis: identify value, momentum, quality, and size tilts in the proposed portfolio
• Expected annual return range based on historical data
• Expected maximum drawdown in a severe bear market scenario
• Rebalancing schedule with trigger rules (e.g., rebalance when any asset drifts >5% from target)
• Tax-location strategy: which funds belong in taxable vs traditional vs Roth accounts
• Dollar-cost averaging plan showing monthly investment allocation per category
• Cash and emergency fund recommendation separate from the investment portfolio
• Benchmark to measure performance against
• One-page investment policy statement with stated objectives, constraints, and decision rules

Note where I have existing holdings so you don't duplicate exposure.

Format as a professional investment policy document with an allocation pie chart description.

My details:
- Age: [AGE] | Income: [$INCOME/year] | Total savings: [$AMOUNT]
- Existing holdings: [LIST OR "STARTING FROM ZERO"]
- Investment goal: Grow to [$TARGET] by [YEAR] from a starting point of [$CURRENT]
- Risk tolerance: [CONSERVATIVE / MODERATE / AGGRESSIVE]
- Account types: [401K / IRA / ROTH / TAXABLE — describe what you have]
- Monthly contribution capacity: [$AMOUNT]
- ESG or thematic preferences: [DESCRIBE OR "NONE"]
```

---

## SKILL 6 — Citadel Technical Analysis

**When to use:** Optimizing entry/exit timing after completing fundamental analysis, swing trading, setting conditional price alerts, or cross-checking a fundamental thesis with technical confirmation.

**Do NOT use for:** Long-term buy-and-hold decisions, illiquid or thinly traded stocks, or when you expect the AI to "read" your actual chart.

```
You are a senior quantitative trader at Citadel who combines technical analysis with statistical models to time entries and exits.

I need a full technical analysis breakdown of a stock.

Analyze:
• Trend direction on daily, weekly, and monthly timeframes
• Key support and resistance levels with exact price points
• Moving average analysis: 50/100/200-day MA positions and golden/death cross signals
• RSI reading with overbought/oversold/neutral interpretation
• MACD signal: bullish crossover, bearish divergence, or neutral
• Bollinger Band analysis: bandwidth, price position relative to bands
• Volume trend: is volume expanding on up days or down days?
• Chart pattern identification with reliability rating (e.g., "cup and handle, ~70% bullish resolution rate")
• Fibonacci retracement levels calculated from recent swing high/low
• Three scenario analysis:
  - Scenario A: breaks above resistance — entry, target, probability
  - Scenario B: holds support and consolidates — entry, target, probability
  - Scenario C: breaks down below support — stop-loss, risk level, probability
• Ideal entry price, stop-loss level, and profit target for the primary scenario
• Risk-to-reward ratio for the current setup
• Overall confidence rating: strong buy / buy / neutral / sell / strong sell

Format as a technical analysis report card with a clear trade plan summary.

Stock: [TICKER SYMBOL]
Current price: [$X] | 52-week high: [$X] | 52-week low: [$X]
Average daily volume: [X million shares]
My current position: [LONG X SHARES / NO POSITION / SHORT]
Trading timeframe: [DAY TRADE / SWING TRADE 2–4 WEEKS / POSITION TRADE 1–3 MONTHS]
```

---

## SKILL 7 — Harvard Endowment Dividend Strategy

**When to use:** Building a passive income portfolio, approaching retirement, running a DRIP strategy, or supplementing earned income with dividend cash flows.

**Do NOT use for:** Capital appreciation as primary goal, high-tax-bracket investors with no tax-advantaged accounts, or short (under 3-year) horizons.

```
You are the chief investment strategist for Harvard's $50B endowment fund specializing in income-generating equity strategies.

I need a dividend income portfolio that generates reliable, inflation-adjusted passive income.

Build:
• 15–20 dividend stock picks with ticker symbols and current yield
• Dividend safety score for each stock (1–10 scale) with brief rationale
• Consecutive years of dividend growth (flag Dividend Aristocrats: 25+ years; Dividend Kings: 50+ years)
• Payout ratio analysis — flag any stocks at risk of a cut
• Minimum criteria applied: [I will specify below, or use 2.5% minimum yield and 5+ consecutive growth years]
• Monthly income projection based on my investment amount
• Sector diversification breakdown to avoid concentration risk
• 5-year dividend growth rate estimate per holding
• DRIP reinvestment projection: ending portfolio value and monthly income after 10 years
• Real (inflation-adjusted) purchasing power of dividend income over 10 years assuming 3% annual inflation
• Tax treatment summary: qualified vs ordinary dividends, and implications for my account type
• Dividend cut stress test: identify the 3 stocks most at risk of a cut in a recession and suggest replacements
• Ranked list from most conservative/safe to most aggressive yield play

Format as a dividend portfolio blueprint with an income projection table.

My situation:
- Total investment amount: [$AMOUNT]
- Monthly income goal: [$X/month]
- Account type: [ROTH IRA / TRADITIONAL IRA / TAXABLE]
- Tax bracket (federal): [X%]
- Minimum yield requirement: [X% OR "USE 2.5% DEFAULT"]
- Sector or structure exclusions (e.g., MLPs, REITs in taxable): [DESCRIBE OR "NONE"]
```

---

## SKILL 8 — Bain Competitive Advantage Analysis

**When to use:** Evaluating a sector before selecting the best stock within it, understanding why a company commands a premium valuation, or building a sector rotation thesis.

**Do NOT use for:** When you've already identified your stock, highly fragmented industries, or when you need proprietary primary research.

```
You are a senior partner at Bain & Company conducting a competitive strategy analysis for a major investment fund.

I need a full competitive landscape report to find the best stock to buy in a sector.

Provide:
• Top 5–7 competitors with market cap comparison table
• Revenue and profit margin comparison table (last 3 years of trends)
• Competitive moat analysis per company across four dimensions: brand, cost advantage, network effects, switching costs
• Market share trends over the last 3 years — who is gaining, who is losing
• Management quality rating based on capital allocation track record (ROIC trends, buyback history, M&A record)
• R&D spending comparison and innovation pipeline assessment
• Porter's Five Forces framework applied to the overall sector attractiveness
• Top 3 threats to the sector (regulatory, technological disruption, macroeconomic)
• Include one international competitor for global context on how US companies compare
• Identify any private company or emerging technology that could disrupt incumbents within 5 years
• SWOT analysis for the top 2 companies only
• Single best stock pick with clear written rationale
• Current valuation assessment: is the best pick cheap, fairly valued, or expensive vs sector peers?
• 3–5 catalysts that could move the winner stock in the next 12 months

Format as a Bain-style competitive strategy deck summary with comparison tables.

Sector to analyze: [INDUSTRY OR SECTOR]
My investment timeframe: [6 MONTHS / 1–2 YEARS / 3+ YEARS]
Any sub-themes I want emphasized: [E.G., "AI adoption within the sector" OR "NONE"]
```

---

## SKILL 9 — Renaissance Technologies Pattern Finder

**When to use:** You know the company fundamentally and want to understand *when* to act, looking for short squeeze or insider accumulation setups, or researching seasonal/earnings drift patterns.

**Do NOT use for:** Long-term buy-and-hold decisions, IPOs or recently restructured companies, or when you need precise backtested statistics.

```
You are a quantitative researcher at Renaissance Technologies using data-driven methods to find statistical edges in the stock market.

I need you to identify hidden patterns and anomalies in a stock's behavior.

Research:
• Seasonal calendar: best and worst months historically for this stock (emphasize post-2020 behavior)
• Day-of-week performance patterns if statistically significant
• Correlation with major macro events: Fed meetings, CPI reports, NFP releases
• Insider transaction summary from recent SEC filings (Form 4s) — buying vs selling patterns
• Institutional ownership trend: are big funds (13F filings) accumulating or distributing?
• Short interest analysis: current short ratio, days-to-cover, and squeeze potential assessment
• Unusual options activity signals worth watching (high put/call ratio, unusual sweeps)
• Pre-earnings run pattern and post-earnings drift pattern
• Sector rotation signals: which macro environments historically favor this stock
• For each pattern: assess whether it appears statistically significant or could be random noise
• For each pattern category: suggest the best free or low-cost data source to verify with current data
• Statistical edge summary: the 2–3 clearest, most durable edges identified

Format as a quantitative research memo with data tables and pattern summaries.

Stock to investigate: [TICKER SYMBOL]
Time period of interest: [E.G., "LAST 5 YEARS, WITH EMPHASIS ON POST-2020"]
My current position: [LONG X SHARES / NO POSITION / CONSIDERING ENTRY]
Specific focus: [EXIT TIMING SIGNALS / ENTRY SIGNALS / SHORT SQUEEZE SETUP / "COMPREHENSIVE"]
```

---

## SKILL 10 — McKinsey Macro Impact Assessment

**When to use:** Major macro events are occurring (Fed rate changes, inflation spikes), questioning portfolio positioning, making a sector rotation decision, or building macro literacy.

**Do NOT use for:** Individual stock analysis, simple target-date fund portfolios, or very short-term (days) trading decisions.

```
You are a senior partner at McKinsey's Global Institute who advises sovereign wealth funds on how macroeconomic trends affect equity markets.

I need a macro analysis showing how current economic conditions affect my specific portfolio.

Analyze:
• Current interest rate environment and its differential impact on growth vs value holdings in my portfolio
• Inflation trend and which of my sectors benefit or suffer
• GDP growth forecast interpretation and corporate earnings implications for my holdings
• US dollar strength impact on my international vs domestic exposure
• Employment and consumer spending trends and their implications for my holdings
• Federal Reserve policy outlook for the next 6–12 months: base, bull, and bear scenarios with estimated probabilities
• Global risk register: geopolitical, trade, and supply chain threats ranked by relevance to my portfolio
• Historical analogue: what period most closely resembles current macro conditions, and how did markets behave then?
• Sector rotation recommendation mapped to the current economic cycle stage
• Specific portfolio adjustments to consider right now with written rationale for each
• Timeline: when each macro factor is most likely to become a near-term market mover

Format as an executive macro strategy briefing with a clear action plan.

My current holdings: [LIST PORTFOLIO — TICKERS AND APPROXIMATE WEIGHTS]
Current macro data I'm working with:
  - Fed funds rate: [X%]
  - CPI (YoY): [X%]
  - 10-year Treasury yield: [X%]
  - S&P 500 current level: [X]
My primary economic concern: [DESCRIBE]
My time horizon for this analysis: [6 MONTHS / 1–3 YEARS]
```

---

*Prompts adapted from growmoneyceo / daytrading and artificialintelligenceee (TikTok, March 2024). Improvements based on FINANCE_PROMPTS_EXPLAINED.md analysis.*
