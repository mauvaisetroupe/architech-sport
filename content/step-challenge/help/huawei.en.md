---
title: Huawei watch
description: Read the steps of a Huawei watch or band in Step Challenge, on an Android phone of any brand.
weight: 2
---

Most watches send their steps to Health Connect, where Step Challenge
reads them (see the [Health Connect help]({{< relref "/step-challenge/help/health-connect" >}})).
**Huawei Health does not**: its data stays in Huawei's cloud. Step
Challenge can read it there, with your permission: this is the
**Huawei Health** source.

This page is for people with a **Huawei watch or band**, on a Huawei
phone or a phone of another brand (Samsung, Google Pixel, Xiaomi…).

## 1. Install Huawei's apps

You probably have them already, since the watch needs them:

1. **AppGallery**, Huawei's app store. On a phone of another brand,
   download it from Huawei's official website,
   [appgallery.huawei.com](https://appgallery.huawei.com/), then install
   it (Android asks you to allow installs from your browser).
2. **Huawei Health**, from AppGallery: the app that pairs and syncs your
   watch.
3. **HMS Core** (Huawei Mobile Services), from AppGallery. It lets
   Step Challenge sign you in to your HUAWEI account. It is often
   installed with Huawei Health: check that it is there and up to date.

## 2. Check that your steps reach Huawei's cloud

Step Challenge reads your steps in Huawei's cloud, not in the watch.

1. Open **Huawei Health** and check that your watch's steps show up.
2. In Huawei Health, **Me → Privacy management**: turn on the sync with
   the cloud.

## 3. Choose Huawei Health in Step Challenge

1. **More** tab, **Step source**.
2. Choose **Huawei Health**, then confirm.
3. Sign in with your **HUAWEI account** and allow reading your steps.
   Only the step count is read, as described in the
   [privacy policy]({{< relref "/step-challenge/privacy" >}}).

When Huawei Health is installed on your phone, the Step Challenge home
screen also suggests it: **Use Huawei Health**.

The steps of the last 30 days are read again from Huawei Health. A day
already sent with more steps keeps its value.

## What changes with Huawei Health

- Your steps arrive when Huawei Health syncs with the cloud, sometimes a
  few minutes behind the watch. Open Huawei Health if a number seems
  late.
- Step Challenge reads your steps **when you open it** (and when you
  pull down to refresh): not in the background yet.
- The minute-by-minute detail (the day's curve, inactivity, active
  minutes) is not available: Step Challenge says so wherever it applies.

## Stop using Huawei Health

**More** tab, **Step source**, choose **Health Connect**. Step Challenge
then removes its access to your HUAWEI account. If it can't, it tells
you: remove it yourself in Huawei Health, **Me → Privacy management**,
in the authorized apps.

## It doesn't work?

- **No steps, or only today's**: check step 2, then wait for Huawei
  Health to sync.
- **HUAWEI sign-in fails**: update HMS Core from AppGallery, then try
  again.
- **To dig deeper**: **More** tab, **Diagnostics**, **Run the
  diagnostics**. It tests the HUAWEI sign-in and the step reading; you
  can copy the result and send it to support.

Still stuck? Write to [support@architech.lu](mailto:support@architech.lu).
