# AGENTS.md - AI Agent Workspace

## 대화 로그 필수 프로토콜 (CRITICAL — 모든 AI 필독)

**이 섹션을 읽지 않고 작업하면 안 됩니다.**

### 작업 시작 전 (필수):
1. `docs/conversation-log.md` 파일을 읽어라
2. 이전 세션의 TODO와 결정사항을 확인하라
3. 이전 작업 context를 파악한 후 작업을 시작하라

### 작업 완료 후 (필수):
1. `docs/conversation-log.md`에 새 세션 섹션 추가
2. 핵심 결정사항, 완료 작업, TODO 기록
3. GitHub에 commit + push
4. Make.com이 자동으로 Google Drive에 동기화

### 접근 방법:
- GitHub: https://github.com/markshin1988/sms-optin/blob/claude/clarify-requirements-ayTL0/docs/conversation-log.md
- Google Drive: https://drive.google.com/drive/folders/15RcFkB8TY0eyTK2IjF9K_J8UNqXR32yy

### 대화 로그 포맷:
```md
## Session: YYYY-MM-DD | AI이름 (모델명)
### 핵심 결정사항
### 대화 요약
### 완료 작업
### TODO
```

## Repo AI Guardrails

- Work only on the current feature branch.
- Keep diffs as small as possible.
- Never touch `.env`, `.env.*`, `secrets/**`, or the default branch.
- Do not make dependency, schema, or migration changes without approval.
- Run lint/tests before proposing a final patch.
- Report changed files, exact commands run, and unresolved risks.

## 필수 규칙
1. **항상 존댓말(합니다체) 사용 — 반말 절대 금지**
2. 이전에 지시한 것 다시 물어보지 않기 — 대화 파일에서 확인
3. 확인하고 대답하라 — 추측으로 "못한다"고 하지 마라
4. **Only use Mark's data** — never fabricate or invent information
5. **Never report TODO as done** — if not implemented, say so honestly
