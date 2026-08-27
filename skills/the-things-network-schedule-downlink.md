---
name: the-things-network-schedule-downlink
description: >-
  Send a downlink to a LoRaWAN device through The Things Stack, and cancel one that has not yet
  been transmitted — the only reversal path on this write surface.
api: The Things Stack HTTP (REST) API v3
base_url: https://eu1.cloud.thethings.network/api/v3
operations:
  - AppAs_DownlinkQueueList
  - AppAs_DownlinkQueuePush
  - AppAs_DownlinkQueueReplace
  - AppAs_SimulateUplink
generated: '2026-08-27'
method: generated
source: openapi/ (operationIds verified), conventions/, errors/, rate-limits/
---

# Schedule (and cancel) a downlink

## This operation has a physical consequence

A downlink is transmitted over licensed-free radio to a device that may be actuating something.
Treat it as `consequence: physical` — see `agentic-access/the-things-network-agentic-access.yml`.
Once the gateway has transmitted it, it **cannot be recalled**.

## 1. Look before you push

`AppAs_DownlinkQueueList` —
`GET /as/applications/{application_id}/devices/{device_id}/down`

Shows what is already queued. Class A devices only receive after they transmit, so a queue can sit
for a long time.

## 2. Push, or replace

- `AppAs_DownlinkQueuePush` — `POST /as/applications/{app}/devices/{dev}/down/push`
  Appends. **Not idempotent** — a retried push enqueues the message twice and the device receives
  it twice.
- `AppAs_DownlinkQueueReplace` — `POST /as/applications/{app}/devices/{dev}/down/replace`
  Replaces the entire queue. **Idempotent by construction.**

**Use `replace` whenever a retry is possible.** The Things Stack publishes no idempotency-key
mechanism, so queue-replace is the only safe-retry primitive on this surface.

Body fields: `downlinks[].frm_payload` (base64), `downlinks[].f_port`, `downlinks[].priority`
(`LOWEST`…`HIGHEST`), `downlinks[].confirmed`.

## 3. Cancel

There is no cancel operation. `AppAs_DownlinkQueueReplace` with an **empty** `downlinks` array
discards everything queued but not yet sent. That window closes at transmission, and its length
depends on the device class (A/B/C) and the next receive window — it is not a stated duration.

## 4. Rehearse without a device

`AppAs_SimulateUplink` — `POST /as/applications/{app}/devices/{dev}/up/simulate` — injects a
synthetic uplink through payload formatters, storage, webhooks and MQTT. Useful for testing the
integration; it does not rehearse the downlink path.

## Rate limits

Downlink queue operations are rate limited **per application** since v3.35.2 (previously
per-device). Many devices under one application will trip `ResourceExhausted` / HTTP 429 sooner
than you expect. Back off using `X-Rate-Limit-Retry`.

## Errors

`error:pkg/ratelimit:rate_limit_exceeded` on 429. Match on `details[].namespace` +
`details[].name`, never on the message text.
