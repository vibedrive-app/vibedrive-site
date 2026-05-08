---
layout: default
title: Privacy Policy
permalink: /privacy/
---

# VibeDrive — Privacy Policy

**Effective date:** 2026-05-02
**Last updated:** 2026-05-02

> **Draft notice.** This document is a publishable starting point reviewed by an AI assistant against the VibeDrive client and Cloud Run backend code. It is **not legal advice**. Before linking it from the Play Store listing or in-app, have it reviewed by an advocate enrolled with an Indian Bar Council, fill in `{{YOUR_FULL_LEGAL_NAME}}` and `{{YOUR_REGISTERED_OFFICE_ADDRESS}}`, and confirm the data flows still match what's deployed.

---

## 1. Who we are

This Privacy Policy describes how **{{YOUR_FULL_LEGAL_NAME}}**, an individual carrying on business as a sole proprietor in India under the trade name **"VibeDrive"** (referred to here as "**we**", "**us**", "**I**", or "**VibeDrive**"), collects, uses, and shares your personal data when you use the **VibeDrive** mobile application for Android (Google Play package `com.drivex.vibedrive`, the "**App**").

For the purposes of the **Digital Personal Data Protection Act, 2023** (India) ("**DPDP Act**"), I am the **Data Fiduciary** in respect of your personal data. For the EU GDPR / UK GDPR, I am the **controller**.

| Detail | Value |
|---|---|
| Data Fiduciary / Controller | {{YOUR_FULL_LEGAL_NAME}}, sole proprietor trading as "VibeDrive" |
| Principal place of business | {{YOUR_REGISTERED_OFFICE_ADDRESS}} |
| General contact | contact@vibedrive.app |
| Privacy / data-rights contact | contact@vibedrive.app |
| Grievance Officer (India, DPDP §8(4) / §13) | See §16 |

Until I incorporate a private limited company or LLP, I am personally the Data Fiduciary. If that changes, this policy will be updated and existing users notified before the change takes effect.

## 2. Scope

This policy applies to the VibeDrive Android application distributed through the Google Play Store. It does not apply to:

- Third-party services we integrate with (Google, Firebase, Cloudflare) — they are governed by their own privacy notices, summarised in §6.
- Any future website or marketing pages, unless that page links back to this policy.

## 3. What VibeDrive does

VibeDrive lets you upload audio tracks, separates them into stems (vocals, drums, bass, other) on our cloud backend using a Demucs neural network, and plays them back with audio effects driven by your phone's motion sensors and GPS. To do that we briefly process audio you upload, ephemeral metadata derived from your own tracks on your device, account information needed to authenticate you, and Google Play purchase tokens used to verify your subscription.

## 4. Personal data we process

### 4.1. Information you provide

| Category | Examples | Why we have it |
|---|---|---|
| Account identifiers | Google account email address, Firebase UID | Sign-in, restoring purchases on a new device |
| Audio you upload | Source audio file (≤ 50 MB), derived stems | Separation pipeline output (returned to you as a `.vdx` file) |
| Subscription information | Google Play purchase token, product ID (e.g., `vibedrive_pro`), base-plan ID (e.g., `monthly`, `yearly`), purchase state | Verifying subscription entitlement and quota |
| Push-notification token | Firebase Cloud Messaging (FCM) registration token | Sending you job-progress, job-complete, and job-failed notifications |
| Support correspondence | Anything you send to contact@vibedrive.app | Replying to you and resolving the issue |

I do **not** ask for your government-issued ID, payment-card numbers, or banking details. Subscription payments are processed by Google Play; I never see your card or billing address.

### 4.2. Information collected automatically when you use the App

