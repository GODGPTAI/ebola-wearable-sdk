# EBOLA AION OEM SDK — Developer API List / डेवलपर API / ডেভেলপার API

**Style:** GitHub rendered Markdown table. **Status key:** Existing contract = Dart SDK API; Starter = included in this ZIP but not deployed; Planned = interface proposal, not callable yet.

## 1. OEM Pricing & Orders / कीमत और ऑर्डर / মূল্য ও অর্ডার
| Method | Type | Description / विवरण / বিবরণ | Parameters | Return / Status |
|---|---|---|---|---|
| `OEMPricingPolicy::extraOemFeeCents()` | PHP static | Server-trusted category; EBOLA=0, external=10000 cents / EBOLA बिना extra fee / EBOLA আলাদা ফি নেই | `trustedClass` | `int` / Starter |
| `OEMPricingPolicy::devicePriceCents()` | PHP static | Base branded glass price / चश्मे की कीमत / চশমার মূল্য | `G1..G4` | `?int` / Starter |
| `OEMOrderService::createDraft()` | PHP method | Draft external paid order / भुगतान draft / অর্ডার খসড়া | `orgId, units, idempotencyKey` | `orderId` / Starter |
| `OEMOrderService::recordVerifiedSettlement()` | PHP method | Process *server-verified* settlement / verified payment / যাচাই করা পেমেন্ট | `orderId, verifiedReceipt` | `void` / Starter |
| `OEMOrderService::reserveUnit()` | PHP method | Consume exactly one paid credit / एक credit / একটি ক্রেডিট | `orderId, deviceHash` | `reservation` / Starter |
| `OEMActivationService::activateExternal()` | PHP method | Verify entitled OEM order before existing API / अनुमति जांच / অনুমতি যাচাই | trusted verified actor + order + hardware claim | `existing licence receipt` / Starter |

## 2. Existing wearable contract / मौजूदा SDK / বর্তমান SDK
| Method | Type | Description / विवरण / বিবরণ | Parameters | Return / Status |
|---|---|---|---|---|
| `EbolaWearableAdapter.scan` | Future | Discover / खोज / খোঁজা | none | devices / Existing abstract contract |
| `EbolaWearableAdapter.connect` | Future | Connect glasses / चश्मा जोड़ें / চশমা সংযোগ | deviceId | void / Existing abstract contract |
| `EbolaWearableAdapter.takePhoto` | Future | Consent-gated camera capture / फोटो / ছবি | connected & capable | asset / Existing abstract contract |
| `EbolaSdkFacade.photo` | Future | Licence, permission and device gate / licence जांच / লাইসেন্স যাচাই | `device,binding,userApproved` | asset / Existing contract |
| `EbolaLicenceGateway.activate` | Future | Licence activate / सक्रिय / চালু | device binding | decision / Existing contract |
| `EbolaLicenceGateway.validate` | Future | Licence validation / सत्यापन / যাচাই | binding | decision / Existing contract |
| `EbolaLicenceGateway.replace` | Future | Approved warranty transfer / बदलें / বদল | approvedCaseId + both devices | decision / Existing contract |
| `EbolaKrishnaApiPort.ask` | Future | Existing KRISHNA Brain / कृष्णा / কৃষ্ণা | prompt, conversation, device, locale | text / Existing contract |
| `EbolaMediaTransferCoordinator.transfer` | Future | Receipt-verified secure Vault transfer / सुरक्षित फाइल / নিরাপদ ফাইল | manifest | vault receipt / Existing contract |

## 3. Company OS API proposals / Agentic company / এজেন্ট কোম্পানি
| Proposed intent | Type | Description / विवरण / বিবরণ | Required inputs | Status |
|---|---|---|---|---|
| `oneQrOpen` | Voice+Vision | Existing referral QR / वही QR / একই QR | sponsor, user session | Planned integration |
| `onboardEbolaHome` | Agent action | House/property / घर / বাড়ি | ownership, images, consent | Planned integration |
| `onboardEbolaShop` | Agent action | Store/products / दुकान / দোকান | merchant auth, products | Planned integration |
| `onboardEbolaRestaurant` | Agent action | Menu and orders / रेस्तराँ / রেস্তোরাঁ | merchant auth, menu | Planned integration |
| `onboardEbolaHotel` | Agent action | Rooms and availability / होटल / হোটেল | merchant auth, inventory | Planned integration |
| `publishWhatsAppCatalog` | Tool action | Authorized catalog / WhatsApp कैटलॉग / ক্যাটালগ | merchant token, consent | Planned integration |
| `manageGoogleBusiness` | Tool action | Business Profile updates / Google व्यापार / ব্যবসা | owner OAuth/scope | Planned integration |
| `captureCrmLead` | Tool action | Leads and followup / CRM लीड / লিড | consent, merchant, contact | Planned integration |
| `createOrderInvoice` | Tool action | Invoice and GST / बिल / বিল | verified order, tax config | Planned integration |
| `prepareMgcOrderDraft` | Trading action | MGC chart and draft only / ट्रेड ड्राफ्ट / ট্রেড খসড়া | broker auth, live data | Planned integration |
| `confirmMgcOrder` | Trading action | Strong fresh trade confirmation / पुष्टि / নিশ্চিতকরণ | explicit auth, risk gate | Planned integration |
| `generateBrahmaVideo` | Agent action | Video workflow / वीडियो / ভিডিও | approved media, model budget | Planned integration |
| `describeScene` | Vision action | Accessibility aid / दृश्य विवरण / দৃশ্য বর্ণনা | camera consent, capability | Planned integration |
| `reportToOwner` | Agent action | 6 directors/30 managers report / रिपोर्ट / রিপোর্ট | job ID, audit | Planned integration |

## 4. Example — mock SDK evaluation
```dart
import 'package:ebola_wearable_sdk/ebola_wearable_sdk.dart';
final registry = EbolaAdapterRegistry();
registry.register(EbolaMockAdapter()); // DEMO: not verified physical glasses
```

**Never** treat these proposed intents as real live API endpoints or trust client-selected `EBOLA_OWN_BRAND` to waive licence fees. See `docs/SECURITY_AND_DEPLOYMENT.md`.
