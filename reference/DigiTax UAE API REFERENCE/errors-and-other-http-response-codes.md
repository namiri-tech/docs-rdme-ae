---
title: Errors and other HTTP response codes
excerpt: >-
  HTTP response codes for troubleshooting: declines, invalid data, network
  problems, and more.
deprecated: false
hidden: false
metadata:
  robots: index
---
## Overview

Conventional HTTP response codes indicate the success or failure of an API request.

Responses are grouped into standard classes:

* Successful responses (200 – 299)
* Redirection messages (300 – 399)
* Client error responses (400 – 499)
* Server error responses (500 – 599)

## Standard Error Response Body

When an error occurs, the DigiTax UAE API returns a standardized JSON error envelope:

```json
{
  "code": 400,
  "message": "invalid tax category code",
  "metadata": {
    "field": "items[0].tax_category_code",
    "details": "Tax category 'X' is not valid in UAE PINT-AE specification."
  }
}
```

---

## DigiTax API HTTP Response Status Codes

For the interactive DigiTax UAE API, these are the primary HTTP response codes:

* **200 OK**: Request succeeded.
* **201 Created**: Resource created successfully.
* **400 Bad Request**: Request payload validation failed.
* **401 Unauthorized**: Authentication failed (missing or invalid `X-API-Key`).
* **403 Forbidden**: Authenticated business lacks permissions for this operation.
* **404 Not Found**: Resource or endpoint path not found.
* **409 Conflict**: Duplicate unique constraint (e.g., duplicated `trader_invoice_number` or existing party TRN for branch).
* **412 Precondition Failed**: Business logic precondition not met.
* **429 Too Many Requests**: Rate limit exceeded.
* **500 Internal Server Error**: Internal server issue.
* **503 Service Unavailable**: Temporary maintenance or downtime.

---

## Further Context and Action Points

### Successful Responses

| HTTP Status Code | Scenario in DigiTax API | Action |
| :--- | :--- | :--- |
| **200 OK** | Typical for successful **GET** and **PUT** requests | Use the API response data as needed |
| **201 Created** | Typical for successful **POST** creation requests | Use the newly created entity response |

### Client Error Responses

| HTTP Status Code | Scenario in DigiTax API | Context & Action |
| :--- | :--- | :--- |
| **400 Bad Request** | Schema or field validation failed | **Examples**: Invalid tax category code, missing mandatory address fields (`city_name`, `street_name`), invalid TRN format.<br/>**Action**: Fix the request body against the schema and retry. |
| **401 Unauthorized** | Missing, expired, or invalid API Key | Returned when `X-API-Key` header is missing or inactive (`{"message": "bad credentials"}`).<br/>**Action**: Verify your API Key from the DigiTax dashboard. |
| **403 Forbidden** | Insufficient permissions | The API Key does not have rights to access this branch or resource. |
| **404 Not Found** | Resource or route not found | **Action**: Check the URL path and ID parameter. |
| **409 Conflict** | Unique constraint violation | **Example**: `trader_invoice_number` must be unique across all invoices/credit notes issued by the business. A duplicate number triggers a 409 Conflict.<br/>**Action**: Retry with a unique identifier. |
| **412 Precondition Failed** | Business state precondition failed | **Example**: In credit notes, `items sent are more than those in the original invoice`.<br/>**Action**: Verify that references to the original document match before issuing the credit note. |
| **429 Too Many Requests** | Rate limit quota reached | **Action**: Back off and retry requests with exponential backoff. |
| **5XX Server Errors** | Service interruption or upstream error | **Action**: Check DigiTax status advisories or reach out to [support@namiri.tech](mailto:support@namiri.tech). |
