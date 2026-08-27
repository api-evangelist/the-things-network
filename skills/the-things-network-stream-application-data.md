---
name: the-things-network-stream-application-data
description: >-
  Get device data out of The Things Stack — choose between webhooks, MQTT, Pub/Sub and the
  Storage Integration, wire it up, and recover messages missed while the receiver was down.
api: The Things Stack HTTP (REST) API v3 + MQTT
base_url: https://eu1.cloud.thethings.network/api/v3
operations:
  - ApplicationWebhookRegistry_ListTemplates
  - ApplicationWebhookRegistry_Set
  - ApplicationWebhookRegistry_List
  - ApplicationWebhookRegistry_Get
  - ApplicationWebhookRegistry_Delete
  - ApplicationPubSubRegistry_Set
  - ApplicationUpStorage_GetStoredApplicationUp
  - Events_Stream
generated: '2026-08-27'
method: generated
source: openapi/ (operationIds verified), asyncapi/the-things-network-webhooks.yml
---

# Stream application data out of The Things Stack

## Pick the surface

| Surface | Use when | Operation / topic |
|---|---|---|
| Webhooks | The receiver is an HTTP service you control | `ApplicationWebhookRegistry_Set` |
| MQTT | You want a long-lived subscription and low latency | `v3/{app}@{tenant}/devices/+/up` |
| Pub/Sub | You already run NATS or your own MQTT broker | `ApplicationPubSubRegistry_Set` |
| Storage | Backfill, or catching up after downtime | `ApplicationUpStorage_GetStoredApplicationUp` |
| Events | Operational events, not application data | `Events_Stream` |

## Webhooks

1. `ApplicationWebhookRegistry_ListTemplates` — `GET /as/webhook-templates` — check whether a
   pre-built template exists for the destination before writing a custom one.
2. `ApplicationWebhookRegistry_Set` —
   `PUT /as/webhooks/{webhook.ids.application_ids.application_id}/{webhook.ids.webhook_id}`

Set `base_url`, `format: json`, and enable the message types you want. Paths for each message type
are **appended** to the base URL; a type with no path goes to the base URL itself.

Narrow the payload with filter paths (e.g. `up.uplink_message`) rather than receiving the whole
envelope — LoRaWAN payloads are small but the metadata is not.

**The Things Stack does not sign webhook payloads.** There is no HMAC signature header.
Authenticate the sender with the optional HTTP Basic credentials on the webhook, or with a secret
segment in the base URL path. Do not assume a signature exists.

Your endpoint **must** return HTTP 200 OK or the delivery counts as failed. Retries with
enqueueing exist since v3.30.1.

## MQTT

Username `{application id}@{tenant id}` (open-source deployments: `{application id}` alone),
password an API key with `RIGHT_APPLICATION_TRAFFIC_READ`.

Subscribe topics:
`join`, `up`, `down/queued`, `down/sent`, `down/ack`, `down/nack`, `down/failed`,
`service/data`, `location/solved` — all under
`v3/{application id}@{tenant id}/devices/{device id}/`.

Publish topics: `down/push` (append) and `down/replace` (replace queue — also the cancel path).

## Catching up after downtime

`ApplicationUpStorage_GetStoredApplicationUp` —
`GET /as/applications/{app}/devices/{dev}/packages/storage/{type}` — returns a stream of stored
upstream messages. This is the recovery path; webhook retries alone will not rescue a long outage.

## Message shape

Every message is a `v3ApplicationUp` envelope: a oneof carrying `uplink_message`, `join_accept`,
`downlink_ack` / `nack` / `sent` / `queued` / `failed`, `location_solved` or `service_data`. Branch
on which key is present.
