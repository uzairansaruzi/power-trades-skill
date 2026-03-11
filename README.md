# PowerTrades — Options Day Trading Skill

An AI agent skill for options day trading, built on my rules and methodology. Use this skill with GitHub Copilot, Claude, ChatGPT, or any AI assistant to get structured trade analysis, risk management, and options chain evaluation.

## Repository Structure

```text
.
├── .agents/
│   └── skills/
│       └── trading_skill/
│           └── SKILL.md
├── .env.example
├── LICENSE
└── README.md
```

## What This Skill Does

- **Top-down technical analysis** — multi-timeframe S&R, patterns, trend identification
- **Options mechanics** — Greeks (Delta, Gamma, Theta, Vega, IV), chain analysis, contract selection
- **Trade execution** — concrete entry/exit rules, scaling framework, pre-market checklist
- **Risk management** — position sizing formulas, PDT rules, max daily loss enforcement
- **Market context** — SPY/QQQ correlation, economic calendar awareness, time-of-day windows
- **Structured output** — standardized formats for trade alerts, analysis, journals, and watchlists

## Quick Start

### 1. Add the skill to your AI agent

**GitHub Copilot CLI / Copilot Chat:**
Point your agent to `.agents/skills/trading_skill/SKILL.md` as the custom skill file.

**Other AI assistants:**
Copy the contents of `.agents/skills/trading_skill/SKILL.md` into your system prompt or knowledge base.

### 2. Set up API keys (optional but recommended)

The skill references free APIs for live market data. To use them:

```bash
cp .env.example .env
# Edit .env and add your API keys (see instructions below)
```

### 3. Install Python dependencies

```bash
pip install yfinance finnhub-python pandas pandas_ta python-dotenv mplfinance requests fredapi polygon-api-client
```

## API Keys

All APIs have free tiers. `yfinance` requires no key at all.

| API | Free Tier | Signup |
|-----|-----------|--------|
| **Yahoo Finance** (`yfinance`) | Unlimited (no key needed) | — |
| **Finnhub** | 60 calls/min | [finnhub.io/register](https://finnhub.io/register) |
| **Alpha Vantage** | 25 calls/day | [alphavantage.co](https://www.alphavantage.co/support/#api-key) |
| **FRED** | 120 calls/min | [fred.stlouisfed.org](https://fred.stlouisfed.org/docs/api/api_key.html) |
| **Polygon.io** | 5 calls/min (delayed) | [polygon.io](https://polygon.io/dashboard/signup) |

See `.env.example` for the full list with step-by-step signup instructions in `.agents/skills/trading_skill/SKILL.md` §2.

## Skill Structure

| Section | What It Covers |
|---------|----------------|
| §1 Role & Purpose | AI agent instructions, guardrails, interaction patterns |
| §2 Data Sources & APIs | Setup, keys, code samples for each API |
| §3 Market Context | Time windows, economic calendar, SPY/VIX correlation |
| §4 Technical Analysis | Candlesticks, S&R, VWAP, EMA, RSI, MACD, volume, patterns |
| §5 Options Mechanics | Greeks, IV, chain analysis, contract selection decision tree |
| §6 Trade Execution | Pre-market checklist, entry rules, exit rules, scaling framework |
| §7 Risk Management | Position sizing formula, PDT rule, golden rules, psychology |
| §8 Output Formats | Trade alert, market analysis, journal, watchlist templates |
| §9 Glossary | 25+ trading terms defined |

## Example Interactions

```
You:   "Analyze AAPL"
Agent: Full top-down TA + options chain summary + trade idea (if setup exists)

You:   "What's the market doing?"
Agent: SPY/QQQ trend, VWAP position, key levels, calendar check

You:   "Size this trade — $10K account, SPY 575c at $2.35, stop at $1.50"
Agent: Position sizing calculation with contracts, risk %, and R:R ratio

You:   "Journal this trade"
Agent: Structured trade log entry with P&L, setup notes, and lessons
```

## Contributing

Contributions are welcome! If you have improvements to the trading methodology, new API integrations, or additional output templates:

1. Fork this repository
2. Create a feature branch (`git checkout -b feature/my-improvement`)
3. Commit your changes (`git commit -m "Add my improvement"`)
4. Push to the branch (`git push origin feature/my-improvement`)
5. Open a Pull Request

## Disclaimer

This skill is for **educational purposes only**. It is not financial advice. Options trading involves significant risk of loss. Past performance does not guarantee future results. Always do your own research and consult a licensed financial advisor before trading.

## License

MIT — see [LICENSE](LICENSE) for details.
