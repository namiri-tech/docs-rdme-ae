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

> Use **DigiTax UAE API** to integrate your system with the FTA E-Invoicing System for automation and to eliminate platform-hopping.

The premise is simple: DigiTax sits between your system and the tax authority's e-invoicing platform over the Peppol network.

You send invoice (and other document) data to DigiTax. DigiTax validates, enriches, signs, and routes them to the tax authority for fiscalization (meeting compliance and reporting requirements) giving you peace of mind and saving you time.


<Image src="https://files.readme.io/962057ae5fb5cf6fd78c5c3a7a5065cc2b42d10a24798169d1ab2852a3b7fffa-DigiTax-TaxAuthoritiesRegulators.png" border={true} />


***

## DigiTax UAE API Endpoints

<Cards columns={1}>
  <Card title="Prerequisites of using the API" href="https://ae.docs.digitax.tech/reference/prerequisites-of-using-the-api" icon="fa-list" />
</Cards>

<Cards columns={1}>
  <Card title="Explore resources endpoints under DigiTax UAE API" icon="fa-book">
    Consider endpoints under **resources** as dynamic references for code lists (tax categories, invoice types, country codes, currencies, ICD schemes, allowance/charge reason codes).
  </Card>

  <Card title="Explore core DigiTax UAE API endpoints" icon="fa-plug">
    * Business
      * Retrieve context: GET [/info](https://ae.docs.digitax.tech/reference/get_info)
    * Parties
      * Create a party: POST [/parties](https://ae.docs.digitax.tech/reference/post_parties)
      * Retrieve multiple parties: GET [/parties](https://ae.docs.digitax.tech/reference/get_parties)
      * Retrieve a single party: GET [/parties/\{id}](https://ae.docs.digitax.tech/reference/get_parties_party-id)
      * Update a party: PUT [/parties/\{id}](https://ae.docs.digitax.tech/reference/put_parties_party-id)
    * Suppliers
      * Create a supplier: POST [/suppliers](https://ae.docs.digitax.tech/reference/post_suppliers)
      * Retrieve multiple suppliers: GET [/suppliers](https://ae.docs.digitax.tech/reference/get_suppliers)
      * Retrieve a single supplier: GET [/suppliers/\{id}](https://ae.docs.digitax.tech/reference/get_suppliers_supplier-id)
    * Items
      * Create an item: POST [/items](https://ae.docs.digitax.tech/reference/post_items)
      * Retrieve multiple items: GET [/items](https://ae.docs.digitax.tech/reference/get_items)
      * Retrieve a single item: GET [/items/\{id}](https://ae.docs.digitax.tech/reference/get_items_item-id)
    * Invoices
      * Create an invoice: POST [/invoices](https://ae.docs.digitax.tech/reference/post_invoices)
      * Retrieve multiple invoices: GET [/invoices](https://ae.docs.digitax.tech/reference/get_invoices)
      * Retrieve a single invoice: GET [/invoices/\{id}](https://ae.docs.digitax.tech/reference/get_invoices_invoice-id)
    * Credit Notes
      * Create a credit note: POST [/credit-notes](https://ae.docs.digitax.tech/reference/post_credit-notes)
      * Retrieve multiple credit notes: GET [/credit-notes](https://ae.docs.digitax.tech/reference/get_credit-notes)
      * Retrieve a single credit note: GET [/credit-notes/\{id}](https://ae.docs.digitax.tech/reference/get_credit-notes_credit-note-id)
    * Self-Billed Invoices
      * Create a self-billed invoice: POST [/self-billed-invoices](https://ae.docs.digitax.tech/reference/post_self-billed-invoices)
      * Retrieve multiple self-billed invoices: GET [/self-billed-invoices](https://ae.docs.digitax.tech/reference/get_self-billed-invoices)
      * Retrieve a single self-billed invoice: GET [/self-billed-invoices/\{id}](https://ae.docs.digitax.tech/reference/get_self-billed-invoices_self-billed-invoice-id)
    * Self-Billed Credit Notes
      * Create a self-billed credit note: POST [/self-billed-credit-notes](https://ae.docs.digitax.tech/reference/post_self-billed-credit-notes)
      * Retrieve multiple self-billed credit notes: GET [/self-billed-credit-notes](https://ae.docs.digitax.tech/reference/get_self-billed-credit-notes)
      * Retrieve a single self-billed credit note: GET [/self-billed-credit-notes/\{id}](https://ae.docs.digitax.tech/reference/get_self-billed-credit-notes_self-billed-credit-note-id)
    * Received Invoices
      * Retrieve multiple received invoices: GET [/received-invoices](https://ae.docs.digitax.tech/reference/get_received-invoices)
      * Retrieve a single received invoice: GET [/received-invoices/\{id}](https://ae.docs.digitax.tech/reference/get_received-invoices_received-invoice-id)
  </Card>
</Cards>

## Welcome to the DigiTax UAE API Hub

We invite you to use the **DigiTax UAE API** to integrate your system with the UAE FTA E-Invoicing System for automated, compliant e-invoicing.

To recap:

* Explore our detailed guides to understand the DigiTax UAE integration. Learn how to navigate them [here](doc:how-to-use-this-site)
* Review the [Prerequisites for using DigiTax UAE API](ref:prerequisites-of-using-the-api)
* For support, [email us](mailto:support@namiri.tech) OR talk to us via the **DigiTax chat** on the bottom-right of any page

Welcome to the Less Taxing solution - DigiTax.


<Image src="https://files.readme.io/d13b6d83ab31573e992719e15714a5956bbdc95acd27c17b572d9bfb0c750e8e-Full-Logo_Slogan_Colour.png" align="center" width="300px" />


<br />
