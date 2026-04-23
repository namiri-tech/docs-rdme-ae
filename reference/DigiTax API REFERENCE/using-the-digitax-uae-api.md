---
title: DigiTax UAE API Introduction
excerpt: An overview of the DigiTax UAE API
deprecated: false
hidden: false
metadata:
  robots: index
---
## Introduction

Before you proceed, we encourage you to get an overview of [DigiTax API and FTA e-Invoicing](doc:getting-started) and [FTA and FTA E-Invoicing System](doc:fta-e-invoicing-system).

> Use **DigiTax UAE API** to integrate your system with FTA E-Invoicing System for automation and to reduce platform-hopping

The premise is simple: DigiTax sits between your system and the tax authority's e-invoicing system.

You send invoice (and other document) data to DigiTax. DigiTax validates, enriches, and routes them to the tax authority for fiscalization (meeting compliance and reporting requirements) giving you peace of mind and saving you time.

<Image border={true} src="https://files.readme.io/962057ae5fb5cf6fd78c5c3a7a5065cc2b42d10a24798169d1ab2852a3b7fffa-DigiTax-TaxAuthoritiesRegulators.png" className="border" />

***

## DigiTax UAE API Endpoints

<Cards columns={1}>
  <Card title="Prerequisites of using the API" href="https://ae.docs.digitax.tech/reference/prerequisites-of-using-the-api" icon="fa-list" />
</Cards>

<Cards columns={1}>
  <Card title="Explore resources endpoints under DigiTax UAE API" icon="fa-book">
    Consider endpoints under **resources** as references for data required for other endpoints.
  </Card>

  <Card title="Explore core DigiTax UAE API endpoints" icon="fa-plug">
    * Business - Retrieve context: GET [/info](https://ae.docs.digitax.tech/reference/get_info)
    * Parties - Create a party: GET [/parties](https://ae.docs.digitax.tech/reference/get_parties)
    * Parties - Retrieve multiple parties: POST [/parties](https://ae.docs.digitax.tech/reference/post_parties)
    * Parties - Retrieve a single party: GET [/parties/\{id\}](https://ae.docs.digitax.tech/reference/get_parties_id)
    * Parties - Update a party: PUT [/parties/\{id\}](https://ae.docs.digitax.tech/reference/put_parties_id)
    * Items - Create an item: GET [/items](https://ae.docs.digitax.tech/reference/get_items)
    * Items - Retrieve multiple items: POST [/items](https://ae.docs.digitax.tech/reference/post_items)
    * Items - Retrieve a single item: GET [/items/\{id\}](https://ae.docs.digitax.tech/reference/get_items_id)
    * Invoices - Create an invoice: GET [/invoices](https://ae.docs.digitax.tech/reference/get_invoices)
    * Invoices - Retrieve multiple invoices: POST [/invoices](https://ae.docs.digitax.tech/reference/post_invoices)
    * Invoices - Retrieve a single invoice: GET [/invoices/\{id\}](https://ae.docs.digitax.tech/reference/get_invoices_id)
    * Credit Notes - Create a credit note: GET [/credit-notes](https://ae.docs.digitax.tech/reference/get_credit-notes)
    * Credit Notes - Retrieve multiple credit notes: POST [/credit-notes](https://ae.docs.digitax.tech/reference/post_credit-notes)
    * Credit Notes - Retrieve a single credit note: GET [/credit-notes/\{id\}](https://ae.docs.digitax.tech/reference/get_credit-notes_id)
    * Debit Notes - Create a debit note: GET [/debit-notes](https://ae.docs.digitax.tech/reference/get_debit-notes)
    * Debit Notes - Retrieve multiple debit notes: POST [/debit-notes](https://ae.docs.digitax.tech/reference/post_debit-notes)
    * Debit Notes - Retrieve a single debit note: GET [/debit-notes/\{id\}](https://ae.docs.digitax.tech/reference/get_debit-notes_id)
    * Self-Billed Invoices - Create a self-billed invoice: GET [/self-billed-invoices](https://ae.docs.digitax.tech/reference/get_self-billed-invoices)
    * Self-Billed Invoices - Retrieve multiple self-billed invoices: POST [/self-billed-invoices](https://ae.docs.digitax.tech/reference/post_self-billed-invoices)
    * Self-Billed Invoices - Retrieve a single self-billed invoice: GET [/self-billed-invoices/\{id\}](https://ae.docs.digitax.tech/reference/get_self-billed-invoices_id)
    * Self-Billed Credit Notes - Create a self-billed credit note: GET [/self-billed-credit-notes](https://ae.docs.digitax.tech/reference/get_self-billed-credit-notes)
    * Self-Billed Credit Notes - Retrieve multiple self-billed credit notes: POST [/self-billed-credit-notes](https://ae.docs.digitax.tech/reference/post_self-billed-credit-notes)
    * Self-Billed Credit Notes - Retrieve a single self-billed credit note: GET [/self-billed-credit-notes/\{id\}](https://ae.docs.digitax.tech/reference/get_self-billed-credit-notes_id)
  </Card>
</Cards>

## DigiTax API

Namiri Technologies, the proprietor of DigiTax, has developed a suite of solutions through the DigiTax Platform. These include:

* DigiTax POS App (Available for Android, iOS, Windows and macOS - not yet available in all markets. UAE is not supported yet.),
* DigiTax Dashboard (Web Browser-based Desktop application)
* DigiTax API

> The first two are powered by the DigiTax API :tada:

### DigiTax API Features

The DigiTax API is built with various industry standards for API platforms in mind. These include:

* RESTful API
* OpenAPI (formerly Swagger): An open-source standard that allows a standardized way to generate, document, and test our APIs.
* Secure authentication with cryptographically signed JWTs (JSON Web Tokens)
* [Standard HTTP response codes](ref:errors-and-other-http-response-codes) for errors and successful requests

### Using DigiTax API

To use this API, you'll need access to DigiTax Dashboard environment to get an API Key. You can test our solutions (DigiTax Dashboard, DigiTax POS App and DigiTax API) for free using test businesses.

These are the steps required to get up and running on the API - [Prerequisites of using DigiTax API](ref:prerequisites-of-using-the-api)

> ℹ️ You can test our solutions before committing
>
> For commercial conversations, get in touch with <Anchor label="our team" target="_blank" href="mailto:support@namiri.tech">our team</Anchor>

### API endpoint parameters

The API endpoints feature three types of parameters:

* Path parameters: Identifiers that are part of the URL path. (e.g. invoices/\{id\})
* Query parameters: Parameters that are appended to the URL after a question mark (?).
* Body parameters: Parameters that are included in the request body.

## Guaranteed safety and integrity

We comply with industry and security best practices.

> 👍 DigiTax is built with the best industry practices and to the highest security standards
