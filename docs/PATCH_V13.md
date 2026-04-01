# PATCH V13 — 감사 패치 중복 충돌 방지

## 발견된 중복

### 스크립트 중복 (같은 역할, 다른 파일)
| 역할 | 기존 (유지) | 중복 (제거 대상) | 상태 |
|------|---------|---------|------|
| 일일 감사 | `daily_full_audit.py` (V11에서 생성) | `daily_audit.py` (구버전) | ⚠️ daily_audit.py는 com.jarvis.daily-audit에서 사용 중 — 도매인 다르면 유지 |
| 메타감사 | `meta_audit.py` (V11에서 생성) | `audit_the_audit.py` (V9에서 생성) | ⚠️ 역할 겨침 — audit_the_audit는 AI 응답 감사, meta_audit는 시스템 감사 |
| V11 감사 | `v11_enforcer.py` | `response_audit_gate.py` | ⚠️ 둘 다 응답 포맷 검증 — 통합 필요 |
| 일일 보고서 | `daily_report_generator.py` | `daily_google_doc_report.py` | ⚠️ 둘 다 보고서 생성 — 출력 대상 다르면 유지 |

### LaunchAgent 중복
| 역할 | 기존 (유지) | 중복 | 충돌 위험 |
|------|---------|---------|------|
| 일일 감사 | `com.jarvis.daily-full-audit-report` (4AM+6AM) | `com.jarvis.daily-audit` | 낮음 — 시간 다름 |
| 보고서 | `com.jarvis.daily-report` | `com.jarvis.daily-doc-report` | 낮음 — 출력 대상 다름 |
| 감사 | `com.jarvis.system-hourly-audit` (1h) | `com.jarvis.hubspot-system-deep-audit` | 없음 — 도메인 다름 |

## 충돌 방지 규칙

### 1. 네임스페이스 규칙
- 새 감사 스크립트는 반드시 `v{N}_` 접두사 사용 (예: `v13_collision_check.py`)
- LaunchAgent Label: `com.jarvis.v{N}-{name}` (예: `com.jarvis.v13-collision-check`)
- 기존 스크립트 수정 금지 — 새 버전으로 대체

### 2. 실행 우선순위
```
system_hourly_audit (1h) — 기본 시스템 감사
  ↓
meta_audit (2h) — hourly 감사의 감사
  ↓
audit_the_audit (V9) — AI 응답 프로토콜 감사
  ↓
v11_enforcer (30min) — 감사 체인 전체 검증
  ↓
v13_collision_check (6h) — 중복 충돌 감지
  ↓
daily_full_audit (4AM+8AM) — 종합 보고서
```

### 3. 충돌 감지 로직
- 같은 LaunchAgent Label = 충돌
- 같은 StartInterval + 같은 도메인 = 충돌
- 같은 파일명 다른 경로 = 충돌
- 같은 Telegram chat_id로 동시 알림 = 노이즈 (주의)

### 4. 현재 판정: 심각한 충돌 없음
- 모든 중복은 역할/도메인/시간이 다름
- 동시 실행되는 충돌 없음
- 단, 향후 새 패치 추가 시 반드시 이 파일 확인 후 추가
