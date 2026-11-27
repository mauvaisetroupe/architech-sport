---
title: Health Connect
description: Allow Step Challenge to read your steps from Health Connect, on any Android phone.
weight: 1
---

On Android, Step Challenge reads your steps from **Health Connect**, the
health data hub of Android. Health Connect collects the steps counted by
your phone and by the watch and fitness apps that write to it (Garmin
Connect, Samsung Health, Zepp, Mi Fitness and many others).

Step Challenge only asks to **read your steps**: no other health data.

## 1. Check that Health Connect is available

- **Android 14 and later**: Health Connect is part of the system. You
  find it in the phone settings (search for "Health Connect").
- **Android 13 and earlier**: install the
  [Health Connect app](https://play.google.com/store/apps/details?id=com.google.android.apps.healthdata)
  from Google Play.

## 2. Allow access to your steps

The first time Step Challenge reads your steps, Android shows the Health
Connect permission screen. Allow **Steps**.

If you refused, or want to check:

1. Open **Health Connect** (phone settings, then search for "Health
   Connect").
2. Go to **App permissions**, then **Step Challenge**.
3. Turn on **Steps**.

The names of the menus may differ slightly depending on your phone's
brand and Android version.

## 3. Let your watch write to Health Connect

If you count your steps with a watch, its app must **send** your steps
to Health Connect. In the watch app (Garmin Connect, Samsung Health,
Zepp, Mi Fitness…), look for Health Connect in its settings and allow it
to write **Steps**.

> **Your steps are in HUAWEI Health?** HUAWEI Health does not send its data to Health
> Connect. See the [HUAWEI Health help]({{< relref "/step-challenge/help/huawei" >}}).

## 4. Check in the app

- Opening the app updates today's steps. The app also synchronizes in
  the background, about every 6 hours.
- If steps are missing: **More** tab, **Diagnostics**, **Run the
  diagnostics**. It checks
  Health Connect, the permission and the connection to the server.

## 5. My steps are counted twice

On some days, Step Challenge shows far more steps than your watch's app
(for example 50,000 instead of 16,000)? Step Challenge copies what Health
Connect holds: the extra steps are there. To check, open **Health
Connect**, **Data and access**, **Steps**, and look at that day.

The most common cause: the watch's app **also** counts the phone's
steps, and adds both before sending them to Health Connect. Health
Connect can then no longer tell them apart.

1. **Keep only the watch in its app.** Take the phone's step counter
   away from it: phone settings, **Apps**, the watch's app (Mi Fitness,
   for example), **Permissions**, **Physical activity**, **Don't allow**.
   If the phone is listed among its devices, remove it too.
2. **Let Health Connect decide.** If you also want the phone's steps
   (on days without the watch), let the phone send them to Health
   Connect itself. Then in **Health Connect**, **Data and access**,
   **Activity**, **Steps**, **Data sources and priority**, put the
   watch's app first: Health Connect keeps its steps and only takes the
   phone's when the watch counted nothing.
3. **Delete the extra steps.** In Health Connect, first take away the
   watch app's permission to write steps (otherwise it may write them
   again), delete its steps for the days concerned, then give the
   permission back and sync the watch.
4. **Correct Step Challenge.** **More** tab, **Step source**, **Read my
   last 30 days again**: Step Challenge shows you the days that change,
   even downward, and only replaces them once you agree. For an older
   day, write to us.

Still stuck? Read the [FAQ]({{< relref "/step-challenge/faq" >}}) or write to
[support@architech.lu](mailto:support@architech.lu).
