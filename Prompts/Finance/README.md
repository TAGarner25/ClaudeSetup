# Finance Prompts Explained
*Total Prompts: 20*
*Theme: Institutional-grade financial analysis using AI role-play personas from elite firms*

> **⚠️ Critical Disclaimer:** All outputs from these prompts are AI-generated and must be treated as educational frameworks, NOT financial advice. AI models have training data cutoffs, cannot access real-time market data unless connected to live tools, and are not licensed financial advisors. Always verify outputs against current data and consult a licensed professional before making investment decisions.

---

## Table of Contents

### Series A — Investment & Trading Prompts (growmoneyceo / daytrading & artificialintelligenceee)
1. [Goldman Sachs-Level Stock Screener](01_Goldman_Sachs_Stock_Screener.md)
2. [Morgan Stanley-Style DCF Valuation Deep Dive](02_Morgan_Stanley_DCF_Valuation.md)
3. [Bridgewater-Inspired Risk Analysis Framework](03_Bridgewater_Risk_Analysis_Framework.md)
4. [JPMorgan-Level Earnings Breakdown](04_JPMorgan_Earnings_Breakdown.md)
5. [BlackRock-Style Portfolio Construction Model](05_BlackRock_Portfolio_Construction.md)
6. [Citadel-Grade Technical Analysis System](06_Citadel_Technical_Analysis_System.md)
7. [Harvard Endowment-Inspired Dividend Strategy](07_Harvard_Endowment_Dividend_Strategy.md)
8. [Bain-Style Competitive Advantage Analysis](08_Bain_Competitive_Advantage_Analysis.md)
9. [Renaissance Technologies Pattern Finder](09_Renaissance_Technologies_Pattern_Finder.md)
10. [McKinsey-Level Macro Impact Assessment](10_McKinsey_Macro_Impact_Assessment.md)

### Series B — Personal Finance & Wealth Planning Prompts (evolving.ai)
11. [Goldman Sachs Wealth Diagnostic](11_Goldman_Sachs_Wealth_Diagnostic.md)
12. [Vanguard Retirement Planning Calculator](12_Vanguard_Retirement_Planning_Calculator.md)
13. [Morgan Stanley Investment Portfolio Architect](13_Morgan_Stanley_Investment_Portfolio_Architect.md)
14. [Deloitte Tax Optimization Strategist](14_Deloitte_Tax_Optimization_Strategist.md)
15. [JPMorgan Debt Elimination Engineer](15_JPMorgan_Debt_Elimination_Engineer.md)
16. [Charles Schwab Emergency Fund and Cash Strategy](16_Charles_Schwab_Emergency_Fund_Cash_Strategy.md)
17. [Northwestern Mutual Insurance Audit](17_Northwestern_Mutual_Insurance_Audit.md)
18. [Fidelity College Savings Architect](18_Fidelity_College_Savings_Architect.md)
19. [Edward Jones Estate Planning Organizer](19_Edward_Jones_Estate_Planning_Organizer.md)
20. [Wealthfront Real Estate Investment Analyzer](20_Wealthfront_Real_Estate_Investment_Analyzer.md)

---

## Cross-Prompt Integration Map

The prompts across both series are most powerful when chained. Series A (investment/trading) and Series B (personal finance) address different layers of financial life but connect at several key points.

### Series A: Investment Research Workflow
```
SECTOR SELECTION
    │
    ▼
Prompt 8 (Bain Competitive Analysis)
"Which company in this sector is the best?"
    │
    ▼
Prompt 1 (Goldman Sachs Stock Screener)
"Screen for top picks matching my profile"
    │
    ├──────────────────────────────────────┐
    ▼                                      ▼
Prompt 2 (Morgan Stanley DCF)         Prompt 9 (Renaissance Patterns)
"What is it worth?"                    "When should I act?"
    │                                      │
    └──────────────┬───────────────────────┘
                   ▼
    Prompt 6 (Citadel Technical Analysis)
    "Where are the key price levels?"
                   │
                   ▼
    Prompt 4 (JPMorgan Earnings Preview)
    "What's the near-term catalyst?"
                   │
    ┌──────────────┴──────────────────────┐
    ▼                                     ▼
Prompt 3 (Bridgewater Risk)         Prompt 10 (McKinsey Macro)
"How much risk am I taking?"         "What macro tailwinds/headwinds?"
    │                                     │
    └──────────────┬──────────────────────┘
                   ▼
    Prompt 5 (BlackRock Portfolio Construction)
    "How does this fit into my overall portfolio?"
                   │
                   ▼
    Prompt 7 (Harvard Dividend Strategy)
    "How do I generate income from this position?"
```

### Series B: Personal Finance Planning Workflow
```
START HERE: Full Financial Picture
    │
    ▼
Prompt 11 (Goldman Sachs Wealth Diagnostic)
"Where do I stand across all financial dimensions?"
    │
    ├─────────────────────┬─────────────────────┐
    ▼                     ▼                     ▼
Prompt 15              Prompt 16             Prompt 17
(JPMorgan Debt)    (Schwab Emergency)    (NW Mutual Insurance)
"Pay off debt"      "Build safety net"    "Fix coverage gaps"
    │                     │                     │
    └─────────────────────┼─────────────────────┘
                          ▼
               Prompt 14 (Deloitte Tax)
               "Minimize what I owe"
                          │
               ┌──────────┼──────────┐
               ▼          ▼          ▼
          Prompt 12   Prompt 13  Prompt 18
         (Vanguard   (MS Portfolio (Fidelity
        Retirement)  Architect)    College)
        "Retire when  "Build the    "Fund the
         I want"       portfolio"    kids"
               │          │
               └────┬─────┘
                    ▼
          Prompt 19 (Edward Jones Estate)
          "Protect and transfer wealth"
                    │
                    ▼
          Prompt 20 (Wealthfront Real Estate)
          "Should I add real estate?"
```

### Series A ↔ Series B Connection Points
- **Prompts 3 + 11:** Bridgewater Risk Assessment feeds into the investment allocation dimension of the Wealth Diagnostic
- **Prompts 5/13:** BlackRock Portfolio Construction and Morgan Stanley Portfolio Architect both produce investment policy statements — use whichever matches your complexity level
- **Prompts 7 + 12:** Harvard Dividend Strategy and Vanguard Retirement both address income generation — align dividend strategy with retirement withdrawal plan
- **Prompts 10 + 14:** McKinsey Macro Assessment informs sector rotation; Deloitte Tax informs tax-efficient implementation of those rotations
- **Prompts 2 + 20:** Morgan Stanley DCF (stocks) and Wealthfront Real Estate use similar NPV/cash flow frameworks — applying both creates consistent analytical standards across asset classes

---

## Universal Improvement Principles for All Prompts

1. **Always provide real, specific inputs** — Every prompt has a bracketed placeholder. The quality of output scales directly with input specificity.
2. **Pair AI output with live data tools** — AI has knowledge cutoffs. Always verify specific numbers (yields, P/E ratios, prices) against current data from Morningstar, Koyfin, TIKR, or Yahoo Finance.
3. **Request confidence flagging** — Add "Flag any data point that may be outdated or that requires real-time verification" to any prompt.
4. **Use iterative refinement** — After the first output, follow up with "Drill deeper into [specific section]" or "Revise assuming [changed assumption]."
5. **Never treat outputs as advice** — Use these prompts to build frameworks and generate hypotheses, then validate with licensed professionals and real data before acting.

---

## Series A — Investment & Trading Prompts
*Focus: Stock screening, valuation, technical analysis, portfolio construction, macro analysis*

---

## 1. Goldman Sachs-Level Stock Screener

### Purpose
This prompt is designed to generate a structured, multi-dimensional stock screening report modeled after the equity research process used by institutional sell-side analysts. It forces the AI to evaluate stocks across nine distinct analytical dimensions simultaneously — from fundamental metrics (P/E, D/E, revenue growth) to qualitative assessments (moat rating) and tactical guidance (entry zones, stop-losses).

The "Goldman Sachs analyst" persona is a prompt engineering technique called **role-play priming**, which biases the model toward professional-grade output structure, formal tone, and comprehensive coverage rather than casual summaries.

### When to Use
**Use when:**
- Starting research on a new sector or theme and need a broad shortlist
- Building a watchlist and want a consistent evaluation framework across multiple stocks
- Teaching yourself fundamental analysis by seeing how a screening framework is structured
- Comparing stocks across a sector before deeper single-stock analysis
- Preparing for a conversation with a financial advisor and want to arrive informed

**Do NOT use when:**
- You need real-time pricing, live P/E ratios, or current earnings data (AI knowledge has a cutoff)
- You're about to make an immediate trade — outputs are frameworks, not signals
- Your portfolio is highly specialized (options, commodities, crypto) — this prompt is equity-focused
- You've already done fundamental research and need execution-level precision

### Expected Output
A structured equity research report containing:
- A summary table with 10 stocks, tickers, and key metrics side-by-side
- Narrative sections covering each of the nine analytical dimensions listed
- Bull/bear price targets with supporting rationale
- Risk ratings (1-10) with written justification
- Entry zones expressed as price ranges
- Stop-loss levels expressed as percentages or price points
- Formatting modeled after a professional sell-side research brief

**Quality will vary significantly** based on how complete your investment profile input is. Vague inputs ("moderate risk, tech stocks") produce generic outputs. Specific inputs ("$50K, 10-year horizon, moderate risk, dividend-paying large-cap tech and healthcare") produce far more actionable results.

### What the Prompt Does Well
- **Comprehensiveness:** Nine distinct analytical dimensions ensure nothing obvious is missed
- **Structured output demand:** Requesting a "summary table" forces tabular formatting that is easy to scan
- **Dual price targets:** Requiring both bull and bear cases forces balanced thinking rather than just a buy thesis
- **Risk quantification:** The 1-10 risk scale with reasoning creates accountability in the output
- **Persona priming:** The Goldman Sachs framing consistently produces more formal, structured responses

### Ways to Improve the Prompt
1. **Add a data freshness instruction:** Append "Note any data points that may be outdated and flag where real-time verification is needed." This makes the AI self-report its limitations.
2. **Specify output format more precisely:** Request "Format each stock entry with a consistent sub-header structure: Ticker | Fundamentals | Moat | Targets | Risk | Entry."
3. **Add exclusion criteria:** Include "Exclude stocks with market cap under $5B, no dividend history, or less than 5 years of public trading data."
4. **Request confidence levels:** Add "For each pick, state your confidence level (High/Medium/Low) and the primary reason for uncertainty."
5. **Add peer comparison instruction:** "For each pick, name the 2-3 closest competitors and state why this pick is superior."
6. **Separate screening from analysis:** First use a simpler screening prompt to get a list, then run a deeper single-stock analysis (Prompt 2) on the top picks.

