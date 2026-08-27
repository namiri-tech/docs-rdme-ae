---
title: Item attributes
excerpt: Peruse further details of attributes filled-in in `/items` endpoint
deprecated: false
hidden: false
metadata:
  robots: index
---
## Tax categories

The UAE PINT-AE specification defines the following tax categories:

| Code | Official Name | Description | Tax Rate | Has Rate |
| :--- | :--- | :--- | :--- | :--- |
| **`S`** | Standard rate | Standard rate taxable supply | `0.05` | true |
| **`N`** | Standard rate additional VAT | Standard VAT calculated on an additional taxable base (profit margin) not included in document totals. Used for the Profit Margin Scheme. | `0.05` | true |
| **`Z`** | Zero-rated | Goods or services taxed at zero percent | `0.00` | true |
| **`E`** | Exempt from tax | Supplies exempt from tax | `0.00` | true |
| **`O`** | Services outside scope | Services and transactions not subject to UAE VAT | `0.00` | true |
| **`AE`** | VAT Reverse Charge | Standard VAT levied directly on the recipient (reverse charge) | `-` | false |

*Note: In the DigiTax API, tax rates are represented as decimal fractions (e.g. `0.05` for 5%).*

---

## Commodity types

| Code | Name | Description |
| :--- | :--- | :--- |
| **`G`** | Goods | Physical products (requires `hs_code`) |
| **`S`** | Services | Intangible services (requires `service_accounting_code`) |
| **`B`** | Both | Items containing both goods and service components |

---

## Countries (ISO 3166-1 alpha-2)

Country codes for item origin and addresses can be queried dynamically via `GET /resources/countries`.

| Country Name | Alpha-2 Code |
| :--- | :--- |
| Afghanistan | AF |
| Albania | AL |
| Algeria | DZ |
| Andorra | AD |
| Angola | AO |
| Argentina | AR |
| Armenia | AM |
| Australia | AU |
| Austria | AT |
| Azerbaijan | AZ |
| Bahrain | BH |
| Bangladesh | BD |
| Belgium | BE |
| Brazil | BR |
| Canada | CA |
| China | CN |
| Cyprus | CY |
| Denmark | DK |
| Egypt | EG |
| France | FR |
| Germany | DE |
| Greece | GR |
| Hong Kong | HK |
| India | IN |
| Indonesia | ID |
| Ireland | IE |
| Italy | IT |
| Japan | JP |
| Jordan | JO |
| Kenya | KE |
| Kuwait | KW |
| Lebanon | LB |
| Malaysia | MY |
| Netherlands | NL |
| Nigeria | NG |
| Norway | NO |
| Oman | OM |
| Pakistan | PK |
| Qatar | QA |
| Saudi Arabia | SA |
| Singapore | SG |
| South Africa | ZA |
| Spain | ES |
| Sweden | SE |
| Switzerland | CH |
| Turkey | TR |
| United Arab Emirates | AE |
| United Kingdom | GB |
| United States of America | US |
| Zambia | ZM |

---

## Common Currencies (ISO 4217)

Currencies can be queried dynamically via `GET /resources/currencies`.

| Code | Currency Name |
| :--- | :--- |
| **`AED`** | UAE Dirham (Default Tax Currency) |
| **`BHD`** | Bahraini Dinar |
| **`CAD`** | Canadian Dollar |
| **`CHF`** | Swiss Franc |
| **`CNY`** | Chinese Yuan Renminbi |
| **`EUR`** | Euro |
| **`GBP`** | Pound Sterling |
| **`INR`** | Indian Rupee |
| **`JPY`** | Japanese Yen |
| **`KES`** | Kenyan Shilling |
| **`KWD`** | Kuwaiti Dinar |
| **`NGN`** | Nigerian Naira |
| **`OMR`** | Omani Rial |
| **`QAR`** | Qatari Rial |
| **`SAR`** | Saudi Riyal |
| **`USD`** | US Dollar |
| **`ZMW`** | Zambian Kwacha |