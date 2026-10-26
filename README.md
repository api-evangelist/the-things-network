# The Things Network / The Things Stack (the-things-network)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
