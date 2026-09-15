# 한국주식데이터 (aikstockdata.com) — watchdog repository

> **Notice (2026-09-15): terms of use changed on 2026-09-14.** The site's published data is now
> under `aiksd-public-1.1`: Non-commercial use with attribution; commercial redistribution is not permitted. The upstream FSC market-price data
> became KOGL Type 4 (attribution · non-commercial · no derivatives) on 2026-09-09, so the earlier
> 2026-09-08 notice that stood here no longer applies.

**Website**: https://aikstockdata.com — KOSPI·KOSDAQ·KONEX 전 종목의 확정 종가(T+1)·DART
공시·실적을 매 거래일 저녁 JSON·CSV 로 발행합니다. 가입도 API 키도 없고, 일반적인 사용 범위에서 별도 쿼터가 없습니다.

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

본 사이트가 공개하는 데이터(/data/public/*)는 출처를 표기하면 비영리 목적으로 인용·이용할 수 있습니다. 상업적(영리) 목적의 재배포는 어떤 경우에도 허용하지 않습니다. 시세(종가·거래량·시가총액 등)는 금융위원회 공공데이터포털이 원천이며 원천의 이용허락범위(공공누리 제4유형: 출처표시·상업적 이용금지·변경금지)와 제공기관 안내도 함께 따라야 하고, 공시 내용은 금융감독원 전자공시시스템(DART)의 이용 조건을 따릅니다. 다만 증권사 실시간 시세 등 원천의 실시간 정보를 그대로 재배포하는 것은 허용되지 않습니다.

    자료: 한국주식데이터(aikstockdata.com) — 원천: 금융감독원 DART · 금융위원회 공공데이터포털
    Source: aikstockdata (aikstockdata.com) — original data: FSS DART, FSC open data portal, Republic of Korea

라이선스 정본: https://aikstockdata.com/licenses/aiksd-public-1.1.txt (2026-09-14부터 · 이전 판 1.0 은 기록으로만 남아 있습니다)

## Disclaimer

본 사이트·저장소의 정보는 투자 권유가 아니며, 특정 종목의 매수·매도를 추천하지 않습니다.
Not investment advice.
