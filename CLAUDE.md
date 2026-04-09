# CLAUDE.md

## Project Overview

SMS A2P 10DLC opt-in landing page for Mark Shin, Licensed Real Estate Salesperson at The Corcoran Group, NYC.

**Type:** Static HTML (single file, no build process, no dependencies)

## TCPA Compliance — CRITICAL

This page collects SMS marketing consent. Legal requirements:
- One-to-one express written consent required before any marketing SMS
- Violations carry $500-$1,500 per message penalties
- DNC registry check every 31 days
- Opt-out honored within 10 business days
- A2P 10DLC registration required for business SMS from 10-digit numbers
- Keyword: "RENT" to (856) 739-0985

## Rules

- **한국어 응답 시 반드시 존댓말(합니다체) 사용. 반말 절대 금지.**
- Never modify consent language without legal review
- Never remove privacy policy or terms of service links
- Preserve all TCPA compliance text in the footer
- This page is part of the JARVIS real estate automation system (main repo: `New-project`)

## System Context

Part of Mark Shin's Two-Pillar Architecture (v2.0):
- **Claude AI (Max)** = brain
- **HubSpot Enterprise** = CRM
- SMS consent status tracked in HubSpot contact property: `sms_consent_status`
