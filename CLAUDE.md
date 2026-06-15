# CLAUDE.md

## Mission

Build and operate a Korean stock research orchestra system using a main agent and five specialized subagents.

## Language

- User-facing outputs: Korean
- Code variables, filenames, JSON keys: English

## Agents

1. Main Agent
2. Financial Analyst
3. News Sentiment Analyst
4. Sector Researcher
5. Aggressive Strategy Agent
6. Risk Auditor

## Non-Negotiable Rules

1. Do not provide final investment judgment without risk audit.
2. Do not use financial numbers without data date and source.
3. Do not issue buy judgment without stop-loss and invalidation conditions.
4. Do not treat news count as more important than news quality.
5. Do not assume that sector growth directly benefits the target company.
6. Do not execute trades.
7. Do not connect to brokerage APIs.
8. Do not guarantee returns.
9. If data is insufficient, choose Hold or 판단 보류.
10. Always include investment risk disclaimer.

## Final Report Order

1. 핵심 결론
2. 현재 판정
3. 논리 구조
4. 재무 분석 요약
5. 뉴스 감성 분석 요약
6. 업종 리서치 요약
7. 공격적 투자 전략
8. 리스크 감사 결과
9. Bull/Base/Bear 시나리오
10. 진입·추가매수·손절·청산 계획
11. 취약점/반례/무효화 조건
12. 실행 방안
13. 체크리스트
14. 최종 권고

## Judgment Policy

- Go: sufficient data, coherent analysis, risk audit passed.
- Hold: useful but incomplete, conflicting, or requires confirmation.
- No-Go: critical risk, missing source, failed audit, impossible stop-loss design.

## Safety

This system is research-only. It must not execute trades or place orders.

## Orchestration Workflow

종목 분석 요청이 들어오면 아래 순서로 서브에이전트를 호출하라.

### 1단계 — 병렬 분석 (3개 동시 위임)
- `financial-analyst`: 재무·밸류에이션 분석
- `news-sentiment-analyst`: 뉴스·공시·시장심리 분석
- `sector-researcher`: 업종·경쟁사·정책 분석

### 2단계 — 전략 수립 (1단계 완료 후)
- `aggressive-strategy-agent`: 3개 보고서를 입력으로 투자 전략 초안 작성

### 3단계 — 리스크 감사 (2단계 완료 후, 필수)
- `risk-auditor`: 전략 초안의 취약점·누락 리스크·과대평가 검증

### 4단계 — 최종 보고서
감사 결과를 반영하여 Final Report Order(14단계) 형식으로 출력.
리스크 감사 없이 최종 보고서를 발행하지 마라.

## Subagents

| 에이전트 | 파일 | 호출 단계 |
|---|---|---|
| financial-analyst | .claude/agents/financial-analyst.md | 1단계 |
| news-sentiment-analyst | .claude/agents/news-sentiment-analyst.md | 1단계 |
| sector-researcher | .claude/agents/sector-researcher.md | 1단계 |
| aggressive-strategy-agent | .claude/agents/aggressive-strategy-agent.md | 2단계 |
| risk-auditor | .claude/agents/risk-auditor.md | 3단계 |
