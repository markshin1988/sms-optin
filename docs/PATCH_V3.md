# PATCH V3 — AI 응답 프로토콜 (NON-NEGOTIABLE)

## 모든 AI는 대답할 때마다 반드시 아래 7단계를 실행해야 합니다.
## 이 파일을 읽었으면 반드시 따라야 합니다. 예외 없음.

---

### 1. 선행감사 (Preflight Audit)
- bore tunnel 상태 확인
- MCP Toolbox 연결 상태 확인
- Make.com 시나리오 상태 확인
- 이전 세션 TODO 확인

### 2. Renew
- conversation-log.md 최신 상태 읽기
- 만료된 연결/토큰 갱신 확인
- 변경된 포트/URL 업데이트

### 3. Sync
- GitHub 3개 리포 동기화 상태 확인
- Google Drive 동기화 확인
- Mac mini 설정 동기화 확인

### 4. Schema Check
- 사용할 도구/API 파라미터 검증
- 데이터 구조 유효성 확인
- 연결 호환성 확인 (__IMTCONN__ 등)

### 5. Dry Run
- 실제 실행 전 시뮬레이션
- 예상 결과 확인
- 부작용 없는지 검증

### 6. Debugging
- 에러 발생 시 즉시 원인 분석
- 수정 후 재실행
- 에러 로그 기록

### 7. Audit + 추천사항
- 완료된 작업 목록
- 실패/미완료 작업 목록
- 다음 단계 추천
- conversation-log.md 업데이트 + GitHub push

---

## 응답 형식

매 응답 끝에 반드시:

```
---
## Patch V3 Report
| 단계 | 상태 | 비고 |
|------|------|------|
| 선행감사 | ✅/❌ | ... |
| Renew | ✅/❌ | ... |
| Sync | ✅/❌ | ... |
| Schema | ✅/❌ | ... |
| Dry Run | ✅/❌ | ... |
| Debug | ✅/❌ | ... |
| Audit | ✅/❌ | ... |

추천사항:
1. ...
2. ...
```

---

## 적용 대상
- Claude Code / CLI
- Codex
- GPT
- Gemini
- Cursor
- VS Code
- 모든 AI

## 저장 위치
- GitHub: 3개 리포 `docs/PATCH_V3.md`
- Mac mini: `~/Documents/New project/PATCH_V3.md`
- Google Drive: 자동 동기화
