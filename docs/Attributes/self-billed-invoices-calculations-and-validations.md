---
title: Self-billed invoices calculations and validations
deprecated: false
hidden: false
metadata:
  robots: index
---
- Requires `supplier_id` (enforced indirectly: without it, `389` fails the regular `IsValidInvoiceType()` check).
- The branch must have company details and a postal address configured.
- Otherwise shares all core invoice validation and calculation rules above.
