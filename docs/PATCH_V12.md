# PATCH V12 — 감사 체인 검증 + 대화 확인 강제 (NON-NEGOTIABLE)

## V11까지의 감사 체인
```
system_hourly_audit (1h) → 시스템 전체 감사
       ↓
meta_audit (2h) → hourly가 돌았는지 감사
       ↓
audit_the_audit (V9) → AI가 V9 프로토콜 지켰는지 감사
       ↓
v11_enforcer (30min) → 위 3개가 다 돌았는지 감사
       ↓
daily_report (4AM+8AM) → 종합 보고서 → Drive 업로드
```

## V12 추가 규칙

### 1. 대화 확인 강제 (Conversation Verification)
- 모든 AI는 대답 전에 **이전 대화 5개 메시지**를 반드시 확인
- 이전에 지시한 것을 다시 물어보면 패치 위반
- "못한다" 말하기 전에 반드시 **확인** (API 호출, 문서 검색, 도구 확인)
- 추측으로 대답 금지 — 확인된 사실만 대답

### 2. V11 감사 검증
- V11 enforcer가 30분마다 돌아가는지 확인
- v11_enforcer.log에 PASS/FAIL 기록 확인
- FAIL이 3회 연속이면 Telegram 알림

### 3. 응답 체크리스트 (V12 추가)
매 응답 전 AI가 자체 확인해야 할 항목:
- [ ] 이전 대화에서 이미 지시한 내용인가?
- [ ] 확인 없이 "못한다"고 하는가?
- [ ] 추측으로 대답하는가?
- [ ] Patch 포맷을 따르고 있는가?
- [ ] conversation-log.md를 읽었는가?

하나라도 위반하면 응답에 `⚠️ V12 위반` 표시

## LaunchAgent 상태 (Mac mini)
| 에이전트 | 주기 | 기능 |
|---------|------|------|
| system-hourly-audit | 1h | 시스템 전체 감사 |
| meta-audit | 2h | hourly가 돌았는지 감사 |
| v11-enforcer | 30min | 감사 체인 전체 검증 |
| bore-auto-reconnect | KeepAlive | bore 끊기면 재연결 |
| daily-full-audit-report | 4AM+6AM | 종합 보고서 + Drive |
| bore-tunnel | KeepAlive | bore 터널 유지 |

## 적용 대상: 모든 AI
