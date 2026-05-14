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

* a single party
* item (at least one)

In this guide, we'll walk through creating a party.

### Creating a party for an FTA e-invoice

A party represents a business entity you transact with, such as a customer. You must create a party before you can issue an invoice to them.

In the context of an e-invoice, there are two parties:

* Buyer
* Seller

The buyer is the party who buys the goods or services, and the seller is the party who sells the goods or services. You, as the API consumer, will be the seller, and your customer will be the buyer. We'll go into more details on this at the [buyer vs seller](#buyer-vs-seller) section below.

To create an FTA e-invoice party, you need the following details:

1. Tax Registration Number
2. Registration Name
3. Company ID
4. Company ID Scheme ID
5. Company ID Scheme Name
6. Address
   1. Country
   2. Country Sub entity
   3. City Name
   4. Street Name
   5. Address Line (optional)
   6. Postal Zone (optional)
7. Contact (optional)
   1. Contact Name
   2. Contact Phone
   3. Contact Email

The screenshot below from the dashboard succinctly shows the details required when creating a party.

<Image align="center" border={true} width="800px" src="https://files.readme.io/63f7fbffd550f30e157d58b7456ea20870c8dcd2947495adf341d3674bc6e9a0-Screenshot_2026-04-23_at_09.21.28_22x.png" className="border" />

On the API, once the required fields are entered into the request body, the response would read like this:

```json
{
  "id": "party_01KPWG0PS82JBV20JD0PC93XBR",
  "created_at": "2026-04-23T06:21:41Z",
  "updated_at": "2026-04-23T06:21:41Z",
  "active": true,
  "tax_registration_number": "112334455667703",
  "registration_name": "CKW",
  "company_id": "1123344556",
  "company_id_scheme_id": "0235",
  "company_id_scheme_name": "TIN",
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

These details are straightforward. They would be retrieved from the FTA registry.

### Company and Scheme Details

When creating a "Party" (either your Company or your Customer) in the UAE PINT-AE framework, the **Company ID Scheme ID** tells the system which official registry the ID number belongs to.

Under the [2026/2027 FTA mandate](doc:e-invoicing-initiative), the options are strictly standardized. Here are your choices:

1. The Mandatory Choice (Electronic Address/Endpoint)

   When identifying a business on the **Peppol Network** (the "Endpoint ID"), the UAE has a specific fixed prefix:

   **Scheme ID:** **`0235`**

   **Value:** Your **TIN** (Tax Identification Number).

   _Note:_ The **TIN** is the **first 10 digits** of your 15-digit TRN. Even if you are part of a tax group, you must use your individual 10-digit TIN.

2. Legal Registration Options (Party Legal Entity)

   When filling out the **Legal Registration Identifier** (to prove the company is a registered legal entity), you should use one of the following codes as the **Scheme ID**:

   <br />

   | **Scheme ID Code** | **What it stands for**         | **When to use it**                                                                   |
   | ------------------ | ------------------------------ | ------------------------------------------------------------------------------------ |
   | **`TRN`**          | Tax Registration Number        | **The Default.** Use this for any VAT-registered business.                           |
   | **`TIN`**          | Tax Identification Number      | Use this for businesses that have a TIN but are not yet VAT registered.              |
   | **`CRN`**          | Commercial Registration Number | Use this if identifying the party by their **Trade License Number**.                 |
   | **`PAS`**          | Passport                       | Only for individual "natural persons" (sole establishments) without a trade license. |
   | **`CD`**           | Cabinet Decision               | Used primarily for Government entities or special exempted bodies.                   |

3. Tax Scheme ID

   For the specific field related to the **Tax Scheme** itself (usually under `cac:PartyTaxScheme`):

   * **Scheme ID:** Always use **`VAT`**.

   * **Company ID:** Use the full **15-digit TRN**.

In this example, I went with:

| Field                   | Value           |
| :---------------------- | :-------------- |
| Tax Registration Number | 112334455667703 |
| Registration Name       | CKW             |
| Company ID              | 1123344556      |
| Company ID Scheme ID    | 0235            |
| Company ID Scheme Name  | TIN             |

### Address

Some fields here are optional. Fill in the address of the party.

### Contact

All fields here are optional. Fill in the contact details of the party.

## Buyer vs Seller

As mentioned previously, an e-invoice has two parties:

* Buyer
* Seller

The buyer is the party who buys the goods or services, and the seller is the party who sells the goods or services.

As soon as you create a business on DigiTax, the business is also classified as a party type: **seller**. This is because your business is registered with the FTA and can therefore issue tax invoices.

**Note**: for a test business on DigiTax, the registered tax authority ID of the seller is that of Namiri Technology (the business that owns DigiTax). You can find this details of your business in the [info](api:get-my-business-details) endpoint.

To confirm this theory, make a GET request to the party endpoint. Expect to find your business as a party listed in the response. This will be one of the two parties in the e-invoice. The other party will be the buyer, which will be a new party you create.

The response payload would look something like this:

```json
{
  "data": [
    {
      "id": "party_01KPWHHB18N1CBXHEPAZQVZDD1",
      "created_at": "2026-04-23T06:48:15Z",
      "updated_at": "2026-04-23T06:51:58Z",
      "active": true,
      "tax_registration_number": "122334455667703",
      "registration_name": "Simple Associates",
      "company_id": "",
      "company_id_scheme_id": "",
      "company_id_scheme_name": "",
      "address": {
        "street_name": "",
        "city_name": "",
        "country_subentity": "",
        "country_code": ""
      }
    },
    {
      "id": "party_01KPWG0PS82JBV20JD0PC93XBR",
      "created_at": "2026-04-23T06:21:41Z",
      "updated_at": "2026-04-23T06:21:41Z",
      "active": true,
      "tax_registration_number": "112334455667703",
      "registration_name": "CKW",
      "company_id": "1123344556",
      "company_id_scheme_id": "0235",
      "company_id_scheme_name": "TIN",
      "address": {
        "street_name": "Park Terrace Drive Way",
        "city_name": "Dubai Silicon Oasis",
        "country_subentity": "DXB",
        "country_code": "AE"
      }
    }
  ],
  "cursor": {
    "page_size": 2
  }
}
```

**active** is a boolean that indicates whether the party is active. If it is true, the party is active. If it is false, the party is inactive.
