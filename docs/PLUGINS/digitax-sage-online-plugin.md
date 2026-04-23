---
title: DigiTax Sage Online plugin
excerpt: >-
  Streamlining Tax Compliance with electronic invoicing powered by DigiTax |
  Sage Online
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

The integration between DigiTax and Sage ensures a seamless workflow for businesses. Users can continue to use Sage as their primary accounting software, with the added benefit of automated tax management through DigiTax. This eliminates the need for manual data entry and reduces the risk of errors, creating a more efficient and reliable process for managing tax compliance.

To create a connection between DigiTax and Sage, you need to create a Tax management account. Most of the process is already handled by the integration. The interface provides a sanity check on how the sync is being processed from your ERP system to DigiTax.

### 1. Set-up and Configuration

* In the Settings module, add your ERP database configuration. This allows all products and services created in the Sage database to be pulled into DigiTax and subsequently synced to eTIMS.

  <Image align="center" src="https://files.readme.io/13f5ddff7402c4779d37e264d276bd16b30a40720b524d39a88c3ecc2074aa9f-Sage.png" />
* Create API Settings to create a connection between your Sage server and the plugin

  <Image align="center" src="https://files.readme.io/345de35ceacbb6b14816ab5d9653d1f533852e946291aed4aacdc30c4c8cb14c-Sage2.png" />

  <br />

### 2. Dashboard

The dashboard displays the metrics on the latest activities

<Image align="center" src="https://files.readme.io/546f5bec1708906f51fbdeeae6917d4ed13898901f4066255fc1e01e3f85b9f5-Sage3.png" />

### 3. Create customers

In the Customers module, click on "Add Customers" and enter the customer details, including Name and PIN. After saving, a DigiTax ID will be generated, and the customer data will be synced to eTIMS.

<Image align="center" src="https://files.readme.io/4350b9c9f1ec565ba3052a4f395b787336ec16cb97982da92b46a43d4f5311b2-Sage4.png" />

### 4. Create Items

Items can be either stock items or non-stock items, such as services. There are three ways to sync items to DigiTax.

* Creating and saving the item manually.

  <Image align="center" src="https://files.readme.io/780bf3a97484e39888f49b65131a9ac156240af5d5ab6a3053b94f6b622193ff-Sage6.png" />
* Import Data from Database

  Based on the settings configuration, the integration will fetch data using a predefined query. This query can be adjusted according to your database setup and fields. Alternatively, you can choose to upload a file containing the items you want to sync to eTIMS.

  <Image align="center" src="https://files.readme.io/2e3e4933c004331d618f32a0245bb2496214cf5fe13504f00fc330c119241751-Sage5.png" />
* Run and save the Query to get a list of items fetched from your ERP

  <Image align="center" src="https://files.readme.io/a43cc6a2414d7205bf4922097d8e4649acc728bc747ce62784b23280cec5febb-AC.png" />
* Note: You can also auto-sync items from the database

  <Image align="center" src="https://files.readme.io/00c82dd0012d2b2f5a11fd6707d89bcc5cdf20f8ef2c32af172db7e96b9084de-AB.png" />

### 5. Create Sales

Sales data is retrieved either from the database or Sage Online and then sent to DigiTax and subsequently synced to eTIMS. It's important to note that transactions with a "not\_sent" status do not have a DigiTax ID.

<Image align="center" src="https://files.readme.io/d475ac06d06240d90657fd0fb68f3b86ea80ca064f586d7c19067b9c8535a2b0-Sage7.png" />

All transactions done on sage can be visible on DigiTax dashboard.