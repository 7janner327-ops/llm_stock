# LLM Stock Analysis

LLM Stock Analysis is a large-language-model–driven framework for researching, scoring, and monitoring public equities using structured fundamentals, market data, and qualitative signals. The goal is repeatable, auditable investment analysis—not hype.

## What This Does

- Ingests **fundamental**, **financial**, and **market** data
- Applies a **scoring rubric** (growth, profitability, balance sheet, valuation, momentum, risk)
- Uses an **LLM as an analyst**, not an oracle:
  - Explains *why* a stock scores well or poorly
  - Flags assumptions, uncertainties, and missing data
- Produces **tables, summaries, and decision-ready outputs**

## Core Principles

- **Evidence first**: Every claim is tied to data or a stated assumption
- **Deterministic structure + probabilistic reasoning**
- **Separation of data, logic, and language**
- **Reproducible runs** with saved inputs and prompts

## Architecture

data/
fundamentals/
prices/
estimates/
prompts/
analyst.md
risk.md
valuation.md
scoring/
rubric.yaml
weights.yaml
pipelines/
ingest.py
score.py
analyze.py
outputs/
reports/
tables/

### Flow

1. **Ingest** raw data (APIs, CSVs, filings)
2. **Normalize** metrics (TTM, YoY, CAGR)
3. **Score** via rubric + weights
4. **Analyze** with LLM (explanations, risks, edge cases)
5. **Output** tables and investment memos

## Example Output

- Composite score (0–100)
- Category scores (Growth, Margins, Balance Sheet, Valuation, Momentum)
- Bull / Bear cases
- Key risks and disqualifiers
- 12–36 month outlook

## Example Prompt (Simplified)

```text
Act as a disciplined equity analyst.
Use only provided data.
Score each category 0–10.
Explain drivers, risks, and assumptions.
If data is missing, say so explicitly.

Installation

git clone https://github.com/yourname/llm-stock-analysis
cd llm-stock-analysis
pip install -r requirements.txt

Usage

python pipelines/ingest.py --ticker NVDA
python pipelines/score.py --ticker NVDA
python pipelines/analyze.py --ticker NVDA

Configuration
	•	scoring/rubric.yaml – metrics and thresholds
	•	scoring/weights.yaml – category weights
	•	prompts/ – analyst behavior and tone

What This Is Not
	•	Not financial advice
	•	Not high-frequency trading
	•	Not prompt-only speculation

Roadmap
	•	Multi-stock portfolio optimization
	•	Backtesting with point-in-time data
	•	Automated earnings analysis
	•	Factor attribution vs benchmarks

Disclaimer

This project is for research and educational purposes only. No investment recommendations are made. Always verify with primary sources.

⸻

Truth beats confidence. Structure beats vibes.

