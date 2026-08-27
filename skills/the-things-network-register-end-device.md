---
name: the-things-network-register-end-device
description: >-
  Register a LoRaWAN end device on The Things Stack, from creating the application to confirming
  the device has joined, using the Device Repository template where the hardware is known.
api: The Things Stack HTTP (REST) API v3
base_url: https://eu1.cloud.thethings.network/api/v3
operations:
  - ApplicationRegistry_Create
  - ApplicationRegistry_IssueDevEUI
  - DeviceRepository_ListBrands
  - DeviceRepository_ListModels
  - DeviceRepository_GetTemplate
  - EndDeviceRegistry_Create
  - EndDeviceRegistry_Get
  - EndDeviceRegistry_List
  - Events_Stream
generated: '2026-08-27'
method: generated
source: openapi/ (operationIds verified), conventions/the-things-network-conventions.yml
---

# Register an end device on The Things Stack

## Before you start

- Auth header on every call: `Authorization: Bearer NNSXS.<token-id>.<token-secret>`.
- Identity Server operations (applications, devices, gateways, API keys) are served **only from
  `eu1`** on The Things Stack Sandbox. Application/Network/Join Server calls work on any cluster.
- Enum values are protobuf constant strings — `MAC_V1_0_3`, not `1.0.3`.

## 1. Make sure the application exists

`ApplicationRegistry_List` — `GET /applications`

If it does not exist, `ApplicationRegistry_Create` — `POST /users/{collaborator.user_ids.user_id}/applications`.
The caller becomes the first collaborator.

## 2. Get a DevEUI if the device has none

`ApplicationRegistry_IssueDevEUI` allocates a DevEUI from The Things Stack's own block. Use it only
when the hardware did not ship with one — a device with a manufacturer DevEUI must keep it.

## 3. Use the Device Repository when the hardware is known

1. `DeviceRepository_ListBrands` — `GET /dr/brands`
2. `DeviceRepository_ListModels` — `GET /dr/models`
3. `DeviceRepository_GetTemplate` —
   `GET /dr/brands/{brand_id}/models/{model_id}/{firmware_version}/{band_id}/template`

The template returns the correct `lorawan_version`, `lorawan_phy_version`, class support flags and
payload formatters. Prefer it over hand-filling those fields.

## 4. Create the device

`EndDeviceRegistry_Create` —
`POST /applications/{end_device.ids.application_ids.application_id}/devices`

Required in the body: `ids.device_id`, `ids.dev_eui`, `ids.join_eui`, `lorawan_version`,
`lorawan_phy_version`, `frequency_plan_id`, and `root_keys.app_key.key` for OTAA.

**The device must also be registered on the Join Server, Network Server and Application Server.**
The single `EndDeviceRegistry_Create` call against the Identity Server creates the registry entry;
the cluster-local registries have their own operations (`JsEndDeviceRegistry_Set`,
`NsEndDeviceRegistry_Set`, `AsEndDeviceRegistry_Set`) and the CLI/Console do all four for you. If
you are driving the REST API directly and the device never joins, this is almost always why.

## 5. Confirm

- `EndDeviceRegistry_Get` with a `field_mask` naming the fields you want back.
- `Events_Stream` — `POST /events` — and watch for `as.up.data.forward` / join events.

## Field masks

Reads take `field_mask` to select fields; **updates take `field_mask` to name what is being
written**. An update with no `field_mask` writes nothing and returns success. This is the most
common failure mode against this API.

## Reversibility

`EndDeviceRegistry_Delete` is **irreversible** — end devices cannot be soft-deleted or restored.
Confirm with a human before calling it. Applications and gateways *can* be restored within 24h.
