---
title: Which packaging unit and quantity unit should I use for services?
deprecated: false
hidden: false
metadata:
  robots: index
---
## Which packaging unit and quantity unit should I use for services?

For physical items, the packaging unit and quantity unit are self-explanatory.

For services, we advise that you use:

* "**NET**" for packaging unit
* "\*\*Pieces/ Item \[Number]\*\*" for quantity unit

### On the Dashboard

<Image align="center" src="https://files.readme.io/2690422f2b5a29d2140a6000d2382492df85eca462beb1411639faaee84e5290-CleanShot_2025-04-22_at_21.54.352x.png" />

### On the API

```json
{
  ...
  "package_unit_code": NT,
  "quantity_unit_code": U,
  ...
}
```