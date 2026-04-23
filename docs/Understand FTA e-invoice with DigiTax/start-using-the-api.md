---
title: Start using the DigiTax UAE API
excerpt: All you need to start using the API
deprecated: false
hidden: false
metadata:
  robots: index
---

## DigiTax suite of products

Namiri Technologies, through our DigiTax Platform, have developed a suite of solutions:

* **DigiTax App** (Compatible with Android and Android POS devices),
* **DigiTax Dashboard** (Responsive, Web-Browser based, Desktop application)
* **DigiTax Plugins** like DigiTax WooCommerce, DigiTax Odoo, DigiTax Quickbooks, DigiTax Sage Online, among others.
* **DigiTax API** (for system-to-system integration without the issue of platform hopping), and

> The first three are powered by the DigiTax API :tada:

Below are the steps required to get up and running

## Prerequisites

The following are the steps to getting a sandbox business (for testing before you go LIVE)

1. [Sign up on DigiTax](https://digitax.tech)
2. Create a profile and select the appropriate country.
3. Create a business with a sample correctly formatted TPIN (Tax Payer Identification Number) like `2002720806` and **set it as a TEST business**, with that, you can now transact on the dashboard.
4. Get API Key (Go to the section **Get API Key** below)

Use the **X-API-Key** in your header when making API calls through the interactive API docs [here](/reference) OR via your integration during testing. This has a quick turn-around of a matter of minutes or hours. Do not wait for days 😊.

## Get API Key

1. Navigate to the "Integrations" menu.  
   Then select "Add API KEY"

<Image align="center" src="https://files.readme.io/89d5e88147a700b1272d84e18c91a9e3a5cc113f7a00f0dcf3441b8ff1cbe0f4-12.png" />

2. Enter a name  

   Stick with 'API Key' for standard integrations. 'License Key' is restricted to specific systems; please only select this option if directed by the support team.

   <Image align="center" src="https://files.readme.io/34a987804e69bd0d0063040d313e1d5593815d9d8d3ecb91adde84fb427370d9-CleanShot_2025-07-09_at_10.19.39_22x.png" />
3. Click "Generate key", copy the key, and click "Save".  
   Test this API key in our interactive DigiTax API Reference before using it in your integration.

   <Image align="center" src="https://files.readme.io/c5d05c08b86a9022877bacf22a0ed00d9e9e5be940fee2d313e2556fdff13d7e-CleanShot_2025-07-09_at_09.22.212x.png" />

In case of any questions, kindly reach out to [support@namiri.tech](mailto:support@namiri.tech) or simply start a chat with DigiTax chat, at the bottom right of this page.

## Going LIVE

To go LIVE on the API, commercial conversations must be complete. If you wish to start those, email [info@namiri.tech](mailto:info@namiri.tech).

Create another business with your TPIN (Tax Payer Identification Number) like `2002720806` and **set it as a LIVE business**.

Follow the steps shared in the email sent by the DigiTax system to your inbox as soon as you successfully create a business.

Once that business goes LIVE, you can go ahead and generate an API key under the "Integrations" tab (see section **Get API Key** above)

Please copy the value that you generate for later use, as you will not see it from the dashboard on subsequent visits. Save it securely.

> 👍 Your integration is LIVE :tada:
>
> Using the LIVE X-API-Key, you'll now be interacting with the production environment of FTA eTIMS

## API Keys management

Once you generate an API key, you have the option to deactivate it (when necessary).

Navigate to the "Integrations" menu and click on the "padlock" icon under the "Action" column.

<Image align="center" src="https://files.readme.io/504535ac9814cbc37cf0e6f703c696185ecc9d3ee1d605d86ee22e31b0efa5e0-1221.png" />

Click "Deactivate key" if you'd like to invalidate the key for API use.

<Image align="center" width="500px" src="https://files.readme.io/be46c930b7a8555cd7e51b5393f0615bff598950d0a608c8761e89f790b1585c-12222.png" />

_To making tax compliance less taxing._
