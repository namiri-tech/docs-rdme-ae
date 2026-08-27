---
title: Party attributes
excerpt: Peruse further details of attributes filled-in in `parties` endpoints
deprecated: false
hidden: false
metadata:
  robots: index
---
## Legal Registration Types

The `company_id_scheme_agency_id` indicates the legal basis of company identification in the UAE:

| Code | Registration Type | Description |
| :--- | :--- | :--- |
| **`TL`** | Commercial/Trade License | Commercial or trade license issued by UAE Department of Economic Development or Free Zone authorities (requires `company_id_scheme_agency_name`). |
| **`CL`** | Commercial License | Commercial license from non-standard registration bodies. |
| **`EID`** | Emirates ID | National identity card for UAE residents and sole establishments. |
| **`PAS`** | Passport | Passport identifier for foreign natural persons (`company_id_scheme_agency_name` must be 2-letter ISO country code). |
| **`CD`** | Cabinet Decision | Official identification for UAE Government ministries and public entities established under Cabinet Decision. |

---

## International Code Designator (ICD) Schemes

When specifying `company_id_scheme_id` or `peppol_id_scheme_id`, use a valid ISO 6523 International Code Designator. Query the full list via `GET /resources/international-code-designator-schemes`.

Key schemes include:

| Code | Scheme Name | Issuing Agency / Context |
| :--- | :--- | :--- |
| **`0235`** | **UAE Tax Identification Number (TIN)** | **Federal Tax Authority (FTA), UAE (Default for UAE Peppol endpoints)** |
| **`9922`** | UAE Party Identifier | Peppol participant scheme for UAE legal entities |
| **`0088`** | Global Location Number (GLN) | Global Standards 1 (GS1) |
| **`0060`** | Data Universal Numbering System (D-U-N-S) | Dun & Bradstreet |
| **`0151`** | Australian Business Number (ABN) | Australian Taxation Office |
| **`0184`** | DIGSTORG | Danish Agency for Digitisation |
| **`0195`** | Singapore Nationwide E-Invoice Framework | Infocomm Media Development Authority, Singapore |
| **`0208`** | Enterprise Number (BCE/KBO) | Banque-Carrefour des Entreprises, Belgium |
| **`0213`** | Finnish Organization VAT Identifier | State Treasury of Finland |
| **`0230`** | National e-Invoicing Framework | Malaysia Digital Economy Corporation (MDEC) |
| **`0231`** | Single Taxable Company (France) | AIFE, France |
