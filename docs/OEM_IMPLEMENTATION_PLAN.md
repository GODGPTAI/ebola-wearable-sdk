# EBOLA AION OEM Licensing — Integration Plan

## Phase 0 — Read-only production audit

Inspect `LICENSE-POLICY.md`, SDK/Android `pubspec.yaml`, `/relay/wearables/licence.php`, `/relay/wearables/bootstrap.php`, `/relay/db.php`, `users`, `aion_wearable_licences`, `aion_wearable_device_claims`, `aion_wearable_tokens`, `aion_wearable_warranty_cases`, and audit tables. Record exact schema, constraints, authentication/session method and indexes. Back up DB before migrations. Never copy DB credentials into repo.

## Phase 1 — Branding and products

- EBOLA G1 US$250, G2 US$500, G3 US$1,000, G4 price TBD: OEM fee INCLUDED ($0 separate). Existing package benefits and metered API plans remain independently priced.
- Trusted server-side order SKU plus settled payment and fulfillment provenance proves an EBOLA branded purchase. Do NOT accept claimed brand from client JSON as pricing authority.
- Third-party OEM: separately approved organization, signed commercial agreement, USD 100 per qualified activated device or matching contract settlement.

## Phase 2 — Additive proposed services (not yet deployed)

| Proposed component | Responsibilities |
|---|---|
| `/developers/index.php` | Developer intro and docs |
| `/developers/register.php` | KYB and OEM onboarding |
| `/developers/dashboard.php` | Organization-owned devices/orders |
| `/developers/pricing.php` | OEM vs EBOLA pricing distinction |
| `/developers/checkout.php` | Third-party paid order intent only |
| `/developers/licences.php` | Device entitlement history |
| `/developers/usage.php` | Cloud metering and receipts |
| `/relay/wearables/oem_activate.php` | Authenticated server-side paid/bundled classification and activation |
| `/relay/wearables/oem_validate.php` | Reuse original entitlement validation |
| `/relay/wearables/oem_replace.php` | Existing approved warranty lifecycle |
| `/admin/oem_licensing.php` | KYB, agreement, refunds, ledger approvals |
| `/ai/wearables/OEMLicenceBillingAgent.php` | Orchestration/audit only; no autonomous payment fabrication |

## Phase 3 — Additive tables (design, not migrated)

`oem_developers` (org verification + approval), `oem_licence_orders` (USD minor units, payment state, idempotency), `oem_device_licence_links` (FK references to existing `aion_wearable_licences`, not a duplicate entitlement), `oem_device_events` (audit), `oem_usage_ledger` (metered services). Confirm actual schema and foreign-key feasibility first.

## Phase 4 — Transactional activation

1. Authenticate server user/OEM and scopes; validate order-owner and device-model permissions.
2. Select classification from **trusted procurement/inventory records**: `EBOLA_OWN_BRAND` entails bundled $0 additional; `THIRD_PARTY_OEM` entails verified $100 paid unit or already settled credit.
3. Use row locks and unique idempotency keys; reject replay, wrong owner, unverified device evidence or reused hardware.
4. Bind exactly once in existing active-licence table and unique device claim. Track paid OEM fulfilment in billing ledger, never in browser state.
5. Return only scoped device entitlement; do not reveal secrets or raw payment keys.
6. Compensate/refund on failed issuance according to processor contract; reconcile delayed webhooks and partial failures.
7. Preserve sponsor code, users row, Secure Vault and remaining entitlement on approved warranty replacement.

## Phase 5 — Tests before production

- EBOLA branded G1/G2/G3/G4 -> OEM fee 0; no separate $100 checkout.
- Third-party OEM 1 activation -> $100; unpaid activation blocked.
- Fraudulent client `brand=EBOLA` -> no free entitlement without trusted branded purchase.
- Free sandbox -> mock only, no paid production service.
- Double-device binding blocked even under parallel requests.
- Duplicate/replayed webhook cannot create extra licences.
- Approved replacement retires old claim; repeated replacement case blocked; no extra $100 for legitimate replacement.
- Revoked/expired licence, wrong user, mismatched model, untrusted firmware/device proofs blocked.
- OAuth/login/QR/sponsor/vault integration unchanged.
- External AI usage billed separately; no lifetime unlimited tokens.
- Physical OEM firmware/API performance measured on actual devices.
