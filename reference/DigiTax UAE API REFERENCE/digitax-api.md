---
title: DigiTax API - General Overview
excerpt: A general overview of the global DigiTax API
deprecated: false
hidden: false
metadata:
  robots: index
---

## DigiTax API

Namiri Technologies, the proprietor of DigiTax, has developed a suite of solutions through the DigiTax Platform. These include:

* DigiTax POS App (Available for Android, iOS, Windows and macOS - market availability varies; UAE support upcoming)
* DigiTax Dashboard (Web Browser-based application)
* DigiTax API

> The first two are powered directly by the DigiTax API :tada:

### DigiTax API Features

The DigiTax API is built following modern industry standards:

* RESTful API architecture
* OpenAPI (Swagger 3.0) compliant specification for automated documentation and client generation
* Secure authentication via API keys passed in the `X-API-Key` HTTP header
* [Standard HTTP response codes](ref:errors-and-other-http-response-codes) for errors and successful operations

### Using DigiTax API

To use this API, you'll need access to the DigiTax Dashboard environment to generate an API Key. You can test our solutions (DigiTax Dashboard and DigiTax API) for free using sandbox test businesses.

Follow the setup steps in [Prerequisites of using DigiTax API](ref:prerequisites-of-using-the-api).

> ℹ️ You can test our solutions before committing
>
> For commercial conversations, get in touch with <Anchor label="our team" target="_blank" href="mailto:support@namiri.tech">our team</Anchor>

### API endpoint parameters

The API endpoints feature three types of parameters:

* **Path parameters**: Identifiers that are part of the URL path (e.g. `/invoices/{id}`)
* **Query parameters**: Parameters appended to the URL query string (e.g. `?page_size=20`)
* **Body parameters**: JSON objects included in the request body for POST/PUT requests

## Guaranteed Safety and Integrity

We comply with industry and security best practices for enterprise financial and tax integrations.

> 👍 DigiTax is built with the best industry practices and to the highest security standards
