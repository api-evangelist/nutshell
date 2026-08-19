---
name: nutshell-quote-to-invoice
description: Take a Nutshell quote through its status transitions and duplicate it into an invoice, then mark the invoice paid.
api: nutshell:rest-api
base_url: https://app.nutshell.com/rest
generated: '2026-08-13'
method: generated
source: openapi/_original/nutshell-api.json
operations:
  - 1aee48fe1472d38116c60c87e2ca4161  # GET /quotes — Get a list of quotes
  - 4c251930a518927960cce7d1211a0945  # GET /quotes/{id} — Get a quote
  - 9809f001604e5cbe8f478e14b6ec6295  # POST /quotes/{id}/status — Update the status of a quote
  - 8ce989ecb071d43420747aa852f155db  # POST /quotes/{id}/invoice — Create an invoice from a quote
  - 44a63cb9277feafb979ccef9038cd6d5  # GET /invoices — Get a list of invoices
  - b9c9d23692da5d58d025a29911416b8f  # GET /invoices/{id} — Get an invoice
  - d35e25a23af6446bdc10dffb07a59c79  # POST /invoices/{id}/status — Update the status of an invoice
---

# Quote to invoice in Nutshell

Quotes and invoices share one status vocabulary: **READY, SENT, REVOKED, ACCEPTED, ARCHIVED**.

## Steps

1. **Find the quote.** `GET /quotes` (operationId `1aee48fe1472d38116c60c87e2ca4161`) or
   `GET /quotes/{id}` (operationId `4c251930a518927960cce7d1211a0945`).
2. **Move it along.** `POST /quotes/{id}/status` (operationId `9809f001604e5cbe8f478e14b6ec6295`) with one
   of the five native statuses. Nutshell's own note: fulfilment states from an external ERP (its docs name
   Odoo) belong in lead custom fields, not in the quote status.
3. **Create the invoice from the quote.** `POST /quotes/{id}/invoice`
   (operationId `8ce989ecb071d43420747aa852f155db`). **No request body is required** — it duplicates the
   quote exactly as the in-app action does. Line items, recipient and most document fields are copied;
   payment, body and footer fields come from the invoice template defaults.
4. **Mark it paid.** `POST /invoices/{id}/status` (operationId `d35e25a23af6446bdc10dffb07a59c79`).
   **ACCEPTED means paid.** An optional `comment` is stored as payment/completion metadata.
5. **Verify.** `GET /invoices/{id}` (operationId `b9c9d23692da5d58d025a29911416b8f`).

## Gotchas

- Step 3 has no idempotency protection and no body to deduplicate on. Re-posting creates a **second
  invoice**. Read `GET /invoices` filtered to the lead before retrying.
- Proposals and invoices are a paid add-on ($79/month at the time of writing). On an account without it
  these endpoints will not be usable.
