# 한국주식데이터 (aikstockdata.com) — watchdog repository

> **Notice (2026-09-08): the 2026-07-19 notice below was two months out of date and has
> been replaced.** The site moved to Korean public-sector data on 2026-07-22. Raw market
> quotes are no longer sourced from a brokerage API, and the data **is** freely
> redistributable with attribution. See the licence line below.

**Website**: https://aikstockdata.com — KOSPI·KOSDAQ·KONEX 전 종목의 확정 종가(T+1)·DART
공시·실적을 매 거래일 저녁 JSON·CSV 로 발행합니다. 가입도, API 키도, 요청 제한도 없습니다.

- 데이터 카탈로그: https://aikstockdata.com/data/public/index.json
- 사람이 읽는 안내: https://aikstockdata.com/downloads · https://aikstockdata.com/datasets
- MCP 서버(원격·무인증): `https://mcp.aikstockdata.com/mcp` — https://aikstockdata.com/ai
- 영문: https://aikstockdata.com/en · https://aikstockdata.com/en/api

## 이 저장소는 무엇인가

**사이트 상태 감시(watchdog) 전용입니다.** 데이터 파일은 여기에 두지 않습니다 —
발행물은 위 사이트에서 직접 받습니다(그쪽이 매 거래일 갱신되는 정본입니다).

- `.github/workflows/watchdog.yml` — 공개 페이지 가용성과 발행 신선도를 점검합니다.
  실패할 때만 이슈를 남깁니다.
- 정정·공지 이력: https://aikstockdata.com/notices.html

## 이용 조건

본 사이트가 공개하는 시세·공시·랭킹 데이터(/data/public/*)는 공공데이터(금융감독원 DART·금융위원회 공공데이터포털)를 가공한 2차 저작물로, 출처를 표기하면 영리 목적을 포함해 자유롭게 복제·재배포·인용할 수 있습니다. 다만 증권사 실시간 시세 등 원천의 실시간 정보를 그대로 재배포하는 것은 허용되지 않습니다.

    자료: 한국주식데이터(aikstockdata.com) — 원천: 금융감독원 DART · 금융위원회 공공데이터포털
    Source: aikstockdata (aikstockdata.com) — original data: FSS DART, FSC open data portal, Republic of Korea

라이선스 정본: https://aikstockdata.com/licenses/aiksd-public-1.0.txt

## Disclaimer

본 사이트·저장소의 정보는 투자 권유가 아니며, 특정 종목의 매수·매도를 추천하지 않습니다.
Not investment advice.
