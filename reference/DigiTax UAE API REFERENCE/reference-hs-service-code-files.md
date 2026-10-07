---
title: 'Reference: HS and Service codes - files'
excerpt: >-
  Find here, CSV and JSON files for Harmonized System (HS) codes of the GCC
  Integrated Customs Tariff and Service Accounting codes
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

An HS (Harmonized System) code is an internationally standardized numerical code that classifies traded products, used by customs around the world to categorize goods for import and export, developed by the World Customs Organization (WCO). In the UAE, HS codes follow the GCC Integrated Customs Tariff (12 digits, HS 2022 based, no separators).

A Service Accounting code (UN CPC Version 2.1) classifies services.

An HS code (`hs_code`) is required when the item's `commodity_code` is `G` (goods) or `B` (both), while a Service Accounting code (`service_accounting_code`) is required when the `commodity_code` is `S` (services) or `B` (both). This is applicable in the following endpoints:

* [POST - items endpoint](https://ae.docs.digitax.tech/reference/post_items)
* [POST - invoices endpoint](https://ae.docs.digitax.tech/reference/post_invoices)

The same lists are also available via the `GET /resources/hs-codes` and `GET /resources/service-codes` endpoints.

## HS Code Files

1. The CSV file containing HS codes is accessible <Anchor label="here" target="_blank" href="https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/hs-codes.csv">here</Anchor>.

   You can download the file programmatically. Below is an example using CURL via terminal:

   ```shell
   curl "https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/hs-codes.csv" > hs-codes.csv
   ```
2. The JSON file containing HS codes is accessible <Anchor label="here" target="_blank" href="https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/hs-codes.json">here</Anchor>.

   You can download the file programmatically. Below is an example using CURL via terminal:

   ```shell
   curl "https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/hs-codes.json" > hs-codes.json
   ```

> Keep the `code` column as text when opening the CSV in a spreadsheet, so leading zeros (e.g. `010121100001`) are not stripped.

## Service Code Files

1. The CSV file containing Service codes is accessible <Anchor label="here" target="_blank" href="https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/service-codes.csv">here</Anchor>.

   You can download the file programmatically. Below is an example using CURL via terminal:

   ```shell
   curl "https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/service-codes.csv" > service-codes.csv
   ```
2. The JSON file containing Service codes is accessible <Anchor label="here" target="_blank" href="https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/service-codes.json">here</Anchor>.

   You can download the file programmatically. Below is an example using CURL via terminal:

   ```shell
   curl "https://raw.githubusercontent.com/namiri-tech/docs-rdme-ae/refs/heads/v1.0/assets/service-codes.json" > service-codes.json
   ```

<br />
