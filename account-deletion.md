---
layout: default
title: Account Deletion
permalink: /account-deletion/
---

# Delete your VibeDrive account

You can delete your VibeDrive account in two ways. Either path completely removes your account and personal data from our servers.

## 1. From inside the app (recommended)

1. Open VibeDrive.
2. Go to **Settings &rarr; Account &rarr; Delete account**.
3. Confirm.

The app calls our backend to revoke your sessions and delete all uploaded audio, derived stems, job records, and your user record across Firebase Authentication, Firestore, and Google Cloud Storage. This typically completes within a minute.

## 2. By email

Send an email titled **"Delete my VibeDrive account"** to [contact@vibedrive.app](mailto:contact@vibedrive.app) **from the Google account email registered with your VibeDrive account**. We will verify and process the deletion within 7 days.

## What gets deleted

When your deletion request is processed:

- Your Firebase refresh tokens are revoked immediately.
- Your user record (email, FCM push token, subscription plan, quota state) is deleted from our database.
- All your uploaded audio, intermediate stems, and `.vdx` outputs in Google Cloud Storage are deleted.
- All your processing job records are deleted.
- Your Firebase Authentication record is deleted.

## What we cannot delete immediately

- **Crash and analytics events already received by Google** (only relevant if you opted into telemetry) &mdash; these are anonymised on the schedule described in our [Privacy Policy](/privacy/).
- **Tax and accounting records** for any past purchases &mdash; retained for 8 financial years as required under Indian tax law (CGST Act &sect;36).

## Cancelling a subscription is separate

If you have an active VibeDrive Starter or Pro subscription, **deleting your account does NOT cancel the subscription**. Google Play will continue to bill it until you cancel at [play.google.com/store/account/subscriptions](https://play.google.com/store/account/subscriptions).

**Cancel your subscription first, then delete your account.**

## Questions

Email [contact@vibedrive.app](mailto:contact@vibedrive.app).
