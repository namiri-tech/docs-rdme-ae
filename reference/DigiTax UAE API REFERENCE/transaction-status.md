---
title: Transaction Status
excerpt: Understand the journey of an invoice and what each status means
deprecated: false
hidden: false
metadata:
  robots: index
---
## DigiTax Queueing system

DigiTax provides the following:

* Asynchronous functionality that automatically retries FTA

* Throttling traffic between the business's throughput and the tax authority's system

These functionalities are possible due to the DigiTax Queueing system.

> 📘 You don't run the risk of double-entry
>
> Every transaction that interacts with FTA's e-invoicing system is first off entered into the DigiTax queueing system to mitigate against possible FTA:
>
> * intermittency and downtime OR
> * slow response rate

## The different transaction statuses and what they mean

Since transactions are first off entered into the DigiTax Queueing system, we give you the following statuses. This is what they mean.

### Transaction statuses

These are the possible options for the `status` property of a response from the invoices endpoints.

| Status    | Meaning                                                                                        | Action                                                                                                                                                   |
| :-------- | :--------------------------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------------------------- |
| pending   | The DigiTax queueing system is **queued** after attempting to reach the FTA e-invoicing system | Check in later. <!-- If you set up [Callback URLs](ref:feature-callback-urls), DigiTax will post to your system when the FTA e-invoicing system sync is done. --> |
| completed | The completed invoice is signed                                                                | Check in later. <!-- If you set up [Callback URLs](ref:feature-callback-urls), DigiTax will post to your system when it is done. -->                              |
| failed    | FTA e-invoicing system rejected the transaction                                                | Please initiate another transaction.                                                                                                                     |

### Invoice Status Details

These are depicted by timestamps both on the DigiTax UAE API and Dashboard.

On the API, these are:

* `created_at` property
* `validated_at` property
* `submitted_at` property
* `reported_at` property

```json
{
    "id": "invoice_01KPWG8DW1CQBNYS34ZX7QG51T",
    "created_at": "2026-04-23T06:25:54Z",
    // other key-value pairs
    "reported_at": null,
    "submitted_at": null,
    "validated_at": null
}
```

of a response from the invoices endpoints.

The timestamps above correspond to what you'd see on the dashboard, under the "Invoices" tab, when you click on the arrow icon next to the block under "Invoice Status". These are:

* `Created`
* `Validated`
* `Submitted`
* `Reported`

<Image align="center" src="https://files.readme.io/6ca8cd751031da29f2f38116d9ff3f9c0215eba17a32c3d61f423f8a21908916-Screenshot_2026-04-23_at_09.26.39_22x.png" />
