---
title: Invoice attributes
excerpt: >-
  Peruse further details of attributes filled-in in `invoices`, `/credit-notes`,
  `self-billed-invoices` and `self-billed-credit-notes` endpoints
deprecated: false
hidden: false
metadata:
  robots: index
---
## Invoice types

| Code | Name                                     | Description                                                                                                                                                                                                      | Invoice Category | Valid for Regular | Valid for Self-billed |
| ---- | ---------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------- | ----------------- | --------------------- |
| 381  | Credit note                              | Document/message for providing credit information to the relevant party.                                                                                                                                         | CREDIT_NOTE      | true              | false                 |
| 81   | Credit note related to goods or services | Document message used to provide credit information related to a transaction for goods or services to the relevant party.                                                                                        | CREDIT_NOTE      | true              | true                  |
| 389  | Self-billed invoice                      | An invoice the invoicee is producing instead of the seller.                                                                                                                                                      | INVOICE          | false             | true                  |
| 261  | Self-billed credit note                  | A document that indicates that the customer is claiming credit in a self billing environment.                                                                                                                    | CREDIT_NOTE      | false             | true                  |
| 380  | Commercial invoice                       | Document/message claiming payment for goods or services supplied under conditions agreed between seller and buyer.                                                                                               | INVOICE          | true              | false                 |
| 480  | Invoice out of scope of tax              | An invoice issued by a party who is out of the scope of tax regulations and shall not collect tax on the invoice. The invoice should not contain tax details or information about the party's tax registrations. | INVOICE          | true              | true                  |

## Credit Note Reason Codes

| Code       | Name                                                                                                                                                         |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| DL8.61.1.A | If the supply was cancelled.                                                                                                                                 |
| DL8.61.1.B | If the tax treatment of the supply has changed due to a change in the nature of the supply.                                                                  |
| DL8.61.1.C | If the previously agreed consideration for the supply was altered for any reason (i.e. bad debt relief).                                                     |
| DL8.61.1.D | If the recipient of goods or recipient of services returned them to the registrant in full or in part and the Consideration was returned in full or in part. |
| DL8.61.1.E | If the tax was charged or tax treatment was applied in error.                                                                                                |
| VD         | Volume Discount.                                                                                                                                             |

<br />