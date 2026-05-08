---
layout: default
title: Terms &amp; Conditions
permalink: /terms/
---

# VibeDrive — Terms & Conditions

**Effective date:** 2026-05-02
**Last updated:** 2026-05-02

> **Draft notice.** This document is a publishable starting point reviewed by an AI assistant against the VibeDrive client and Cloud Run backend code. It is **not legal advice**. Before linking it from the Play Store listing or in-app, have it reviewed by an advocate enrolled with an Indian Bar Council, fill in `{{YOUR_FULL_LEGAL_NAME}}`, `{{YOUR_REGISTERED_OFFICE_ADDRESS}}`, and `{{YOUR_CITY}}, {{YOUR_STATE}}` (used for forum), and confirm you are happy with the dispute-resolution and refund clauses.

---

## 1. Agreement to these Terms

These Terms & Conditions ("**Terms**") form a binding contract between you and **{{YOUR_FULL_LEGAL_NAME}}**, an individual carrying on business as a sole proprietor in India under the trade name **"VibeDrive"** (referred to here as "**we**", "**us**", "**I**", or "**VibeDrive**"). They govern your use of the VibeDrive Android application (Google Play package `com.drivex.vibedrive`, the "**App**") and any related backend services (collectively, the "**Service**").

**By installing, signing into, or using the App, you agree to these Terms.** If you do not agree, do not use the Service.

These Terms together with our Privacy Policy at https://vibedrive.app/privacy (incorporated by reference) constitute an "electronic record" under the **Information Technology Act, 2000** and do not require a physical or digital signature.

If you use the Service on behalf of an organisation, you confirm you are authorised to bind that organisation, and "you" means both you personally and the organisation.

## 2. Eligibility

You may use the Service only if:

- You are at least **13 years old** (or the higher age applicable in your jurisdiction; see §2.1).
- You can form a binding contract under §11 of the **Indian Contract Act, 1872** or the equivalent in your jurisdiction.
- You are not barred from using software services under any applicable sanctions or export-control law.
- Your account has not been previously suspended or terminated by us.

### 2.1. Indian users — age 18+

If you are resident in India, **you must be at least 18 years old** to use the Service. This is required to give valid consent under the **Indian Contract Act, 1872** §10–§11 and to be a "Data Principal" capable of consenting to processing under the **Digital Personal Data Protection Act, 2023** §6 without parental consent. We do not currently support a parental-consent flow for Indian children, and Indian users who are under 18 must not use the Service.

### 2.2. Other jurisdictions

If you are outside India, the minimum age is 13 unless local law requires a higher age (for example, 14 in Spain or 16 in some EU member states under GDPR Art. 8).

## 3. Your account

To use the Service you must sign in with a Google account through Firebase Authentication. You are responsible for:

- Keeping your Google credentials secure.
- All activity that happens under your account.
- Notifying us promptly at contact@vibedrive.app if you suspect unauthorised access.

We may refuse, suspend, or terminate any account at our discretion if we reasonably believe you are violating these Terms or applicable law, or if continuing the account would expose us or other users to material risk.

## 4. The Service

VibeDrive lets you upload audio tracks, processes them on our cloud backend to separate them into stems (vocals, drums, bass, other), packages the result into a `.vdx` file, and plays it back with audio effects driven by your phone's motion sensors. The cloud pipeline currently runs on Google Cloud Platform.

We may add, change, or remove features at any time. Where a change materially reduces what we previously offered to a paying subscriber, we will give reasonable notice and, where required by law, allow you to cancel and obtain a pro-rata refund of any unused prepaid period.

## 5. Licence to use the App

Subject to your compliance with these Terms, we grant you a personal, limited, non-exclusive, non-transferable, non-sublicensable, revocable licence to install and use the App on Android devices that you own or control, solely for personal, non-commercial use.

## 6. Your content

### 6.1. What is "Your Content"

"**Your Content**" means any audio file you upload to the Service, the stems and `.vdx` files derived from those uploads, any track metadata you enter, and any other material you provide through the App.

### 6.2. Ownership

Your Content remains yours. We do not claim ownership in it.

### 6.3. Licence you grant us