### Additional Resources
- **Morningstar Stock Screener** (morningstar.com) — Cross-reference AI picks against real screener data
- **Simply Wall St** (simplywall.st) — Visualizes many of the same dimensions this prompt covers
- **CFA Institute: Equity Valuation** — Foundational reading on what institutional analysts actually measure
- **Howard Marks: The Most Important Thing** — Essential reading on risk-adjusted thinking, which underpins the moat/risk scoring
- **Damodaran Online** (pages.stern.nyu.edu/~adamodar) — Aswath Damodaran's free valuation datasets and frameworks

---

## 2. Morgan Stanley-Style DCF Valuation Deep Dive

### Purpose
This prompt generates a Discounted Cash Flow (DCF) model walkthrough for a specific stock, structured as an investment banking valuation memo. DCF is the gold-standard intrinsic value methodology used in M&A, private equity, and fundamental investing. The prompt is designed to produce a full model output with visible math, making it both educational and analytically useful.

The "Morgan Stanley VP" persona is calibrated specifically for valuation — Morgan Stanley is known for rigorous M&A advisory work, making the persona highly appropriate to the task.

### When to Use
**Use when:**
- You want to understand whether a stock is overvalued or undervalued relative to its cash flows
- Learning DCF methodology and want to see it applied to a real company
- Preparing a bull/bear case for a long-term investment thesis
- Running scenario analysis before an earnings release or major corporate event
- Comparing the AI's DCF output against analyst consensus targets as a sanity check

**Do NOT use when:**
- The company has no consistent or predictable cash flows (early-stage startups, biotech pre-revenue)
- You need current financial data — AI cannot pull live 10-K filings without tools
- You're evaluating financial companies (banks, insurance) where DCF is not the primary valuation methodology
- You need the model in spreadsheet form — this produces a narrative memo, not a live Excel model

### Expected Output
A structured investment banking memo containing:
- 5-year revenue projection table with explicit growth rate assumptions
- Operating margin progression year-by-year with historical anchor points
- Free cash flow calculations laid out per year
- WACC build-up (cost of equity, cost of debt, capital structure)
- Terminal value via both Exit Multiple and Gordon Growth Model
- Sensitivity matrix (usually 3x3 or 5x5) showing intrinsic value at varying WACC and growth assumptions
- Market price vs DCF value gap analysis
- A clear verdict: undervalued / fairly valued / overvalued
- Key assumption risks (the "model-breakers")

### What the Prompt Does Well
- **Dual terminal value methods:** Requiring both exit multiple AND perpetuity growth forces cross-validation and highlights model sensitivity
- **Sensitivity table demand:** This is the most important output of any DCF — the prompt correctly prioritizes it
- **"Key assumptions that could break the model":** This is professional-grade discipline that most retail investors skip entirely
- **Memo format request:** Structures the output for readability and professional presentation
- **"Clear math" instruction:** Reduces the AI's tendency to state conclusions without showing work

### Ways to Improve the Prompt
1. **Provide anchor data:** Add "Use the most recent annual revenue of $[X]B and operating margin of [Y]% as your base year inputs." This dramatically improves accuracy.
2. **Specify WACC inputs:** "Assume a risk-free rate of [X]%, equity risk premium of [Y]%, and beta of [Z] for the cost of equity calculation." This prevents the AI from using generic estimates.
3. **Request a base/bull/bear scenario set:** "Run three scenarios: Base (consensus), Bull (+20% revenue premium), Bear (-20% revenue haircut) with separate DCF outputs for each."
4. **Add comparable company context:** "Include a comparable company trading multiples table (EV/EBITDA, P/E, P/FCF) for context against the DCF output."
5. **Request explicit assumption disclosure:** "For every assumption you make, state the source or basis (e.g., 'management guidance,' 'sector average,' 'my estimate')."
6. **Follow up with Prompt 1:** Use the stock screener first to select your target, then apply this deep-dive valuation.

### Additional Resources
- **Damodaran's DCF Valuation Spreadsheets** (pages.stern.nyu.edu/~adamodar/New_Home_Page/spreadsh.htm) — Real, downloadable DCF models
- **WSJ.com / Macrotrends.net** — Free historical financial data for revenue, margins, and cash flow
- **Breaking Into Wall Street (BIWS)** — Gold-standard DCF modeling courses used by actual investment banking analysts
- **"Valuation" by McKinsey & Company** — The definitive textbook on DCF and corporate valuation
- **TIKR Terminal** (tikr.com) — Pulls real financial data for the inputs this prompt needs

---

## 3. Bridgewater-Inspired Risk Analysis Framework

### Purpose
This prompt generates a portfolio-level risk assessment modeled after Bridgewater Associates' "All Weather" and risk-parity philosophy. Rather than asking "what should I buy," it asks "what could hurt me and by how much." The prompt covers correlation analysis, concentration risk, stress testing, hedging, and rebalancing — the full suite of institutional risk management disciplines applied to a retail portfolio.

Ray Dalio's "radical transparency" framing signals the AI to be blunt and data-driven rather than comforting or vague.

### When to Use
**Use when:**
- Your portfolio has grown and you've never formally assessed its risk structure
- You've recently added several positions and want to check for concentration/correlation problems
- Markets are volatile and you want to stress-test before a potential drawdown
- You're approaching a life event (retirement, large expense) where downside protection matters more
- You want to understand your true risk exposure versus your perceived risk tolerance

**Do NOT use when:**
- Your portfolio is simple (e.g., 3-fund portfolio) — the framework is overkill and adds little value
- You cannot or do not want to provide your actual holdings — vague inputs produce useless outputs
- You're looking for stock picks — this prompt is purely about risk, not alpha generation
- You need options Greeks or volatility surface analysis — this is macro/fundamental risk, not derivatives risk

### Expected Output
A professional risk management report containing:
- Correlation matrix or heatmap description showing which holdings move together
- Sector concentration breakdown with percentage allocations
- Geographic/currency exposure summary
- Interest rate sensitivity by position (duration-equivalent analysis)
- Recession scenario with estimated portfolio drawdown percentage
- Liquidity ratings per holding (days to liquidate without significant market impact)
- Position sizing recommendations with suggested maximum weights
- Tail risk scenarios (e.g., 2008-style crash, 2020 COVID drop) with estimated impact
- Three hedging strategies with implementation specifics
- Rebalancing action list with target allocations

### What the Prompt Does Well
- **Holistic risk coverage:** Nine risk dimensions are covered, preventing tunnel vision on any single factor
- **Concrete output demands:** "Heat map summary table" and "specific allocation percentages" force actionable formatting
- **Tail risk inclusion:** Explicitly requesting low-probability, high-impact scenarios is how professionals think about risk
- **Hedging specificity:** Asking for "top 3 risks" with hedging strategies focuses output rather than producing vague generic advice
- **Rebalancing with percentages:** Demanding specific numbers forces the AI to commit to recommendations rather than hedging with vague language

### Ways to Improve the Prompt
1. **Provide your actual holdings:** The more specific (tickers, weights, dollar values), the more useful the output. Generic inputs like "tech stocks" produce generic outputs.
2. **Add your investment horizon:** "My time horizon is [X] years. Weight short-term liquidity risk accordingly."
3. **Include your income stability:** "My income is [stable/variable]. Adjust liquidity risk ratings with this context."
4. **Request correlation to benchmarks:** "Include correlation to SPY, AGG, and GLD as benchmark anchors."
5. **Add a "do nothing" scenario:** "If I make no changes, what is the probability of a >20% drawdown in the next 12 months based on current positioning?"
6. **Pair with Prompt 10:** After identifying macro risks here, use the McKinsey Macro prompt to understand the economic drivers behind those risks.

### Additional Resources
- **Portfolio Visualizer** (portfoliovisualizer.com) — Free tool to run actual correlation analysis and stress tests
- **Ray Dalio: Principles for Navigating Big Debt Crises** — Free PDF from Bridgewater explaining their risk framework
- **"The Intelligent Asset Allocator" by William Bernstein** — Foundational text on correlation-based portfolio construction
- **FRED (Federal Reserve Economic Data)** — Macro data for interest rate sensitivity analysis
- **Callan Periodic Table of Investment Returns** — Visual tool for understanding asset class risk/return cycles

---

## 4. JPMorgan-Level Earnings Breakdown

### Purpose
This prompt generates a pre-earnings research brief modeled after institutional sell-side previews published before a company's quarterly report. Earnings events are one of the highest-volatility, most predictable in their timing but least predictable in their outcome moments in investing. This prompt structures a comprehensive pre-earnings game plan covering historical beat/miss patterns, consensus estimates, Wall Street's key watch metrics, options-implied moves, and a recommended positioning strategy.

### When to Use
**Use when:**
- A stock you hold or are watching is 1-4 weeks from reporting earnings
- You want to understand the key metrics analysts will focus on (not just EPS)
- Deciding whether to hold through earnings, reduce position, or add a hedge
- Learning about a company's earnings pattern before initiating a position
- Building options strategies around an earnings event and want directional context

