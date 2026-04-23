---
title: 'Feature: Callback URLs'
excerpt: Learn how to use callback URLs to receive notifications about transaction statuses
deprecated: false
hidden: false
metadata:
  robots: index
---
## Understanding Callback URLs

When you make a request to DigiTax API, we immediately return a response. The status of that transaction by default is `DRAFT`.

*Below is a snippet of the response to a POST invoice request. The status property reads "DRAFT".*

```json
{
  "id": "invoice_01KPWG8DW1CQBNYS34ZX7QG51T",
  "created_at": "2026-04-23T06:25:54Z",
  "status": "DRAFT",
  // other key-value pairs
  "validated_at": null,
  "submitted_at": null,
  "reported_at": null
}
```

Notice the other key-value pairs, `reported_at`, `submitted_at` and `validated_at` all read "null". This is because the invoice has not yet been submitted to the tax authority's system and has not been validated by the tax authority's system. It has also not been reported to the tax authority's system. These values will be populated as soon as the invoice is submitted to the tax authority's system and validated by the tax authority's system. It will also be populated as soon as the invoice is reported to the tax authority's system.

More on the different transaction statuses and what they mean can be found [in the transaction status page](ref:transaction-status).

We save it into our queuing system to be **validated**, **submitted** and **reported**. This step changes the status property from `DRAFT` to `COMPLETED`. This is apparent via the DigiTax Dashboard or when you make a **GET** request.

*Below is a snippet of the response of a GET invoice request. The status property reads "COMPLETED".*

```json
{
  "id": "invoice_01KPWG8DW1CQBNYS34ZX7QG51T",
  "created_at": "2026-04-23T06:25:54Z",
  "status": "COMPLETED",
  // other key-value pairs
  "validated_at": "2026-04-23T10:26:23.262Z",
  "submitted_at": "2026-04-23T10:27:11.191Z",
  "reported_at": "2026-04-23T10:27:20.262Z"
}
```

<!-- *Below is the invoice above as viewed on the dashboard* -->

The tax authority's system or DigiTax may take some time to sign an invoice, and it is not efficient to have you, as the API caller or consumer, wait for a response. Callback URLs are useful since they inform you as soon as a particular event like a status change happens after data processing on the tax authority's system or DigiTax.

## Where to use Callback URLs

We accept an optional `callback_url` property for the following endpoints:

* [Create invoice](ref:post_invoices) (**POST**)
* [Create credit note](ref:post_credit-notes) (**POST**)
* [Create self-billed invoice](ref:post_self-billed-invoices) (**POST**)
* [Create self-billed credit note](ref:post_self-billed-credit-notes) (**POST**)

More details under [Scenarios](#scenarios) section below.

During testing, we encourage you to use a site like [webhook.site](https://webhook.site)

Our system will POST data to the callback URL when we have new information about the invoice, usually after syncing with the tax authority's system.

## Scenarios

We send a callback when invoice has been signed.

When an invoice, credit note, self-billed invoice or self-billed credit note has been synced to FTA, we also send a POST request to the `callback_url`. The request body contains a `data` object with details about the synced invoice, credit note, self-billed invoice or self-billed credit note and an `event` property with the value `invoice.sync`.

## Structure and example

Example response when an invoice, credit note, self-billed invoice or self-billed credit note has been synced to FTA

```json
{
  "data": {
    "id": "invoice_01KPWG8DW1CQBNYS34ZX7QG51T",
    "created_at": "2026-04-23T06:25:54Z",
    "status": "COMPLETED",
    // other key-value pairs
    "validated_at": "2026-04-23T10:26:23.262Z",
    "submitted_at": "2026-04-23T10:27:11.191Z",
    "reported_at": "2026-04-23T10:27:20.262Z"
  },
  "event": "invoice.sync"
}
```
