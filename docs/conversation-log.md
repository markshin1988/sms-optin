# AI Conversation Log

> 이 파일은 모든 AI 세션의 대화 내용을 기록합니다.
> 모든 AI는 작업 전 이 파일을 읽고, 작업 후 업데이트해야 합니다.
> Make.com을 통해 Google Drive에 자동 동기화됩니다.

## 접근 방법 (모든 AI용)

| 방법 | URL |
|------|-----|
| GitHub (sms-optin) | https://github.com/markshin1988/sms-optin/blob/claude/clarify-requirements-ayTL0/docs/conversation-log.md |
| GitHub (new-project) | https://github.com/markshin1988/new-project/blob/claude/clarify-requirements-ayTL0/docs/conversation-log.md |
| GitHub (realestate-crm-automation) | https://github.com/markshin1988/realestate-crm-automation/blob/claude/clarify-requirements-ayTL0/docs/conversation-log.md |
| Google Drive | https://drive.google.com/drive/folders/15RcFkB8TY0eyTK2IjF9K_J8UNqXR32yy |

## 원격 접속 (bore tunnel)

| 항목 | 값 |
|------|-----|
| **Endpoint** | `http://bore.pub:29953` |
| **Auth Key** | `jarvis2026` |
| **Host** | Mac-mini.local |
| **User** | markshin |
| **Method** | POST with JSON `{"key":"jarvis2026","cmd":"shell command"}` |
| **Response** | `{"out":"stdout","err":"stderr","rc":0}` |

### 사용법 (모든 AI):
```bash
curl -X POST http://bore.pub:29953 -d '{"key":"jarvis2026","cmd":"echo hello"}'
```

**주의:** bore.pub 포트는 재연결 시 변경될 수 있음. 변경 시 endpoint.txt + Telegram 알림으로 업데이트됨.

## AI별 설정 파일 현황

| 파일 | 적용 대상 | 상태 |
|------|----------|------|
| `CLAUDE.md` | Claude Code, Claude CLI | 3개 리포 설정 완료 |
| `AGENTS.md` | Codex (OpenAI), Open Code, Antigravity, 범용 AI | 3개 리포 설정 완료 |
| `.github/copilot-instructions.md` | GitHub Copilot | 3개 리포 설정 완료 |
| `.cursorrules` | Cursor | 3개 리포 설정 완료 |
| `.continuerules` | VS Code Continue | 3개 리포 설정 완료 |
| `docs/conversation-log.md` (이 파일) | GPT, Gemini, Notion AI, Make.com AI, HubSpot Breeze | URL로 접근 |

## MCP Toolbox

| 항목 | 값 |
|------|-----|
| **MCP Server URL** | `https://us2.make.com/mcp/server/a48da2dc-3ad3-4f4d-a16e-70165d7a6c46` |
| **MCP Key** | `qb3xS-hYpWqqKRyMtSyBT4jzSisodHyT4i2k5Iwq7h` |

---

## Session: 2026-04-01 | Claude Code (Opus 4.6) — Part 2

### 핵심 결정사항 (추가)
1. **bore.pub tunnel 설정** — Mac mini에 원격 명령 실행 가능 (bore.pub:29953, AUTH_KEY=jarvis2026)
2. **Make.com MCP Toolbox 생성** — 35개 도구 (Telegram 13 + HubSpot 12 + GitHub 2 + Google 3 + 기타)
3. **Anthropic Claude 연결 추가** — Make.com AI Agents에 Claude 모델 사용 가능
4. **JARVIS-CRM-Master 에이전트** — Make.com AI Agents에서 생성 진행 중

### Make.com 연결 현황 (업데이트)
| 연결 | ID | 상태 |
|------|-----|------|
| HubSpot CRM | 8151035 | 연결됨 |
| Google (Drive/Sheets) | 8151141 | 연결됨 |
| GitHub | 8151670 | 연결됨 |
| Telegram (JARVIS Bot) | 8152088 | 연결됨 |
| Telegram (2nd) | 8152767 | 연결됨 |
| OpenAI | 8152358 | 연결됨 |
| Google Calendar | 8153833 | 연결됨 |
| Calendly | 8155176 | 연결됨 |
| Anthropic Claude | 신규 | 생성 중 |