| Category | Examples | When collected | Stored where |
|---|---|---|---|
| Device sensors | IMU (accelerometer, gyroscope, magnetometer) and GPS readings | Only while a driving session is active | **On your device only — not transmitted to our servers** |
| Approximate / precise location | GPS coordinates, derived speed and heading | Only while a driving session is active and you have granted the location permission | **On your device only — not transmitted to our servers** |
| Crash diagnostics | Stack traces, native crash dumps, device model, OS version, app version, line of code that crashed | **Only if you opt in** to "Share crash reports" on the privacy onboarding screen or in Settings | Firebase Crashlytics (Google) |
| Usage analytics | Which screens you open, which features you tap, anonymous session counts | **Only if you opt in** to "Share anonymous usage analytics" | Firebase Analytics (Google) |
| Backend logs | API request timestamps, HTTP status codes, request IDs, your Firebase UID | Whenever the App calls the backend | Cloud Run service logs (Google), retained 30 days max |
| Device-integrity attestations | Play Integrity Token, Firebase App Check token | When the App calls protected backend endpoints | Used in real time; not persisted server-side beyond the request lifecycle |

**Sensor and location data stays on your device.** It is used to drive the audio engine in real time. We do not upload raw sensor traces, GPS tracks, driving routes, listening histories, or any per-track metadata derived on your device, except as set out below.

**Crash and analytics telemetry is opt-in.** Both toggles default to **off** on first launch. You can change them at any time under **Settings → Privacy**. Turning a toggle off stops new events from your device immediately.

### 4.3. What leaves your device when you use specific features

