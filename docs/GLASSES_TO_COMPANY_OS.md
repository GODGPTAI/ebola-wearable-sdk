# EBOLA AION — One QR, One Owner, Whole Company OS

**English:** ONE QR → existing signup/login/dashboard → consented device session → KRISHNA → existing 6 Directors / 30 Managers / specialist agents → authenticated external tools → evidence → Secure Vault → voice summary.  
**हिंदी:** एक QR → मौजूदा signup → KRISHNA → 6 Directors/30 Managers → अधिकृत एजेंट → सुरक्षित परिणाम।  
**বাংলা:** একটি QR → বিদ্যমান signup → KRISHNA → ৬ ডিরেক্টর/৩০ ম্যানেজার → অনুমোদিত এজেন্ট → নিরাপদ ফলাফল।

## Categories & developer service boundaries
| Segment | Voice example (English / हिंदी / বাংলা) | Source of truth | Required authorization | Implementation state |
|---|---|---|---|---|
| ONE QR and sponsor | “Open my QR” / “मेरा QR खोलो” / “আমার QR খোলো” | Existing dashboard & signup.php?ref= | Existing authenticated identity | Reuse existing; glasses integration planned |
| EBOLA HOME | “Register my home” / “मेरा घर जोड़ो” / “আমার বাড়ি যোগ করো” | Existing property/onboarding records | owner, consent, documents | Planned wearable integration |
| EBOLA SHOP | “List 10 products” / “उत्पाद जोड़ो” / “পণ্য যোগ করো” | Existing merchant catalog | merchant OAuth/auth | Planned wearable integration |
| EBOLA RESTAURANT | “Update menu” / “मेन्यू बदलो” / “মেনু বদলাও” | Existing restaurant module | merchant authorization | Planned wearable integration |
| EBOLA HOTEL/STAY | “Show room stock” / “कमरे बताओ” / “রুম দেখাও” | Existing booking inventory | property operator | Planned wearable integration |
| WhatsApp Commerce | “Reply to customer” / “ग्राहक को जवाब” / “ক্রেতাকে উত্তর” | Official WhatsApp API | merchant-specific Cloud API, opt-in | Planned integration |
| Google Growth | “Update hours” / “समय बदलो” / “সময় বদলাও” | Google Business Profile | valid Google scope | Planned integration |
| CRM | “Follow up leads” / “लीड फॉलोअप” / “লিড ফলো-আপ” | existing CRM | per-merchant consent | Planned integration |
| Finance/EBOLAPE | “Read invoice” / “बिल पढ़ो” / “বিল পড়ো” | existing financial ledger | authenticated user + approval | Planned integration |
| Solar and EV | “Prepare solar quote” / “सोलर कोटेशन” / “সোলার কোটেশন” | pricing and property records | sales approval | Planned integration |
| BRAHMA Film | “Make approved reel” / “रील बनाओ” / “রিল তৈরি করো” | film jobs + Vault receipts | consent/media rights | Planned integration |
| DRISHTI EYE | “Describe surroundings” / “आसपास बताओ” / “চারপাশ বলো” | permissioned vision provider | camera consent; accessibility disclaimer | Planned integration |
| #PropPromptTrading | “Read MGC chart, don't trade” / “चार्ट पढ़ो” / “চার্ট পড়ো” | live official market source | broker permission, risk gates | Planned; no verified live execution |
| Developer/OEM | “Show licence status” / “लाइसेंस बताओ” / “লাইসেন্স দেখাও” | existing licence API | scoped token | Backend tested, app integration pending |

## Director and manager map (role proposal; do not substitute for live registry)
| Director | 5 suggested manager workstreams | Delegation boundary |
|---|---|---|
| D1 — Executive | Strategy; roadmap; budget; projects; owner approvals | Decisions remain under owner policy |
| D2 — Engineering | SDK; OEM devices; AI router; Vault; CI | No secret exposure or unapproved deployments |
| D3 — Commerce | Shop; WhatsApp; Google; CRM; marketing | Merchant authorization required |
| D4 — Operations | Home; Restaurant; Hotel; Inventory; logistics | Tenant-scoped data |
| D5 — Finance | Billing; device licences; payments; warranty; reporting | Payment settlement proof required |
| D6 — Trust | Privacy; KYC; compliance; security; audit | Deny unauthorized actions |

**No duplicate backend:** do not replace `/relay/gptgpt6/ask_ai.php`, `/krishna.php`, `/relay/secure/secure_storage.php`, `/relay/wearables/licence.php`, or canonical `aion_wearable_*` tables. No second signup or QR. Warranty replacement must retain user sponsor identity and Vault data. Broker execution requires explicit fresh confirmation and provider receipt; glasses do not provide inherent live market data or an optical display without hardware proof.
