---
name: nutshell-price-a-lead-with-products
description: Attach catalogue products to a Nutshell lead, adjust quantity and price through product maps, and set an installment schedule.
api: nutshell:rest-api
base_url: https://app.nutshell.com/rest
generated: '2026-08-13'
method: generated
source: openapi/_original/nutshell-api.json
operations:
  - 09a50065f621a61a55b5bc5c0df3f338  # GET /products — List all products
  - 5a47a634e21ffbad6a5c268af67a63ae  # PATCH /leads/{id} — Update a lead
  - 4bc737ff6f91aab43dc7617f2c36ab3c  # GET /productmaps — Get lead products
  - 741f6e4eb5abcbdfc94754dd76257d9e  # GET /productmaps/{id} — Get lead product
  - 427685c90f14ed7ca22515715a03b4e4  # PATCH /productmaps/{id} — Update a lead's product information
  - 7aa410de8a00f46edf22043fee324e39  # DELETE /productMaps/{id} — Delete a product on a lead
  - 7c4277bf7ac3a1e50fb98c713565bc36  # GET /leads/{id}/installments — Get installments for a lead
  - 32aed6101ab1c412a24275e076aaba1f  # POST /leads/{id}/installments — Update installments for a lead
---

# Price a Nutshell lead with products

Lead value is **calculated from the products attached to the lead**, not set directly — unless you
override it. The join record between a product and a lead is a **product map**, and it carries the
quantity and any custom price.

## Steps

1. **Find the product.** `GET /products` (operationId `09a50065f621a61a55b5bc5c0df3f338`).
2. **Attach it to the lead** with a JSON Patch add:

   ```json
   [ { "op": "add", "path": "/leads/0/links/products/-", "value": "3-products" } ]
   ```

   `PATCH /leads/{id}` (operationId `5a47a634e21ffbad6a5c268af67a63ae`),
   `Content-Type: application/json-patch+json`.
3. **Find the product map id.** Re-read the lead and take `links.productMaps[]`, or call
   `GET /productmaps` (operationId `4bc737ff6f91aab43dc7617f2c36ab3c`) /
   `GET /productmaps/{id}` (operationId `741f6e4eb5abcbdfc94754dd76257d9e`).
4. **Change quantity or price** on the map, not on the product:

   ```json
   [ { "op": "replace", "path": "/productMaps/0/quantity", "value": "5" } ]
   ```

   `PATCH /productmaps/{id}` (operationId `427685c90f14ed7ca22515715a03b4e4`).
   Note the body path uses camelCase `productMaps` while the URL path is lowercase `productmaps`.
5. **Remove a product** with `DELETE /productMaps/{id}` (operationId `7aa410de8a00f46edf22043fee324e39`).
6. **Override the total** if you must: patch `/leads/0/manualValue` with the amount **as a string**, or
   patch `/leads/0/valueToProductMode` with no value to hand control back to the product sum.
7. **Schedule payments.** `GET /leads/{id}/installments`
   (operationId `7c4277bf7ac3a1e50fb98c713565bc36`) and
   `POST /leads/{id}/installments` (operationId `32aed6101ab1c412a24275e076aaba1f`).
   The POST **replaces** the whole schedule with the array you send — objects of
   `id`, `dueTime` (ISO 8601), `description`, `value`, `isFailed`. Lead installments require the
   feature on the account plan; expect a failure if it is not enabled.

## Gotchas

- `/productmaps/{id}` and `/productMaps/{id}` both exist in the published spec — GET/PATCH use the
  lowercase path and DELETE uses the camelCase one. Do not normalise the casing.
- Money is an object (`amount`, `currency`, `formatted`), not a number.