| Feature | What leaves the device | What happens to it on the server |
|---|---|---|
| Sign-in | Firebase ID token, Google account email | Used to identify you; email stored in your `users/{uid}` record |
| Track upload | Source audio file via a 1-hour signed Google Cloud Storage URL | Stored in the `vibedrive-uploads` bucket; **deleted automatically after 1 day** |
| Stem separation | Job parameters (UID, jobId, GCS path) | Triggers a Cloud Run GPU job; intermediate WAV stems written to `vibedrive-processing` bucket and **deleted automatically after 1 day**; final `.vdx` written to your `vibedrive-vault` cloud library on Cloudflare R2 and kept until you delete it (subject to your plan's library cap; see §8) |
| Job notifications | FCM token (sent via `PUT /v1/users/fcm-token`) | Stored in your `users/{uid}` record; used by FCM to push job-status messages to your device |
| Track transitions | Per-track derived metadata (BPM, drum pattern, vocal segments, song structure) for the tracks you are mixing | Used in-memory to compute transition recommendations; **not stored** |
| Subscription verification | Google Play purchase token, product ID | Sent to Google Play Developer API for verification; entitlement is recorded in your `users/{uid}` record |
| Account deletion | Authenticated `DELETE /v1/users/me` request | See §13 |
| Data export | Authenticated `GET /v1/users/me/export` request | See §10.4 |

### 4.4. Information we receive from third parties

| Source | Information | Purpose |
|---|---|---|
| Firebase Authentication (Google) | Your Google account email and a stable Firebase UID | Authentication |
| Google Play Billing | Purchase token, product ID, base-plan ID, purchase state | Verifying your subscription |
| Firebase App Check / Google Play Integrity API | Attestation tokens proving the request comes from a genuine, unmodified install of VibeDrive | Anti-abuse — preventing tampered clients from calling our backend |

We do **not** purchase data about you from data brokers, advertising networks, or social platforms. We do not show advertising in the App and do not use your data for advertising.

## 5. How we use your data

We use your data to:

1. **Provide the core service** — sign you in, run stem separation on the Cloud Run backend, deliver `.vdx` files back to your device, and run the on-device driving-state audio engine.
2. **Operate the cloud pipeline** — receive uploaded audio, dispatch GPU jobs, package output, and notify you when jobs complete or fail.
3. **Process subscriptions** — verify Google Play purchase tokens, record your entitlement, enforce quotas (15 / 60 / 300 minutes per month for Free / Starter / Pro respectively).
4. **Maintain reliability and security** — detect crashes (if you opt in), prevent abuse of our backend by tampered or automated clients, rate-limit anomalous traffic.
5. **Improve the product** — understand which features are used (if you opt in to analytics).
6. **Communicate with you** — reply to support emails and send transactional notifications.
7. **Comply with law** — respond to lawful requests, enforce our Terms, and meet tax / accounting obligations.

We do **not** use your audio, sensor data, location, or listening history to train machine-learning models, build advertising profiles, or sell to third parties.

### 5.1. Lawful basis (DPDP Act, India)

We process your personal data on the basis of your **consent** under §6 of the DPDP Act 2023, given when you accept this Privacy Policy and the Terms & Conditions and grant in-app permissions. You may withdraw your consent under §6(4) of the DPDP Act at any time by deleting your account (see §13). Processing already carried out before withdrawal remains lawful.

For records we are legally required to retain (tax, accounting), we rely on §7(b) of the DPDP Act (compliance with law).

### 5.2. Lawful basis (GDPR / UK GDPR — EEA, UK, Switzerland)

Where the GDPR applies, we rely on the following Art. 6 bases:

| Processing | Legal basis |
|---|---|
| Account creation, separation, playback, billing | Contract (Art. 6(1)(b)) |
| Crash reporting and analytics | Consent (Art. 6(1)(a)) — revocable at any time |
| Anti-abuse / Play Integrity attestation | Legitimate interests (Art. 6(1)(f)) — fraud prevention and protecting backend availability |
| Tax and accounting records | Legal obligation (Art. 6(1)(c)) |

## 6. Third-party services and processors

The following providers process information on our behalf as **Data Processors** (DPDP) / **sub-processors** (GDPR). Each link is the provider's own privacy notice.

| Service | Provider | What it sees | Privacy notice |
|---|---|---|---|
| Firebase Authentication | Google | Email, Firebase UID, sign-in events | https://firebase.google.com/support/privacy |
| Firebase Crashlytics | Google | Crash stack traces, device/app metadata (opt-in) | https://firebase.google.com/support/privacy |
| Firebase Analytics | Google | Pseudonymous usage events (opt-in) | https://firebase.google.com/support/privacy |
| Firebase App Check | Google | Attestation tokens | https://firebase.google.com/support/privacy |
| Firebase Cloud Messaging (FCM) | Google | FCM token, message payloads (job ID, download URL, BPM, error code) | https://firebase.google.com/support/privacy |
| Google Play Integrity API | Google | Device + app integrity verdict | https://policies.google.com/privacy |
| Google Cloud Run | Google | Backend API requests, server logs | https://cloud.google.com/terms/cloud-privacy-notice |
| Google Cloud Storage | Google | Audio uploads (`vibedrive-uploads`) and intermediate stems (`vibedrive-processing`) | https://cloud.google.com/terms/cloud-privacy-notice |
| Cloudflare R2 | Cloudflare | Your `.vdx` cloud library (`vibedrive-vault`) | https://www.cloudflare.com/privacypolicy/ |
| Google Cloud Firestore | Google | User and job records | https://cloud.google.com/terms/cloud-privacy-notice |
| Google Cloud Tasks | Google | Job dispatch payloads (UID, jobId, GCS paths) | https://cloud.google.com/terms/cloud-privacy-notice |
| Google Play Billing + Play Developer API | Google | Purchase tokens, product IDs | https://policies.google.com/privacy |

If we add another processor beyond those listed above, this table will be updated before that processor receives any production data.

## 7. Sharing, disclosure, and cross-border transfer

### 7.1. We do not sell your data

We do **not sell** your personal data, and we do **not share** it for cross-context behavioural advertising or for ad targeting. We disclose personal data only:

- **To the processors listed in §6**, under written terms (Google Cloud Data Processing Addendum) that limit them to processing on our instructions.
- **To you** — your account information is shown back to you in the App.
- **In legal contexts** — to comply with subpoenas, court orders, or other legally binding requests; to enforce our Terms; or to protect the rights, property, or safety of users, the public, or VibeDrive.
- **In a corporate transaction** — if the proprietorship is converted to a private limited company, an LLP, or transfers its business, your data may be transferred subject to the surviving entity honouring this policy. We will notify you in-app or by email before any such transfer becomes effective.

### 7.2. Cross-border transfer

Although the Data Fiduciary (the proprietor) is resident in India, the App's backend infrastructure is operated on **Google Cloud Platform in the United States** (Cloud Run, Cloud Storage, Firestore, Cloud Tasks; primary region `us-central1`) and on **Cloudflare R2 object storage** for your `.vdx` cloud library (region selected per launch market). When you use the App, your personal data is transferred to and processed in those regions.

We rely on:

- For Indian users: §16 of the DPDP Act, which permits transfer of personal data outside India except to countries that the Central Government may notify as restricted. As of the effective date above, no such country has been notified. If a restriction is notified that affects our infrastructure, we will migrate accordingly or notify you.
- For EEA / UK / Swiss users: the European Commission's Standard Contractual Clauses (SCCs), executed with Google Cloud as part of the [Google Cloud DPA](https://cloud.google.com/terms/data-processing-addendum).

We may, in the future, migrate to Google Cloud regions in India (`asia-south1`, Mumbai; `asia-south2`, Delhi). If we do, we will update this policy.

## 8. Retention

| Data | Retention |
|---|---|
| Source audio you upload (`vibedrive-uploads` bucket) | **Deleted automatically after 1 day** |
| Intermediate WAV stems (`vibedrive-processing` bucket) | **Deleted automatically after 1 day** |
| Final `.vdx` cloud library (`vibedrive-vault` bucket on Cloudflare R2) | Kept until you delete the track via **Library → Delete** or `DELETE /v1/users/me/tracks/{trackId}`. Subject to your plan's library cap (1 GB Free / 5 GB Starter / 50 GB Pro). On subscription downgrade, over-cap tracks are marked `frozen` after a 30-day grace and remain stored (but not playable) until you delete or re-upgrade. Signed download URLs expire after 1 hour. |
| User record in Firestore (email, plan, FCM token, quota) | Until you delete your account (see §13), or 24 months after your last sign-in, whichever is sooner |
| Job history in Firestore | Same as the user record |
| On-device caches (stems, settings, sensor smoothing state) | Until you uninstall the App or clear app data |
| Crash reports (if opted in) | 90 days (Firebase Crashlytics default) |
| Analytics events (if opted in) | 14 months (Firebase Analytics default) |
| Cloud Run request logs | ≤ 30 days |
| Subscription / billing records (for tax compliance) | 8 financial years from the end of the relevant year, per §36 of the CGST Act 2017 |
| Support correspondence | 24 months after the ticket is closed |

## 9. Security

We protect your data with measures commensurate to its sensitivity, including:

- **TLS** in transit between the App and our backend.
- **Encryption at rest** on Google Cloud Storage and Firestore (Google-managed keys).
- **On-device** encryption of authentication tokens via the Android Keystore (`EncryptedSharedPreferences`).
- **Authentication on every protected endpoint** — Firebase ID token, plus Play Integrity and Firebase App Check tokens for high-risk operations (uploads, job start, account deletion).
- **R8** code-shrinking and resource-shrinking on release builds.
- **Principle of least privilege** for proprietor access to production systems.

We comply with the Indian **Information Technology (Reasonable Security Practices and Procedures and Sensitive Personal Data or Information) Rules, 2011**, the cybersecurity-incident reporting obligations in the **Indian Computer Emergency Response Team (CERT-In) Directions dated 28 April 2022**, and Google Cloud's standard security posture for the services we use.

No system is perfectly secure. If we become aware of a breach affecting your personal data, we will notify you, the Indian Data Protection Board, CERT-In, and other applicable regulators in line with our legal obligations and within the timelines they prescribe (CERT-In: within **6 hours** of becoming aware of a notifiable incident).

## 10. Your rights — Indian users (DPDP Act 2023)

If you are a **Data Principal** under the DPDP Act, you have the following rights in relation to personal data we process about you:

| Right | DPDP cite | How to exercise |
|---|---|---|
| Right to access information about your personal data | §11(1)(a) | Use **Settings → Account → Export my data** in-app, or call `GET /v1/users/me/export`, or email contact@vibedrive.app |
| Right to correction or completion of inaccurate data | §12(1)(a) | Email contact@vibedrive.app from your registered email |
| Right to erasure of personal data no longer required for the purpose for which it was collected | §12(1)(b) | Use **Settings → Account → Delete account** in-app, or email contact@vibedrive.app |
| Right of grievance redressal | §13 | See §16 below |
| Right to nominate another person to exercise your rights in case of death or incapacity | §14 | Email contact@vibedrive.app with your nominee's name and contact details; we will record the nomination |
| Right to withdraw consent | §6(4) | Stop using the App and/or delete your account |

We will respond to a verified rights request within **30 days** of receipt. We may extend this once by a further 30 days for complex requests, in which case we will tell you why.

### 10.1. Verification

To prevent unauthorised data disclosure, we will verify a rights request by confirming you can sign in to the registered Google account, or by other reasonable means proportionate to the sensitivity of the request.

### 10.2. Complaints

If you are dissatisfied with our response or our handling of your data, you may complain to:

1. Our Grievance Officer (§16) in the first instance.
2. The **Data Protection Board of India**, established under Chapter V of the DPDP Act, at the contact details published from time to time on the Ministry of Electronics & Information Technology website.

### 10.3. Children

VibeDrive is not directed to **children** as defined in §2(f) of the DPDP Act (any individual under 18 in India). If you are under 18 and resident in India, **do not use the App**. We do not knowingly process personal data of Indian children. We do not undertake tracking, behavioural monitoring, or targeted advertising in respect of children under §9(3). If you believe an Indian child has provided us data, email contact@vibedrive.app and we will delete it.

For users **outside India**, see §14.

### 10.4. Data portability via API

The App and our backend support a **data export endpoint** (`GET /v1/users/me/export`) that returns:

- Your user record (email, subscription plan, quota state, FCM token excluded for safety)
- Your last 500 jobs with their status, stages, durations, and BPM values
- The export timestamp

The endpoint is accessible from in-app **Settings → Account → Export my data**. The response is a structured JSON document suitable for re-import or archival.

## 11. Your rights — EEA, UK, and Swiss users (GDPR / UK GDPR / FADP)

If you are in the EEA, the UK, or Switzerland, you have these rights under the GDPR (and the UK GDPR / Swiss FADP equivalents):

- Access (Art. 15)
- Rectification (Art. 16)
- Erasure / "right to be forgotten" (Art. 17)
- Restriction of processing (Art. 18)
- Data portability (Art. 20) — see §10.4 for the export endpoint
- Objection (Art. 21), including objection to processing based on legitimate interests
- Withdraw consent (Art. 7(3)) at any time, without affecting the lawfulness of processing before withdrawal — applies to the crash and analytics toggles
- Lodge a complaint with your local supervisory authority. A list of authorities is at https://edpb.europa.eu/about-edpb/about-edpb/members_en. UK residents may complain to the **Information Commissioner's Office** at https://ico.org.uk/make-a-complaint/.

To exercise these rights, email contact@vibedrive.app from your registered Google account email. We will respond within 30 days.

> Because we are an Indian-domiciled controller offering services into the EU/UK, GDPR Art. 27 may require us to designate a representative in the Union and/or the UK. We will appoint and publish that representative before commencing material processing of EEA/UK personal data; until that appointment, requests can be sent directly to the address above and we will route them.

## 12. Your rights — California residents (CCPA / CPRA)

If you reside in California, you have the following rights:

- **Right to know** the categories of personal information collected, sources, purposes, and categories of third parties (all summarised above).
- **Right to access** the specific pieces of personal information we hold (see §10.4).
- **Right to delete**, subject to exceptions in Cal. Civ. Code § 1798.105(d).
- **Right to correct** inaccurate personal information.
- **Right to limit use of sensitive personal information** — VibeDrive does not use sensitive personal information for any purpose beyond what § 1798.121 permits without consent.
- **Right to opt out of sale or sharing** — **we do not sell or share your personal information** as those terms are defined under the CCPA / CPRA.
- **Right to non-discrimination** for exercising any of these rights.

To exercise, email contact@vibedrive.app or use the in-app **Delete account** action. We respond within 45 days (extendable once by 45 days where permitted). You may designate an authorised agent in writing.

## 13. Account deletion

You can delete your account in three ways:

1. **In the App**: **Settings → Account → Delete account**. Confirm the warning. The App calls `DELETE /v1/users/me` on our backend.
2. **Web form** (if available): {{ACCOUNT_DELETION_WEB_URL}}.
3. **By email**: send "Delete my VibeDrive account" from your registered Google account email to contact@vibedrive.app. We will process within 7 days of verification.

When the deletion request is processed, the backend executes the following cascade:

1. Your Firebase refresh tokens are **revoked immediately** — any cached session is invalidated.
2. Your `users/{uid}` record is tombstoned in Firestore. From this point we treat your account as non-existent for read traffic.
3. Any in-flight separation jobs you own are **failed** with `error: ACCOUNT_DELETED`; reserved quota is released.
4. **All your blobs are deleted** — `vibedrive-uploads/{uid}/` and `vibedrive-processing/{uid}/` from Google Cloud Storage, and `vibedrive-vault/{uid}/` from Cloudflare R2 — typically within seconds.
5. Your job records in Firestore are deleted.
6. Your `users/{uid}` record is deleted.
7. Your Firebase Authentication record is deleted.

Steps 1–7 normally complete within 1 minute. The only data we cannot delete are events that have already left our control — Firebase Crashlytics and Analytics events that are already in Google's systems are retained per the timelines in §8 and are anonymised after that period; tax records we are legally required to retain.

> **If you have an active paid subscription, deleting your account does NOT cancel it.** Google Play will continue to bill the subscription until you cancel it via https://play.google.com/store/account/subscriptions. We cannot cancel your Play subscription on your behalf. **Cancel first, then delete.**

## 14. Children outside India

For users **outside India**, the minimum age to use VibeDrive is **13 years**. We do not knowingly process personal data of children under 13 (or under the equivalent minimum age in your jurisdiction; e.g., 14 in Spain or 16 in some EU member states under GDPR Art. 8). If you believe a child has provided us data, email contact@vibedrive.app and we will delete it.

## 15. Permissions we request

| Permission | Why VibeDrive needs it | What happens if you deny |
|---|---|---|
| `INTERNET` | Auth, separation, streaming, telemetry | The App cannot function |
| `ACCESS_FINE_LOCATION` / `ACCESS_COARSE_LOCATION` | Detect speed and heading for the driving audio engine | Driving features disabled; static playback still works |
| `ACTIVITY_RECOGNITION` | Detect when you start driving | Driving sessions cannot be auto-started |
| `FOREGROUND_SERVICE` (and audio-foreground variants) | Continue audio playback when the App is backgrounded | Playback may be paused |
| `POST_NOTIFICATIONS` | Show playback controls and processing-job status | You will not see the media notification or job updates |
| `READ_MEDIA_AUDIO` (Android 13+) / `READ_EXTERNAL_STORAGE` (older) | Import tracks you select | You cannot import local files |

Sensor permissions like accelerometer and gyroscope are not runtime-permissioned on Android.

## 16. Grievance Officer (India)

Per §8(4) and §13 of the DPDP Act 2023 and Rule 5(3) of the Consumer Protection (E-Commerce) Rules, 2020:

> **Grievance Officer:** {{YOUR_FULL_LEGAL_NAME}}
> **Designation:** Proprietor, VibeDrive
> **Address:** {{YOUR_REGISTERED_OFFICE_ADDRESS}}
> **Email:** contact@vibedrive.app
> **Acknowledgment time:** within **48 hours** of receipt of grievance
> **Resolution time:** within **30 days** of receipt of grievance

If you are not satisfied with the response, you may escalate to the Data Protection Board of India (§10.2) or to the consumer fora established under the Consumer Protection Act, 2019.

## 17. Changes to this Policy

We may update this policy. The "Last updated" date at the top reflects the current version. If we make material changes — new categories of personal data, new purposes of processing, or sharing with new categories of third parties — we will notify you in-app and, where required by law, ask for renewed consent before the change takes effect. Older versions will be available at {{POLICY_ARCHIVE_URL}}.

## 18. Contact

**{{YOUR_FULL_LEGAL_NAME}}** (sole proprietor, trading as "VibeDrive")
{{YOUR_REGISTERED_OFFICE_ADDRESS}}
Email: contact@vibedrive.app

For privacy questions, rights requests, grievances, or complaints, write from your registered Google account email.
