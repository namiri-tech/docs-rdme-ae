---
title: An UAE FTA e-invoice flow in DigiTax
excerpt: >-
  This guide introduces us to a PINT-AE compliant e-invoices for the United Arab
  Emirates. In following guides we'll cover the steps it takes to get create
  your first invoice
deprecated: false
hidden: false
metadata:
  robots: index
---
## DigiTax UAE and FTA e-invoicing system

> **DigiTax UAE** integrates you with FTA e-invoicing system

**DigiTax** is a solution that sits between you; the taxpayer, and the FTA e-invoicing system.

With DigiTax, you gain access to a streamlined invoicing system that ensures compliance and supports your business's growth. Together, DigiTax and FTA e-Invoicing are transforming how businesses in the UAE manage their tax and invoicing obligations.

For us to support individuals and businesses to generate FTA e-invoices, DigiTax is licensed as an FTA-approved system integrator.

The speed at which FTA invoices are generated is dependent on network capacity, connectivity, and responsiveness of FTA's e-invoicing system and the Peppol network transmitting the network traffic.

<Callout icon="🥇" theme="default">
  ### DigiTax is a leading FTA-approved system integrator
</Callout>

## An FTA e-invoice

An FTA e-invoice has several variations of invoice fields. It contains:

* a single party
* item (at least one)

### Creating an FTA invoice

To create an FTA invoice, you need to:

1. Create an item
2. Create a party
3. Create an invoice

After that, you can view the invoice details

## FTA e-invoice details

Below is an invoice with one party and one item created through DigiTax in two views:

* Visually rendered on the DigiTax dashboard
* In JSON data accessible via REST API

### FTA e-invoice on the DigiTax Dashboard

Expect a similar render when an invoice is printed.

<Image align="center" border={true} caption="FTA e-invoice on DigiTax Dashboard" src="https://files.readme.io/2c4a034774a4e4cf56512f646ea71e71b9db3ae14f2cfa86b35abfa613e076a3-Screenshot_2026-04-23_at_09.27.262x.png" width="800px" />

### FTA e-invoice via the DigiTax API

Expect a similar response to be consumed by your system once you've integrated with DigiTax UAE API.

```json
{
  "id": "invoice_01KPWG8DW1CQBNYS34ZX7QG51T",
  "created_at": "2026-04-23T06:25:54Z",
  "updated_at": "2026-04-23T06:25:54Z",
  "active": true,
  "invoice_number": "INV26-113-062554561-QB4DEJ",
  "uuid": "dfa7e0f0-3318-410a-ba10-d4209a388c24",
  "transaction_type_code": "00000011",
  "transaction_types": [
    "SUPPLY_THROUGH_ECOMMERCE",
    "EXPORTS"
  ],
  "invoice_type_code": "380",
  "issue_date": "2026-04-23",
  "due_date": "2026-04-24",
  "document_currency_code": "AED",
  "tax_currency_code": "AED",
  "tax_currency_exchange_rate": 1,
  "billing_reference": [],
  "additional_documents": [],
  "customer_party_id": "party_01KPWG0PS82JBV20JD0PC93XBR",
  "line_extension_amount": 400,
  "tax_exclusive_amount": 400,
  "tax_inclusive_amount": 420,
  "payable_amount": 420,
  "allowance_total_amount": 0,
  "charge_total_amount": 0,
  "prepaid_amount": 0,
  "payable_rounding_amount": 0,
  "tax_amount": 20,
  "tax_included_indicator": false,
  "tax_amount_in_tax_currency": 20,
  "status": "FAILED",
  "allowance_charges": [],
  "payments": [
    {
      "id": "payment_01KPWG8DW2E1RGG4QZ1RFGHQ3N",
      "payment_means_code": "10",
      "payment_means_code_name": "In cash"
    }
  ],
  "items": [
    {
      "id": "invoiceitem_01KPWG8DW1CQBNYS34ZZ5TJVYD",
      "created_at": "2026-04-23T06:25:54Z",
      "updated_at": "2026-04-23T06:25:54Z",
      "active": true,
      "item_id": "item_01KPWDCXKRTYTKMWK6T3EGAKZV",
      "line_id": 1,
      "quantity": 20,
      "unit_of_measure_code": "XBG",
      "line_extension_amount": 400,
      "tax_amount": 20,
      "price_amount": 20,
      "gross_price": 20,
      "tax_category_code": "S",
      "tax_rate": 0.05,
      "allowance_charges": []
    }
  ],
  "taxes": [
    {
      "id": "taxbreakdown_01KPWG8DW2E1RGG4QZ1P1RPABT",
      "tax_category_code": "S",
      "taxable_amount": 400,
      "tax_amount": 20,
      "currency": "AED",
      "tax_rate": 0.05
    }
  ],
  "reported_at": null,
  "submitted_at": null,
  "validated_at": null
}
```

Next, let's cover creating the prerequisites of an invoice: item and party.
