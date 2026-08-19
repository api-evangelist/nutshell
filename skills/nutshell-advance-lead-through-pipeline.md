---
name: nutshell-advance-lead-through-pipeline
description: Move a Nutshell lead across a pipeline (stageset), inspect its stage history, and close it won, lost or cancelled with an outcome.
api: nutshell:rest-api
base_url: https://app.nutshell.com/rest
generated: '2026-08-13'
method: generated
source: openapi/_original/nutshell-api.json
operations:
  - 7e925de7233253ea915fdf486fb23321  # GET /stagesets — Get a list of pipelines
  - 14af5dd687ab31f65e5af1a2b1fa5527  # GET /stages — Get a list of stages
  - ac69339d38f3809791db2340e47bff9b  # POST /leads/{id}/stageset — Set the pipeline for a lead
  - 3cc07d39be52c9a287e147e138f88446  # GET /leads/{id}/stages — Get all stages associated with lead
  - 023ebfb59f2c7fe37eb81dc618d24af0  # GET /outcomes — Get a list of lead outcomes
  - 74bb9b0e446b6a0a9913e5b8f8bca628  # POST /leads/{id}/status — Update the status of a lead
  - 104d97bbcf04ea8a2ac72428fbdaa10b  # POST /leads/{id}/reopen — Reopen a lead
  - cb65d8c1aa9bba020e669ab84d846887  # POST /leads/{id}/watch — Watch a lead
---

# Advance a lead through a Nutshell pipeline

Nutshell calls pipelines **stagesets**. A lead belongs to one stageset and sits in one of its stages.

## Steps

1. **List the pipelines.** `GET /stagesets` (operationId `7e925de7233253ea915fdf486fb23321`).
2. **List the stages.** `GET /stages` (operationId `14af5dd687ab31f65e5af1a2b1fa5527`) to find the stage
   ids belonging to the pipeline you picked.
3. **Assign the lead to a pipeline.** `POST /leads/{id}/stageset`
   (operationId `ac69339d38f3809791db2340e47bff9b`).
4. **Read the stage history.** `GET /leads/{id}/stages`
   (operationId `3cc07d39be52c9a287e147e138f88446`) returns every stage the lead has occupied, including
   how long it spent in each — this is the input for cycle-time analysis, not a plain current-stage read.
5. **Close the lead.** `GET /outcomes` (operationId `023ebfb59f2c7fe37eb81dc618d24af0`) to resolve a valid
   outcome, then `POST /leads/{id}/status` (operationId `74bb9b0e446b6a0a9913e5b8f8bca628`) to set won,
   lost or cancelled. The same call accepts the outcome and the competitor/product maps.
6. **Reopen if the deal comes back.** `POST /leads/{id}/reopen` (operationId `104d97bbcf04ea8a2ac72428fbdaa10b`).
7. **Optionally follow it.** `POST /leads/{id}/watch` (operationId `cb65d8c1aa9bba020e669ab84d846887`)
   subscribes **the authenticated user** — you cannot watch on behalf of someone else.

## Reporting

`GET /stagesets/{id}/export` (operationId `add7f9ef66629fa4ccee5dcc0479795b`) returns a **CSV** export of
lead movement through a pipeline. It is the only non-JSON response on the API — do not send it to a JSON parser.

## Gotchas

- A lead's user-facing **number** (`Lead-1001`) is not its **id**. The object carries both.
- There is no idempotency key: re-POSTing a status change is not safe to retry blindly.
