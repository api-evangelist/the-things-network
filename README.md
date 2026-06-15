# The Things Network / The Things Stack (the-things-network)

The Things Network (TTN) is a free, community-operated global LoRaWAN network with over 280,000 members and 21,000 gateways across 153 countries. It runs on The Things Stack, the open-source (Apache-2.0) LoRaWAN Network Server developed and maintained by The Things Industries. The Things Stack v3 implements the full LoRaWAN Network Reference Model — Identity Server, Application Server, Network Server, Gateway Server, Join Server, Device Repository, Packet Broker Agent — and exposes a unified HTTP REST and gRPC API plus MQTT, webhooks, and Pub/Sub integrations. The same software powers self-hosted deployments, the free The Things Network community network, The Things Stack Cloud (Discovery, Standard, Plus tiers), and The Things Stack Enterprise.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/the-things-network/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/the-things-network/refs/heads/main/apis.yml)

## Scope

- **Access:** 3rd-Party

## Tags

- LoRaWAN
- IoT
- Internet Of Things
- Open Source
- Network Server
- LPWAN
- Telemetry
- Sensors
- Gateways
- Connectivity
- Apache 2.0

## APIs

### The Things Stack Identity Server

User, organization, OAuth client, API key, session, invitation, bookmark, notification, contact-info, and entity-search APIs. The Identity Server is the single source of truth for identity, access, and entity membership across the Things Stack.

