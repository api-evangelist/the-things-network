---
name: the-things-network-manage-access
description: >-
  Mint, scope and revoke credentials on The Things Stack — API keys with explicit Rights,
  collaborators, and the pseudo-rights trap that silently widens an agent's access over time.
api: The Things Stack HTTP (REST) API v3
base_url: https://eu1.cloud.thethings.network/api/v3
operations:
  - ApplicationAccess_CreateAPIKey
  - ApplicationAccess_ListAPIKeys
  - ApplicationAccess_UpdateAPIKey
  - ApplicationAccess_SetCollaborator
  - ApplicationAccess_ListRights
  - GatewayAccess_CreateAPIKey
  - UserAccess_CreateAPIKey
  - OrganizationAccess_CreateAPIKey
generated: '2026-08-27'
method: generated
source: >-
  openapi/ (operationIds verified),
  scopes/the-things-network-scopes.yml (70 Rights from rights.proto v3.36.2)
---

# Manage access on The Things Stack

## One vocabulary for everything

API keys and OAuth tokens carry the **same** permission vocabulary: the `Rights` enum. 70 rights,
grouped by entity — user, application, gateway, organization, client — plus two globals
(`RIGHT_SEND_INVITES`, `RIGHT_ALL`). The full list with descriptions is in
`scopes/the-things-network-scopes.yml`.

## Mint a scoped key

`ApplicationAccess_CreateAPIKey` — `POST /applications/{application_ids.application_id}/api-keys`

Body: `name`, `rights[]`, and — please — `expires_at`.

Same shape for `GatewayAccess_CreateAPIKey`, `UserAccess_CreateAPIKey`,
`OrganizationAccess_CreateAPIKey`.

The response contains the only copy of the secret you will ever see. The key format is
`NNSXS.<token-id>.<token-secret>`; only `token-id` is retrievable afterwards.

## Never grant a pseudo-right to a machine

`RIGHT_APPLICATION_ALL`, `RIGHT_GATEWAY_ALL`, `RIGHT_USER_ALL`, `RIGHT_ORGANIZATION_ALL`,
`RIGHT_CLIENT_ALL` and `RIGHT_ALL` are documented as covering **"all current and future"** rights
on that entity. A key granted one of these silently gains every right The Things Stack adds in a
later release. For an agent credential, enumerate the rights explicitly.

## Rights an agent usually needs

| Task | Rights |
|---|---|
| Read devices | `RIGHT_APPLICATION_DEVICES_READ` |
| Register devices | `RIGHT_APPLICATION_DEVICES_WRITE` (+ `_WRITE_KEYS` for OTAA root keys) |
| Read uplinks | `RIGHT_APPLICATION_TRAFFIC_READ` |
| Send downlinks | `RIGHT_APPLICATION_TRAFFIC_DOWN_WRITE` |
| Read gateway status | `RIGHT_GATEWAY_STATUS_READ`, `RIGHT_GATEWAY_INFO` |

`RIGHT_APPLICATION_LINK` and `RIGHT_GATEWAY_LINK` are **API-key-only** — they cannot be granted to
an OAuth token — and they are infrastructure credentials, not agent credentials.

## Check before you act

`ApplicationAccess_ListRights` — `GET /applications/{application_ids.application_id}/rights` —
returns the rights the *calling* credential actually has on that entity. Cheaper than discovering
the gap through a 403.

## Expiry and revocation

- API keys have **no expiry by default**. Set `expires_at` at create time.
- Revoke by deleting the key. Revocation is immediate.
- `ApplicationAccess_UpdateAPIKey` can narrow rights or set an expiry on an existing key.

## What a permission failure looks like

HTTP 403 with `details[].namespace: pkg/auth/rights`, `details[].name: no_user_rights`. Match on
that pair — not on the message string, which is translated and interpolated.
