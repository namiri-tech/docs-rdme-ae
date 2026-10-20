# DigiTax UAE API Hub — documentation issues for follow-up

September 22, 2026 · Raised by @Caine Wanjau

Issues found while testing the `ae-dgtax` MCP connector against the live OpenAPI spec and the published guide pages. Each item names the affected page, what's wrong, and a suggested fix.

---

## P1 — Wrong, and breaking integrations today

### 1. `/docs/create-a-party` describes a schema the API doesn't accept

The guide shows a flat structure — `registration_name`, `company_id`, `company_id_scheme_id`, `company_id_scheme_agency_id`, `company_id_scheme_agency_name` at the top level — plus a sample response in that shape.

The OpenAPI spec nests all of it under `legal_entity` and requires `tax_identification_number`, which the guide never mentions.

| Guide says | Spec says |
| --- | --- |
| *(absent)* | `tax_identification_number` — **required** |
| `registration_name` | `legal_entity.registration_name` |
| `company_id` | `legal_entity.registration_number` |
| `company_id_scheme_id` | `legal_entity.registration_scheme` |
| `company_id_scheme_agency_id` | `legal_entity.issuing_authority_code` |
| `company_id_scheme_agency_name` | `legal_entity.issuing_authority_name` |
| `peppol_id_scheme_id` | `peppol_id_scheme` |

The guide also presents the TRN as the primary identifier, while the spec makes the TIN required for every party and the TRN optional and UAE-only. That's a different mental model of what identifies a party, not a cosmetic rename.

A developer following this page builds a payload that fails. It's also the page they read first.

**Fix:** rewrite the field list, the JSON examples and the dashboard-mapping section against the current spec. Keep the guide's genuinely useful additions — that the TIN is the first 10 digits of the TRN, and the registration-type table (`TL`, `CL`, `EID`, `PAS`, `CD`). Check whether the `GET /parties` example response is also stale.

**Also check:** whether `/docs/create-an-item` and `/docs/create-fta-e-invoice-in-digitax` have drifted the same way. Same vintage, likely the same problem.

---

## P2 — Breaking customer setup

### 2. `/docs/mcp` gives the wrong Claude Desktop instructions

The Claude Desktop tab tells users to add a `url` entry to `claude_desktop_config.json`. Claude Desktop will not connect to remote servers configured that way — the connector silently does nothing.

The correct flow is Settings → Connectors → Add custom connector → name + URL, then enable it per conversation via **+** → Add connectors.

**Fix:** replace that tab. ReadMe's MCP panel has a "Generate MCP Template" button that produces current connection instructions, which may be quicker than hand-writing it.

---

## P3 — Misleading but not blocking

### 3. `/docs/peppol-and-pint-ae` — the 5-corner diagram routes FTA reporting through the buyer

The Mermaid diagram shows the FTA copy flowing `C4 → C5`, i.e. from the buyer's system.

The API spec is explicit that DigiTax does both: `submitted_at` is delivery to C3, `reported_at` is delivery to C5. Both are C2 actions.

Beyond being wrong, it's commercially unhelpful — it makes compliance look like the buyer's job rather than something DigiTax handles.

**Fix:** redraw so reporting originates from C2.

### 4. `/docs/invoice-calculations-and-validations` — internal engineering notes on a public page

The page contains a parenthetical stating that the `tax_representative_party_id` check "is correctly implemented but has no dedicated test". It says nothing damaging about the product, but it's not a phrase worth having a procurement reviewer quote back.

The transaction-types section also points to "the prior message" for the full per-type required-field table — a dangling reference suggesting the page was pasted from a chat and never re-edited. The referenced table is useful content that is now missing entirely.

**Fix:** strike the test note; restore the per-type table or link to wherever it actually lives.

---

## Smaller items

### 5. `/docs/mcp` never explains authentication

The page promises "real-time data from your DigiTax UAE account" but offers only generic boilerplate about passing headers. Link `/reference/prerequisites-of-using-the-api` so readers can find where the `X-API-Key` comes from.

### 6. `/docs/mcp` test question may be wrong

It suggests asking about a Profit Margin Scheme invoice "using tax category N". Worth verifying against the validation rules, where `N` is forbidden at document level on allowances and charges.

### 7. Tax category codes aren't publicly browsable

`GET /resources/tax-categories` requires a key, so a customer can't check valid codes without credentials. Support is answering this by hand. A short public reference table would remove the round trip.

---

## Open question for engineering, not docs

### 8. No update path for items

`/parties/{party_id}` has `PUT`; `/items/{item_id}` has only `GET`. A wrong HS code on an existing item appears to have no API-side correction route — and the `detailed-` endpoints reuse existing items unchanged, so they won't fix it either.

If a mechanism exists, it isn't documented. If it doesn't, it will surface in the first enterprise deal with a large catalogue.

---

## Process gap worth closing at the same time

Nothing that goes wrong inside a customer's AI session currently reaches us. MCP is a per-session connection with no channel back.

Suggested callout for the end of `/docs/mcp`:

> **Found something wrong in an AI answer?**
These tools read our live spec and documentation, but AI assistants can still misread, over-generalise, or give an answer that's out of date. If an answer looks wrong — a field that doesn't exist, a validation rule that doesn't match what the API actually does, or a contradiction between two pages — please tell us.
Email us or use the **DigiTax chat** at the bottom-right of any page.
It helps us if you include:

> - the question you asked
> - the answer you got
> - the endpoint or page it relates to, if you know it
>
> Always verify against the API Reference before relying on an AI-generated answer in production.


Also worth checking whether the AI Booster Pack surfaces MCP query analytics — particularly searches that returned no results, which would be the single most useful signal for docs gaps.

---

## Suggested order

1. Item 1 — actively misleading anyone integrating today
2. Item 2 — actively breaking customer setups
3. Items 3–7 alongside, since several are on the same two pages
4. Item 8 — route to engineering, not docs