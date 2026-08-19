---
title: Item calculations and validations
deprecated: false
hidden: false
metadata:
  robots: index
---
## Item data

### Creation

- `commodity_code`: one of `G` (Goods), `S` (Services), `B` (Both).
- `hs_code`: required for `G`/`B`; must NOT be set for `S`.
- `service_accounting_code`: required for `S`/`B`; must NOT be set for `G`.
- `standard_item_scheme`: valid ISO ICD 6523 scheme identifier.
- `origin_country_code`: valid ISO 3166-1 alpha-2.
- `tax_category_code`: one of `S, E, O, AE, Z, N`.
- Returns `AlreadyExists` if `item_code` already exists for the branch.
- **AE (reverse charge) note**: an item used on an invoice with tax category `AE` must have `standard_item_id` + `standard_item_scheme = 0160` (GS1/GLN) — checked **at invoice creation time**, not at item creation.

### Update

Only `name`/`description` can change; there are no format constraints on either.

## **Line items** (per item on an invoice/credit note)

- `item_id` must reference an existing item in the branch; no duplicates in the same request.
- `quantity` must be > 0; `price_amount` must be ≥ 0 (0 valid for free goods).
- `gross_price`/`price_discount`, if either set → `price_amount = gross_price − price_discount`.
- `unit_of_measure_code` must be valid.
- `item_nature_code` required when `tax_category_code = AE`; must be a valid goods type code.
- `tax_exemption_reason_code` required when `tax_exemption_reason` set.
- Item-level allowances/charges: `tax_category_code` must **not** be set (only doc-level A/Cs carry a category); same `base_amount × multiplier_rate = amount` and reason-code rules as doc-level.
