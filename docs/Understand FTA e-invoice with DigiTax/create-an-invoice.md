---
title: Create an invoice
excerpt: Learn how to create a standard FTA e-invoice using the DigiTax UAE's API
deprecated: false
hidden: false
metadata:
  robots: index
---
## An FTA e-invoice

To recap, even though [an FTA e-invoice](doc:create-an-fta-e-invoice-in-digitax) has several variations of invoice fields, it mainly contains:

* a single party
* item (at least one)

In this guide, we'll walk through creating an item.

### Creating a standard FTA e-invoice

An invoice represents the PINT-AE compliant e-invoice document itself. It references existing [Parties](doc:create-a-party) and [Items](doc:create-an-item).

To create a standard FTA e-invoice, you need the following details:

1. [Parties](doc:create-a-party) (buyer and seller - you, the issuer)
2. [Items](doc:create-an-item) (at least one)
3. Invoice details
