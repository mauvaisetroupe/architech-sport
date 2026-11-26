---
title: HUAWEI Health
description: Read in Step Challenge the steps synced with HUAWEI Health, on an Android phone of any brand.
weight: 2
---

Most watches send their steps to Health Connect, where Step Challenge
reads them (see the [Health Connect help]({{< relref "/step-challenge/help/health-connect" >}})).
**HUAWEI Health does not**: its data stays in Huawei's cloud. Step
Challenge can read it there, with your permission: this is the
**HUAWEI Health** source.

This page is for people whose watch or band syncs with **HUAWEI Health**,
on a Huawei phone or a phone of another brand (Samsung, Google Pixel, Xiaomi…).

## 1. Install Huawei's apps

You probably have them already, since the watch needs them:

1. **AppGallery**, Huawei's app store. On a phone of another brand,
   download it from Huawei's official website,
   [appgallery.huawei.com](https://appgallery.huawei.com/), then install
   it (Android asks you to allow installs from your browser).
2. **HUAWEI Health**, from AppGallery: the app that pairs and syncs your
   watch.
3. **HMS Core** (Huawei Mobile Services), from AppGallery. It lets
   Step Challenge sign you in to your HUAWEI account. It is often
   installed with HUAWEI Health: check that it is there and up to date.

## 2. Check that your steps reach Huawei's cloud

Step Challenge reads your steps in Huawei's cloud, not in the watch.

1. Open **HUAWEI Health** and check that your watch's steps show up.
2. In HUAWEI Health, **Me → Privacy management**: turn on the sync with
   the cloud.

## 3. Choose HUAWEI Health in Step Challenge

1. **More** tab, **Step source**.
2. Choose **HUAWEI Health**, then confirm.
3. Sign in with your **HUAWEI account** and allow reading your steps.
   Only the step count is read, as described in the
   [privacy policy]({{< relref "/step-challenge/privacy" >}}).

When HUAWEI Health is installed on your phone, the Step Challenge home
screen also suggests it: **Use HUAWEI Health**.

The steps of the last 30 days are read again from HUAWEI Health. A day
already sent with more steps keeps its value. On the authorization
screen, also tick reading **historical data**: without it, HUAWEI Health
only gives the steps recorded since your authorization.

## What changes with HUAWEI Health

- Your steps arrive when HUAWEI Health syncs with the cloud, sometimes a
  few minutes behind the watch. Open HUAWEI Health if a number seems
  late.
- Step Challenge reads your steps **when you open it** (and when you
  pull down to refresh): not in the background yet.
- The day's curve (Statistics → 1D) is hour by hour, if your watch
  sends this detail to HUAWEI Health (Huawei watches do); otherwise only
  the day's total exists.
- The minute-by-minute detail (inactivity, active minutes, activity
  score) is not available: Step Challenge says so wherever it applies.

## Stop using HUAWEI Health

**More** tab, **Step source**, **Remove access to HUAWEI Health** (or
choose **Health Connect**). Step Challenge removes its access and reads
your steps from Health Connect again. If it can't, it tells you: remove
it yourself in HUAWEI Health, **Me → Privacy management**, in the
authorized apps.

Steps already sent stay in Step Challenge; to erase them, delete your
account (**More**, **Account**).

## It doesn't work?

- **No steps, or only today's**: check step 2, then wait for HUAWEI
  Health to sync.
- **HUAWEI sign-in fails**: update HMS Core from AppGallery, then try
  again.
- **"Step Challenge can't access your steps in HUAWEI Health"**: the
  permission was withdrawn in HUAWEI Health, refused, or given without
  the steps box. Tap **Authorize HUAWEI Health** and tick the steps.
- **"HUAWEI Health Kit denies access to your steps"**: tap **Authorize
  again** and tick the steps. If that's not enough, in HUAWEI Health,
  **Me → Privacy management**, check that **HUAWEI Health Kit** is on
  and that Step Challenge is allowed there.
- **"HMS Core isn't responding"**, or loading that never ends: close
  Step Challenge completely (swipe it out of recent apps) and open it
  again.
- **Steps no longer update**: in HUAWEI Health, **Me → Privacy
  management**, turn **HUAWEI Health Kit** off for about ten seconds,
  then back on.
- **To dig deeper**: **More** tab, **Diagnostics**, **Run the
  diagnostics**. It tests the HUAWEI sign-in and the step reading; you
  can copy the result and send it to support.

Still stuck? Write to [support@architech.lu](mailto:support@architech.lu).
