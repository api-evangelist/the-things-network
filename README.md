# The Things Network / The Things Stack (the-things-network)

The Things Network (TTN) is a free, community-operated global LoRaWAN network with 280,000+ members and 21,000+ gateways across 153 countries. It runs on **The Things Stack**, the open-source (Apache-2.0) LoRaWAN Network Server developed and maintained by The Things Industries. The same software powers self-hosted deployments, the community network, The Things Stack Cloud (Discovery, Standard, Plus tiers), and The Things Stack Enterprise.

The Things Stack v3 implements the full LoRaWAN Network Reference Model — Identity Server, Application Server, Network Server, Gateway Server, Join Server, Device Repository, Packet Broker Agent — and exposes a unified HTTP REST and gRPC API plus MQTT, webhooks, and Pub/Sub integrations.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/the-things-network/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=opensource-api-evangelist&utm_content=repo)

## Tags

LoRaWAN, IoT, Internet Of Things, Open Source, Network Server, LPWAN, Telemetry, Sensors, Gateways, Connectivity, Apache 2.0

## At a Glance

| Property | Value |
|---|---|
| Software | The Things Stack v3 (`v3.36`) |
| License | Apache 2.0 |
| Language | Go (server) + JavaScript (Console) |
| Source | [TheThingsNetwork/lorawan-stack](https://github.com/TheThingsNetwork/lorawan-stack) |
| API surface | HTTP REST + gRPC (270 documented HTTP routes across 67 services) + MQTT + Webhooks + Pub/Sub |
| Auth | API key (`Authorization: Bearer NNSXS.…`), OAuth 2.0, session cookies |
| Hosted | The Things Network (community, free) and The Things Stack Cloud (Discovery / Standard / Plus / Enterprise) |
| Self-host | Docker, Kubernetes / Helm, source build |

## APIs

### The Things Stack Identity Server
User, organization, OAuth client, API key, session, invitation, bookmark, notification, contact-info, and entity-search APIs.

- [Documentation](https://www.thethingsindustries.com/docs/api/reference/)
- [OpenAPI](openapi/the-things-stack-identity-server-openapi.yml)
- [JSON Schema — User](json-schema/the-things-stack-user-schema.json)
- [JSON Schema — Organization](json-schema/the-things-stack-organization-schema.json)
- [JSON Schema — APIKey](json-schema/the-things-stack-api-key-schema.json)
- [Naftiko Capability — Tenant Administration](capabilities/tenant-administration.yaml)

### The Things Stack Application Server
ApplicationRegistry, ApplicationAccess, AppAs uplink/downlink/queue, AsEndDeviceRegistry, ApplicationPackages, payload formatters, and the ApplicationUpStorage integration.

- [Documentation](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/application-server/)
- [OpenAPI](openapi/the-things-stack-application-server-openapi.yml)
- [JSON Schema — ApplicationUp](json-schema/the-things-stack-application-up-schema.json)
- [Example — Uplink Message](examples/the-things-stack-uplink-message-example.json)
- [Naftiko Capability — Uplink to Cloud](capabilities/uplink-to-cloud.yaml)

### The Things Stack Network Server
NS-side MAC state, ADR, MAC settings profiles, and the LoRaWAN 1.1 Relay configuration service.

- [Documentation](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/network-server/)
- [OpenAPI](openapi/the-things-stack-network-server-openapi.yml)
- [Naftiko Capability — End Device Lifecycle](capabilities/end-device-lifecycle.yaml)

### The Things Stack Gateway Server
GatewayRegistry, GatewayAccess, batch registry/access, Managed Gateway WiFi/Ethernet profiles, GatewayClaimingServer, GatewayQRCodeGenerator, and Gs connection stats.

- [Documentation](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/gateway-server/)
- [OpenAPI](openapi/the-things-stack-gateway-server-openapi.yml)
- [JSON Schema — Gateway](json-schema/the-things-stack-gateway-schema.json)
- [JSON Schema — Gateway Status](json-schema/the-things-stack-gateway-status-schema.json)
- [Example — Gateway Create](examples/the-things-stack-gateway-create-example.json)
- [Naftiko Capability — Gateway Onboarding](capabilities/gateway-onboarding.yaml)

### The Things Stack Join Server
OTAA join handling, root-key registry, JsEndDeviceRegistry, external HSM-backed crypto.

- [Documentation](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/join-server/)
- [OpenAPI](openapi/the-things-stack-join-server-openapi.yml)
- [Naftiko Capability — End Device Lifecycle](capabilities/end-device-lifecycle.yaml)

### The Things Stack End Device Registry
EndDeviceRegistry, EndDeviceBatchRegistry, EndDeviceTemplateConverter, EndDeviceQRCodeGenerator, EndDeviceClaimingServer, and the LoRaWAN DeviceRepository.

- [Documentation](https://www.thethingsindustries.com/docs/devices/)
- [OpenAPI](openapi/the-things-stack-end-device-registry-openapi.yml)
- [JSON Schema — EndDevice](json-schema/the-things-stack-end-device-schema.json)
- [Example — End Device Create](examples/the-things-stack-end-device-create-example.json)
- [Naftiko Capability — End Device Lifecycle](capabilities/end-device-lifecycle.yaml)

### The Things Stack Integrations
Application Webhooks and Application Pub/Sub (NATS / MQTT / AWS IoT / Azure IoT) registry APIs.

- [Documentation](https://www.thethingsindustries.com/docs/integrations/)
- [OpenAPI](openapi/the-things-stack-integrations-openapi.yml)
- [JSON Schema — ApplicationWebhook](json-schema/the-things-stack-application-webhook-schema.json)
- [JSON Schema — ApplicationPubSub](json-schema/the-things-stack-application-pubsub-schema.json)
- [Example — Webhook Create](examples/the-things-stack-webhook-create-example.json)
- [Naftiko Capability — Uplink to Cloud](capabilities/uplink-to-cloud.yaml)

### The Things Stack Packet Broker Agent
Packet Broker Agent — register networks, set forwarder and home-network routing policies, enable LoRaWAN passive and peering roaming.

- [Documentation](https://www.thethingsindustries.com/docs/reference/packet-broker/)
- [OpenAPI](openapi/the-things-stack-packet-broker-agent-openapi.yml)
- [Naftiko Capability — Packet Broker Roaming](capabilities/packet-broker-roaming.yaml)

### The Things Stack Events
Real-time event stream across IS/AS/NS/GS/JS via gRPC streaming or HTTP server-sent events. Includes NotificationService.

- [Documentation](https://www.thethingsindustries.com/docs/reference/events/)
- [OpenAPI](openapi/the-things-stack-events-openapi.yml)

## Naftiko Capabilities

- [End Device Lifecycle](capabilities/end-device-lifecycle.yaml) — register device on AS + NS + JS and verify activation
- [Gateway Onboarding](capabilities/gateway-onboarding.yaml) — register, claim, and configure a LoRaWAN gateway
- [Uplink to Cloud](capabilities/uplink-to-cloud.yaml) — stream uplinks via webhooks / pub-sub / storage
- [Tenant Administration](capabilities/tenant-administration.yaml) — users, orgs, OAuth clients, API keys
- [Packet Broker Roaming](capabilities/packet-broker-roaming.yaml) — LoRaWAN roaming policies

## Plans, Rate Limits, FinOps

- [Plans and Pricing](plans/the-things-network-plans-pricing.yml) — Open Source (self-hosted) / TTN Community / Discovery / Standard / Plus / Enterprise
- [Rate Limits](rate-limits/the-things-network-rate-limits.yml) — API rate limits, webhook concurrency, TTN community fair-use (~30s airtime/day, 10 downlinks/day), and regional LoRaWAN duty-cycle limits
- [FinOps Mapping](finops/the-things-network-finops.yml) — FOCUS-aligned cost surface

## Reference Artifacts

- [JSON-LD Context](json-ld/the-things-network-context.jsonld)
- [JSON Structure Overview](json-structure/the-things-network-structure.json)
- [Vocabulary](vocabulary/the-things-network-vocabulary.yml)
- [Spectral Ruleset](rules/the-things-network-rules.yml)

## Governance

- **The Things Industries** — Dutch company that builds, maintains, and commercially supports The Things Stack and operates The Things Stack Cloud and the public The Things Network community network.
- **The Things Network** — the community network and the foundation-style community on top of it (forums, local chapters in 100+ cities, certified developer program, public device repository).
- **License** — Apache 2.0 for The Things Stack; community contributions via the TheThingsNetwork and TheThingsIndustries GitHub organizations.
- **Standards** — LoRaWAN 1.0.x / 1.0.4 / 1.1 specifications maintained by the LoRa Alliance.
