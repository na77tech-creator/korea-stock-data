# Korea Stock Data Center — Daily KOSPI/KOSDAQ Dataset for AI

> **Korea Stock Data Center** is a free, AI-readable data source for the Korean stock market. Every trading day it automatically collects prices, fundamentals, and analyst consensus estimates for top KOSPI/KOSDAQ companies by market cap, and publishes them as date-stamped CSV/JSON. Built for machine consumption — structured endpoints (`/data/latest.json`) and an `/llms.txt` manifest let LLMs and agents ingest the dataset directly. No scraping, no API keys. Not investment advice; informational purposes only.

**Website**: https://aikstockdata.com

한국주식(KOSPI·KOSDAQ) 시가총액 상위 종목의 시세·재무·컨센서스 추정치를 **매 거래일 오전 10시·오후 4시(KST) 자동 수집**해 무료 공개합니다. 로그인·API키·크롤링 불필요.

## Data endpoints (live site)

| URL | Description |
|---|---|
| `https://aikstockdata.com/data/latest.json` | Latest snapshot — self-describing (units, field definitions, English aliases, disclaimer) |
| `https://aikstockdata.com/data/top50.json` | Lightweight — top 50 by market cap + top 50 by estimated growth |
| `https://aikstockdata.com/data/index.json` | Date index of historical CSV snapshots (time-series entry point) |
| `https://aikstockdata.com/data/universe_YYYYMMDD.csv` | Full daily CSV for a given trading day |
| `https://aikstockdata.com/llms.txt` | LLM manifest — how AI agents should read this site |
| `https://aikstockdata.com/feed.xml` | RSS feed of daily updates |

## Fields

Price, market cap, shares outstanding, PER, PBR, forward EPS, forward PER, estimated operating-income YoY growth, quarterly operating-income YoY, analyst rating. Prices in KRW, market cap in 100M KRW. `null` means data not provided (not zero). English field aliases are inside `latest.json`.

## Use with AI

Paste a data URL into ChatGPT / Claude / Gemini and ask, e.g.:
> "Read this JSON and list stocks with forward PER under 15 and estimated operating-income growth over 20%, as a table."
> https://aikstockdata.com/data/latest.json

See the prompt guide: https://aikstockdata.com/ai.html

## Source & License

Data source: Korea Investment & Securities (한국투자증권) OpenAPI. Free to use; please credit "Korea Stock Data Center (aikstockdata.com)". Not investment advice.

Keywords: Korean stock data, KOSPI KOSDAQ dataset, stock screening data for AI, forward PER, analyst consensus, 한국주식 데이터, 종목 추천 데이터, AI 주식 분석.
