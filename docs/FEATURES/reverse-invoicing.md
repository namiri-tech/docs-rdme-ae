---
title: Reverse Invoicing
excerpt: >-
  Reverse invoicing allows businesses to enable customers to generate invoices
  on their behalf, streamlining the billing process.
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

Typically, invoicing is the obligation of the supplier to get paid for the service rendered or goods sold.

### Usual invoice creation

An invoice generation flow has two parties - a buyer and a supplier (of a good or service), with the supplier typically issuing an invoice and the buyer later on paying for the good or service bought.

<Image align="center" border={true} caption="Typical invoice creation" src="https://files.readme.io/ee63be285ab27d07c794eb7c3092ce9969506a59c0ce749eeeb0e9f641e55773-invoice.png" />

### Reverse invoice creation

With an aim to streamline the generation of invoices, reverse invoicing allows the buyer (instead of the supplier) to initiate the generation of an invoice.

<Image align="center" border={true} caption="Reverse invoice creation" src="https://files.readme.io/f001df64537cf1935f26dac52f0d38631da278578fb190053b854b1e04683b89-reverse-invoice.png" />

> 📘 With Reverse invoicing, the invoice generation is initiated by the buyer

## Reverse Invoicing In-depth

Reverse Invoicing is a consent-driven innovation, meaning the supplier will have to pre-authorize either per invoice or one-time (in the cases of recurrent invoices)

The prerequisites are:

* The supplier is registered with the tax regulator to generate invoices
* The supplier permits the buyer to generate invoices on their behalf, either one-time (IMPLICIT) or per invoice (EXPLICIT)

### Reverse Invoicing Process (General)

This is how it works:

1. A supplier record is added by the buyer, providing the PIN, Name, and Phone number
2. FTA sends a token to the added supplier to be used as verification that permission has been granted for reverse invoicing (Details to follow) marking the supplier status as COMPLETED
3. The typical invoice flow is now followed, only that supplier details are included, and the outcome would be as though the supplier generated the invoice, yet it was initiated by the buyer

### Reverse Invoicing Process in DigiTax API

Below are the main endpoints to use:

1. [Save a business supplier (**POST**)](https://ke.docs.digitax.tech/reference/post_suppliers)\
   Include the required attributes - Returns a supplier object with `id` (referred to as **supplier\_id** below).
2. [Get a business supplier (**GET**)](https://ke.docs.digitax.tech/reference/get_suppliers-supplier-id)\
   Specify the `supplier_id` - Use this endpoint to confirm status.
   Status should be `COMPLETED` before proceeding.
3. [Add reverse invoice with item information (**POST**)](https://docs.digitax.tech/reference/post_reverse-invoices-with-items)\
   Include the `supplier_id` among other required attributes - Returns a sale object with `id` (referred to as **sale\_id** below).
4. [Get reverse invoice (**GET**)](https://docs.digitax.tech/reference/get_reverse-invoices-sale-id)\
   Specify the `sale_id` - Use this endpoint to confirm status.

### Reverse Invoicing Process in DigiTax Dashboard

Below are the main steps after you navigate to the "Suppliers" tab of your business. This feature needs to be enabled beforehand.

1. Add a supplier providing the required fields: PIN, Name, and Phone number. Email address is optional.

   <Image align="center" className="border" border={true} width="300px" src="https://files.readme.io/189591ecbb402ba8da95db2f03070c76ba9599a71dd2a69064247b477e40d3d7-CleanShot_2025-07-15_at_20.32.482x.png" />
2. Once the supplier status is **Completed**, navigate to "Reverse Invoices" tab and create a reverse invoice.
   1. Click "Add Reverse Invoice"
   2. Click on the field under **Items**, then "+ Create New Item" to enter your item details.

      <Image align="center" className="border" border={true} width="450px" src="https://files.readme.io/92e8d29b9e197ff5ca7392733273127ee4671b26855fbccf3f0c4a4c479da36d-CleanShot_2025-07-15_at_21.30.042x.png" />
   3. Once item is saved, select item, specify unit price and quantity, then click "+Add Item to Cart". Add more items, if applicable, then click "Continue"

      <Image align="center" className="border" border={true} width="450px" src="https://files.readme.io/d996e89a9f59f0918b9e24590c90a7ec48e4db2f526a171770296bf72a51915e-CleanShot_2025-07-15_at_21.33.432x.png" />
   4. Select Supplier and optionally fill the other fields before clicking "Continue". After confirming the details on the review screen, click "Save" to create the reverse invoice.

      <Image align="center" className="border" border={true} width="450px" src="https://files.readme.io/5418f7cee7a486a8de69c7628a46f61f06f6eddc39ef7eef36f80685a0fa29d5-CleanShot_2025-07-15_at_21.33.232x.png" />