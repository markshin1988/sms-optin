# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## 대화 로그 필수 프로토콜 (CRITICAL)

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
- Show a short plan before editing.
- Make the smallest possible diff.
- Never read `.env`, `.env.*`, or `secrets/**`.
- Ask before dependency changes, migrations, deletes, or external user-facing actions.
- Run lint/tests after edits.
- Final response must include changed files, commands run, and remaining risks.

## Project Overview

SMS Opt-in — SMS 옵트인 관련 프로젝트.

## Critical Rules

1. **Double-check before every action** — CHECK1: data, CHECK2: links/targets
2. **Only use Mark's data** — never fabricate or invent information
3. **Never report TODO as done** — if not implemented, say so honestly
4. **한국어 응답 시 반드시 존댓말(합니다체) 사용. 반말 절대 금지.**
5. 확인하고 대답하라 — 추측으로 "못한다"고 하지 마라