You grant **{{YOUR_FULL_LEGAL_NAME}}** a worldwide, royalty-free, non-exclusive licence to host, store, transmit, process, and adapt Your Content **solely** to operate the Service for you (e.g., to run separation jobs, store stems, deliver `.vdx` outputs back to you, and back them up). This licence ends when Your Content is deleted from our systems per the retention table in the Privacy Policy.

We do **not** use Your Content to train machine-learning models, build advertising profiles, or for any other purpose unrelated to operating the Service for you.

### 6.4. Your representations about Your Content

By uploading Your Content you represent and warrant that:

- You own Your Content, or you have all rights, licences, consents, and permissions necessary to upload, process, and play it through the Service.
- Your Content does not infringe any third party's intellectual property, privacy, publicity, or other rights, and does not violate any applicable law.
- You will not upload audio that you obtained illegally — for example, audio ripped from a streaming service in violation of that service's terms.
- VibeDrive is a tool that processes audio you provide. We do not host, license, or curate audio content. **Liability for the legal status of source material rests entirely with you**, and you indemnify us under §15 for any third-party claim arising from Your Content.

You are solely responsible for Your Content and its consequences.

## 7. Acceptable use

You agree not to:

1. Use the Service for any unlawful purpose or in violation of any applicable law (including the **Information Technology Act, 2000**, the **Copyright Act, 1957**, export-control law, sanctions, and computer-misuse law).
2. Reverse-engineer, decompile, disassemble, modify, or attempt to extract source code or model weights from the App, except to the extent that local law (e.g., EU Software Directive 2009/24/EC Art. 6, or the Indian Copyright Act §52(1)(ab)) expressly permits despite this limitation.
3. Tamper with, repackage, or distribute modified versions of the App.
4. Bypass or attempt to bypass authentication, attestation (Firebase App Check, Play Integrity), rate limits, or other protective measures.
5. Use scripts, bots, scrapers, emulator farms, or other automated means to access the Service without our written permission.
6. Use the Service to process audio you do not have rights to, including content from third-party streaming services obtained in breach of their terms.
7. Interfere with or disrupt the integrity or performance of the Service or its underlying infrastructure.
8. Resell, sublicense, lease, or otherwise commercially exploit the Service or any part of it.
9. Use the Service in a manner that violates traffic laws or endangers yourself or others (see §16 — Driving safety).
10. Upload content that is "obscene", "grossly offensive", or otherwise restricted under §66A / §67 of the IT Act 2000 or **IT (Intermediary Guidelines and Digital Media Ethics Code) Rules, 2021**, Rule 3(1)(b).

We may investigate suspected violations and take appropriate action, including warning you, suspending your access, removing content, or terminating your account.

## 8. Plans and Subscriptions

### 8.1. Plans

VibeDrive currently offers three plans:

| Plan | Monthly minutes of audio you can process | Maximum source file size | Maximum concurrent jobs |
|---|---|---|---|
| **Free** | 15 | 20 MB | 1 |
| **Starter** | 60 | 50 MB | 2 |
| **Pro** | 300 | 50 MB | 5 |

Free is the default for every new account. Starter and Pro are paid auto-renewing subscriptions sold through Google Play Billing under the product IDs `vibedrive_starter` and `vibedrive_pro` (or such other product IDs as we configure in the Play Console from time to time). Each paid product offers monthly and yearly base plans. Prices, free-trial availability, and any introductory-offer details are displayed in the App and on the Google Play Store at the time of purchase, **inclusive of applicable taxes** where Google is required to collect them.

By tapping the purchase button you agree to those prices, the auto-renewal terms in §8.4, and these Terms.

### 8.2. Billing through Google Play