**Do NOT use when:**
- Earnings already occurred — this is a preview prompt, not a post-earnings analysis tool
- The company is very small/micro-cap with limited analyst coverage (consensus estimates won't exist in AI training data)
- You need the actual current implied volatility or options pricing — this requires a live options chain
- You're already deep in the company's fundamentals and need next-level specificity beyond what AI can provide

### Expected Output
A pre-earnings research brief containing:
- Historical beat/miss table for the last 4 quarters (EPS and revenue, actual vs estimate)
- Upcoming quarter consensus EPS and revenue estimates
- 3-5 company-specific KPIs Wall Street is focused on (e.g., for AMZN: AWS growth, ad revenue; for NVDA: data center revenue)
- Segment revenue breakdown with trend analysis
- Summary of last earnings call management guidance
- Options-implied earnings day move (expressed as ±%)
- Stock price reaction history on past 4 earnings days (day-of return)
- Bull case: what would cause upside surprise and estimated % move
- Bear case: what would cause downside miss and estimated % move
- Positioning recommendation: buy before, sell before, wait for reaction

### What the Prompt Does Well
- **Decision summary at top:** Requesting this first prevents burying the conclusion in analysis
- **Options implied move inclusion:** This is how professional traders size earnings risk — it's rarely included in retail-level analysis
- **Segment-level breakdown:** Forces granularity beyond headline EPS — crucial for understanding what actually drives the stock
- **Historical price reaction data:** Anchors expectations to actual market behavior rather than theoretical targets
- **Three-way decision framework:** Buy/sell/wait structure is more useful than a generic buy/sell signal

### Ways to Improve the Prompt
1. **Provide the earnings date and quarter:** "Q4 FY2025 earnings on [date]" reduces ambiguity and improves historical framing.
2. **Add your current position:** "I currently hold [X shares / no position / a short put expiring on earnings day]." This allows the AI to tailor the recommendation.
3. **Specify the key metrics you care about:** If you know the stock well, add "I specifically want analysis on [metric X] as the primary driver."
4. **Add post-earnings follow-up instruction:** "After providing the preview, suggest a post-earnings reaction playbook for both the beat and miss scenarios."
5. **Request analyst estimate range (not just consensus):** "Show the range of analyst estimates (high/low/consensus) to understand dispersion risk."
6. **Combine with Prompt 6:** After the earnings preview, use the Citadel Technical Analysis prompt to identify key price levels that may be triggered by the earnings reaction.

### Additional Resources
- **Earnings Whispers** (earningswhispers.com) — Tracks earnings dates, consensus, and whisper numbers
- **SeekingAlpha Earnings Calendar** — Analyst previews and post-earnings transcripts
- **OptionStrat** (optionstrat.com) — Visualizes options strategies for earnings plays
- **Estimize** — Crowdsourced earnings estimates that often outperform Wall Street consensus
- **Koyfin** (koyfin.com) — Free platform with earnings history, beat/miss records, and analyst estimates

---

## 5. BlackRock-Style Portfolio Construction Model

### Purpose
This is a from-scratch portfolio construction prompt that generates a complete, personalized investment policy statement (IPS) — the foundational document every institutional investor uses to govern portfolio management. It covers asset allocation, ETF selection, core vs satellite structure, tax strategy, rebalancing rules, and dollar-cost averaging, structured as a professional IPS document.

BlackRock's persona is ideal here because they are the world's largest asset manager and are known for systematic, multi-asset portfolio construction (iShares ETF line, Aladdin risk platform).

### When to Use
**Use when:**
- Starting a new portfolio from scratch and need a structured framework
- Your portfolio has grown organically and lacks intentional structure
- You've changed life circumstances (new job, marriage, approaching retirement) and need a portfolio overhaul
- You want a written investment policy document to guide future decisions and prevent emotional trading
- Learning about asset allocation principles for different life stages

**Do NOT use when:**
- You already have a detailed portfolio plan managed by an advisor — this overlaps with their work
- You want individual stock picks — this prompt is ETF/fund focused for broad exposure
- You need tax-specific legal advice — the output provides frameworks, not CPA-level guidance
- Your situation involves complex assets (real estate, business equity, restricted stock units) that require professional structuring

### Expected Output
A professional investment policy document containing:
- Asset allocation breakdown (e.g., 70% equities, 20% bonds, 10% alternatives) with exact percentages
- Specific ETF/fund recommendations per category with ticker symbols and expense ratios
- Core/satellite labeling (core = broad index, satellite = tactical or thematic positions)
- Historical return range for the proposed allocation (e.g., "Expected 7-9% annually, historically -25% in worst year")
- Maximum drawdown estimate in a severe bear market scenario
- Rebalancing schedule (quarterly, annually, or threshold-based trigger rules)
- Tax efficiency strategy (which assets go in which account types)
- DCA plan with suggested monthly investment amounts per category
- Benchmark selection (e.g., 60/40 blended benchmark)
- One-page IPS summary with stated objectives, constraints, and decision rules

### What the Prompt Does Well
- **Pie chart description request:** Forces a visual summary that makes allocation immediately interpretable
- **DCA plan inclusion:** Often overlooked but critical for investors adding money over time
- **Tax efficiency strategy:** Addresses asset location (not just allocation) — a meaningful alpha source for taxable investors
- **Rebalancing trigger rules:** Giving specific rules (e.g., "rebalance when any asset drifts >5% from target") creates discipline
- **IPS format:** A written policy document prevents panic selling and drift from original intent

### Ways to Improve the Prompt
1. **Be exhaustive in "My details":** Age, income, total savings, goals, timeline, risk tolerance, account types, AND existing holdings. The more context, the more tailored the output.
2. **Add specific return goal:** "I need this portfolio to grow to $[X] by [year] from a starting point of $[Y]." This allows the AI to back-calculate required return and assess feasibility.
3. **Specify what you already own:** "I already have $[X] in [SPY/company stock/401K]. Do not duplicate these exposures."
4. **Request factor exposure analysis:** "Identify the factor tilts (value, momentum, quality, size) in the proposed portfolio."
5. **Add a liquidity reserve instruction:** "Include a cash/emergency fund recommendation separate from the investment portfolio."
6. **Request ESG or thematic screening if relevant:** "Exclude sin stocks (tobacco, weapons)" or "Include a clean energy satellite position."

### Additional Resources
- **Vanguard Portfolio Allocation Models** (investor.vanguard.com) — Free, evidence-based allocation frameworks by risk level
- **Portfolio Charts** (portfoliocharts.com) — Visualizes historical performance, drawdowns, and safe withdrawal rates for many portfolio types
- **"A Random Walk Down Wall Street" by Burton Malkiel** — The foundational case for index-based portfolio construction
- **Bogleheads Wiki** (bogleheads.org/wiki) — Extensive free resource on low-cost, evidence-based investing
- **iShares ETF Screener** (ishares.com) — BlackRock's own ETF selection tool with expense ratios and factor exposures

---

## 6. Citadel-Grade Technical Analysis System

### Purpose
This prompt generates a comprehensive technical analysis report covering trend, momentum, volume, chart patterns, and probabilistic trade setups for a single stock. It is structured as a "report card" with a trade plan, modeled after the quantitative trading framework used by hedge funds like Citadel that blend technical signals with statistical models.

Technical analysis is a discipline with well-defined vocabulary and structured frameworks — making it well-suited for AI generation, as the outputs are template-able and verifiable against actual chart data.

### When to Use
**Use when:**
- You've completed fundamental analysis and want to optimize entry/exit timing
- Short-to-medium term trading (days to weeks) where price action matters more than valuation
- Swing trading or momentum strategies where chart patterns are primary drivers
- Setting up conditional alerts (e.g., "alert me when price crosses 200 DMA")
- Cross-checking a fundamental thesis with technical confirmation or contradiction

**Do NOT use when:**
- You are a long-term buy-and-hold investor — timing matters far less over 10+ year horizons
- You need real-time price data — AI does not have live chart access without tools
- The stock has very low volume or is thinly traded — technical signals are unreliable on illiquid stocks
- You expect the AI to "see" the chart — it is generating analysis from trained patterns, not reading your actual chart

### Expected Output
A technical analysis report card containing:
- Trend direction on daily/weekly/monthly timeframes (e.g., "Uptrend on daily, consolidating on weekly")
- Key support levels and resistance levels with specific price points
- Moving average analysis: 50/100/200-day MA positions, golden/death cross signals
- RSI reading with interpretation (overbought/oversold/neutral)
- MACD signal (bullish crossover, bearish divergence, etc.)
- Bollinger Band analysis (bandwidth, price position relative to bands)
- Volume trend (expanding on up days vs down days)
- Chart pattern identification with reliability rating
- Fibonacci retracement levels calculated from recent swing high/low
- Trade plan: entry price, stop-loss, profit target, risk-to-reward ratio
- Overall confidence rating: strong buy / buy / neutral / sell / strong sell

### What the Prompt Does Well
- **Multi-timeframe analysis:** Daily/weekly/monthly framing prevents false signals from a single timeframe
- **Plain-English interpretation request:** Makes the output accessible to non-technical users
- **Risk-to-reward ratio demand:** Forces the AI to calculate whether the setup is worth taking
- **Chart pattern identification:** Adds pattern-recognition value that complements indicator analysis
- **Report card format:** Makes the output scannable and comparable across different stocks

### Ways to Improve the Prompt
1. **Provide current price and recent range:** "Current price is $[X], 52-week high $[Y], 52-week low $[Z]." This dramatically improves accuracy of support/resistance estimates.
2. **Specify the trading timeframe:** "I am a swing trader with a 2-4 week holding period." vs "I day trade on the 15-minute chart." This changes the relevant signals entirely.
3. **Add volume context:** "Average daily volume is [X]M shares." Without this, volume trend analysis lacks a baseline.
4. **Request multiple scenario analysis:** "Provide the technical setup for three scenarios: (1) breaks above resistance, (2) holds support, (3) breaks down below support."
5. **Pair with a real chart tool:** TradingView or Thinkorswim for actual visualization — use this prompt to know what to look for, then verify on the real chart.
6. **Combine with Prompt 4:** Use earnings preview to know when the next catalyst is, then use this prompt to find the technical setup going into that event.

### Additional Resources
- **TradingView** (tradingview.com) — Best free charting platform; validate AI technical analysis here
- **StockCharts.com** — Excellent educational library on every indicator this prompt covers
- **"Technical Analysis of the Financial Markets" by John Murphy** — The definitive textbook on TA
- **Investopedia Technical Analysis Section** — Free, thorough explanations of every indicator mentioned
- **Thinkorswim by TD Ameritrade** — Professional-grade paper trading with full technical indicator suite

---

## 7. Harvard Endowment-Inspired Dividend Strategy

### Purpose
This prompt generates a dividend income portfolio construction plan modeled after endowment fund management principles — specifically Harvard's focus on consistent, inflation-adjusted income generation. It covers stock selection, dividend safety scoring, DRIP compounding projections, tax considerations, and portfolio diversification, structured as a dividend portfolio blueprint.

The Harvard endowment persona emphasizes long-duration thinking and income reliability over capital growth speculation — appropriate framing for dividend investing.

### When to Use
**Use when:**
- Building or optimizing a passive income portfolio for current or near-future income needs
- Approaching or in retirement and prioritizing income over growth
- Seeking to supplement earned income with dividend cash flows
- Learning which metrics (payout ratio, consecutive growth years, safety score) matter most in dividend investing
- Running a DRIP strategy and want to model long-term compounding impact

**Do NOT use when:**
- Your primary objective is capital appreciation — dividend stocks typically underperform growth stocks in bull markets
- You are in a high tax bracket with no tax-advantaged accounts — qualified dividends are taxed less favorably than long-term capital gains in some brackets
- You need current, live dividend yields — AI data may be outdated; verify on dividend tracking sites
- The time horizon is very short (under 3 years) — dividend compounding needs time to work meaningfully

### Expected Output
A dividend portfolio blueprint containing:
- 15-20 stock picks with tickers and current yield
- Safety score (1-10) per stock with brief rationale
- Consecutive dividend growth years (Dividend Aristocrats/Kings criteria)
- Payout ratio per stock with red flags identified
- Monthly income projection table based on stated investment amount
- Sector allocation breakdown (utilities, financials, consumer staples, etc.)
- 5-year dividend growth rate estimates per holding
- DRIP projection: ending value and income after 10 years of reinvestment
- Tax treatment summary (qualified vs ordinary dividends, Roth vs taxable account implications)
- Ranked list from most conservative to most aggressive yield plays

### What the Prompt Does Well
- **DRIP compounding projection:** This is the most underappreciated aspect of dividend investing — showing the 10-year reinvestment effect is genuinely educational
- **Safety scoring:** Forces quality assessment, preventing yield-chasing into dividend traps
- **Monthly income projection:** Personalizes the output and makes the goal tangible
- **Payout ratio red flag analysis:** Critical for identifying unsustainable dividends before a cut
- **Ranked list from safest to most aggressive:** Allows users to calibrate their own risk appetite within the recommendations

### Ways to Improve the Prompt
1. **Specify your income goal in dollar terms:** "I need $2,500/month in dividend income from a $600K portfolio." This gives the AI a concrete yield target to hit.
2. **Add constraints on minimum yield:** "Only include stocks with a minimum 2.5% yield and 5+ consecutive years of dividend growth."
3. **Request Dividend Aristocrat/King filtering:** "Preference for Dividend Aristocrats (25+ years of growth) or Dividend Kings (50+ years)."
4. **Specify sector exclusions:** "Exclude MLP and REIT structures if I'm investing in a taxable account" (due to tax complexity).
5. **Add inflation adjustment to the projection:** "Show the real (inflation-adjusted) purchasing power of the dividend income over 10 years assuming 3% inflation."
6. **Request a dividend cut stress test:** "Identify the 3 stocks most at risk of a dividend cut in a recession and suggest replacements."

### Additional Resources
- **Dividend.com** — Free dividend safety scores, history, and yield data
- **Simply Safe Dividends** (simplysafedividends.com) — Best-in-class dividend safety scoring (paid, but highly regarded)
- **DRIP Returns Calculator** (dripreturnscalculator.com) — Validate the AI's DRIP projections with real data
- **"The Ultimate Dividend Playbook" by Josh Peters** — Foundational text on dividend investing philosophy
- **Seeking Alpha Dividend Screener** — Community analysis of dividend safety and growth outlook

---

## 8. Bain-Style Competitive Advantage Analysis

### Purpose
This prompt generates a sector-level competitive landscape report modeled after management consulting deliverables. Rather than analyzing a single stock, it maps the competitive dynamics of an entire industry — identifying which company has the most durable competitive advantage and why. The output informs stock selection by understanding competitive positioning before looking at valuation.

Bain & Company is specifically known for competitive strategy work (they co-developed Net Promoter Score and are famous for market share analysis), making the persona highly appropriate for this type of analysis.

### When to Use
**Use when:**
- Evaluating an entire sector before selecting the best individual stock within it
- Understanding why one company in a sector should trade at a premium to peers
- Building a thesis around a sector rotation or thematic investment (e.g., AI infrastructure, biotech, clean energy)
- Learning competitive analysis frameworks (Porter's Five Forces, moat analysis) applied to real companies
- Preparing for a deep-dive into a new industry where you have limited existing knowledge

**Do NOT use when:**
- You already know which stock you want — skip to Prompt 2 (DCF) or Prompt 6 (Technical) instead
- The sector is highly fragmented (thousands of small players) — the "top 5-7 competitors" structure won't work
- You need proprietary market research — AI-generated competitive analysis reflects publicly available information, not primary research
- The sector has changed rapidly recently (e.g., post-disruption) and AI training data may be stale

### Expected Output
A competitive strategy deck summary containing:
- Market cap comparison table for top 5-7 competitors
- Revenue and profit margin comparison table
- Moat analysis per company across four dimensions: brand, cost advantage, network effects, switching costs
- Market share trend data over 3 years (who is gaining/losing)
- Management quality ratings with capital allocation evidence (ROIC trends, buyback history, M&A track record)
- R&D spending comparison with innovation pipeline assessment
- Top 3 sector threats (regulatory, technological disruption, macroeconomic)
- SWOT analysis for the top 2 companies
- Single best stock pick with written rationale
- 3-5 catalysts that could move the recommended stock in the next 12 months

### What the Prompt Does Well
- **Moat framework with four dimensions:** Brand/cost/network/switching is a clean, structured framework that produces consistent, comparable output
- **Management quality through capital allocation:** This is a sophisticated quality metric often overlooked by retail investors
- **SWOT for top 2 only:** Limiting SWOT to 2 companies prevents the output from becoming bloated
- **Single best pick with rationale:** Forces a conclusion rather than presenting options without guidance
- **Catalyst identification:** Bridges the gap between analysis and investment timing

### Ways to Improve the Prompt
1. **Specify the timeframe of interest:** "I'm looking for a 2-3 year holding period" vs "I'm looking for a 6-month tactical trade." This changes which catalysts and competitors matter most.
2. **Add a valuation filter:** "After identifying the best company, note whether it is currently cheap, fairly valued, or expensive relative to sector peers."
3. **Include emerging disruptors:** "Identify any private company or emerging technology that could disrupt the incumbents in this sector within 5 years."
4. **Request Porter's Five Forces:** Adding "Apply Porter's Five Forces framework to assess overall sector attractiveness" adds a rigorous structural overlay.
5. **Ask for international comparison:** "Include one international competitor for global context on how US companies compare globally."
6. **Pair with Prompt 2:** After identifying the best company here, run a full DCF valuation on it using Prompt 2.

### Additional Resources
- **IBISWorld Industry Reports** — Paid but comprehensive sector competitive analysis
- **CB Insights Industry Analyst Reports** — Free and paid sector disruption analysis
- **"Competitive Strategy" by Michael Porter** — The foundational text behind every framework this prompt uses
- **"The Outsiders" by William Thorndike** — Deep dive on capital allocation as a management quality metric
- **Stratechery** (stratechery.com) — Ben Thompson's technology sector competitive analysis (free weekly)

---

## 9. Renaissance Technologies Pattern Finder

### Purpose
This prompt generates a quantitative research memo focused on identifying statistical patterns, seasonal anomalies, insider activity, institutional flows, and options signals for a specific stock. It is modeled after the data-driven, pattern-seeking approach of Renaissance Technologies — arguably the most successful quant hedge fund in history.

The prompt is distinct from fundamental analysis: it focuses on *behavioral and statistical edges* (what actually happens vs what should theoretically happen) rather than valuation or cash flows.

### When to Use
**Use when:**
- You know the company fundamentally and want to understand *when* to act
- You're a systematic or semi-systematic trader who values statistical evidence over narrative
- Looking for short interest squeeze setups, insider accumulation signals, or unusual options activity
- Building a thesis around seasonal patterns (e.g., "tax loss harvesting in December, January effect")
- Researching pre-earnings behavior or post-earnings drift patterns for a recurring trade

**Do NOT use when:**
- Your investment is purely long-term — statistical edges over days/weeks are noise at 10-year horizons
- The stock is new to the market (IPO) or has changed business model significantly — historical patterns don't apply
- You expect precise statistical outputs — AI cannot run actual backtests; it describes known patterns from training data
- You're looking for a comprehensive valuation — this prompt is about behavioral edges, not intrinsic value

### Expected Output
A quantitative research memo containing:
- Seasonal calendar showing best and worst months historically for this stock
- Day-of-week performance pattern if statistically significant
- Correlation data between this stock and major macro events (Fed meetings, CPI releases, NFP)
- Insider transaction summary from recent SEC filings (Form 4s)
- Institutional ownership trend (13F data interpretation)
- Short interest ratio and days-to-cover with squeeze probability assessment
- Unusual options activity flags (high put/call ratio, unusual sweep orders, etc.)
- Pre-earnings run pattern and post-earnings drift pattern analysis
- Sector rotation signal analysis (which macro environments favor this stock)
- Statistical edge summary: the 2-3 clearest, most durable edges identified

### What the Prompt Does Well
- **Breadth of signal types:** Covers 10 distinct categories of patterns, creating a comprehensive edge map
- **Insider/institutional focus:** These are legally disclosed informational advantages that retail investors often ignore
- **Short squeeze analysis:** Highly relevant for certain stocks and market environments
- **Pre/post-earnings pattern specificity:** This is one of the most repeatable patterns in markets and valuable to understand
- **Quantitative memo format:** Positions findings as data-driven rather than speculative

### Ways to Improve the Prompt
1. **Specify the time period precisely:** "I care about patterns over the last 5 years, with emphasis on post-2020 behavior." Avoids irrelevant historical data from structurally different market regimes.
2. **Add your specific holding context:** "I currently hold a long position. I'm specifically looking for exit timing signals and risk factors."
3. **Request statistical significance framing:** "For each pattern, estimate whether it appears statistically significant or might be random noise."
4. **Ask for data source recommendations:** "For each pattern category, suggest the best free or low-cost data source to verify this with real data."
5. **Combine with live data tools:** AI can describe patterns; tools like Finviz, Unusual Whales, or OpenInsider can verify them with current data.
6. **Pair with Prompt 6:** After finding the key patterns and timing signals here, use the Technical Analysis prompt to identify price levels where those signals become actionable.

### Additional Resources
- **OpenInsider** (openinsider.com) — Free real-time SEC Form 4 insider transaction data
- **Finviz.com** — Free stock screener with short interest, institutional ownership, and insider data
- **Unusual Whales** (unusualwhales.com) — Options flow and unusual activity tracker
- **Koyfin** (koyfin.com) — Institutional ownership trends from 13F filings
- **Quantpedia** (quantpedia.com) — Database of documented quantitative trading strategies with academic citations

---

## 10. McKinsey-Level Macro Impact Assessment

### Purpose
This prompt generates a top-down macroeconomic analysis showing how current economic conditions (interest rates, inflation, GDP, dollar, employment) affect a specific portfolio. It bridges the gap between macro commentary (which is abundant) and portfolio-level action (which is rarely spelled out). Structured as an executive strategy briefing, it culminates in a specific action plan.

McKinsey's Global Institute is specifically focused on economic research for institutional decision-makers — making the persona appropriate for generating structured, action-oriented macro analysis rather than generic economic commentary.

### When to Use
**Use when:**
- Major macro events are occurring (Fed rate changes, inflation spikes, recession fears) and you want to understand the portfolio impact
- You're questioning whether your portfolio is positioned correctly for the current economic cycle
- Making a sector rotation decision and want macro support for the thesis
- Preparing for a major life event (large withdrawal, new investment) and want macro timing context
- Building macro literacy to understand how economic data releases affect your holdings

**Do NOT use when:**
- You want individual stock analysis — this is top-down macro, not bottom-up stock picking
- Your portfolio is very simple (e.g., target-date fund) — macro positioning is handled automatically
- You need precise economic forecasts — AI outputs are frameworks, not Bloomberg or IMF forecasts
- You're a very short-term trader (days) — macro trends operate over months to years

### Expected Output
An executive macro strategy briefing containing:
- Interest rate environment analysis and its differential impact on growth vs value holdings
- Inflation trajectory analysis with sector-level winners/losers
- GDP growth forecast interpretation and earnings implications
- Dollar strength analysis for international vs domestic exposure
- Employment/consumer spending trend analysis and implications
- Fed policy outlook with probability-weighted scenarios for next 6-12 months
- Global risk register: geopolitical, trade, supply chain threats ranked by portfolio relevance
- Sector rotation recommendation mapped to current cycle position
- Specific portfolio changes with rationale (e.g., "reduce long-duration bonds, increase energy exposure")
- Timeline of when each macro factor is likely to become a near-term market mover

### What the Prompt Does Well
- **Connects macro to portfolio action explicitly:** Most macro commentary stops at description; this prompt demands actionable recommendations
- **Timeline inclusion:** Asking *when* forces the AI to prioritize signals rather than treating all risks as equally immediate
- **Sector rotation framework:** Aligns portfolio positioning to economic cycle stage (expansion, peak, contraction, trough)
- **Specific adjustments demanded:** "Specific portfolio adjustments I should consider right now" prevents vague non-answers
- **Dual focus (global + domestic):** Including geopolitics and trade wars alongside domestic macro is comprehensive

### Ways to Improve the Prompt
1. **Include current macro data:** "Current Fed funds rate is [X]%, CPI is [Y]% YoY, 10-year Treasury yield is [Z]%." This grounds the analysis in actual current data rather than AI estimates.
2. **Specify your portfolio holdings:** The more detailed your holdings list, the more specific the impact analysis. Generic holdings produce generic advice.
3. **Add a time horizon for macro concerns:** "I'm primarily concerned about the next 6 months vs next 3 years." Short and long-term macro concerns differ substantially.
4. **Request probability-weighted scenarios:** "Give me base, bull, and bear macro scenarios with estimated probabilities and portfolio impact for each."
5. **Ask for historical analogues:** "What historical period most closely resembles current macro conditions, and how did markets behave then?"
6. **Combine with Prompt 3:** Use the Bridgewater Risk Analysis to identify your portfolio's specific vulnerabilities, then use this McKinsey prompt to understand the macro drivers behind those risks.

### Additional Resources
- **FRED (Federal Reserve Economic Data)** (fred.stlouisfed.org) — The authoritative free source for all macroeconomic data referenced in this prompt
- **JP Morgan's Guide to the Markets** (am.jpmorgan.com) — Published quarterly, visually-rich macro data and market analysis
- **BCA Research** (bcaresearch.com) — Institutional-grade macro research (paid, but free previews available)
- **"The Intelligent Investor" by Benjamin Graham** — Chapter on market fluctuations and macro-market cycles remains essential reading
- **Ray Dalio's "How the Economic Machine Works"** — Free 30-minute video explaining the macro framework that underlies Bridgewater's approach

---

---

## Series B — Personal Finance & Wealth Planning Prompts
*Source: evolving.ai (TikTok, February 20)*
*Focus: Holistic personal finance — diagnostics, retirement, tax, debt, insurance, estate, real estate*

---

## 11. Goldman Sachs Wealth Diagnostic

### Purpose
This prompt generates a comprehensive personal financial health diagnostic — a full balance sheet, cash flow analysis, and 10-dimension assessment of where someone stands financially. Unlike the Series A prompts which focus on investing and markets, this prompt zooms out to the entire financial picture: net worth, debt, insurance, retirement readiness, taxes, and estate planning, all scored and prioritized into an action plan.

The "Goldman Sachs Private Wealth" persona is calibrated for ultra-high-net-worth clients ($10M+), which signals the AI to use institutional-grade thoroughness and analytical rigor rather than generic personal finance advice.

### When to Use
**Use when:**
- You've never done a comprehensive financial review and want a starting baseline
- Life has changed significantly (marriage, divorce, new job, inheritance, new child) and you need a reset
- You sense your finances are disorganized but don't know where to start prioritizing
- You want one output that covers everything before deciding which specialist (CPA, CFP, estate attorney) to hire
- Preparing for a meeting with a financial advisor and want to arrive with a structured self-assessment

**Do NOT use when:**
- You need legal advice on estate documents — AI output is a framework, not a legal instrument
- You want detailed investment portfolio construction — use Prompts 5 or 13 for that
- Your finances are genuinely complex (multiple businesses, international assets, trusts) — the framework won't capture the nuance
- You're unwilling to provide detailed financial inputs — vague inputs produce a generic checklist, not a diagnostic

### Expected Output
A financial diagnostic report containing:
- Personal balance sheet (assets vs liabilities = net worth)
- Monthly cash flow statement with savings rate percentage
- Emergency fund adequacy rating (months of expenses covered vs target)
- Debt priority list ranked by interest rate with payoff recommendations
- Insurance gap analysis (over/under-insured assessment per category)
- Portfolio allocation vs age-appropriate benchmark
- Retirement readiness score with projected shortfall or surplus
- Tax efficiency rating with top missed strategies
- Estate planning status checklist (which documents exist vs missing)
- Overall financial health score (1-100) with top 3 prioritized action items

### What the Prompt Does Well
- **10-dimension breadth:** Covers every major personal finance category in one output — rare for a single prompt
- **Scoring system:** The 1-100 financial health score creates a memorable anchor and motivator
- **Prioritized action plan:** "Top 3 actions to improve it" prevents overwhelm from a 10-category analysis
- **Scorecard format request:** Structures the output for quick executive review before diving into details
- **Wealth advisor framing:** Signals the AI toward comprehensive, professional-grade analysis vs generic budgeting advice

### Ways to Improve the Prompt
1. **Provide all 8 financial dimensions in your input:** Age, income, expenses, debts, savings, investments, insurance, and goals. Skipping any category degrades the corresponding section significantly.
2. **Add a "biggest financial worry" field:** "My primary financial concern right now is [X]." This helps the AI weight the prioritized action plan appropriately.
3. **Request a 12-month roadmap:** "After the diagnostic, provide a month-by-month action plan for the first year."
4. **Ask for a gap-to-goal analysis:** "For each dimension, show the gap between my current state and the recommended target."
5. **Specify life stage context:** "I am [early career / mid-career / pre-retirement / in retirement]." This calibrates benchmarks correctly.
6. **Use as a gateway prompt:** This diagnostic is ideal as the first prompt — its output tells you which of the other 19 prompts to use next.

### Additional Resources
- **Personal Capital / Empower** (empower.com) — Free net worth and cash flow tracking that mirrors this diagnostic
- **CFP Board Financial Planning Process** — The professional framework this prompt approximates
- **"I Will Teach You to Be Rich" by Ramit Sethi** — Practical personal finance system covering most of these dimensions
- **CFPB Financial Well-Being Scale** — Free validated tool for measuring financial health (research-grade)
- **NerdWallet Financial Health Score** — Free simplified version of the scoring concept in this prompt

---

## 12. Vanguard Retirement Planning Calculator

### Purpose
This prompt generates a complete, mathematically grounded retirement plan — from target retirement number calculation through Social Security timing, withdrawal strategy, and healthcare cost projection. It is structured as a Vanguard-style planning report with projection tables and milestones, covering both the accumulation phase (saving) and decumulation phase (spending in retirement).

Vanguard's persona is ideal here — they manage over $9 trillion and are the industry standard for retirement planning education and low-cost index investing.

### When to Use
**Use when:**
- You want to know your specific retirement number and whether you're on track
- You're confused about the optimal order of account contributions (401K vs IRA vs Roth vs HSA)
- Approaching retirement and need to think through withdrawal sequencing and Social Security timing
- Starting your career and want a complete savings roadmap from now until retirement
- You've had a major income change and need to recalculate your retirement trajectory

**Do NOT use when:**
- You have a pension — the framework is built around market-based portfolios; pension integration requires different modeling
- You need actuarial-precision calculations — AI projections are illustrative, not guaranteed
- Your retirement involves significant real estate, business sale, or inheritance — these need custom modeling
- You need state-specific retirement tax rules — verify output against your state's specific treatment of retirement income

### Expected Output
A retirement planning report containing:
- Target retirement portfolio size (the "retirement number") with calculation methodology
- Monthly savings required starting today to reach that number
- Glide path allocation table (e.g., stocks/bonds by decade from now to age 90)
- Annual account contribution strategy table (401K, IRA, Roth IRA, HSA, taxable)
- Employer match optimization analysis (free money capture assessment)
- Social Security timing scenarios (claim at 62 vs 67 vs 70 with lifetime benefit comparison)
- Withdrawal strategy (4% rule, bucket strategy, or Roth conversion ladder)
- Inflation adjustment showing real vs nominal retirement number
- Healthcare cost estimate in retirement (a frequently underestimated line item)
- Month-by-month income source breakdown in retirement (Social Security + portfolio + other)

### What the Prompt Does Well
- **Social Security timing comparison:** This is one of the highest-impact retirement decisions and is rarely modeled well by retail investors — including it is excellent
- **Healthcare cost projection:** Most retirement plans dramatically underestimate this — explicitly requesting it is valuable
- **Withdrawal strategy demand:** Covers both the accumulation question (how much to save) AND the decumulation question (how to spend it) — most retirement prompts only do the former
- **Milestone tables by age:** Creates actionable checkpoints rather than a single terminal number
- **Account strategy specificity:** Breaking down contributions by account type optimizes both returns and taxes

### Ways to Improve the Prompt
1. **Provide your current retirement savings:** "I currently have $[X] in 401K, $[Y] in IRA, $[Z] in taxable." This allows the AI to calculate actual trajectory vs generic starting-from-zero projections.
2. **Specify your expected Social Security benefit:** "My estimated Social Security benefit at 67 is $[X]/month per SSA.gov." This is the single most important input for the income planning section.
3. **Add your expected retirement spending:** "I need $[X]/month in today's dollars to maintain my lifestyle." Retirement number calculations are only as good as the spending assumption.
4. **Request a Monte Carlo interpretation:** "Describe what a Monte Carlo simulation would likely show for a 90% success rate withdrawal strategy."
5. **Add a "what if I retire early" scenario:** Include "Also show what changes if I retire at [age X] instead of [target age]."
6. **Pair with Prompt 14 (Tax Optimization):** Roth conversion strategies and tax-efficient withdrawal sequencing are heavily intertwined with retirement planning.

### Additional Resources
- **SSA.gov My Social Security** — Get your actual Social Security benefit estimate
- **Vanguard Retirement Nest Egg Calculator** (vanguard.com) — Validate AI outputs with Vanguard's own tool
- **FIRECalc** (firecalc.com) — Free historical success-rate calculator for retirement portfolios
- **"The Simple Path to Wealth" by JL Collins** — Straightforward Vanguard-aligned retirement philosophy
- **Fidelity Retirement Score** (fidelity.com) — Free tool that mirrors many elements of this prompt

---

## 13. Morgan Stanley Investment Portfolio Architect

### Purpose
This prompt is distinct from Prompt 5 (BlackRock Portfolio Construction) in an important way: it emphasizes a wealth management context (high-net-worth client with specific goals, income needs, and restrictions) rather than a systematic asset allocation framework. It adds income layer vs growth layer separation, tax-location optimization, and fund selection rationale — making it more suitable for investors with larger, more complex portfolios who want to understand *why* each holding exists in their portfolio.

### When to Use
**Use when:**
- You have a substantial portfolio ($250K+) and want professional-grade structure with rationale
- Your portfolio has evolved organically and lacks intentional income vs growth separation
- You have both taxable and tax-advantaged accounts and want to optimize which assets go where
- You want specific fund picks with expense ratios and selection reasoning, not just asset class targets
- You have income needs from the portfolio (near-retirement or supplemental income goals)

**Do NOT use when:**
- You're early-stage with limited assets — Prompt 5 (BlackRock) is better suited for building from scratch
- You want pure factor/quantitative analysis — this is a wealth management framework, not a quant model
- You have restrictions (ESG, sector exclusions, concentrated stock positions) that aren't reflected in the input — always include these in your profile
- You need specific tax-loss harvesting execution — this prompt designs structure, not real-time tax tactics

### Expected Output
A Morgan Stanley-style investment policy statement containing:
- Asset allocation table with exact percentages across US stocks, international stocks, bonds, real estate, alternatives
- ETF/fund selection table: ticker, expense ratio, category, and selection rationale for each holding
- Core/satellite breakdown with stability and growth layers clearly labeled
- Risk profile assessment matching portfolio aggressiveness to actual financial situation
- Diversification stress-test (no single stock/sector/region dominates)
- Income layer analysis (dividend yield, bond yield, expected cash flow)
- Growth layer analysis (expected capital appreciation above benchmark)
- Rebalancing trigger rules and calendar
- Tax-location map (which holdings belong in taxable vs Roth vs traditional accounts)
- Benchmark specification with tracking methodology

### What the Prompt Does Well
- **Income vs growth layer separation:** This is how professional portfolio managers think — most retail investors don't make this distinction explicit
- **Tax-location optimization:** Often worth 0.5-1% annually in after-tax returns — explicitly requesting it is high-value
- **Fund selection rationale:** Demanding "why each was selected" prevents a generic ETF list and forces quality reasoning
- **Risk profiling beyond emotion:** "Match my portfolio aggressiveness to my actual financial situation, not just my emotions" is an excellent constraint that prevents overconfidence-driven allocation
- **Benchmark specification:** Tells you how to measure whether the portfolio is actually working

### Ways to Improve the Prompt
1. **Be specific about investable assets vs total net worth:** "I have $[X] to invest, separate from my home equity and retirement accounts."
2. **List existing holdings:** "I currently hold [SPY, AAPL, BRK.B] and prefer not to liquidate these." Prevents duplicate exposure recommendations.
3. **Specify income requirement:** "I need $[X]/month in portfolio income." This calibrates the income layer size.
4. **Add a concentrated stock position flag:** If you have RSUs, company stock, or a large single-position, note it explicitly.
5. **Request a transition plan:** "I'm currently 100% in cash/target date fund. Show me how to implement this allocation over 6 months."
6. **Pair with Prompt 14 (Tax Optimization):** Tax-location strategy in this prompt directly connects to the broader tax strategy in Prompt 14.

### Additional Resources
- **Morningstar Portfolio X-Ray** — Free tool to check actual diversification vs what you think you own
- **ETF.com** — ETF comparison, expense ratios, and factor exposure analysis
- **"The Bogleheads' Guide to Investing"** — Evidence-based portfolio construction philosophy
- **PWL Capital Model Portfolios** (pwlcapital.com) — Free, publicly shared institutional-quality model portfolios
- **iShares Core Series** — BlackRock's low-cost building block ETFs used by most model portfolios

---

## 14. Deloitte Tax Optimization Strategist

### Purpose
This prompt generates a comprehensive tax minimization strategy memo covering 10 distinct legal tax reduction levers — from bracket management and retirement contributions through business deductions, capital gains timing, charitable giving, HSA strategy, and estate/gift planning. It is modeled after the strategic tax advisory work done by Big Four accounting firms for high-income clients, not the compliance-focused work of a typical CPA.

The distinction is critical: compliance = filing correctly. Optimization = reducing what you legally owe. This prompt focuses entirely on optimization.

### When to Use
**Use when:**
- You're a high-income earner ($150K+) who suspects you're overpaying in taxes
- You're a business owner with deduction opportunities you may not be fully utilizing
- Approaching year-end and want to take tax actions before December 31
- You've had a major income event (bonus, stock vesting, business sale) requiring tax planning
- You want to understand the full menu of legal tax strategies before meeting with a CPA

**Do NOT use when:**
- You need to actually file your taxes — this is strategy, not compliance
- Your situation involves complex international tax (PFIC, FATCA, foreign trusts) — requires specialized counsel
- You want guaranteed savings numbers — AI estimates are illustrative; verify with a licensed CPA
- You're in a very simple tax situation (W-2 only, standard deduction, no investments) — most strategies won't apply

### Expected Output
A tax planning memo containing:
- Current estimated tax liability under existing approach
- Tax bracket analysis with specific income-shifting strategies
- Retirement account contribution optimization (which accounts, how much, Roth conversion analysis)
- Tax-loss harvesting plan with specific timing guidance
- Business deduction checklist with estimated savings per category
- Income timing strategy (accelerate vs defer income based on rate comparison)
- Capital gains holding period analysis (short vs long-term tax rate differential)
- Charitable giving strategies with estimated after-tax cost comparison
- HSA maximization plan with triple-tax-advantage calculation
- Estate/gift tax annual exclusion and trust strategy overview
- Implementation calendar: what to do before year-end vs what to do annually

### What the Prompt Does Well
- **"Strategies most accountants never mention"** framing: Biases the AI toward advanced/underutilized strategies rather than generic advice
- **Estimated savings per strategy demand:** Forces quantification rather than vague suggestions
- **Year-round calendar format:** Converts a one-time analysis into a recurring framework
- **HSA as stealth retirement account:** This is genuinely underutilized and valuable to highlight
- **Business owner deductions inclusion:** Covers a high-value category often absent from personal finance prompts

### Ways to Improve the Prompt
1. **Specify your marginal tax rate:** "I'm in the [22% / 24% / 32% / 37%] federal bracket and [X%] state bracket." This is the single most important input for strategy relevance.
2. **List your income sources explicitly:** W-2, 1099, K-1, rental income, capital gains — each has different optimization strategies.
3. **Add your business structure:** Sole proprietor, S-corp, LLC, C-corp — dramatically changes the deduction landscape.
4. **Include your current deductions:** "I currently itemize/take standard deduction and contribute $[X] to retirement accounts."
5. **Request a "low-hanging fruit" priority ranking:** "Rank strategies by ease of implementation and estimated savings impact."
6. **Always verify with a CPA:** AI can generate the strategy menu; a licensed CPA confirms applicability to your specific situation and executes correctly.

### Additional Resources
- **IRS Publication 17** — Comprehensive tax guide; free and authoritative
- **Kitces.com** — Financial planning blog with excellent advanced tax strategy content
- **"Tax-Free Wealth" by Tom Wheelwright** — Business-focused tax reduction strategies
- **TurboTax TaxCaster** — Free tool to estimate tax liability under different scenarios
- **NAPA (National Association of Plan Advisors)** — Resource for retirement plan tax strategies

---

## 15. JPMorgan Debt Elimination Engineer

### Purpose
This prompt generates a complete, mathematically precise debt elimination roadmap — comparing payoff strategies, calculating true interest costs, modeling the impact of extra payments, and identifying refinancing/consolidation opportunities. Unlike generic "pay off debt" advice, this prompt treats debt elimination as an engineering problem with optimization variables (method, payment amount, timing, refinancing) and quantifiable outcomes.

The JPMorgan Private Bank persona signals aggressive, sophisticated debt management rather than conservative budgeting advice.

### When to Use
**Use when:**
- You have multiple debts and aren't sure the optimal order or strategy to pay them off
- You want to see the actual math: how much interest you'll pay under current vs optimized plans
- Deciding between avalanche, snowball, consolidation, or balance transfer strategies
- You have a lump sum and want to know the highest-impact way to apply it
- Motivation is flagging and you want a milestone-based plan to maintain momentum

**Do NOT use when:**
- You have only one debt — strategy comparison adds no value; just pay it down aggressively
- Your debt situation involves bankruptcy consideration — requires legal counsel, not AI optimization
- You're evaluating whether to take on new debt (mortgage, business loan) — this prompt is payoff-focused
- You need current refinancing rates — AI doesn't have live rate data; verify on Bankrate or Credible

### Expected Output
A debt elimination roadmap containing:
- Complete debt inventory table (balance, rate, minimum payment, payoff date for each)
- Avalanche vs Snowball comparison with exact payoff dates and total interest paid under each
- Month-by-month payment allocation schedule showing which debt gets paid when
- Extra payment sensitivity table ($100/$250/$500 extra → how many months/years saved)
- Total interest comparison: current plan vs optimized plan (a motivating dollar amount)
- Refinancing analysis per debt with rate threshold where refinancing makes sense
- Consolidation analysis with break-even calculation
- Balance transfer strategy with 0% APR window and required payment to clear before rate expires
- 3-5 realistic income acceleration ideas specific to the user's situation
- Milestone map with celebration rewards at each debt payoff

### What the Prompt Does Well
- **Strategy comparison with exact math:** Avalanche vs snowball is often debated without doing the actual arithmetic — this prompt demands it
- **Extra payment sensitivity table:** Highly motivating — showing that $100/month extra eliminates years of debt is powerful
- **Income acceleration ideas:** Most debt payoff content ignores the income side; this prompt explicitly addresses it
- **Milestone celebration plan:** Behavioral finance research confirms reward-based systems improve follow-through
- **Debt-free countdown tracker:** Creates a visual goal that sustains motivation over a multi-year payoff journey

### Ways to Improve the Prompt
1. **Provide complete debt data:** For each debt: balance, interest rate (APR), minimum payment, and type (credit card, student loan, auto, mortgage). Incomplete data produces incomplete analysis.
2. **Add your monthly budget surplus:** "After all expenses, I have $[X]/month available for debt payoff." This is the critical constraint for calculating payoff timelines.
3. **Specify any upcoming lump sums:** "I expect a $[X] tax refund / bonus in [month]." This allows the plan to incorporate windfall allocation.
4. **Flag any debts with prepayment penalties:** Some auto loans and mortgages penalize early payoff — note these explicitly.
5. **Request a "debt snowflake" section:** Small, irregular extra payments from daily savings that add up over time.
6. **Pair with Prompt 14 (Tax Optimization):** Student loan interest deduction, mortgage interest deduction, and business debt interest are all tax-deductible; the tax prompt informs which debts are "cheaper" after tax.

### Additional Resources
- **Undebt.it** (undebt.it) — Free tool that runs the exact avalanche vs snowball comparison this prompt produces
- **Bankrate Debt Payoff Calculator** — Validate AI timelines with this live tool
- **"The Total Money Makeover" by Dave Ramsey** — The canonical snowball method framework
- **Credible / LendingTree** — Live refinancing rate comparison for actual implementation
- **NFCC (National Foundation for Credit Counseling)** — Free and low-cost debt counseling for complex situations

---

## 16. Charles Schwab Emergency Fund and Cash Strategy

### Purpose
This prompt generates a comprehensive cash management system — covering emergency fund sizing, account selection, the cash tier hierarchy (immediate/30-day/90-day access), sinking funds for predictable expenses, automated savings architecture, and the cash vs invest decision framework. Most personal finance advice treats emergency funds as a single number ("save 3-6 months"); this prompt treats cash management as a system with multiple layers.

Charles Schwab's persona is appropriate — they are known for bank-grade cash management tools (high-yield checking, automated investing) and financial planning education.

### When to Use
**Use when:**
- You don't have a clear emergency fund or it's underfunded
- Your cash is sitting in a low-yield account and you want to optimize interest income
- You often overdraft or run into "money emergencies" that feel unpredictable but are actually predictable
- You want to set up an automated savings system that runs without constant attention
- You're deciding between saving more cash vs investing more and need a framework

**Do NOT use when:**
- Your cash management is already well-optimized — this prompt adds most value to people earlier in their financial journey
- You need investment advice — this prompt is explicitly about cash and liquid savings
- You want specific current APY rates — AI data may be stale; always verify on Bankrate or NerdWallet
- You're in a financial emergency right now — this is a planning prompt, not crisis management

### Expected Output
A cash management plan containing:
- Emergency fund target in exact dollars (based on expenses, income stability, dependents)
- Savings acceleration timeline (month-by-month plan to reach target in 6-12 months)
- Account type recommendation (HYSA, money market, T-bills) with pros/cons for each tier
- Tier system description: Tier 1 (immediate access), Tier 2 (30-day), Tier 3 (90-day)
- Sinking fund list with monthly contribution amounts for each predictable expense category
- Automated transfer schedule (amounts, dates, source and destination accounts)
- Cash vs invest decision framework (when adding to emergency fund beats investing)
- Opportunity fund concept and sizing recommendation
- Cash flow calendar mapping income and expense timing to specific dates
- Overdraft elimination strategy

### What the Prompt Does Well
- **Three-tier cash architecture:** This is genuinely sophisticated and rarely taught in personal finance — it optimizes liquidity while maximizing yield
- **Sinking fund inclusion:** Converts "surprise" expenses (car repair, medical) into planned expenses — a significant stress reducer
- **Automated savings system:** Behavioral automation is one of the highest-ROI financial interventions
- **Opportunity fund concept:** Separates "emergency reserves" from "opportunistic capital" — prevents dipping into emergency funds for investments
- **Cash flow calendar:** Mapping income/expenses to specific dates prevents overdrafts without requiring complex budgeting

### Ways to Improve the Prompt
1. **Provide income timing details:** "I get paid on [dates]. My largest bills are due on [dates]." This makes the cash flow calendar actionable.
2. **List your irregular expenses:** "I spend ~$[X] annually on [car maintenance / medical / home repairs / travel]." This calibrates sinking fund amounts.
3. **Specify income stability:** "My income is [very stable W-2 / variable 1099 / seasonal]." Job stability is the primary variable in emergency fund sizing.
4. **Add family size and dependents:** More dependents = larger emergency fund target.
5. **Request HYSA recommendations with current rates:** Note that AI rates are likely stale — append "recommend account types and suggest I verify current APY on Bankrate before opening."
6. **Pair with Prompt 12 (Vanguard Retirement):** The "cash vs invest" decision directly interfaces with retirement contribution prioritization.

### Additional Resources
- **Bankrate High-Yield Savings Comparison** — Current APY rates for HYSA account selection
- **NerdWallet Best High-Yield Savings Accounts** — Independent comparison with accessibility ratings
- **"The Automatic Millionaire" by David Bach** — The foundational text on automated savings systems
- **Marcus by Goldman Sachs / Ally / SoFi** — Three consistently top-ranked HYSA providers
- **YNAB (You Need a Budget)** — Software tool that operationalizes the cash flow calendar concept

---

## 17. Northwestern Mutual Insurance Audit

### Purpose
This prompt generates a comprehensive insurance coverage review across all major insurance categories — life, health, disability, auto, home, and umbrella liability — with a focus on identifying both gaps (underinsured risks) and waste (overpaying for unnecessary coverage). Most people never systematically audit their insurance; they just pay premiums until a life event forces a review.

Northwestern Mutual's persona is calibrated for comprehensive insurance planning — they are one of the largest insurance companies and known for whole-of-life financial protection planning.

### When to Use
**Use when:**
- You haven't reviewed your insurance coverage in 2+ years
- A major life event has occurred (marriage, divorce, new child, home purchase, income change)
- You suspect you're overpaying for coverage you don't need
- You've never had disability insurance reviewed or don't have it at all
- You want to understand whether whole life vs term life makes sense for your situation

**Do NOT use when:**
- You need actual policy quotes — AI cannot provide real pricing; use independent brokers or comparison sites
- You've just had a claim — this is planning, not claims handling
- Your insurance needs are highly specialized (aviation, marine, professional liability) — requires specialty brokers
- You need legal interpretation of existing policy language — requires a licensed insurance attorney

### Expected Output
An insurance review document containing:
- Life insurance needs calculation (income replacement + debt coverage + dependent support)
- Term vs whole life comparison over 20 years with actual cost differential
- Health insurance plan optimization (deductible, premium, HSA eligibility assessment)
- Disability insurance adequacy check (short-term vs long-term, own-occupation definition)
- Auto and home coverage comparison vs recommended minimums with savings opportunities
- Umbrella liability assessment with coverage amount recommendation
- Coverage gap map (risks with no current insurance protection)
- Beneficiary audit checklist (which accounts/policies need updates)
- Premium reduction strategies (bundling, deductible adjustments, credit score impact)
- Annual review calendar with triggers for coverage reassessment

### What the Prompt Does Well
- **Gap identification:** Finding what you're NOT covered for is often more valuable than optimizing existing coverage
- **Term vs whole life cost comparison:** This is a high-stakes decision where the math is rarely done — requiring it is excellent
- **Disability insurance inclusion:** Statistically the most underinsured risk for working-age adults — it's the right call to include
- **Premium optimization without reducing coverage:** Frames cost-cutting constructively rather than just "cancel policies"
- **Annual review calendar:** Insurance coverage needs change with life events; a trigger-based review system prevents coverage drift

### Ways to Improve the Prompt
1. **List all current policies with premium amounts:** Type, insurer, coverage amount, and annual premium for each. Without this, gap analysis is generic.
2. **Include dependents and income details:** Life and disability insurance sizing depends heavily on income replacement needs and number of dependents.
3. **Add asset values:** Home value, car value, and net worth all affect coverage level recommendations.
4. **Specify health usage patterns:** "I use healthcare frequently / rarely / primarily for prescriptions." This calibrates deductible vs premium optimization.
5. **Request an insurance priority ranking:** "Rank which coverage gaps are most urgent to address first given my situation."
6. **Pair with Prompt 11 (Goldman Sachs Wealth Diagnostic):** The insurance audit is one of 10 dimensions in the full diagnostic; these two prompts complement each other directly.

### Additional Resources
- **Policygenius** (policygenius.com) — Independent insurance marketplace for term life and disability quotes
- **NAIC Consumer Information Source** — Verify insurer financial stability ratings before purchasing
- **"The Insurance Bible"** — Free educational resource covering all insurance types
- **White Coat Investor Insurance Guide** — Excellent coverage of disability insurance for professionals
- **Independent Insurance Agents (IIABA)** — Find a local independent agent who can compare multiple carriers

---

## 18. Fidelity College Savings Architect

### Purpose
This prompt generates a complete college savings plan covering cost projections, 529 plan analysis, investment allocation strategy, financial aid optimization, scholarship preparation, and backup savings vehicles. College planning is unique because it involves a fixed deadline (the child's enrollment date), known cost escalation rates, and significant interaction effects with financial aid — making it more complex than generic savings planning.

Fidelity's persona is appropriate — they are the largest 529 plan administrator in the US and publish extensively on college savings strategy.

### When to Use
**Use when:**
- You have children and want to start or optimize college savings
- You're unsure which state's 529 plan to use (not always your home state)
- You want to understand how your savings choices affect financial aid eligibility
- You have multiple children and need a strategy that funds all of them without sacrificing retirement
- Grandparents want to contribute and you need to understand the tax-optimal way to structure that

**Do NOT use when:**
- Your child is already in college — the planning window for 529 optimization has largely closed
- You don't have retirement adequately funded — retirement savings should take priority over 529 contributions in most cases
- You expect full financial aid eligibility — 529 assets are counted in aid calculations
- You need specific state 529 plan details — verify current plan terms at savingforcollege.com

### Expected Output
A college savings plan containing:
- Cost projection table for public, private, and elite universities at enrollment date (inflated)
- 529 plan recommendation (home state vs another state's superior plan) with tax benefit calculation
- Monthly savings target to cover projected costs starting from current date
- Age-based allocation glide path (aggressive → conservative as enrollment approaches)
- Financial aid impact analysis (how 529 assets affect EFC/SAI and aid eligibility)
- Scholarship preparation timeline (when to start PSAT/SAT prep, extracurriculars, essays)
- Alternative vehicle comparison (Coverdell ESA, custodial account, Roth IRA backup)
- Multi-child funding strategy (separate accounts, shared priority, birth-order sequencing)
- Grandparent contribution strategy (superfunding, direct tuition payment, SECURE 2.0 rollover rules)
- Worst-case contingency plan (loans, community college transfer, work-study optimization)

### What the Prompt Does Well
- **Financial aid strategy inclusion:** Most 529 guides ignore this — the interaction between assets and aid is a meaningful planning variable
- **Scholarship preparation timeline:** Proactive scholarship strategy can reduce the savings burden — good to include
- **Grandparent contribution optimization:** SECURE 2.0 changed the rules here; this is a high-value planning area
- **Worst-case plan:** Acknowledging that savings may fall short and planning for it prevents paralysis
- **Multi-child strategy:** Often overlooked — funding two or more children requires explicit prioritization rules

### Ways to Improve the Prompt
1. **Provide children's exact ages:** The savings timeline is entirely dependent on years until enrollment.
2. **Specify state of residence:** State income tax deduction for 529 contributions varies by state — home state plan may or may not be optimal.
3. **Include your income:** Affects financial aid eligibility and tax benefit calculations.
4. **Add target school type:** "Aiming for public flagship / private liberal arts / elite research university" calibrates the cost projection.
5. **Request a FAFSA impact analysis:** "Show how different savings amounts in 529 vs Roth IRA affect Expected Family Contribution."
6. **Always cross-reference:** Use savingforcollege.com to verify the specific 529 plan recommendation before opening an account.

### Additional Resources
- **Savingforcollege.com** — The definitive 529 comparison tool with current state plan details
- **Federal Student Aid (studentaid.gov)** — Official FAFSA/financial aid information
- **College Board Annual Tuition Data** — For verifying cost projection benchmarks
- **"How to Pay for College" by Kalman Chany** — The most comprehensive book on financial aid strategy
- **Fidelity 529 College Savings Plan** — One of the top-rated plans nationally; compare against your home state

---

## 19. Edward Jones Estate Planning Organizer

### Purpose
This prompt generates a comprehensive estate planning checklist and strategy document — covering essential legal documents, beneficiary audit, asset titling, trust analysis, probate avoidance, digital asset succession, guardian designation, inheritance structure, tax-efficient wealth transfer, and letter of intent. Most people dramatically underestimate the complexity and importance of estate planning until it's too late.

The Edward Jones persona is well-suited here — they explicitly market estate planning coordination as a core wealth management service and serve a broad, non-institutional client base.

### When to Use
**Use when:**
- You have children (especially minor children) and have not designated a guardian in writing
- You have assets that would go through probate without proper planning (real estate, bank accounts without beneficiaries)
- You've had a major life event (marriage, divorce, new child, significant wealth accumulation) and haven't updated documents
- You want to understand whether you need a trust vs a will
- You have digital assets (crypto, online accounts) with no succession plan

**Do NOT use when:**
- You need actual legal documents drafted — this prompt produces a planning framework, not legally binding instruments; always use a licensed estate attorney
- Your estate involves complex business succession, international assets, or contested beneficiary situations — requires specialized legal counsel
- You want investment advice — this is purely estate and legacy planning
- Your estate planning is already complete and recently reviewed — no new value here

### Expected Output
An estate planning guide containing:
- Document checklist (will, revocable living trust, durable power of attorney, healthcare directive) with status tracker
- Beneficiary audit table (every account with beneficiary designation and whether it's current)
- Asset titling analysis (joint tenancy vs tenancy in common vs TOD vs trust)
- Trust analysis (whether a revocable living trust is warranted for your situation with specific benefits)
- Probate avoidance strategy (which assets skip probate and which go through it)
- Digital asset succession plan template (passwords, accounts, crypto, online property)
- Guardian designation checklist with legal requirements by state
- Inheritance structure options (outright vs staged vs trust-based distributions)
- Wealth transfer strategies (annual exclusion gifts, 529 superfunding, irrevocable trusts)
- Letter of intent template (personal wishes, funeral preferences, family messages)
- Action plan for completing all missing elements with priority order

### What the Prompt Does Well
- **Digital asset plan:** This is genuinely underserved in traditional estate planning — crypto and online accounts can be permanently lost without succession planning
- **Asset titling review:** One of the most consequential and overlooked estate planning details — how an asset is titled often overrides what a will says
- **Document status tracker:** Converts a daunting topic into a checklist with clear completion states
- **Trust analysis with specific benefits:** Rather than generically recommending trusts, demands situation-specific analysis
- **Letter of intent:** A non-legal but personally meaningful document that provides guidance beyond just asset distribution

### Ways to Improve the Prompt
1. **Provide your full asset picture:** Real estate (how titled), investment accounts (beneficiaries on file?), retirement accounts, life insurance, business interests, and any trusts already in place.
2. **Specify family structure:** Married, single, divorced, blended family, minor children, special needs dependents — each changes the estate plan significantly.
3. **Include your state of residence:** Probate rules, trust laws, and estate tax thresholds vary dramatically by state.
4. **Note any existing documents:** "I have a will from [year] but nothing else." This focuses the gap analysis on what's missing.
5. **Add wealth transfer goals:** "I want to leave [X]% to children, [Y]% to charity, and minimize estate taxes." This shapes the inheritance structure recommendations.
6. **Always engage an estate attorney:** AI can produce the planning framework and checklist; a licensed attorney drafts the actual documents and ensures state-law compliance.

### Additional Resources
- **Nolo Press** (nolo.com) — Free and affordable plain-English estate planning guides
- **Trust & Will / Fabric** — Online estate document services for basic wills and trusts
- **ACTEC (American College of Trust and Estate Counsel)** — Find a qualified estate planning attorney
- **IRS Estate and Gift Tax Information** (irs.gov) — Current exclusion amounts and rules
- **"Beyond the Grave" by Gerald Condon** — Highly readable book on estate planning and family wealth transfer

---

## 20. Wealthfront Real Estate Investment Analyzer

### Purpose
This prompt generates a complete real estate investment analysis — covering cash flow, cap rate, cash-on-cash return, appreciation projections, rent vs buy comparison, REIT alternative analysis, tax benefits, leverage analysis, and break-even timeline. It treats a real estate decision as a pure financial analysis problem with quantifiable outputs, comparable to how institutional real estate investment firms evaluate property deals.

Wealthfront's persona is appropriate — they are known for data-driven, algorithmic investment analysis and have published extensively on rent vs buy analysis using actual market data.

### When to Use
**Use when:**
- Evaluating whether to purchase a rental property
- Deciding between buying a primary residence vs continuing to rent
- Comparing direct real estate investment vs REITs
- You want to know the break-even timeline on a real estate investment before committing
- Evaluating a 1031 exchange opportunity

**Do NOT use when:**
- You need current mortgage rates — AI rates are not live; use Bankrate or your lender
- The property requires deep due diligence (structural issues, title problems, zoning) — requires physical inspection and legal review
- You're evaluating commercial real estate — this prompt is residential/small multifamily focused
- You need a formal appraisal for financing purposes — AI analysis does not substitute for a licensed appraiser

### Expected Output
A real estate investment analysis containing:
- Monthly cash flow projection (income minus all expense categories)
- Cap rate calculation with local market benchmark comparison
- Cash-on-cash return with full cash invested denominator (down payment + closing costs + initial repairs)
- 5/10/20-year appreciation forecast based on market conditions and historical trends
- Rent vs buy break-even analysis (how many years before buying becomes cheaper than renting)
- REIT comparison (what return a comparable real estate ETF would generate with the same capital)
- Tax benefit calculation (depreciation, mortgage interest, 1031 exchange potential)
- Vacancy and maintenance reserve recommendation (% of rent to set aside)
- Leverage sensitivity analysis (how different LTV ratios affect returns)
- Break-even timeline (when cumulative cash flow + appreciation exceeds all costs)
- Buy/pass recommendation with supporting rationale

### What the Prompt Does Well
- **Cap rate with benchmark comparison:** Prevents buying in overpriced markets where cap rates are too compressed for positive cash flow
- **Cash-on-cash return with full denominator:** Many analyses use just the down payment — including closing costs is more accurate
- **REIT alternative analysis:** Forces comparison to the next-best alternative — critical for honest ROI assessment
- **Rent vs buy for primary residence:** This is often more nuanced than people realize and the math frequently surprises people
- **Leverage analysis:** Explicitly addressing how mortgage leverage amplifies both gains AND losses is honest and important

### Ways to Improve the Prompt
1. **Provide complete property economics:** Purchase price, expected monthly rent, down payment amount, estimated mortgage rate, property taxes, insurance estimate, HOA if any, and estimated repair costs. The more specific, the more accurate the cash flow model.
2. **Specify the local market:** City/metro matters enormously for cap rate benchmarks and appreciation forecasts.
3. **Add your tax situation:** Rental income treatment and depreciation benefits depend on your income level and whether you're a "real estate professional" per IRS rules.
4. **Include property condition:** "Turnkey vs needs $[X] in renovations" affects the true initial cash invested.
5. **Request a sensitivity analysis:** "Show how the analysis changes if rent is 10% lower or vacancy rate is 15% instead of 8%."
6. **Verify cap rates locally:** Use LoopNet, CoStar, or local broker data to validate AI cap rate benchmarks for your specific market.

### Additional Resources
- **BiggerPockets Rental Property Calculator** (biggerpockets.com) — Free, widely-used rental analysis tool to validate AI outputs
- **LoopNet / CoStar** — Local cap rate data and comparable sales
- **Roofstock Marketplace** — Turnkey rental properties with pre-analyzed cash flow data
- **"The Book on Rental Property Investing" by Brandon Turner** — Most widely read rental real estate investment guide
- **SmartAsset Rent vs Buy Calculator** — For primary residence rent vs buy analysis

---

*Document generated: 2026-03-19 (updated with Series B)*    
*Total prompts: 20 across 2 series*  
*Tags: #finance #investing #personal-finance #prompt-engineering #stock-analysis #portfolio-management #retirement #tax-optimization #debt-elimination #estate-planning #real-estate #AI-tools*
