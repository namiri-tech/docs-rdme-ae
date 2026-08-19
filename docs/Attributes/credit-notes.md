---
title: Credit notes calculations and validations
deprecated: false
hidden: false
metadata:
  robots: index
---
Shares all invoice validations (issue-date window, items, allowances/charges, delivery, transaction types) — differences only:

- `credit_note_reason_code`: valid code if provided.
- `original_invoice_id`: required unless reason is _Volume Discount_.
- **Type mapping to original invoice**: `380→381`, `480→81`, `389→261`. Type `81` carries the same E/O/Z + `company_id` restriction as `480`. Type `261` (self-billed credit note) needs the branch company/postal check — same bypass gap as self-billed invoices above.

**When&#x20;**`original_invoice_id`**&#x20;is provided:**

- Must reference an invoice, not another credit note.
- `customer_party_id` (or `supplier_id` for self-billed) must match the original.
- `issue_date` ≥ original's `issue_date`.
- `document_currency_code` and `tax_currency_exchange_rate` (if provided) must match the original.
- `transaction_types`, if provided, must match the original; otherwise inherited.
- Every credit-note item must reference an item on the original invoice.
- Per-item line amount can't exceed the original line; cumulative credited amount across all prior credit notes for that item can't exceed the original line amount.
- Total `payable_amount` can't exceed the original invoice's.