---
title: Create an item
excerpt: An item is a prerequisite of an invoice
deprecated: false
hidden: false
metadata:
  robots: index
---
## An FTA e-invoice

To recap, even though [an FTA e-invoice](doc:create-fta-e-invoice-in-digitax) has several variations of invoice fields, it mainly contains:

* a single party
* item (at least one)

In this guide, we'll walk through creating an item.

### Creating an item for an FTA e-invoice

An item represents a product or service that you sell. Creating items beforehand simplifies invoice creation by making them reusable.

To create an FTA e-invoice item, you need the following details:

Review item attributes <Anchor label="here" target="_blank" href="doc:item-attributes">here</Anchor>

1. Item name
2. Tax category
3. Commodity code
4. HS code (applicable if the item's commodity code is for a good or both)
5. Service accounting code (applicable if the item's commodity code is for a service or both)
6. Item code(optional)
7. Origin country(optional)
8. Standard item scheme(optional)
9. Description

The screenshot below from the dashboard succinctly shows the details required when creating a simple item (Cement).

<Image align="center" border={true} width="600px" src="https://files.readme.io/bd3b4b2d3958d2b5e332d49d751c67a929d3b0c9fac5309776040bc2b0f93de8-Screenshot_2026-05-21_at_10.55.062x.png" className="border" />

On the API, once the required fields are entered into the request body, the response would read like this:

```json
{
      "id": "item_01KS4RJY95WJR4BAJYS84CDFQ2",
      "created_at": "2026-05-21T07:56:46Z",
      "updated_at": "2026-05-21T07:56:46Z",
      "active": true,
      "name": "Cement",
      "description": "Cement",
      "item_number": "ITM26-141-075646757-47VTNB",
      "commodity_code": "G",
      "hs_code": "84137000",
      "tax_category_code": "N",
      "item_properties": []
    }
```

<br />
