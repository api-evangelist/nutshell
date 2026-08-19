---
name: nutshell-capture-inbound-lead
description: Turn an inbound enquiry into a Nutshell company, person and lead, attributed to a source and tagged, using the Nutshell REST API.
api: nutshell:rest-api
base_url: https://app.nutshell.com/rest
generated: '2026-08-13'
method: generated
source: openapi/_original/nutshell-api.json
operations:
  - 0e0199fef8e93c05437d3a33104886d1  # POST /accounts — Create an account
  - 376a09558c05d3d4d273459f15a57326  # POST /contacts — Create a contact
  - 7d9961f8fbd457ba5670721926517135  # POST /leads — Create a lead
  - 2d07cb07b45de2ae13701b873b26cf9e  # GET /sources — Get a list of sources
  - cd431c40f2b57127c71b15044d270a13  # POST /sources — Create a new source
  - 422aa2c0d6493b41248e46c6ac93a43b  # GET /tags — Get a list of tags
  - 5a47a634e21ffbad6a5c268af67a63ae  # PATCH /leads/{id} — Update a lead
---

# Capture an inbound lead in Nutshell

Nutshell's three core entities are **accounts** (Companies in the UI), **contacts** (People) and
**leads**. An inbound enquiry usually needs all three, linked together.

## Before you start

- Authenticate with HTTP Basic: username is a Nutshell user's **email address**, password is an
  **API key** from Setup > API keys. Everything is HTTPS-only under `app.nutshell.com`.
- Nutshell ids look like `3-accounts`, `55-contacts`, `1003-leads`. Prefer that form over bare integers.
- There is **no idempotency key**. A retried POST creates a duplicate record. Check before you create.

## Steps

1. **Look for an existing company first.** `GET /accounts?filter[name][]=<company name>`
   (operationId `ee7a9535ab7ae30da91d6d9cebe2ed85`). The filter grammar is documented at
   https://developers.nutshell.com/docs/filters.
2. **Create the company if it is new.** `POST /accounts`
   (operationId `0e0199fef8e93c05437d3a33104886d1`) with an entity-keyed array body:
   `{"accounts":[{"name":"My first company"}]}`. Only one record per request.
   Keep the returned `id` (e.g. `3-accounts`).
3. **Create the person.** `POST /contacts` (operationId `376a09558c05d3d4d273459f15a57326`).
   Only one contact may be created at a time.
4. **Resolve the source.** `GET /sources` (operationId `2d07cb07b45de2ae13701b873b26cf9e`) and reuse an
   existing id; only `POST /sources` (operationId `cd431c40f2b57127c71b15044d270a13`) when the channel
   genuinely does not exist yet — sources are a small controlled vocabulary, not free text.
5. **Create the lead.** `POST /leads` (operationId `7d9961f8fbd457ba5670721926517135`). Only one lead
   can be created per request.
6. **Link and tag with JSON Patch.** `PATCH /leads/{id}` (operationId `5a47a634e21ffbad6a5c268af67a63ae`)
   with `Content-Type: application/json-patch+json`:

   ```json
   [
     { "op": "add", "path": "/leads/0/links/contacts/-", "value": "55-contacts" },
     { "op": "add", "path": "/leads/0/links/tags/-", "value": "15-tags" }
   ]
   ```

   The trailing `/-` is required on every `add`. The `0` index is Nutshell's convention, not a record offset.
   Tags are entity-specific: a tag created for leads cannot be applied to a contact or account.

## Failure handling

- `400` is the only error the spec declares and it has no body. It almost always means a malformed
  JSON Patch document — wrong `op`, wrong `path`, or a missing `/-` on an `add`.
- `401` returns an **HTML** body, not JSON. Do not parse the error as JSON.
- Capture the `x-nutshell-request-id` response header and quote it in any support ticket.
