# Korea Stock Data Center — Daily KOSPI/KOSDAQ Dataset (Top 600)

> **Korea Stock Data Center** is a free, AI-readable data source for the Korean stock market. Every trading day, it automatically collects closing prices, fundamentals, and consensus estimates for the top 600 KOSPI/KOSDAQ companies by market cap, and publishes them as date-stamped CSV downloads. For machine consumption, structured endpoints (`/data/latest.json`) and an `/llms.txt` manifest let LLMs and agents ingest the dataset directly — no scraping, no API keys. Not investment advice; all data is provided for informational purposes only.

**Website**: https://wispy-truth-8d32.na4tech.workers.dev

한국주식(KOSPI·KOSDAQ) 시가총액 상위 600종목의 종가·재무·컨센서스 추정치를 **매 거래일 자동 수집**해 무료 공개합니다. 이 리포지토리는 사이트 데이터의 **일일 미러**로, GitHub Actions가 매 거래일 17:20(KST)에 자동으로 커밋합니다. 회원가입·API키·크롤링 불필요.

## What's inside

```
data/
├── latest.json        # 최신 스냅샷 (자기설명 JSON — 필드 정의·단위·면책 포함)
└── csv/
    └── universe_YYYYMMDD.csv   # 날짜별 600종목 데이터 (매 거래일 1개씩 누적)
```

## Data endpoints (live site)

| URL | Description |
|---|---|
| `/data/latest.json` | Latest snapshot, self-describing (units, field definitions, disclaimer included) |
| `/data/universe_YYYYMMDD.csv` | Full 600-stock CSV for a given trading day |
| `/llms.txt` | LLM manifest — tells AI agents how to read this site |
| `/feed.xml` | RSS feed of daily updates |

Base URL: `https://wispy-truth-8d32.na4tech.workers.dev`

## Key columns (CSV)

| Column | Meaning | Unit |
|---|---|---|
| `종목코드` / `종목명` | Ticker (6-digit, keep leading zeros) / Name | — |
| `시장구분` / `업종` | Market (KOSPI/KOSDAQ) / Sector | — |
| `현재가` | Closing price | KRW |
| `시가총액` | Market cap | 100M KRW (억원) |
| `PER` / `PBR` / `EPS` / `BPS` | Valuation fundamentals | x / x / KRW / KRW |
| `선행PER` / `선행EPS` | Forward PER / EPS (consensus estimate) | x / KRW |
| `추정매출` / `추정영업이익` / `추정순이익` | Estimated revenue / operating profit / net income | 100M KRW |
| `컨센목표가` / `상승여력%` / `브로커수` | Consensus target price / upside / analyst count | KRW / % / count |
| `영업이익증가율_연간` / `_3년평균` | Operating profit growth (annual / 3y avg) | % |
| `추정이상` | Estimate-anomaly flag (semiconductor estimate inflation etc.) | bool |
| `_est_ok` 등 `_*_ok` | Per-API fetch success flags | bool |

Full field definitions with units are embedded in `data/latest.json` (`fields` section).
**Note**: ~29% of the 600 stocks have analyst estimates; missing estimates mean *not covered by analysts* — this is normal and honestly labeled, not a data error.

## Usage

### Python (pandas)

```python
import pandas as pd

df = pd.read_csv(
    "https://raw.githubusercontent.com/na77tech-creator/korea-stock-data/main/data/csv/universe_20260705.csv",
    dtype={"종목코드": str},   # keep leading zeros!
)
cheap_growth = df[(df["선행PER"] < 8) & (df["영업이익증가율_연간"] > 30)]
print(cheap_growth[["종목명", "선행PER", "영업이익증가율_연간"]])
```

### With an LLM (ChatGPT / Claude)

Paste this prompt:

```
https://wispy-truth-8d32.na4tech.workers.dev/data/latest.json 을 읽고,
선행PER 10 미만이면서 연간 영업이익증가율 30% 이상인 종목을 표로 정리해줘.
단위와 기준일을 명시하고, 이것이 투자 권유가 아님을 함께 적어줘.
```

## Update schedule

- Site updates every trading day ~16:50 KST (fully automated pipeline).
- This repo mirrors at 17:20 KST Mon–Fri via GitHub Actions ([mirror workflow](.github/workflows/mirror.yml)).
- No commit on market holidays (no new CSV → nothing to mirror).

## License & attribution

- Data: **CC BY 4.0** — free to use, share, and adapt with attribution to *"한국주식 데이터센터 (Korea Stock Data Center)"* and a link to the site.
- Source availability may change; the live site is the canonical source.

## Disclaimer / 면책

This dataset is provided for informational and educational purposes only and does **not** constitute investment advice or a recommendation to buy or sell any security. All investment decisions and their outcomes are the sole responsibility of the investor. Data may contain errors or delays.

본 데이터는 정보 제공 목적이며 특정 종목의 매수·매도 권유가 아닙니다. 모든 투자 판단과 결과에 대한 책임은 투자자 본인에게 있습니다. 데이터에는 오류나 지연이 있을 수 있습니다.