All subscription payments are processed by Google through Google Play Billing under the [Google Play Terms of Service](https://play.google.com/intl/en_us/about/play-terms/). We never see your payment card or banking details. Your subscription is governed jointly by these Terms and Google Play's terms.

For Indian users, Google is the **deemed supplier** for GST purposes under §14 of the **Integrated Goods and Services Tax Act, 2017**. Prices shown to Indian users on Google Play are inclusive of applicable Indian GST collected by Google.

### 8.3. Free trials and introductory offers

If we offer a free trial or introductory offer, the duration and conversion price are shown to you in the App before you start. **Unless cancelled before the trial ends, your subscription will automatically convert to a paid subscription at the standard price and billing cycle and you will be charged through Google Play.** Only one free trial is permitted per account and per Google Play account. Repeated trial use through new accounts is not permitted.

### 8.4. Auto-renewal disclosure (required by Google Play and applicable law)

> **Your VibeDrive Starter or Pro subscription auto-renews.**
>
> - Payment will be charged to your Google Play account at confirmation of purchase.
> - The subscription **automatically renews** at the end of each billing period (monthly or yearly, depending on the plan you chose) at the standard price unless you cancel **at least 24 hours before the end of the current period**.
> - Your Google Play account will be charged for the renewal within 24 hours of the period end.
> - You can manage and cancel your subscription at any time at **https://play.google.com/store/account/subscriptions** or through the Google Play Store app under **Menu → Subscriptions**.
> - Cancelling stops future renewals; it does not refund the current paid period unless required by law (see §8.7).

### 8.5. Price changes

We may change subscription prices. If we do, we will notify you in advance through the App and/or your account email at least 30 days before the change takes effect, and Google Play will independently surface the new price for your renewal consent. If you do not consent to the new price through Google Play before your next renewal, your subscription will not auto-renew at the new price and access to paid features will end at the close of your current paid period.

### 8.6. Restoring purchases

If you reinstall the App or sign in on a new device, tap **Restore purchases** under **Settings → Subscription** to reattach an active subscription to your account. Restoration is keyed to your Google Play account and your Firebase Auth account.

### 8.7. Refunds and statutory rights

Refunds and cancellations are governed by [Google Play's policy](https://support.google.com/googleplay/answer/2479637). To request a refund, follow Google Play's process. We may, at our discretion, also assist with a refund directly; contact contact@vibedrive.app.

**Statutory consumer rights — India.** Nothing in these Terms limits any non-waivable right you have under the **Consumer Protection Act, 2019**, the **Consumer Protection (E-Commerce) Rules, 2020**, or any other consumer-protection law applicable in India.

**Statutory rights — EEA / UK.** If you are a consumer in the EEA, the UK, or another jurisdiction with a mandatory withdrawal or cooling-off right for digital services, you retain that right. Where the law (e.g., EU Directive 2011/83/EU Art. 16(m)) lets us require you to waive your withdrawal right in exchange for immediate access to digital content, your purchase of a subscription with immediate activation constitutes that consent and waiver, except to the extent local law forbids it.

### 8.8. Quotas

Each plan has a monthly minute quota (§8.1). Quotas reset monthly on a cycle anchored to your account creation. Unused minutes do **not** roll over. If you upgrade mid-cycle, the new plan's quota replaces the old one for the remainder of the cycle. We reserve the right to fail or delay processing if you exceed the maximum-concurrent-jobs limit for your plan.

## 9. Intellectual property

### 9.1. Our IP

The App, the backend, our brand, our logos, and all content other than Your Content are owned by **{{YOUR_FULL_LEGAL_NAME}}** or our licensors and are protected by the **Indian Copyright Act, 1957**, the **Trade Marks Act, 1999**, and equivalent laws in other jurisdictions. Except for the licence expressly granted in §5, no rights are granted to you.

### 9.2. Feedback

If you send us feedback, suggestions, or feature requests, you grant us a perpetual, irrevocable, royalty-free, worldwide licence to use, modify, and incorporate that feedback into the Service without obligation to you.

### 9.3. Copyright complaints

If you believe content available through the Service infringes your copyright, send a written notice to contact@vibedrive.app that includes:

- A description of the copyrighted work.
- The location (within the App) of the allegedly infringing material.
- Your contact information.
- A statement, in good faith, that you have a bona fide belief that the use is not authorised by the copyright owner, its agent, or the law.
- A statement, signed under penalty of perjury, that the information in the notice is accurate and that you are the owner or are authorised to act on the owner's behalf.

We act as an "intermediary" within the meaning of §2(1)(w) of the IT Act 2000. On receipt of an effective notice we will act expeditiously to remove or disable access to the material in line with §79 of the IT Act 2000 and Rule 3(1)(d) of the IT (Intermediary Guidelines and Digital Media Ethics Code) Rules, 2021. Repeat infringers may have their accounts terminated.

For US users, we also accept notices that meet the requirements of 17 U.S.C. § 512(c)(3) at the same address.

## 10. Third-party services

The Service relies on third-party services, including Google Play Services, Firebase, Google Cloud Run, Google Cloud Storage, Cloudflare R2 (object storage for your cloud library), and Google Play Billing. Your use of those services is subject to the third party's own terms and privacy policies, summarised in our Privacy Policy.

We are not responsible for third-party services. Outages, bugs, or policy changes at those providers may affect the Service.

## 11. Privacy

Your use of the Service is also governed by our Privacy Policy at https://vibedrive.app/privacy, which is incorporated into these Terms by reference.

## 12. Termination

### 12.1. Termination by you

You may stop using the Service at any time by uninstalling the App. To delete your account, see **Settings → Account → Delete account**, or email contact@vibedrive.app. To stop subscription billing, cancel via Google Play (§8.4) — **deleting your account does NOT cancel an active subscription on Google Play**.

### 12.2. Termination by us

We may suspend or terminate your access to the Service, with or without notice, if:

- You materially breach these Terms.
- Continued provision would expose us or other users to legal, security, or financial risk.
- We are required to do so by law, by a court order, or by a directive from a competent authority.
- We discontinue the Service or a feature you depend on, in which case we will give reasonable notice and, where you are a paying subscriber, a pro-rata refund of any unused prepaid period.

### 12.3. Effect of termination

On termination, your licence under §5 ends; we will delete or anonymise Your Content per the Privacy Policy retention schedule; the following sections survive: §6.3 (residual processor licence for backups), §7 (acceptable use), §9 (IP), §13 (disclaimers), §14 (limitation of liability), §15 (indemnification), and §17 (dispute resolution).

## 13. Disclaimers

**The Service is provided "as is" and "as available", with all faults and without warranty of any kind.** To the maximum extent permitted by law, we and our licensors disclaim all warranties, express or implied, including merchantability, fitness for a particular purpose, non-infringement, accuracy, and uninterrupted operation.

We do not warrant that:

- The Service will be uninterrupted, error-free, or secure.
- Stem-separation results will meet your expectations or be free of audio artifacts.
- The driving-detection features will accurately characterise all driving conditions.
- Your Content will be preserved without loss; **uploads and intermediate stems are deleted within 1 day; final `.vdx` outputs are kept in your cloud library until you delete them, subject to your plan's library cap (see Privacy Policy §8). On subscription downgrade, over-cap tracks become non-playable after a 30-day grace period until you delete enough to fit the new cap or re-upgrade.**

These disclaimers apply only to the extent permitted by law. As a consumer in India, the EEA, the UK, Australia, or another jurisdiction with mandatory consumer guarantees, you retain those rights.

## 14. Limitation of liability

To the maximum extent permitted by law:

- **No indirect damages.** Neither we nor our licensors will be liable for any indirect, incidental, consequential, special, exemplary, or punitive damages, or for any loss of profits, revenue, data, goodwill, or business, arising out of or related to the Service, even if advised of the possibility.
- **Cap on direct damages.** Our total cumulative liability for all claims relating to the Service in any 12-month period will not exceed the greater of (a) the amounts you paid us for the Service in that 12-month period, or (b) **₹5,000** (Indian Rupees five thousand only).

These limits do not apply to liability that cannot be excluded or limited under applicable law (for example, gross negligence, wilful misconduct, or non-excludable consumer guarantees).

## 15. Indemnification

You agree to indemnify and hold harmless **{{YOUR_FULL_LEGAL_NAME}}**, our processors, and our agents from any claim, demand, loss, liability, damage, or expense (including reasonable legal fees) arising out of or related to: (i) your use of the Service; (ii) Your Content; (iii) your violation of these Terms; or (iv) your violation of any third party's rights or any applicable law.

This section does not apply where prohibited by law and is limited to the extent permitted in consumer contracts in your jurisdiction.

## 16. Driving safety

VibeDrive's driving features react to motion data while you are driving. **You are responsible for safe operation of your vehicle and for compliance with all traffic laws, including the Motor Vehicles Act, 1988 (India) and any state-level rules on use of mobile devices in vehicles.** Do not interact with the App in ways that distract you while driving — set your music and effects before you start, mount your device safely, and keep your attention on the road. We are not liable for any consequences of your operation of a vehicle while using the App.

## 17. Governing law and dispute resolution

### 17.1. Governing law

These Terms are governed by the laws of the Republic of India, without regard to its conflict-of-laws rules. The UN Convention on Contracts for the International Sale of Goods does not apply.

### 17.2. Forum

Subject to §17.3 and §17.4, the courts at **{{YOUR_CITY}}, {{YOUR_STATE}}, India** shall have **exclusive jurisdiction** over any dispute arising out of or related to these Terms, and you consent to personal jurisdiction there.

### 17.3. Mandatory consumer protections

If you are a consumer, mandatory consumer-protection laws of your country of residence may give you additional rights and may override the choice of law and forum in §17.1 and §17.2 to the extent of the conflict. **Indian consumers** retain the right to file complaints before the District, State, or National Consumer Disputes Redressal Commission having territorial jurisdiction, in line with the Consumer Protection Act, 2019.

### 17.4. Arbitration / class-action waiver — US users only

If you are a resident of the United States, the parties agree that any dispute will be resolved through binding individual arbitration administered by **JAMS** under its Streamlined Arbitration Rules, with the arbitration seated in **Wilmington, Delaware** (or such other US seat as JAMS may designate). **Neither party may bring claims as part of a class, collective, or representative action.** You may opt out of this arbitration agreement by emailing contact@vibedrive.app within 30 days of first accepting these Terms.

This §17.4 **does not apply** to users resident in India, the EEA, the UK, or any other jurisdiction whose mandatory law makes class-action waivers in consumer contracts unenforceable.

## 18. Grievance Redressal (India) — IT Rules 2021 / Consumer Protection (E-Commerce) Rules 2020

> **Grievance Officer:** {{YOUR_FULL_LEGAL_NAME}}
> **Designation:** Proprietor, VibeDrive
> **Address:** {{YOUR_REGISTERED_OFFICE_ADDRESS}}
> **Email:** contact@vibedrive.app
> **Acknowledgment time:** within **48 hours** of receipt
> **Resolution time:** within **30 days** of receipt of complaint

Indian users may also escalate to:

- The **Data Protection Board of India** (for personal-data complaints under the DPDP Act, 2023).
- The **District / State / National Consumer Disputes Redressal Commission** under the Consumer Protection Act, 2019.
- The Government of India's **National Consumer Helpline** at https://consumerhelpline.gov.in.

## 19. Changes to these Terms

We may update these Terms from time to time. The "Last updated" date at the top reflects the current version. If we make material changes — particularly to the subscription, refund, or dispute-resolution clauses — we will notify you in-app and give at least **30 days' notice** before the change takes effect, with the right to cancel your subscription before then. Continued use of the Service after the effective date of revised Terms constitutes acceptance.

Older versions are available at {{TERMS_ARCHIVE_URL}}.

## 20. Miscellaneous

- **Entire agreement.** These Terms, together with the Privacy Policy and any in-app purchase confirmations, are the entire agreement between you and us about the Service.
- **No waiver.** Our failure to enforce a right is not a waiver of it.
- **Severability.** If any provision is held unenforceable, the remaining provisions continue in effect.
- **Assignment.** You may not assign these Terms. We may assign them on conversion of the proprietorship to a private limited company or LLP, on merger, or on a sale of the business, on notice to you.
- **No third-party beneficiaries.** Except for our processors named in the Privacy Policy, no third party has rights under these Terms.
- **Force majeure.** Neither party is liable for failures caused by events beyond its reasonable control.
- **Distribution channel.** The App is distributed only through Google Play. Provisions specific to other app stores (Apple App Store, Amazon Appstore, etc.) do not apply.
- **Electronic signature / record.** These Terms constitute an "electronic record" under the IT Act, 2000 and do not require a physical or digital signature.

## 21. Contact

**{{YOUR_FULL_LEGAL_NAME}}** (sole proprietor, trading as "VibeDrive")
{{YOUR_REGISTERED_OFFICE_ADDRESS}}
General support: contact@vibedrive.app
Privacy / data requests: contact@vibedrive.app
Grievance / copyright complaints: contact@vibedrive.app
