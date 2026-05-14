---
title: How to use this site
excerpt: >-
  If you're new to here, learn how to navigate these DigiTax UAE API Hub pages
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

* **Table of contents** on the right-hand side (Only on Desktop)
* **Hover to view Glossary definitions (mouseover)**: We don't want to get lost in the jargon. Words (acronyms) listed in the Glossary appear on a page as underlined with a dotted line.

  Like <Glossary>API</Glossary>, hover (or click - _On Mobile_) to view the definition.

## 🚦 Interactive API Docs

For a great developer experience, the endpoints in the [DigiTax UAE API reference](/reference) are interactive.

Once you're set up in the DigiTax Dashboard, you can generate a sandbox or LIVE **X-API-Key** for authorization. Read more on the [API prerequisites](ref:prerequisites-of-using-the-api).

Explore the [API endpoints](/reference).

### Code samples

You can make use of up to 20 programming language code samples for requests to get you started, regardless of the language you're using.

<Image align="center" width="360px" src="https://files.readme.io/18fab9d0ba74fe79ca356fbda311e278e6b92caa26dab89ba40e56e52d985db2-CleanShot_2025-02-27_at_12.19.552x.png" />

### Pagination

We support **cursor-based pagination requests** for endpoints whose **GET** requests return a list of objects.

#### Parameters for paginated requests

The following are optional query parameters for paginated requests like [GET invoices](https://ae.docs.digitax.tech/reference/get_invoices).

| Parameter | Explanation                                                              |
| :-------- | :----------------------------------------------------------------------- |
| before    | When paginating results, a pointer to an ID before which we want results |
| after     | When paginating results, a pointer to an ID after which we want results  |
| page_size | The maximum number of items to return per page, defaults to 20           |

These are also explained on the API endpoint page(s).

### Requests

After making requests via our interactive API reference, the most recent requests are saved for review under the "Recent Requests" section.

<Image align="center" width="360px" src="https://files.readme.io/17102ca17357bbe74dc763eec7c4288fd9dcd8e09e8b7173339166f7b69305da-CleanShot_2025-02-27_at_12.31.522x.png" />

### Parameters

Parameters (or Params) come in two types in the DigiTax UAE API - Query Params and Body Params.

Below are examples:

* Query Params

  An example is seen in [Get invoices](https://ae.docs.digitax.tech/reference/get_invoices) endpoint

<Image align="center" border={true} width="360px" src="https://files.readme.io/ed5701501c2285fdd10a25061c91929c120bfa7ba917d2dea83aa16215e43124-Screenshot_2026-04-22_at_11.01.552x.png" className="border" />

* Body Params

  An example is seen in [Create an item](https://ae.docs.digitax.tech/reference/post_items) endpoint

<Image align="center" border={true} width="360px" src="https://files.readme.io/097f0e019386346f995df37a8766c6a2febf82e64ef0aac4f205278d960fd79a-Screenshot_2026-04-22_at_11.02.362x.png" className="border" />

## 💬 We're here to help

If you get stuck, [email us](mailto:support@namiri.tech)  or use the **DigiTax chat** on the bottom right of any page.

We're excited you're here! 💚
