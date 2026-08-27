---
title: Types of FTA e-invoices
excerpt: Overview of supported e-invoice document types under UAE PINT-AE
deprecated: false
hidden: false
metadata:
  robots: index
---
The DigiTax UAE API supports the full lifecycle of electronic invoices compliant with the UAE Federal Tax Authority (FTA) PINT-AE framework:

## Outbound Document Types

### 1. Invoices (Standard & Out-of-Scope)
* **Description**: Standard commercial invoices issued by a seller to a buyer for goods or services supplied. Includes standard commercial invoices (UNCL 1001 code `380`) and invoices out of scope of tax (code `480`).
* **API Documentation**: [POST /invoices](https://ae.docs.digitax.tech/reference/post_invoices) | [GET /invoices](https://ae.docs.digitax.tech/reference/get_invoices)

### 2. Credit Notes
* **Description**: Negative adjustments or corrections issued against an existing invoice (e.g. for cancellations, price reductions, returns, or billing errors). Covers standard credit notes (code `381`) and credit notes related to goods or services (code `81`).
* **API Documentation**: [POST /credit-notes](https://ae.docs.digitax.tech/reference/post_credit-notes) | [GET /credit-notes](https://ae.docs.digitax.tech/reference/get_credit-notes)

### 3. Self-Billed Invoices
* **Description**: Invoices issued by the buyer (customer) on behalf of the supplier under a prior self-billing agreement (code `389`).
* **API Documentation**: [POST /self-billed-invoices](https://ae.docs.digitax.tech/reference/post_self-billed-invoices) | [GET /self-billed-invoices](https://ae.docs.digitax.tech/reference/get_self-billed-invoices)

### 4. Self-Billed Credit Notes
* **Description**: Credit notes issued by the buyer in a self-billing arrangement to adjust a previous self-billed invoice (code `261`).
* **API Documentation**: [POST /self-billed-credit-notes](https://ae.docs.digitax.tech/reference/post_self-billed-credit-notes) | [GET /self-billed-credit-notes](https://ae.docs.digitax.tech/reference/get_self-billed-credit-notes)

---

## Inbound Document Types

### 5. Received Invoices
* **Description**: Inbound e-invoices and credit notes transmitted to your business over the Peppol network from your registered suppliers.
* **API Documentation**: [GET /received-invoices](https://ae.docs.digitax.tech/reference/get_received-invoices) | [GET /received-invoices/{id}](https://ae.docs.digitax.tech/reference/get_received-invoices-received-invoice-id)