- **Human URL:** [https://www.thethingsindustries.com/docs/api/reference/](https://www.thethingsindustries.com/docs/api/reference/)

#### Tags

- Identity
- OAuth
- Users
- Organizations
- Multi-Tenancy

#### Properties

- [Documentation](https://www.thethingsindustries.com/docs/api/reference/)
- [OpenAPI](openapi/the-things-stack-identity-server-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/the-things-stack-identity-server.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/the-things-stack-identity-server.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/the-things-stack-user-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/the-things-stack-organization-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/the-things-stack-api-key-schema.json) — [JSON Schema](https://json-schema.org/specification)

### The Things Stack Application Server

Application registry, application access rights, AppAs uplink/downlink/queue APIs, AsEndDeviceRegistry, payload-formatter management, ApplicationUpStorage (storage integration), and ApplicationPackages (LoRa Cloud DAS/GNSS/Modem, multicast, etc.). Owns the application-level data path.

- **Human URL:** [https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/application-server/](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/application-server/)

#### Tags

- Application Server
- LoRaWAN
- Uplink
- Downlink
- Payload Formatters
- Application Packages

#### Properties

- [Documentation](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/application-server/)
- [OpenAPI](openapi/the-things-stack-application-server-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/the-things-stack-application-server.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/the-things-stack-application-server.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/the-things-stack-application-up-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/the-things-stack-uplink-message-example.json)

### The Things Stack Network Server

NS-side end-device MAC state, ADR, MAC settings profiles, and the v1.1 LoRaWAN Relay configuration service (CtrlUplinkList, UpdateUplinkList, RelayForwardDownlinkReq). Handles deduplication, frame counter tracking, and gateway scheduling.

- **Human URL:** [https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/network-server/](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/network-server/)

#### Tags

- Network Server
- LoRaWAN MAC
- ADR
- MAC Settings
- Relay

#### Properties

- [Documentation](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/network-server/)
- [OpenAPI](openapi/the-things-stack-network-server-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/the-things-stack-network-server.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/the-things-stack-network-server.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### The Things Stack Gateway Server

Gateway registry, access, batch registry/access, Managed Gateway configuration (WiFi / Ethernet profiles), gateway claiming, gateway QR codes, Gs connection stats, and GtwGs/NsGs internal interfaces. Supports Semtech UDP packet forwarder, Basic Station (LBS), and MQTT v2/v3.

- **Human URL:** [https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/gateway-server/](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/gateway-server/)

#### Tags

- Gateway Server
- LoRaWAN
- Packet Forwarder
- Managed Gateways
- LBS
- UDP

#### Properties

- [Documentation](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/gateway-server/)
- [OpenAPI](openapi/the-things-stack-gateway-server-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/the-things-stack-gateway-server.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/the-things-stack-gateway-server.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/the-things-stack-gateway-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/the-things-stack-gateway-status-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/the-things-stack-gateway-create-example.json)

### The Things Stack Join Server

OTAA join handling, root-key registry, JsEndDeviceRegistry, AsJs/AppJs/NsJs internal interfaces, NetworkCryptoService and ApplicationCryptoService for external HSM-backed crypto, and ApplicationActivationSettings.

- **Human URL:** [https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/join-server/](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/join-server/)

#### Tags

- Join Server
- LoRaWAN
- OTAA
- Root Keys
- Crypto

#### Properties

- [Documentation](https://www.thethingsindustries.com/docs/the-things-stack/architecture/components/join-server/)
- [OpenAPI](openapi/the-things-stack-join-server-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/the-things-stack-join-server.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/the-things-stack-join-server.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### The Things Stack End Device Registry

EndDeviceRegistry, EndDeviceBatchRegistry, EndDeviceTemplateConverter, EndDeviceQRCodeGenerator, EndDeviceClaimingServer/BatchClaimingServer, and the DeviceRepository (LoRaWAN Device Repository search across vendors, models, firmware versions, profiles, and payload codecs).

- **Human URL:** [https://www.thethingsindustries.com/docs/devices/](https://www.thethingsindustries.com/docs/devices/)

#### Tags

- End Devices
- Device Repository
- Claiming
- QR Codes
- Templates

#### Properties

- [Documentation](https://www.thethingsindustries.com/docs/devices/)
- [OpenAPI](openapi/the-things-stack-end-device-registry-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/the-things-stack-end-device-registry.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/the-things-stack-end-device-registry.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/the-things-stack-end-device-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/the-things-stack-end-device-create-example.json)

### The Things Stack Integrations

Application Webhook and Application Pub/Sub registry APIs. Webhooks deliver uplink, join, ack/nack, queued, failed, location-solved, and service-data messages to HTTP(S) endpoints. Pub/Sub binds applications to NATS or MQTT brokers and AWS IoT / Azure IoT bridges.

- **Human URL:** [https://www.thethingsindustries.com/docs/integrations/](https://www.thethingsindustries.com/docs/integrations/)

#### Tags

- Webhooks
- Pub/Sub
- MQTT
- NATS
- AWS IoT
- Azure IoT

#### Properties

- [Documentation](https://www.thethingsindustries.com/docs/integrations/)
- [OpenAPI](openapi/the-things-stack-integrations-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/the-things-stack-integrations.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/the-things-stack-integrations.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/the-things-stack-application-webhook-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/the-things-stack-application-pubsub-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/the-things-stack-webhook-create-example.json)

### The Things Stack Packet Broker Agent

Packet Broker Agent (Pba) — info, register/deregister network, list networks/tenants/policies, set forwarder and home-network routing policies, manage gateway visibility. Enables LoRaWAN passive and peering roaming between networks running on the Packet Broker.

- **Human URL:** [https://www.thethingsindustries.com/docs/reference/packet-broker/](https://www.thethingsindustries.com/docs/reference/packet-broker/)

#### Tags

- Packet Broker
- Roaming
- LoRaWAN
- Networks

#### Properties

- [Documentation](https://www.thethingsindustries.com/docs/reference/packet-broker/)
- [OpenAPI](openapi/the-things-stack-packet-broker-agent-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/the-things-stack-packet-broker-agent.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/the-things-stack-packet-broker-agent.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### The Things Stack Events

Real-time event stream across the Identity Server, Application Server, Network Server, Gateway Server, and Join Server. Subscribe to events on applications, gateways, devices, users, organizations, and OAuth clients via gRPC streaming or HTTP server-sent events. Includes the NotificationService for in-app notifications.

- **Human URL:** [https://www.thethingsindustries.com/docs/reference/events/](https://www.thethingsindustries.com/docs/reference/events/)

#### Tags

- Events
- Streaming
- Observability
- Notifications

#### Properties

- [Documentation](https://www.thethingsindustries.com/docs/reference/events/)
- [OpenAPI](openapi/the-things-stack-events-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/the-things-stack-events.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/the-things-stack-events.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://www.thethingsnetwork.org)
- [Portal](https://www.thethingsindustries.com)
- [Documentation](https://www.thethingsindustries.com/docs/)
- [Documentation](https://www.thethingsindustries.com/docs/api/)
- [C L I](https://www.thethingsindustries.com/docs/api/reference/cli/)
- [Source Code](https://github.com/TheThingsNetwork/lorawan-stack)
- [Changelog](https://github.com/TheThingsNetwork/lorawan-stack/releases)
- [Source Code](https://github.com/TheThingsNetwork)
- [Source Code](https://github.com/TheThingsIndustries)
- [Source Code](https://github.com/TheThingsNetwork/lorawan-devices)
- [Source Code](https://github.com/TheThingsNetwork/lorawan-frequency-plans)
- [SDK](https://github.com/TheThingsNetwork/lorawan-webhook-templates)
- [Tools](https://github.com/TheThingsNetwork/lorawan-stack-migrate)
- [Community](https://www.thethingsnetwork.org/forum/)
- [Community](https://www.thethingsnetwork.org/community)
- [Portal](https://console.cloud.thethings.network)
- [Events](https://www.thethingsindustries.com/docs/the-things-stack/management/events/)
- [Rate Limits](https://www.thethingsindustries.com/docs/reference/rate-limiting/)
- [Documentation](https://www.thethingsindustries.com/docs/the-things-stack/installation/)
- [Status Page](https://status.thethingsindustries.com/)
- [License](https://github.com/TheThingsNetwork/lorawan-stack/blob/v3.36/LICENSE)
- [Plans](https://www.thethingsindustries.com/stack/plans/)
- [Plans](plans/the-things-network-plans-pricing.yml)
- [Rate Limits](rate-limits/the-things-network-rate-limits.yml)
- [Fin Ops](finops/the-things-network-finops.yml)
- [Vocabulary](vocabulary/the-things-network-vocabulary.yml)
- [JSON-LD](json-ld/the-things-network-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [JSON Structure](json-structure/the-things-network-structure.json)
- [Spectral Rules](rules/the-things-network-rules.yml) — [Spectral](https://docs.stoplight.io/docs/spectral)
- [LinkedIn](https://www.linkedin.com/company/the-things-industries/)
- [Twitter](https://twitter.com/thethingsntwrk)
- [Standard](https://www.lora-alliance.org/)
