---
title: How to use this site
excerpt: >-
  If you're new here, learn how to navigate these DigiTax UAE API Hub pages
  below
deprecated: false
hidden: false
metadata:
  robots: index
---
## 📖 Guides

This is the overview page of the Guides section.

Explore the guides as outlined on the left-hand menu.

### Guide page features

* **Table of contents** on the right-hand side (Desktop)
* **Hover to view Glossary definitions (mouseover)**: Acronyms and technical terms listed in the Glossary appear on a page underlined with a dotted line.

  Like <Glossary>API</Glossary>, hover (or tap on mobile) to view the definition.

## 🚦 Interactive API Docs

For a great developer experience, the endpoints in the [DigiTax UAE API reference](/reference) are interactive.

Once you're set up in the DigiTax Dashboard, you can generate a sandbox or LIVE **X-API-Key** for authorization. Read more on the [API prerequisites](ref:prerequisites-of-using-the-api).

Explore the [API endpoints](/reference).

### Code samples

You can make use of code samples in over 20 programming languages for requests to get you started quickly.

<Image align="center" width="360px" src="https://files.readme.io/18fab9d0ba74fe79ca356fbda311e278e6b92caa26dab89ba40e56e52d985db2-CleanShot_2025-02-27_at_12.19.552x.png" />

### Pagination

We support **cursor-based pagination requests** for endpoints whose **GET** requests return a list of objects.

#### Parameters for paginated requests

The following are optional query parameters for paginated requests like [GET invoices](https://ae.docs.digitax.tech/reference/get_invoices).

| Parameter | Explanation |
| :--- | :--- |
| **`before`** | A cursor pointer to an ID before which we want results (for previous page) |
| **`after`** | A cursor pointer to an ID after which we want results (for next page) |
| **`page_size`** | The maximum number of items to return per page (defaults to `20`, maximum: `20`) |

These are also explained on the API endpoint page(s).

### Parameters

Parameters come in two types in the DigiTax UAE API: Query Params and Body Params.

* **Query Params**: Used in listing endpoints like [GET invoices](https://ae.docs.digitax.tech/reference/get_invoices)
* **Body Params**: Passed in JSON request bodies like [POST items](https://ae.docs.digitax.tech/reference/post_items) or [POST invoices](https://ae.docs.digitax.tech/reference/post_invoices)

## 💬 We're here to help

If you get stuck, [email us](mailto:support@namiri.tech) or use the **DigiTax chat** on the bottom right of any page.

We're excited you're here! 💚
