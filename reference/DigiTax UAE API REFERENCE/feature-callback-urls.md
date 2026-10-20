---
title: 'Feature: Callback URLs'
excerpt: >-
  Learn how to use callback URLs to receive notifications about transaction
  statuses
deprecated: false
hidden: false
metadata:
  robots: index
---
## Understanding Callback URLs

When you make a request to the DigiTax API, we immediately return a response. The status of that transaction by default is `PROCESSING`.

_Below is a snippet of the response to a POST invoice request. The **overall_status** property reads "PROCESSING"._

```json
{
  "id": "invoice_01KPWG8DW1CQBNYS34ZX7QG51T",
  "created_at": "2026-04-23T06:25:54Z",
  "overall_status": "PROCESSING",
  // other key-value pairs
  "validation": {
    "status": "PROCESSING",
    "validated_at": null,
    "errors": []
  },
  "submission": {
    "status": null,
    "predefined_endpoint": null,
    "sent_at": null,
    "accepted_at": null,
    "rejected_at": null,
    "rejection_reason": null,
    "as4_message_id": null
  },
  "reporting": {
    "status": null,
    "sent_at": null,
    "accepted_at": null,
    "rejected_at": null,
    "rejection_reason": null,
    "as4_message_id": null,
    "withdrawal": null
  },
}
```

Notice the other key-value pairs with status: `validation.status` reads "PROCESSING", and `submission.status` and `reporting.status` read "null". This is because the invoice:
- is being processed in DigiTax
- has not yet been submitted to the customer party's AP
- has not yet been reported to the tax authority's system.

These values will be populated as soon as the invoice is both submitted and reported.

More on the different transaction statuses and what they mean can be found [in the transaction status page](ref:transaction-status).

DigiTax saves the invoice into our queuing system to be **validated**, **submitted** and **reported**. This step changes the status property from `PROCESSING` to `COMPLETED`. This is apparent via the DigiTax Dashboard or when you make a **GET** request.

_Below is a snippet of the response of a GET invoice request. The status property reads "COMPLETED"._

```json
  "overall_status": "COMPLETED",
  "validation": {
    "status": "PASSED",
    "validated_at": "2026-10-20T07:35:48Z",
    "errors": []
  },
  "submission": {
    "status": "NOT_REQUIRED",
    "predefined_endpoint": "9900000098",
    "sent_at": null,
    "accepted_at": null,
    "rejected_at": null,
    "rejection_reason": null,
    "as4_message_id": null
  },
  "reporting": {
    "status": "ACCEPTED",
    "sent_at": "2026-10-20T07:35:51Z",
    "accepted_at": "2026-10-20T07:35:57Z",
    "rejected_at": null,
    "rejection_reason": null,
    "as4_message_id": "325aca99-da25-4fbd-8e39-6aec8b2ee814@phase4",
    "withdrawal": null
  },
```

Status change make some time and it is not efficient to have you, as the API caller or consumer, to wait for a response. Callback URLs are useful since they inform you as soon as a particular event like a status change happens.

## Configure callbacks in the DigiTax Dashboard

Callback URLs are set per business in the DigiTax Dashboard. Test and Live are configured separately, so set your URLs in each environment you use.

### Step 1: Open Event Callbacks

In the sidebar, open **Integrations**, then click **Event Callbacks**.

<Image align="center" border={true} className="border" width="800px" src="https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/callbacks/01-integrations-event-callbacks.png" />

### Step 2: Choose an event

The Event Callbacks page lists the events you can subscribe to. Click **+ Add Callback URL** next to the event you want.

<Image align="center" border={true} className="border" width="800px" src="https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/callbacks/02-event-callbacks-page.png" />

| Event | Fired when |
| :--- | :--- |
| Invoice Status Changed | An invoice you issued is validated, submitted, reported or withdrawn |
| Received Invoice Status Changed | An invoice you received is saved or reported to the tax authority |

The document types that fire **Invoice Status Changed** are invoices, credit noets, self-billed invoices and self-billed credit notes.

### Step 3: Enter your URL and save

Enter an HTTPS URL, for example `https://your-server.com/webhooks/invoice-status`, then click **Save**.

<Image align="center" border={true} className="border" width="800px" src="https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/callbacks/03-add-callback-url.png" />

### How callbacks work

* DigiTax sends a JSON payload to your URL with a **POST** request when the event fires.
* HTTPS is required so payloads stay encrypted in transit.
* You can toggle a callback off at any time without deleting its URL.
* The **Delivery readiness** panel shows how many events have a callback URL configured.

### Callback retries and timeouts

DigiTax retries sendind the callbacks up to 5 times with a exponential back-off of 5 seconds.

A 2XX HTTP response from your server counts as a successful delivery.

## Where to use Callback URLs

We accept an optional `callback_url` property for the following endpoints:

> 🚧 TODO: Confirm that per-request `callback_url` is supported on AE. It is not defined in the AE OpenAPI specification.

* [Create invoice](ref:post_invoices) (**POST**)
* [Create credit note](ref:post_credit-notes) (**POST**)
* [Create self-billed invoice](ref:post_self-billed-invoices) (**POST**)
* [Create self-billed credit note](ref:post_self-billed-credit-notes) (**POST**)

More details under [Scenarios](#scenarios) section below.

During testing, we encourage you to use a site like [webhook.site](https://webhook.site)

Our system will POST data to the callback URL when we have new information about the invoice, usually after syncing with the tax authority's system.

## Scenarios

We send a callback when the invoice has been signed.

When an invoice, credit note, self-billed invoice or self-billed credit note has been synced to FTA, we also send a POST request to the `callback_url`. The request body contains a `data` object with details about the synced invoice, credit note, self-billed invoice or self-billed credit note and an `event` property with the value `invoice.sync`.

> 🚧 TODO: Confirm the `event` value sent for **Invoice Status Changed** callbacks configured in the dashboard (is it still `invoice.sync`?).

When an invoice you received is saved or reported to the tax authority, we send a POST request to the URL set for **Received Invoice Status Changed**.

> 🚧 TODO: Confirm the `event` value and `data` contents for **Received Invoice Status Changed**.

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

> 🚧 TODO: Add a sample payload for **Invoice Status Changed** and **Received Invoice Status Changed**.

### Verify the signature

Each payload is signed so you can confirm it came from DigiTax before you process it.

> 🚧 TODO: Document the signature header name, the algorithm (for example HMAC-SHA256), where to find the signing secret, and the steps to verify a payload.
