---
title: Item attributes
excerpt: Peruse further details of attributes filled-in in `/items` endpoint
deprecated: false
hidden: true
metadata:
  robots: index
---
## Tax categories

| Code | Name                                                   | Description                                                                                                                     | Tax Rate | Has Rate |
| ---- | ------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------- | -------- | -------- |
| O    | Services outside the scope of tax / Not subject to tax | Code specifying that taxes are not applicable to the services and/or not subject to VAT                                         | 0        | true     |
| AE   | VAT Reverse Charge                                     | Code specifying that the standard VAT rate is levied from the invoicee.                                                         | -        | false    |
| Z    | Zero-rated                                             | Code specifying that the goods and/or services are at a zero rate.                                                              | 0        | true     |
| N    | Standard rate plus additional VAT                      | Standard VAT calculated for an additional taxable base when the additional taxable base is not included in the document totals. | -        | false    |
| S    | Standard rate                                          | Code specifying the standard rate.                                                                                              | 5%       | true     |
| E    | Exempt from tax                                        | Code specifying that taxes are not applicable.                                                                                  | 0        | true     |

<br />
