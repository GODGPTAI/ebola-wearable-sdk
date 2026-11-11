# EBOLA AION — GLOBAL OEM WEARABLE-TO-BUSINESS OS LICENSING

**FINAL PRICING POLICY — 11 November 2026**  
**Company:** GODGPTAI GREENS INNOVATION AND AI TECHNOLOGIES PRIVATE LIMITED  
**CIN:** U62099WR2026PTC293581  
**Portal:** https://ebolascan.online/developerebolaaiindex.php  
**SDK:** https://github.com/GODGPTAI/ebola-wearable-sdk

> **CRITICAL: EBOLA-branded G1/G2/G3/G4 customers NEVER pay an additional $100 OEM SDK fee. The EBOLA device entitlement is bundled into the glasses purchase price. The $100 commercial per-device charge is only for separately contracted third-party OEMs/manufacturers deploying EBOLA technology in their own devices.**

## 1. Customer categories / ग्राहक / গ্রাহক

| Category | Product price / मूल्य / মূল্য | Extra OEM SDK licence fee | Rule / नियम / নিয়ম |
|---|---:|---:|---|
| EBOLA-branded G1 | **US$250** | **US$0 additional** | Included in hardware package |
| EBOLA-branded G2 | **US$500** | **US$0 additional** | Included in hardware package |
| EBOLA-branded G3 | **US$1,000** | **US$0 additional** | Included in hardware package |
| EBOLA-branded G4 | Price to be confirmed | **US$0 additional** | Included in hardware package |
| Approved third-party OEM commercial activation | OEM contract/device price separately determined | **US$100 per physical activated device** | Paid, verified, unique binding |
| Developer sandbox | Free evaluation (subject to terms) | **US$0 until commercial activation** | Mock/test only; no commercial production rights |
| Cloud AI, voice, live vision/video usage | Subscription or metered price | **Separate from device OEM fee** | Not unlimited lifetime usage |

**English:** EBOLA AI G1–G4 buyers pay no separate USD 100 SDK licence. The included entitlement is for the purchased EBOLA device. Third-party OEM manufacturers owe USD 100 for each qualifying paid commercial device activation under an executed agreement.

**हिंदी:** EBOLA G1–G4 चश्मा खरीदने वाले ग्राहकों से अलग $100 SDK लाइसेंस शुल्क **नहीं लिया जाएगा**। लाइसेंस चश्मे की कीमत में शामिल है। $100 प्रति सक्रिय डिवाइस शुल्क केवल अनुबंधित बाहरी OEM निर्माता/डेवलपर पर लागू होगा। AI cloud subscription/usage अलग हो सकता है।

**বাংলা:** EBOLA G1–G4 স্মার্ট গ্লাসের নিজস্ব গ্রাহকদের আলাদা $100 SDK লাইসেন্স ফি **দিতে হবে না**। ডিভাইস লাইসেন্সটি চশমার মূল্যের মধ্যে অন্তর্ভুক্ত। শুধুমাত্র চুক্তিবদ্ধ তৃতীয় পক্ষের OEM নির্মাতাদের প্রতি বাণিজ্যিকভাবে সক্রিয় ডিভাইসে $100 দিতে হবে। AI ক্লাউড ব্যবহার/সাবস্ক্রিপশন আলাদা হতে পারে।

## 2. Single-device entitlement rules

- One active physical device bound per entitlement; prevent simultaneous premium-service use on a second device.
- Manufacturer-attested or cryptographically bound device identity is preferred; a raw client-supplied device ID is insufficient by itself.
- A genuine EBOLA branded device sale provisions a **bundled** entitlement; OEM payment collection MUST NOT be triggered for that sale.
- Third-party OEM activation requires signed OEM agreement, verified order, confirmed settled payment or authorized prepaid credit, unique provisioning nonce, and audit trail.
- No issuance from client-submitted `brand=EBOLA` alone: **server-side trusted procurement/inventory records** decide brand and entitlement class.
- An approved one-year replacement (where applicable to product terms) revokes/retires old device binding, transfers remaining entitlement to replacement, and preserves existing account, sponsor identity, encrypted Secure Vault; no repeat OEM device licence charge for legitimate replacement under contract.
- Deactivation/suspension alone does not create a freely reusable licence or paid activation credit.
- Revocation, expiry, warranty approval and replacement require authenticated, role-scoped server operations and durable audit entries.

## 3. Global developer commercial funnel

Public docs -> OEM registration / KYC / corporate review -> executed licence agreement -> SDK evaluation -> hardware/firmware compatibility certification -> confirmed $100/device payment for third-party OEM -> authenticated device binding -> KRISHNA/EBOLA service permissions -> optional metered cloud AI.

GitHub does not collect a USD 100 fee merely because someone downloads code. Keep source rights explicit and third-party SDK compatibility/licences independently checked. GitHub repository visibility does not grant OEM production activation.

## 4. One-man company OS — scope

Wearables act as a consented camera/microphone/speaker/control interface to the existing **KRISHNA Master Brain**, not as an independent all-powerful on-device server. Preserve existing `/krishna.php`, `/relay/gptgpt6/ask_ai.php`, `/relay/secure/secure_storage.php`, `/signup.php?ref=...`, `/dashboard.php`, ONE QR and sponsor identity. Backend routes tasks via **6 Directors, 30 Managers, registered specialist AI agents**. Domains include EBOLA HOME, SHOP, RESTAURANT, HOTELS/STAY, property, solar, WhatsApp/Google (authorized integrations), CRM, payment initiation, invoice/stock, vision accessibility, content/video/3D, support, learning, developer services and risk-gated trading.

**Reality statement:** SDK contract/unit tests and backend licence lifecycle tests do not certify real G1–G4 BLE, camera, payments, WhatsApp API, trading execution or the 30-manager orchestration. Per-feature integrations and OEM hardware must be tested. Orders, payments, messages, public listings and trading require account authorization/confirmation, current provider permissions and verifiable receipts.

## 5. Illustrative gross OEM revenue (third-party ONLY)

| External third-party paid activations | USD 100/device gross |
|---:|---:|
| 100 | $10,000 |
| 1,000 | $100,000 |
| 10,000 | $1,000,000 |
| 100,000 | $10,000,000 |

Illustration only, not guaranteed revenue. Excludes taxes, refunds, chargebacks, payment processing, infrastructure and support. **Do not add $100 to EBOLA branded device prices.**

## 6. Commercial agreement and publication safeguards

Final OEM pricing is a *proposed offer*, not an executed agreement. Review vendor SDK rights, patent/trademark/IP issues, privacy law, GST/export invoices, KYC/KYB, payment provider rules and warranty terms with appropriate counsel. Before any repository becomes public, inspect Git history, `LICENSE`, dependency licences, secrets, supplier code, keys and proprietary files. Publishing docs in a separate public repo is safer than opening private source by default.

## 7. API and database implementation boundaries

Existing `/relay/wearables/licence.php` and five `aion_wearable_*` tables are the canonical entitlement lifecycle. Proposed `oem_*` order/credit/settlement tables must be additive, reconciled to actual schema and transactional; **do not import a second active-licence store**. Use webhook signature verification, replay protection, price/amount/currency verification, invoice/order ownership, idempotent activation and atomic credit consumption; never trust browser-reported payment success.

Separate metered AI plan/subscriptions (e.g. INR 500/1,000/5,000 if offered) from the included device entitlement. **No unlimited AI API usage** is implied by device purchase.
