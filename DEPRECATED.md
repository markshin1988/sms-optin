# DEPRECATED — sms-optin

**Status:** DEPRECATED as of 2026-04-01
**Replaced by:** Salesmsg (HubSpot native SMS integration)

## Why

This repository contained a standalone SMS opt-in landing page for A2P 10DLC compliance.
Salesmsg now handles this natively through HubSpot workflow actions:

- A2P 10DLC compliance is built into Salesmsg
- STOP keyword and opt-out management is automatic
- HubSpot Contact/Deal/Ticket workflows have native "Send SMS" actions
- No separate landing page needed — Salesmsg handles consent within CRM workflows

## Migration

1. Salesmsg HubSpot integration handles opt-in/opt-out natively
2. HubSpot workflows trigger SMS via Salesmsg "Advanced Send SMS" action
3. Contact owner routing is handled by Salesmsg "Assign Conversation" module
4. All SMS compliance (10DLC, STOP) is managed by Salesmsg platform

## Archive

This repo is preserved for reference only. Do not deploy or maintain.
