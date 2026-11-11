# Implementation boundaries, security and checklist

## What exists vs what needs integration
- Existing: EBOLA wearable SDK v0.3.1 Flutter/Dart contracts, mock adapter, previously tested 13 unit tests; existing PHP wearable licence lifecycle and 5 tables from earlier Hostinger test screenshots.
- This kit: pure pricing policy, transactional order/credit reservation starter, activation wrapper requiring dependency injection, additive proposed SQL. **No payment processor, KYB, licence-writing bridge, real OEM device attestation, UI or business integrations in production**.
- Required to go live: review actual `/relay/db.php` function, licence schema and endpoint authorization; processor webhook signature verifier, reconciliation, OEM approval, hardware proof and mutually-agreed contract; implement adapter to existing licence issue API under a privileged backend-only scope; stage tests.

## Threat controls
1. Use `EBOLA_OWN_BRAND` classification ONLY from verified internal hardware sale/fulfilment records; **never** from POST form values.
2. Only third-party verified settled USD 100 units can consume OEM credits; audit refunds and chargebacks.
3. Reserve exactly one unit with row locks, unique device hash, transaction + idempotency. Provider settlement receipts require authenticated signed webhook and unique processor reference.
4. No licence issuance on caller-reported payment success; never log keys, passwords, device raw identifiers or sensitive receipts.
5. Existing device licence API is authoritative. Avoid a second active licence register. Provisioning must use transaction-safe/compensating reconciliation.
6. Enforce legitimate warranty replacement: case approved once, old binding retired, same model where policy requires, $0 OEM replacement fee, same user/sponsor/Vault.
7. Separate OEM entitlement from metered cloud AI tokens, voice, live vision and trading market data.
8. The owner must expressly authorize orders, financial transfers, outbound campaigns, profile edits and broker trades.

## Review before schema execution
- Full database backup and test in staging, verify MySQL/MariaDB version and collation.
- Verify no existing `oem_*` table names; inspect ORM/table columns and unique indexes.
- Run `sql/001_oem_additive_schema.sql` only via reviewed, authenticated DBA action; it does not change users or aion_wearable_*.
- Never place SQL migrations or the `src` directory in public web root. Keep under private `$HOME/ebola_projects/...`.

## GitHub visibility
If the SDK is private, unauthed users see 404. Use a distinct public documentation repo for marketing while keeping supplier dependencies and private SDK code protected. GitHub's public source access may interact with licence rights; review licence history before switching visibility.

## Deployment acceptance cases
- G1/G2/G3/G4 own-brand: extra $0, but trusted seller proof mandatory.
- Third-party: exactly $100 each; payment/credit required; duplicate device fails.
- Invalid category, changed price, replayed settlement, same device concurrent activation, refund/chargeback race fail closed.
- Approved replacement transfers; retired device cannot recycle.
- Existing login, sponsor, ONE QR, secure Vault and PHP website unchanged.
