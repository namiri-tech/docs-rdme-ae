---
title: Create a UAE FTA e-invoice in DigiTax
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

<Image align="center" border={true} caption="FTA e-invoice on DigiTax Dashboard" src="https://files.readme.io/5da5e420c1be73154330b9b291efd2b0fe987e61ece8449601dd3d5555f8aaf5-Screenshot_2026-05-21_at_10.40.232x.png" width="800px" />

### FTA e-invoice via the DigiTax API

Expect a similar response to be consumed by your system once you've integrated with DigiTax UAE API.

```json
{
  "id": "invoice_01KRH2NMR8AE2VSY4DMSZSDNVH",
  "created_at": "2026-05-13T16:28:12Z",
  "updated_at": "2026-05-13T16:28:17Z",
  "active": true,
  "invoice_number": "INV26-133-162812424-BNG6DR",
  "uuid": "12fd92b4-05d0-40e5-a573-e4aa7d642db3",
  "trader_invoice_number": "INV-002",
  "transaction_type_code": "10001000",
  "transaction_types": [
    "FREE_TRADE_ZONE",
    "CONTINUOUS_SUPPLY"
  ],
  "invoice_type_code": "380",
  "issue_date": "2026-05-06",
  "issue_time": "10:00:00",
  "due_date": "2026-06-05",
  "tax_point_date": "2026-05-05",
  "document_currency_code": "USD",
  "tax_currency_code": "AED",
  "tax_currency_exchange_rate": 3.67,
  "buyer_reference": "BR-2026-00789",
  "accounting_cost": "CAPEX-2024-Q4",
  "project_reference": "PROJ-JEBEL-2024",
  "note": "General invoice details",
  "invoice_period": {
    "start_date": "2026-05-06",
    "end_date": "2026-06-05",
    "billing_frequency_code": "MTH"
  },
  "billing_reference": [
    {
      "id": "DA-2024-001",
      "document_type_code": "916",
      "document_description": "Despatch Advice",
      "issue_date": "2026-05-06"
    }
  ],
  "despatch_document_reference": {
    "id": "DA-2024-001",
    "document_type_code": "916",
    "document_description": "Despatch Advice",
    "issue_date": "2026-05-06"
  },
  "receipt_document_reference": {
    "id": "DA-2024-001",
    "document_type_code": "916",
    "document_description": "Despatch Advice",
    "issue_date": "2026-05-06"
  },
  "originator_document_reference": {
    "id": "DA-2024-001",
    "document_type_code": "916",
    "document_description": "Despatch Advice",
    "issue_date": "2026-05-06"
  },
  "contract_document_reference": {
    "id": "DA-2024-001",
    "document_type_code": "916",
    "document_description": "Despatch Advice",
    "issue_date": "2026-05-06"
  },
  "additional_documents": [
    {
      "id": "DA-2024-001",
      "document_type_code": "916",
      "document_description": "Despatch Advice",
      "issue_date": "2026-05-06"
    }
  ],
  "customer_party_id": "party_01KRGD0QZG5TXDYXTRHF3C4FNH",
  "delivery": {
    "actual_delivery_date": "2026-05-06",
    "delivery_location_id": "LOC-JEBEL-ALI-001",
    "delivery_location_scheme_id": "0088",
    "delivery_address": {
      "street_name": "Sheikh Zayed Road, Tower 1",
      "additional_street_name": "Floor 22",
      "city_name": "Dubai",
      "postal_zone": "00000",
      "country_subentity": "DXB",
      "country_code": "AE",
      "address_line": "Near Dubai Mall"
    },
    "delivery_party_name": "Global Imports FZE - Warehouse",
    "delivery_terms_id": "DAP"
  },
  "line_extension_amount": 4950,
  "tax_exclusive_amount": 4900,
  "tax_inclusive_amount": 5147.5,
  "payable_amount": 5147.5,
  "allowance_total_amount": 50,
  "charge_total_amount": 0,
  "prepaid_amount": 0,
  "payable_rounding_amount": 0,
  "tax_amount": 247.5,
  "tax_included_indicator": false,
  "tax_amount_in_tax_currency": 908.33,
  "status": "SUBMITTED",
  "allowance_charges": [
    {
      "charge_indicator": false,
      "amount": 50,
      "base_amount": 1000,
      "multiplier_rate": 0.05,
      "reason_code": "95",
      "reason": "Volume discount",
      "tax_category_code": "E",
      "tax_rate": 0,
      "tax_exemption_reason_code": "DL8.46.1",
      "tax_exemption_reason": "Certain financial services"
    }
  ],
  "payments": [
    {
      "id": "payment_01KRH2NMR8AE2VSY4DN49BDJYV",
      "payment_means_code": "30",
      "payment_means_code_name": "Credit transfer",
      "payment_id": "PAY-REF-2024-001",
      "payee_account_id": "AE070331234567890123456",
      "payee_account_name": "Acme Trading LLC - Main Account",
      "payee_financial_institution_bic": "ADCBAEAA",
      "card_primary_account_number": "66541234",
      "payment_terms_note": "Payment due within 30 days",
      "payment_terms_due_date": "2026-06-05"
    }
  ],
  "items": [
    {
      "id": "invoiceitem_01KRH2NMR8AE2VSY4DMXM0ZGQZ",
      "created_at": "2026-05-13T16:28:12Z",
      "updated_at": "2026-05-13T16:28:12Z",
      "active": true,
      "item_id": "item_01KRGD1Z8XZNECPQE1KE00CJDE",
      "line_id": 1,
      "note": "General invoice item details",
      "quantity": 10,
      "unit_of_measure_code": "EA",
      "line_extension_amount": 4950,
      "tax_amount": 247.5,
      "price_amount": 500,
      "price_discount": 25,
      "gross_price": 525,
      "tax_category_code": "S",
      "tax_rate": 0.05,
      "accounting_cost": "CC-OPEX-001",
      "invoice_period": {
        "start_date": "2026-05-06",
        "end_date": "2026-06-05",
        "billing_frequency_code": "MTH"
      },
      "buyers_item_id": "BUY-ITEM-9901",
      "sellers_item_id": "PUMP-X500-BLK",
      "allowance_charges": [
        {
          "charge_indicator": false,
          "amount": 50,
          "base_amount": 1000,
          "multiplier_rate": 0.05,
          "reason_code": "95",
          "reason": "Volume discount"
        }
      ],
      "allowance_total_amount": 50,
      "item_nature_code": "DL8.48.8.2"
    }
  ],
  "taxes": [
    {
      "id": "taxbreakdown_01KRH2NMR8AE2VSY4DN1GQEQWR",
      "tax_category_code": "S",
      "taxable_amount": 4950,
      "tax_amount": 247.5,
      "currency": "USD",
      "tax_rate": 0.05
    },
    {
      "id": "taxbreakdown_01KRH2NMR8AE2VSY4DN24E870K",
      "tax_category_code": "E",
      "taxable_amount": -50,
      "tax_amount": 0,
      "currency": "USD",
      "tax_rate": 0
    }
  ],
  "beneficiary_trn": "123456789098703",
  "principle_trn": "123456789098703",
  "reported_at": "2026-05-13T16:28:17Z",
  "submitted_at": "2026-05-13T16:28:16Z",
  "validated_at": "2026-05-13T16:28:14Z"
}
```

Next, let's cover creating the prerequisites of an invoice: item and party.
