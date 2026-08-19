---
title: Party validations
deprecated: false
hidden: false
metadata:
  robots: index
---
## Party data

- `taxpayer.tax_registration_number`: valid UAE TRN (15 digits, starts `1`, ends `03`).
- `taxpayer.contact_phone`: E.164 format.
- `taxpayer.address.country_code`: valid ISO 3166-1 alpha-2.
- `taxpayer.address.country_subentity`: valid UAE emirate code, only checked when `country_code = AE`.
- `taxpayer.company_id_scheme_id`: valid ISO ICD 6523 scheme identifier.
- `taxpayer.company_id_scheme_agency_id`: one of `TL, CL, EID, PAS, CD`.
- Cross-field: `agency_id = TL` → `agency_name` required (issuing authority name); `agency_id = PAS` → `agency_name` must be a valid ISO alpha-2 country code.
- Returns `AlreadyExists` if a party already exists for the branch.
- Update: all fields optional, evaluated against the merged state; `tax_registration_number` cannot change after creation (enforced implicitly - the field simply isn't on the update proto).