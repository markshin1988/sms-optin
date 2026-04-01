# PATCH V8 — AI 응답 프로토콜 (NON-NEGOTIABLE)

## 모든 AI는 대답할 때마다 반드시 아래를 실행해야 합니다.
## 예외 없음. 안 하면 패치 버전 올라감.

---

### 1. 선행감사 (Preflight Audit)
- bore tunnel 상태 확인
- MCP Toolbox 연결 상태 확인
- Make.com 시나리오 상태 확인
- 이전 세션 TODO 확인
- conversation-log.md 읽기

### 2. Renew
- 만료된 연결/토큰 갱신 확인
- 변경된 포트/URL 업데이트
- 새로운 도구/모델 확인

### 3. Sync
- GitHub 3개 리포 동기화 상태
- Google Drive 동기화
- Mac mini 설정 동기화

### 4. Schema Check
- 도구/API 파라미터 검증
- 데이터 구조 유효성
- 연결 호환성 (__IMTCONN__ 등)
- 모델 ID 정확성 확인

### 5. Dry Run
- 실제 실행 전 시뮬레이션
- 예상 결과 확인
- 부작용 검증

### 6. Debugging
- 에러 즉시 원인 분석
- 수정 후 재실행
- 에러 로그 기록

### 7. Audit + 추천사항
- 완료 작업 목록
- 실패/미완료 목록
- 다음 단계 추천
- conversation-log.md 업데이트 + GitHub push

### 8. 감사 결과값 (V8 추가)
- 이번 대답에서 위 7단계를 실제로 실행했는지 자가감사
- 3번 연속 대답에서 모두 실행했는지 카운터 표시
- 보고서에 감사 실행 증거 포함 (executionId, 스크린샷, 로그 등)

---

## 응답 형식 (매 응답 끝에 반드시)

```
---
## Patch V8 Report (연속 감사 #N/3)
| 단계 | 상태 | 증거 |
|------|------|------|
| 선행감사 | ✅/❌ | bore: OK/FAIL, MCP: N tools, Scenario: active/inactive |
| Renew | ✅/❌ | 갱신한 항목 목록 |
| Sync | ✅/❌ | GitHub push SHA, Drive sync 상태 |
| Schema | ✅/❌ | 검증한 파라미터/모델 ID |
| Dry Run | ✅/❌ | executionId 또는 시뮬레이션 결과 |
| Debug | ✅/❌ | 에러 내용 + 수정 내역 |
| Audit | ✅/❌ | 완료/미완료 작업 카운트 |
| 감사결과값 | ✅/❌ | 7단계 전부 실행 여부 + 3회 연속 감사 카운터 |

추천사항:
1. ...
2. ...

감사 증거:
- executionId: xxx
- 로그: xxx
- push SHA: xxx
```

---

## 적용 대상
- 모든 AI (Claude, Codex, GPT, Gemini, Cursor, VS Code, 기타)

## 사용 가능한 Anthropic 모델 (Make.com 기준)
| 모델 | ID |
|------|-----|
| Claude Opus 4.6 | claude-opus-4-6 |
| Claude Sonnet 4.6 | claude-sonnet-4-6 |
| Claude Opus 4.5 | claude-opus-4-5-20251101 |
| Claude Sonnet 4.5 | claude-sonnet-4-5-20250929 |
| Claude Haiku 4.5 | claude-haiku-4-5-20251001 |
| Claude Opus 4.1 | claude-opus-4-1-20250805 |
| Claude Opus 4 | claude-opus-4-20250514 |
| Claude Sonnet 4 | claude-sonnet-4-20250514 |
| Claude Haiku 3 | claude-3-haiku-20240307 |

## 저장 위치
- GitHub: 3개 리포 `docs/PATCH_V8.md`
- Mac mini: `~/Documents/New project/PATCH_V8.md`
- Google Drive: 자동 동기화
