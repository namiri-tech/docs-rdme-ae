---
title: Create a party
excerpt: A party is a prerequisite of an invoice
deprecated: false
hidden: false
metadata:
  robots: index
---
## An FTA e-invoice

To recap, even though [an FTA e-invoice](doc:create-fta-e-invoice-in-digitax) has several variations of invoice fields, it mainly contains:

* a single customer party
* item (at least one)

In this guide, we'll walk through creating a party.

### Creating a party for an FTA e-invoice

A party represents a business entity you transact with, such as a customer (buyer). You must create a party before you can issue an invoice to them.

In the context of an e-invoice, there are two primary roles:

* **Buyer (Customer)**: The recipient of the goods or services.
* **Seller (Supplier)**: The issuer providing the goods or services.

When issuing regular tax invoices, you are the seller (configured under your DigiTax business), and your customer is the buyer created as a party. See the [buyer vs seller](#buyer-vs-seller) section below for details on self-billing.

To create an FTA e-invoice party, you need the following details:

> Review party attributes <Anchor label="here" target="_blank" href="doc:party-attributes">here</Anchor>

1. **Tax Registration Number (`tax_registration_number`)**: 15-digit UAE TRN
2. **Registration Name (`registration_name`)**: Legal entity name
3. **Company ID (`company_id`)**: Registration/identifier number (e.g. Trade License number, Emirates ID)
4. **Company ID Scheme ID (`company_id_scheme_id`)**: ISO 6523 ICD code (e.g. `0235` for UAE FTA scheme)
5. **Company ID Scheme Agency ID (`company_id_scheme_agency_id`)**: Legal registration type (`TL`, `CL`, `EID`, `PAS`, `CD`)
6. **Company ID Scheme Agency Name (`company_id_scheme_agency_name`)**: Issuing authority name (e.g. "Department of Economic Development" for `TL`, or 2-letter ISO country code for `PAS`)
7. **Address (`address`)**:
   1. Country Code (`country_code`, e.g. `AE`)
   2. Country Subentity (`country_subentity`, e.g. `DXB`)
   3. City Name (`city_name`)
   4. Street Name (`street_name`)
   5. Address Line (optional)
   6. Postal Zone (optional)
8. **Contact (optional)**:
   1. Contact Name (`contact_name`)
   2. Contact Phone (`contact_phone`)
   3. Contact Email (`contact_email`)
9. **Peppol Identification (optional)**:
   1. Peppol ID (`peppol_id`)
   2. Peppol Scheme ID (`peppol_id_scheme_id`, e.g. `9922`)

The screenshot below from the dashboard succinctly shows the details required when creating a party.

<Image align="center" border={true} width="800px" src="https://files.readme.io/63f7fbffd550f30e157d58b7456ea20870c8dcd2947495adf341d3674bc6e9a0-Screenshot_2026-04-23_at_09.21.28_22x.png" className="border" />

On the API, once the required fields are submitted in `POST /parties`, the response will read:

```json
{
  "id": "party_01KPWG0PS82JBV20JD0PC93XBR",
  "created_at": "2026-04-23T06:21:41Z",
  "updated_at": "2026-04-23T06:21:41Z",
  "active": true,
  "tax_registration_number": "112334455667703",
  "registration_name": "CKW Trading LLC",
  "company_id": "CN-1123344556",
  "company_id_scheme_id": "0235",
  "company_id_scheme_agency_id": "TL",
  "company_id_scheme_agency_name": "Department of Economic Development",
  "address": {
    "street_name": "Park Terrace Drive Way",
    "city_name": "Dubai Silicon Oasis",
    "country_subentity": "DXB",
    "country_code": "AE"
  }
}
```

## Party details

### Tax Registration Number and Registration Name

The `tax_registration_number` is the 15-digit TRN assigned to the entity by the Federal Tax Authority (FTA). The `registration_name` must match the official registered legal name of the entity.

### Company and Scheme Details

When creating a party in the UAE PINT-AE framework, the identifier scheme defines the authority and type of registration.

1. **Electronic Address / Endpoint ID (Peppol Network)**

   The standard Peppol participant scheme for the UAE:
   * **Scheme ID:** **`0235`**
   * **Value:** The party's 10-digit **TIN** (the first 10 digits of the 15-digit TRN).

2. **Legal Registration Types (`company_id_scheme_agency_id`)**

   | **Code** | **Registration Type** | **When to use it** |
   | :--- | :--- | :--- |
   | **`TL`** | Commercial/Trade License | **Default.** For standard UAE VAT-registered commercial businesses. Requires `company_id_scheme_agency_name`. |
   | **`CL`** | Commercial License | For entities with specialized commercial licenses. |
   | **`EID`** | Emirates ID | For individual UAE residents or sole proprietorships. |
   | **`PAS`** | Passport | For natural persons without a UAE trade license (`agency_name` must be 2-letter ISO country code). |
   | **`CD`** | Cabinet Decision | For Government ministries, public authorities, or special exempted statutory bodies. |

In our example, we used:

| Field | Value |
| :--- | :--- |
| Tax Registration Number | `112334455667703` |
| Registration Name | `CKW Trading LLC` |
| Company ID | `CN-1123344556` |
| Company ID Scheme ID | `0235` |
| Company ID Scheme Agency ID | `TL` |
| Company ID Scheme Agency Name | `Department of Economic Development` |

### Address

The address requires `country_code` (e.g. `AE`), `country_subentity` (e.g. `DXB`), `city_name`, and `street_name`. `postal_zone` and `address_line` are optional.

### Contact

Optional contact person fields: `contact_name`, `contact_phone`, and `contact_email`.

## Buyer vs Seller

In standard e-invoicing:
* **Seller**: Your business issuing the invoice.
* **Buyer**: Your customer receiving the invoice, created via `POST /parties`.

> 📘 Note on Party Creation and Self-Billing
> 
> Rows in the `parties` collection are created explicitly when you call `POST /parties`, or automatically during **self-billed** document creation (`POST /self-billed-invoices` / `POST /self-billed-credit-notes`), where your own business is registered as the self-billing customer party.
> 
> Creating a business on DigiTax does not automatically populate `GET /parties` until parties are added or self-billing documents are processed.

When fetching all parties via `GET /parties`, the response includes all active registered customer parties:

```json
{
  "data": [
    {
      "id": "party_01KPWG0PS82JBV20JD0PC93XBR",
      "created_at": "2026-04-23T06:21:41Z",
      "updated_at": "2026-04-23T06:21:41Z",
      "active": true,
      "tax_registration_number": "112334455667703",
      "registration_name": "CKW Trading LLC",
      "company_id": "CN-1123344556",
      "company_id_scheme_id": "0235",
      "company_id_scheme_agency_id": "TL",
      "company_id_scheme_agency_name": "Department of Economic Development",
      "address": {
        "street_name": "Park Terrace Drive Way",
        "city_name": "Dubai Silicon Oasis",
        "country_subentity": "DXB",
        "country_code": "AE"
      }
    }
  ],
  "cursor": {
    "page_size": 20
  }
}
```
