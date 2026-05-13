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
    * Business
      * Retrieve context: GET [/info](https://ae.docs.digitax.tech/reference/get_info)
    * Parties
      * Create a party: GET [/parties](https://ae.docs.digitax.tech/reference/get_parties)
      * Retrieve multiple parties: POST [/parties](https://ae.docs.digitax.tech/reference/post_parties)
      * Retrieve a single party: GET [/parties/\{id}](https://ae.docs.digitax.tech/reference/get_parties_id)
      * Update a party: PUT [/parties/\{id}](https://ae.docs.digitax.tech/reference/put_parties_id)
    * Items
      * Create an item: GET [/items](https://ae.docs.digitax.tech/reference/get_items)
      * Retrieve multiple items: POST [/items](https://ae.docs.digitax.tech/reference/post_items)
      * Retrieve a single item: GET [/items/\{id}](https://ae.docs.digitax.tech/reference/get_items_id)
    * Invoices
      * Create an invoice: GET [/invoices](https://ae.docs.digitax.tech/reference/get_invoices)
      * Retrieve multiple invoices: POST [/invoices](https://ae.docs.digitax.tech/reference/post_invoices)
      * Retrieve a single invoice: GET [/invoices/\{id}](https://ae.docs.digitax.tech/reference/get_invoices_id)
    * Credit Notes
      * Create a credit note: GET [/credit-notes](https://ae.docs.digitax.tech/reference/get_credit-notes)
      * Retrieve multiple credit notes: POST [/credit-notes](https://ae.docs.digitax.tech/reference/post_credit-notes)
        * Retrieve a single credit note: GET [/credit-notes/\{id}](https://ae.docs.digitax.tech/reference/get_credit-notes_id)
    * Debit Notes
      * Create a debit note: GET [/debit-notes](https://ae.docs.digitax.tech/reference/get_debit-notes)
      * Retrieve multiple debit notes: POST [/debit-notes](https://ae.docs.digitax.tech/reference/post_debit-notes)
      * Retrieve a single debit note: GET [/debit-notes/\{id}](https://ae.docs.digitax.tech/reference/get_debit-notes_id)
    * Self-Billed Invoices
      * Create a self-billed invoice: GET [/self-billed-invoices](https://ae.docs.digitax.tech/reference/get_self-billed-invoices)
      * Retrieve multiple self-billed invoices: POST [/self-billed-invoices](https://ae.docs.digitax.tech/reference/post_self-billed-invoices)
      * Retrieve a single self-billed invoice: GET [/self-billed-invoices/\{id}](https://ae.docs.digitax.tech/reference/get_self-billed-invoices_id)
    * Self-Billed Credit Notes
      * Create a self-billed credit note: GET [/self-billed-credit-notes](https://ae.docs.digitax.tech/reference/get_self-billed-credit-notes)
      * Retrieve multiple self-billed credit notes: POST [/self-billed-credit-notes](https://ae.docs.digitax.tech/reference/post_self-billed-credit-notes)
      * Retrieve a single self-billed credit note: GET [/self-billed-credit-notes/\{id}](https://ae.docs.digitax.tech/reference/get_self-billed-credit-notes_id)
  </Card>
</Cards>

## Once again, welcome to the DigiTax Nigeria API Hub

Once again, thank you for reviewing the getting started page of the DigiTax UAE API hub. We're excited you're here! 💚

We invite you to use the **DigiTax UAE API** to integrate your system with the UAE FTA E-Invoicing System for automation and to reduce platform-hopping

To recap:

* Explore our detailed guides to gain understanding of DigiTax Nigeria integration. Learn how to navigate them [here](doc:how-to-use-this-site)
* Get the [Prerequisites for using DigiTax UAE API](https://ae.docs.digitax.tech/update/reference/prerequisites-of-using-the-api)
* For support, [email us](mailto:support@namiri.tech) OR talk to us via the **DigiTax chat** on the bottom-right of any page

Welcome to the Less Taxing solution - DigiTax.

<Image align="center" border={true} width="300px" src="https://files.readme.io/d13b6d83ab31573e992719e15714a5956bbdc95acd27c17b572d9bfb0c750e8e-Full-Logo_Slogan_Colour.png" className="border" />
