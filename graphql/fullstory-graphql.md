# FullStory GraphQL Schema

## Overview

This is a conceptual GraphQL schema for the FullStory digital experience analytics platform. It is derived from the public FullStory developer documentation, covering the Server-Side API v2, Sessions API, Segments Export API, and Webhooks API.

Reference: [https://developer.fullstory.com/](https://developer.fullstory.com/)

The schema is not an officially published FullStory GraphQL endpoint. It models the platform's core domain concepts as GraphQL types to support tooling, documentation, and integration design.

## Schema Source

- **Primary docs:** https://developer.fullstory.com/
- **GitHub org:** https://github.com/fullstorydev
- **Server API base URL:** https://api.fullstory.com
- **Schema file:** [fullstory-schema.graphql](fullstory-schema.graphql)

## Type Summary

| Category | Types |
|---|---|
| Authentication | APIKey, Token, DataCenter |
| Device / Environment | Browser, OperatingSystem, DeviceInfo, UserAgent |
| Page / URL | PageURL, PageVisit |
| Events | EventType, Event (interface), ClickEvent, ScrollEvent, InputEvent, NavigateEvent, CustomEvent |
| Errors | Error (interface), ConsoleError, NetworkError, CrashEvent, StackFrame |
| User Identity | UserIdentity, UserAttributes, CustomProperties, User |
| Sessions | SessionID, RecordingStatus, Session, SessionReplay |
| Recordings | Recording, RecordingSegment, RecordingData |
| DOM Elements | ElementClass, ElementSelector, CSSSector, Element |
| Segments | LogicalOperator, ComparisonOperator, Condition, ConditionGroup, UserField, EventField, PageField, SegmentDefinition, SegmentRule, Segment |
| Funnels | FunnelStep, Funnel, ConversionMetric |
| Heatmaps | HeatZone, HeatMap, ClickMap, ClickMapElement, ScrollMap, ScrollBucket |
| Insights | Insight, MetricReport, DashboardPanel, Dashboard |
| Webhooks | WebhookEvent, OmniChannel |
| Operations | Query, Mutation |

**Total named types: 62**

## Key Domain Concepts

### Sessions and Replays

The `Session` type is the central entity. Each session belongs to a `User`, carries `DeviceInfo` and `UserAgent` metadata, and contains a sequence of `PageVisit` records and `Event` records. A `SessionReplay` links to the FullStory replay player URL and exposes replay availability status via `RecordingStatus`.

### Events

Events implement the `Event` interface and are discriminated by `EventType`. The schema covers the primary interaction events (click, scroll, input, navigate) as well as developer-defined `CustomEvent` records sent through the Server API.

### Errors

The `Error` interface covers three error categories FullStory captures automatically: `ConsoleError` (JavaScript console.error), `NetworkError` (failed network requests), and `CrashEvent` (application crashes with stack traces).

### Users

Users are identified via `UserIdentity` using a developer-assigned `uid`. Arbitrary attributes are attached as `UserAttributes` key-value pairs. The schema also exposes `CustomProperties` for org-level property registration.

### Segments

Segments group users by shared behaviour using a tree of `ConditionGroup` and `Condition` nodes combined with `AND`/`OR` logical operators. Each condition targets a `UserField`, `EventField`, or `PageField` with a `ComparisonOperator`.

### Funnels

Funnels chain ordered `FunnelStep` records, each backed by an event type and optional conditions. The funnel exposes aggregate `conversionRate` and per-step dropout counts.

### Heatmaps

`HeatMap`, `ClickMap`, and `ScrollMap` aggregate interaction data at the page level. Click maps resolve interactions to individual `Element` records identified by `ElementSelector` and `CSSSector`.

### Webhooks and OmniChannel

`WebhookEvent` represents a push notification delivered to a subscriber. `OmniChannel` models destination integrations (Slack, data warehouses, CDPs, etc.) registered in the FullStory platform.

## Example Query

```graphql
query GetSessionWithEvents($sessionId: ID!) {
  session(id: $sessionId) {
    id {
      value
      orgId
    }
    user {
      identity {
        uid
        email
        displayName
      }
    }
    startedAt
    durationMs
    replay {
      replayUrl
      status
      availableUntil
    }
    events(types: [CLICK, NAVIGATE, CUSTOM]) {
      id
      type
      timestamp
      ... on ClickEvent {
        x
        y
        targetText
        element {
          tag
          selector {
            css
          }
        }
      }
      ... on NavigateEvent {
        fromUrl { href }
        toUrl { href }
      }
      ... on CustomEvent {
        name
        properties
      }
    }
    errors {
      id
      message
      timestamp
      ... on NetworkError {
        url
        statusCode
        method
      }
      ... on ConsoleError {
        stack
      }
    }
  }
}
```

## Example Mutation

```graphql
mutation IdentifyUser($uid: String!, $attrs: JSON) {
  identifyUser(uid: $uid, attributes: $attrs) {
    id
    identity {
      uid
      email
      displayName
    }
    updatedAt
  }
}
```
