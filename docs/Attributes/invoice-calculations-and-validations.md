---
title: Invoice calculations and validations
deprecated: false
hidden: false
metadata:
  robots: index
---
**Core document fields**

- `document_currency_code`: valid ISO 4217; `tax_currency_exchange_rate` required (>0, ≤6 decimals) when currency ≠ AED, must be 1/omitted when AED.
- `issue_date`: not future, not >30 days past, evaluated in Asia/Dubai time.
- `due_date`: required when the payable amount > 0, unless `DEEMED_SUPPLY`.&#x20;
- `tax_point_date`: must be before `issue_date`.
- `trader_invoice_number`: unique per branch (checked in-app + DB unique constraint, race-safe).
- `note`: required when `invoice_period.billing_frequency_code = OTH`.
- `beneficiary_trn` / `principle_trn`: valid TRN; required by `FREE_TRADE_ZONE`/`AGENT_BILLING` respectively; principle TRN must differ from the branch's own TRN.
- `customer_party_id` / `payee_party_id` / `tax_representative_party_id` / `supplier_id`: must reference existing entities in the branch. (`tax_representative_party_id` check is correctly implemented but has no dedicated test.)
- `payments`: at least one entry required, except `DEEMED_SUPPLY`.

**Invoice type codes**

- `380` Commercial Invoice: must have at least one item that isn't E/O.
- `480` Out-of-Scope Invoice: items + doc-level A/Cs restricted to E/O/Z; buyer must have `company_id`; forbidden with `SUMMARY_INVOICE`/`DEEMED_SUPPLY`/`PROFIT_MARGIN_SCHEME`.
- `389` — see **Self-Billed Invoices** below.

**Transaction types** (combinable) — `FREE_TRADE_ZONE`, `AGENT_BILLING`, `SUMMARY_INVOICE`, `CONTINUOUS_SUPPLY`, `EXPORTS` (forbidden with `PROFIT_MARGIN_SCHEME`), `SUPPLY_THROUGH_ECOMMERCE`, `PROFIT_MARGIN_SCHEME` (forbidden with `EXPORTS`/type 480), `DEEMED_SUPPLY` (forbidden with type 480) - each with its own required fields (see prior message for the full per-type table).

**Document-level allowances/charges**

- `tax_category_code` required; `N` forbidden at doc level.
- `tax_rate` between 0–1, must satisfy per-category rules.
- `amount = base_amount × multiplier_rate` ⁣when both given.
- `reason_code` validated against charge vs. allowance reason lists; exemption reason code required for category `E`.

**Document-level calculations**

- Tax breakdown buckets grouped by `(taxCategoryCode, taxRate)`; `TaxableAmount = Σ line.LineExtensionAmount ± doc-level A/C` per bucket; only S buckets get `Round(TaxableAmount × rate)`. Rounding happens **once here**, not per line.
- `LineExtensionAmount = Σ line.LineExtensionAmount`
- `TaxAmount = Σ bucket.TaxAmount`
- `TaxExclusiveAmount = LineExtensionAmount − docAllowances + docCharges`
- `TaxInclusiveAmount = TaxExclusiveAmount + TaxAmount`
- `PayableAmount = TaxInclusiveAmount − PrepaidAmount + PayableRoundingAmount` (`PrepaidAmount` is its own request field, not summed from `payments` — payments carry method metadata only).
- `TaxAmountInTaxCurrency = Round(TaxAmount × taxCurrencyExchangeRate)`; `TaxCurrencyCode` hardcoded to AED.
