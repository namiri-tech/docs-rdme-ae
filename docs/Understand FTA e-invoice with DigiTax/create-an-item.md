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

An item represents a product or service that you sell. Creating items beforehand simplifies invoice creation by making them reusable across multiple invoices.

To create an FTA e-invoice item, you need the following details:

> Review item attributes <Anchor label="here" target="_blank" href="doc:item-attributes">here</Anchor>

1. **Item name (`name`)**: Product or service title
2. **Tax category (`tax_category_code`)**: e.g., `S` (Standard rate), `Z` (Zero-rated), `E` (Exempt), `O` (Out of scope), `AE` (Reverse charge), or `N` (Standard rate additional VAT / Margin Scheme)
3. **Commodity code (`commodity_code`)**: `G` (Goods), `S` (Services), or `B` (Both)
4. **HS code (`hs_code`)**: Applicable if the item's commodity code is for a good (`G` or `B`)
5. **Service accounting code (`service_accounting_code`)**: Applicable if the item's commodity code is for a service (`S` or `B`)
6. **Item code (`sellers_item_id` / `buyers_item_id`)** (optional)
7. **Origin country (`origin_country_code`)** (optional)
8. **Standard item scheme (`standard_item_id` / `standard_item_scheme_id`)** (optional)
9. **Description (`description`)**

The screenshot below from the dashboard succinctly shows the details required when creating a simple item (Cement).

<Image align="center" border={true} width="600px" src="https://files.readme.io/bd3b4b2d3958d2b5e332d49d751c67a929d3b0c9fac5309776040bc2b0f93de8-Screenshot_2026-05-21_at_10.55.062x.png" className="border" />

On the API, submitting `POST /items` returns the created item:

```json
{
  "id": "item_01KS4RJY95WJR4BAJYS84CDFQ2",
  "created_at": "2026-05-21T07:56:46Z",
  "updated_at": "2026-05-21T07:56:46Z",
  "active": true,
  "name": "Cement",
  "description": "Portland Cement (50kg Bag)",
  "item_number": "ITM26-141-075646757-47VTNB",
  "commodity_code": "G",
  "hs_code": "25232900",
  "tax_category_code": "S",
  "item_properties": []
}
```

> 📘 Note on Item Updates
> 
> Items are created via `POST /items` and retrieved via `GET /items` or `GET /items/{item_id}`. Once items are referenced in issued invoices, their fiscal details remain immutable to preserve audit integrity.
