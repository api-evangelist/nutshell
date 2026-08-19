---
name: nutshell-sync-crm-changes
description: Keep an external system in step with Nutshell using the events change-log feed, the deletion feed and the webhook firehose.
api: nutshell:rest-api
base_url: https://app.nutshell.com/rest
generated: '2026-08-13'
method: generated
source: openapi/_original/nutshell-api.json + https://developers.nutshell.com/docs/working-with-webhooks
operations:
  - 975fac2bed2a6a346717a88cfcdb9324  # GET /events — Get a list of events
  - eade9331abb11f33feaeb9e9d8ae89a7  # GET /events/deleted — Get deletion events
  - 8e55836889bb7d432d5fe3d9bfe608b7  # GET /leads/{id} — Get a lead
  - 8a291bf9a1a7e4a7fd1ca0cabfdaa8a7  # GET /contacts/{id} — Get a contact
  - e011fe1a74d2ca75e6294040b98423f1  # GET /accounts/{id} — Get an account
---

# Sync Nutshell changes into another system

Nutshell gives you two ways to learn that something changed, and they are not equivalent.

## Push: the webhook firehose

- Subscriptions are created **in the Nutshell UI only** (Setup > API keys). There is no API to register
  a webhook, so this cannot be provisioned programmatically.
- You cannot subscribe to specific event types. Every webhook receives **all** events; filter your side.
- Nutshell says its documented event list is partial and it biases toward emitting more.
- Nutshell's own advice: treat the payload as a **prompt that something changed**, then re-fetch the
  entity over REST. Do not build on the fields inside the hook.
- The envelope is `meta` / `links` / `events` / `actors` / `payloads`. Read `events[].action`,
  `events[].actorType` and `events[].payloadType` to decide what happened, then follow
  `events[].links.payloads` to the changed ids.
- No signature-verification scheme and no retry policy are documented. Treat the endpoint as
  unauthenticated input and validate everything.

## Pull: the events feed

- `GET /events` (operationId `975fac2bed2a6a346717a88cfcdb9324`) is the same change-log that powers
  notifications and timelines.
- `GET /events/deleted` (operationId `eade9331abb11f33feaeb9e9d8ae89a7`) is a **separate** feed. Deletions
  will not appear in the main feed — poll both or you will silently keep tombstoned records.
- Filter by time with the documented timespan grammar, e.g.
  `filter[createdTime]=2025-03-01T00:00:00 TO 2025-03-15T23:59:59`.

## Re-fetch

Follow up with `GET /leads/{id}`, `GET /contacts/{id}` or `GET /accounts/{id}`. Ids can be comma-joined
in one path segment to batch the read: `/rest/contacts/3-contacts,55-contacts`.

## Constraints to design around

- **No pagination is documented** and the spec declares no cursor or page parameters. For large
  instances use saved filters (`GET /filters`, operationId `9bbf17f9beb5e7eebe638a634e861945`) and the
  `/leads/list`, `/contacts/list` and `/accounts/list` list-item endpoints to bound the result set.
- **No rate limits are published** and no `RateLimit-*` or `Retry-After` headers are returned. Choose a
  conservative poll interval and back off on any non-2xx.
