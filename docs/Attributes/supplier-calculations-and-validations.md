---
title: Supplier calculations and validations
deprecated: false
hidden: false
metadata:
  robots: index
---
Supplier validation rules follow the **same validation rules as Party**, including the same update behavior (immutable TRN, optional fields on update, merged-state cross-field checks).

- Returns `AlreadyExists` if a supplier already exists for the branch.