### Make.com MCP 도구 (올바른 __IMTCONN__ 파라미터로 재생성)
| 도구 | ID | 서비스 |
|------|-----|--------|
| Send Telegram Message to Mark | 4601770 | Telegram |
| Send Telegram Document | 4601818 | Telegram |
| Search HubSpot Contacts | 4601789 | HubSpot |
| Search HubSpot Deals | 4601791 | HubSpot |
| Create HubSpot Contact | 4601797 | HubSpot |
| Create HubSpot Deal | 4601799 | HubSpot |
| Get HubSpot Contact Details | 4601800 | HubSpot |
| Get HubSpot Deal Details | 4601802 | HubSpot |
| Update HubSpot Contact | 4601804 | HubSpot |
| Update HubSpot Deal | 4601806 | HubSpot |
| Create HubSpot Note | 4601809 | HubSpot |
| Create HubSpot Task | 4601811 | HubSpot |
| Create HubSpot Company | 4601812 | HubSpot |
| Search HubSpot Companies | 4601813 | HubSpot |
| List HubSpot Deal Pipelines | 4601816 | HubSpot |
| Create GitHub Issue | 4601823 | GitHub |
| Search GitHub Issues | 4601824 | GitHub |

### 이번 세션 완료 작업 (추가)
- [x] bore.pub tunnel 연결 확인 (bore.pub:29953)
- [x] Make.com MCP 도구 22개 `__IMTCONN__` 파라미터로 재생성
- [x] MCP Toolbox에 도구 추가 (UI에서 완료)
- [x] Anthropic Claude 연결 생성 진행
- [ ] JARVIS-CRM-Master AI Agent 생성 완료
- [ ] Google Drive/Calendar/Gmail 연결 승인 (credential request 대기)
- [ ] MCP Toolbox에 새로 생성한 도구 추가

### TODO (다음 세션)
- JARVIS-CRM-Master 에이전트 생성 및 테스트 완료
- Google Drive/Calendar/Gmail MCP 도구 생성
- bore.pub 포트 변경 시 자동 업데이트 로직 확인
- Make.com 나머지 시나리오들 (S1~S7) 활성화
- 에이전트 테스트: `Search for contact markshin1988@gmail.com`

---

## Session: 2026-04-01 | Claude Code (Opus 4.6) — Part 1

### 핵심 결정사항
1. **대화 로그 시스템 구축** — 모든 AI 세션의 대화를 하나의 파일로 관리
2. **GitHub 3개 리포에 동시 저장** — `sms-optin`, `new-project`, `realestate-crm-automation`
3. **Google Drive 자동 동기화** — Make.com 시나리오로 GitHub commit 감지 → Google Drive 폴더에 자동 업로드
4. **모든 AI용 설정 파일 생성** — 15개 파일 (3개 리포 × 5개 설정 파일)

### 완료 작업
- [x] 대화 로그 파일 생성 및 GitHub 3개 리포에 push
- [x] Make.com에 GitHub 연결 추가 (ID: 8151670)
- [x] Make.com 시나리오 "Integration Google Drive + Telegram" 활성화
- [x] 3개 리포에 CLAUDE.md, AGENTS.md, copilot-instructions.md, .cursorrules, .continuerules 생성/수정

---

## 업데이트 규칙

### AI가 이 파일을 업데이트할 때:
1. 새 세션 시작 시 `## Session:` 섹션 추가
2. 핵심 결정사항, 대화 요약, 완료 작업, TODO 기록
3. 이전 세션의 TODO를 확인하고 진행 상황 업데이트
4. GitHub에 commit + push → Make.com이 자동으로 Google Drive 동기화

### 포맷 규칙:
- 최신 세션이 맨 위에 위치
- 날짜 형식: YYYY-MM-DD
- 체크박스로 작업 완료 여부 표시
