# Stock Research Orchestra

이 프로젝트는 주식 종목을 재무, 뉴스, 업종, 전략, 리스크 감사 관점에서 분업 분석하여 한국어 투자 리서치 보고서를 생성하는 Claude Code 기반 분석 시스템이다.

## 구성

- Main Agent: 전체 지휘 및 최종 보고서 작성
- Financial Analyst: 재무·회계품질·밸류에이션 분석
- News Sentiment Analyst: 뉴스·공시·이벤트 감성 분석
- Sector Researcher: 업종·경쟁사·정책 분석
- Aggressive Strategy Agent: 공격형 진입·청산 전략 수립
- Risk Auditor: 반대논리·리스크 감사

## 주요 원칙

- 출처 없는 수치 사용 금지
- 기준일 없는 판단 금지
- 손절 없는 매수 의견 금지
- 리스크 감사 없는 최종 판정 금지
- 실거래 실행 금지

## 사용 예시

```text
삼성전자를 중기 관점에서 분석해줘. 현재 미보유이고 공격적 성향이다.
```

## 프로젝트 파일 구조

```text
stock_research_orchestra/
├─ CLAUDE.md
├─ README.md
├─ prompts/
│  ├─ main_agent.md
│  ├─ financial_analyst.md
│  ├─ news_sentiment_analyst.md
│  ├─ sector_researcher.md
│  ├─ aggressive_strategy_agent.md
│  └─ risk_auditor.md
├─ schemas/
│  ├─ input_schema.json
│  ├─ financial_output_schema.json
│  ├─ news_output_schema.json
│  ├─ sector_output_schema.json
│  ├─ strategy_output_schema.json
│  ├─ risk_audit_output_schema.json
│  └─ final_report_schema.json
├─ templates/
│  ├─ final_report_template.md
│  ├─ agent_summary_template.md
│  └─ risk_disclaimer.md
├─ examples/
│  ├─ sample_input_kr.json
│  ├─ sample_final_report.md
│  └─ sample_agent_outputs.json
├─ tests/
│  ├─ validation_checklist.md
│  └─ red_team_cases.md
└─ docs/
   ├─ operating_policy.md
   ├─ data_source_policy.md
   └─ no_trade_execution_policy.md
```

## 최종 보고서 구성

1. 핵심 결론
2. 현재 판정
3. 재무 분석
4. 뉴스 감성
5. 업종 리서치
6. 공격적 투자 전략
7. 리스크 감사
8. 시나리오
9. 진입·손절·청산 계획
10. 최종 권고

## 주의

본 시스템은 투자 참고용 리서치 자동화 도구이며, 매수·매도 권유 또는 수익 보장을 의미하지 않는다.
