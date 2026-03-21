# FullStory (fullstory)
FullStory is a digital experience intelligence platform that captures and analyzes user interactions across websites and mobile apps. Their developer platform provides server-side APIs, client SDKs, and webhook integrations for programmatically managing user data, exporting behavioral segments, retrieving session replays, and building event-driven workflows.

**URL:** [Visit APIs.json URL](https://raw.githubusercontent.com/api-evangelist/fullstory/refs/heads/main/apis.yml)

## Scope

- **Type:** Contract
- **Position:** Consuming
- **Access:** 3rd-Party

## Tags:

 - Analytics, Digital Experience, Session Replay, Webhooks, Data Export

## Timestamps

- **Created:** 2026-03-20
- **Modified:** 2026-03-20

## APIs

### FullStory Server API
The FullStory Server API is a RESTful API that enables developers to programmatically send user and event data to FullStory. It supports creating and updating individual users, batch importing users, sending server-side events, and batch importing events. The API uses JSON for request and response bodies and authenticates via API keys. Developers can use it to enrich FullStory session data with server-side context that is not available in the browser or mobile app.

**Human URL:** [https://developer.fullstory.com/server/getting-started/](https://developer.fullstory.com/server/getting-started/)


#### Tags:

 - Analytics, Digital Experience, Users, Events, Session Replay

#### Properties

- [Documentation](https://developer.fullstory.com/server/getting-started/)
- [OpenAPI](openapi/fullstory-server-api-openapi.yml)

### FullStory Segments Export API
The FullStory Segments Export API provides an asynchronous workflow for downloading captured event data from FullStory. Developers can initiate export jobs to aggregate segment data, query for the status of running jobs, and retrieve download URLs for completed exports. Two types of segment data are available for export: individuals matching a segment and events performed by those individuals. This API is useful for integrating FullStory behavioral data into external analytics pipelines and data warehouses.

**Human URL:** [https://developer.fullstory.com/server/v1/segments/create-segment-export/](https://developer.fullstory.com/server/v1/segments/create-segment-export/)


#### Tags:

 - Analytics, Data Export, Segments, Digital Experience

#### Properties

- [Documentation](https://developer.fullstory.com/server/v1/segments/create-segment-export/)
- [OpenAPI](openapi/fullstory-segments-export-api-openapi.yml)

### FullStory Sessions API
The FullStory Sessions API allows developers to retrieve session replay URLs for specific users. By querying with a user email address or user ID, the API returns a list of session URLs that can be used to view recorded sessions in the FullStory platform. This is particularly useful for building integrations that link customer support tickets, CRM records, or other tools directly to relevant FullStory session replays.

**Human URL:** [https://developer.fullstory.com/server/getting-started/](https://developer.fullstory.com/server/getting-started/)


#### Tags:

 - Sessions, Session Replay, Analytics, Digital Experience

#### Properties

- [Documentation](https://developer.fullstory.com/server/getting-started/)
- [OpenAPI](openapi/fullstory-sessions-api-openapi.yml)

### FullStory Webhooks API
The FullStory Webhooks API enables developers to create, update, retrieve, and manage webhook endpoints that receive real-time notifications from FullStory. Supported event types include segment creation, segment threshold alerts, and custom event notifications. Webhooks allow event-driven integrations that respond immediately to behavioral signals detected by FullStory, eliminating the need for polling and enabling automated workflows based on user activity patterns.

**Human URL:** [https://developer.fullstory.com/destinations/v1/webhooks/getting-started/](https://developer.fullstory.com/destinations/v1/webhooks/getting-started/)


#### Tags:

 - Webhooks, Events, Notifications, Segments

#### Properties

- [Documentation](https://developer.fullstory.com/destinations/v1/webhooks/getting-started/)
- [OpenAPI](openapi/fullstory-webhooks-api-openapi.yml)
- [AsyncAPI](asyncapi/fullstory-webhooks-asyncapi.yml)

### FullStory Browser SDK
The FullStory Browser SDK is a JavaScript library that enables developers to manage FullStory data capture on websites, retrieve deep links to session replays, and send custom events. It provides functions for identifying users, setting user properties, tracking custom events with the FS.event API, and generating session replay URLs for integration with other platforms. The SDK supports privacy controls, consent management, and selective data capture to help developers comply with data protection requirements.

**Human URL:** [https://developer.fullstory.com/](https://developer.fullstory.com/)


#### Tags:

 - JavaScript, Browser, Data Capture, Session Replay, Custom Events

#### Properties

- [Documentation](https://developer.fullstory.com/)

## Common Properties

- [Portal](https://developer.fullstory.com/)
- [Documentation](https://developer.fullstory.com/server/getting-started/)
- [Website](https://www.fullstory.com/)
- [PrivacyPolicy](https://www.fullstory.com/legal/privacy-policy/)
- [TermsOfService](https://www.fullstory.com/legal/terms-and-conditions/)
- [Support](https://help.fullstory.com/)
- [Blog](https://www.fullstory.com/blog/)
- [Login](https://app.fullstory.com/login)

## Maintainers

**FN:** API Evangelist

**Email:** info@apievangelist.com
