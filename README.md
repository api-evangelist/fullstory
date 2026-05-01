# FullStory (fullstory)

FullStory is a digital experience intelligence platform that captures and analyzes user interactions across websites and mobile apps. The FullStory developer platform exposes server-side REST APIs for sending user and event data, exporting behavioral segments, retrieving session replay URLs, and managing webhook destinations, plus a Browser SDK for client-side data capture and custom events.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/fullstory/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Consumer
- **Access:** 3rd-Party

## Tags

- Analytics
- Digital Experience
- Session Replay
- Webhooks
- Data Export

## Timestamps

- **Created:** 2026-03-20
- **Modified:** 2026-04-28

## APIs

### FullStory Server API

The FullStory Server API is a RESTful API that enables developers to programmatically send user and event data to FullStory. It supports creating and updating individual users, batch importing users, sending server-side events, and batch importing events. The API uses JSON for request and response bodies and authenticates via API keys. Developers can use it to enrich FullStory session data with server-side context that is not available in the browser or mobile app.

**Human URL:** https://developer.fullstory.com/server/getting-started/

**Base URL:** `https://api.fullstory.com`

#### Tags

- Analytics, Digital Experience, Users, Events, Session Replay

#### Properties

- [Documentation](https://developer.fullstory.com/server/getting-started/)
- [OpenAPI](openapi/fullstory-server-api-openapi.yml)

### FullStory Segments Export API

The FullStory Segments Export API provides an asynchronous workflow for downloading captured event data from FullStory. Developers can initiate export jobs to aggregate segment data, query for the status of running jobs, and retrieve download URLs for completed exports. Two types of segment data are available for export: individuals matching a segment and events performed by those individuals.

**Human URL:** https://developer.fullstory.com/server/v1/segments/create-segment-export/

**Base URL:** `https://api.fullstory.com`

#### Tags

- Analytics, Data Export, Digital Experience, Segments

#### Properties

- [Documentation](https://developer.fullstory.com/server/v1/segments/create-segment-export/)
- [OpenAPI](openapi/fullstory-segments-export-api-openapi.yml)

### FullStory Sessions API

The FullStory Sessions API allows developers to retrieve session replay URLs for specific users. By querying with a user email address or user ID, the API returns a list of session URLs that can be used to view recorded sessions in the FullStory platform. This is particularly useful for building integrations that link customer support tickets, CRM records, or other tools directly to relevant FullStory session replays.

**Human URL:** https://developer.fullstory.com/server/getting-started/

**Base URL:** `https://api.fullstory.com`

#### Tags

- Analytics, Digital Experience, Session Replay, Sessions

#### Properties

- [Documentation](https://developer.fullstory.com/server/getting-started/)
- [OpenAPI](openapi/fullstory-sessions-api-openapi.yml)

### FullStory Webhooks API

The FullStory Webhooks API enables developers to create, update, retrieve, and manage webhook endpoints that receive real-time notifications from FullStory. Supported event types include segment creation, segment threshold alerts, and custom event notifications. Webhooks allow event-driven integrations that respond immediately to behavioral signals detected by FullStory, eliminating the need for polling and enabling automated workflows based on user activity patterns.

**Human URL:** https://developer.fullstory.com/destinations/v1/webhooks/getting-started/

**Base URL:** `https://api.fullstory.com`

#### Tags

- Events, Notifications, Segments, Webhooks

#### Properties

- [Documentation](https://developer.fullstory.com/destinations/v1/webhooks/getting-started/)
- [OpenAPI](openapi/fullstory-webhooks-api-openapi.yml)
- [AsyncAPI](asyncapi/fullstory-webhooks-asyncapi.yml)

### FullStory Browser SDK

The FullStory Browser SDK is a JavaScript library that enables developers to manage FullStory data capture on websites, retrieve deep links to session replays, and send custom events. It provides functions for identifying users, setting user properties, tracking custom events with the FS.event API, and generating session replay URLs for integration with other platforms.

**Human URL:** https://developer.fullstory.com/browser/getting-started/

#### Tags

- Browser, Custom Events, Data Capture, JavaScript, Session Replay

#### Properties

- [Documentation](https://developer.fullstory.com/browser/getting-started/)
- [Distribution: @fullstory/browser](https://www.npmjs.com/package/@fullstory/browser)

## Artifacts

| Type | File | Description |
|------|------|-------------|
| OpenAPI | [openapi/fullstory-server-api-openapi.yml](openapi/fullstory-server-api-openapi.yml) | Server API for users and events |
| OpenAPI | [openapi/fullstory-segments-export-api-openapi.yml](openapi/fullstory-segments-export-api-openapi.yml) | Async segment export jobs |
| OpenAPI | [openapi/fullstory-sessions-api-openapi.yml](openapi/fullstory-sessions-api-openapi.yml) | Session replay URL lookup |
| OpenAPI | [openapi/fullstory-webhooks-api-openapi.yml](openapi/fullstory-webhooks-api-openapi.yml) | Webhook destination management |
| AsyncAPI | [asyncapi/fullstory-webhooks-asyncapi.yml](asyncapi/fullstory-webhooks-asyncapi.yml) | Webhook event payloads |
| JSON Schema | [json-schema/fullstory-user-schema.json](json-schema/fullstory-user-schema.json) | User payload |
| JSON Schema | [json-schema/fullstory-event-schema.json](json-schema/fullstory-event-schema.json) | Event payload |
| JSON Schema | [json-schema/fullstory-segment-schema.json](json-schema/fullstory-segment-schema.json) | Segment payload |
| JSON Schema | [json-schema/fullstory-session-schema.json](json-schema/fullstory-session-schema.json) | Session payload |
| JSON Schema | [json-schema/fullstory-webhook-endpoint-schema.json](json-schema/fullstory-webhook-endpoint-schema.json) | Webhook endpoint configuration |
| JSON-LD | [json-ld/fullstory-context.jsonld](json-ld/fullstory-context.jsonld) | Linked data context for FullStory entities |

## Common Properties

- [Website](https://www.fullstory.com/)
- [Portal](https://developer.fullstory.com/)
- [Documentation](https://developer.fullstory.com/server/getting-started/)
- [Login](https://app.fullstory.com/login)
- [Support](https://help.fullstory.com/)
- [Blog](https://www.fullstory.com/blog/)
- [PrivacyPolicy](https://www.fullstory.com/legal/privacy-policy/)
- [TermsOfService](https://www.fullstory.com/legal/terms-and-conditions/)

## Maintainers

**FN:** Kin Lane

**Email:** kin@apievangelist.com
