---
title: Privacy Policy — Step Challenge
linkTitle: Privacy policy
description: What data Step Challenge collects, why, and how to delete it.
updated: 27 November 2026
---

Step Challenge is a step-counting and challenge application that allows
users to track their daily steps and participate in step challenges.

## 1. Data we collect

Step Challenge collects only the data necessary to provide its services.

### Account information

Users sign in to Step Challenge with their Google account. When signing
in, Google provides the application with a signed identity token. From
this token, Step Challenge stores only:

- The stable, technical Google account identifier (the OpenID Connect
  "subject"), used to recognize the user at their next sign-in;
- A display name chosen by the user, shown to other participants. The
  application suggests the first name of the Google account, which the
  user can change before saving it and at any time afterwards.

Step Challenge does **not** store the user's email address, profile
photo or any other Google account information, and does not access any
Google service on the user's behalf.

After sign-in, the application keeps a session token in the device's
secure storage (Android Keystore). The server keeps only a cryptographic
hash of this token.

### Step data

When the user gives permission, Step Challenge can read step-count data
from the health platform available on the user's device.

On Android, Step Challenge uses **Health Connect** to read step counts
recorded by the phone or by compatible devices and applications (for
example Garmin, Samsung or Xiaomi). Step Challenge only requests read
access to step data. With the user's permission ("Access data in the
background"), it also reads them about every 6 hours when the app is not
open, so that friends see up-to-date steps in the leaderboard. This
permission can be withdrawn at any time in the Health Connect settings.

Instead, the user can choose **HUAWEI Health**, which receives the
steps of the watches and bands synced with it, on any Android phone. Step Challenge
then reads the steps through **HUAWEI Health Kit** (see section 3). Only
one source is used at a time, chosen by the user in the application
settings.

On Android devices without Health Connect (for example Huawei phones),
the version distributed on Huawei AppGallery can instead read the
phone's own **step counter** (a sensor of the phone), with the
user's permission ("Physical activity"). Step Challenge reads it only
while the app is open, and keeps on the phone only the last reading
and the day's total; only the daily step count is sent to the server.
This permission can be withdrawn at any time in the Android app
settings.

Step data may include:

- The number of steps recorded for a given day;
- The date associated with the step count;
- For a day, its active, very active and inactive minutes, computed on
  the phone from the steps of each minute. The steps per minute stay on
  the phone: only these three daily totals are sent to the server.

Step Challenge does not request access to unrelated health information
such as heart rate, sleep, blood pressure, body measurements or medical
information unless such access is explicitly described in a future
version of the application.

### Friends, invitations and blocks

To show each user the steps of their friends only, the server stores:

- Friendships between two accounts, and the date they were created;
- Invitations: their author, creation and expiry dates (7 days) and
  number of uses. Only a cryptographic hash of the invitation code is
  stored, never the code itself;
- Nicknames a user gives to their friends, visible only to that user;
- Blocks: the blocked account and its display name at the time of
  blocking.

### Reports

When a user reports another user, the server stores the reporting and
reported accounts, the reported display name at the time of the report,
the reason, an optional comment written by the reporting user and, if
any, the invitation through which the reported user was seen. Reports
are used only to moderate the service. The reported user is not told,
and never sees who reported them.

### Consents

The server keeps a record of the user's consents, with their date:

- the acceptance of the terms of use and of this privacy policy, with
  the version accepted;
- each authorization to read HUAWEI Health granted (with the
  permissions granted) or withdrawn (in Step Challenge, in the HUAWEI
  Health app, or refused by HUAWEI Health Kit), as noticed by the
  application.

This record contains no step data. It serves to prove the consents and
their withdrawal, and is deleted with the account.

## 2. How we use step data

Step data is used only to provide Step Challenge functionality,
including:

- Displaying the user's daily step count;
- Displaying step history and statistics;
- Computing active minutes and the activity score;
- Calculating challenge and leaderboard results;
- Synchronizing step counts with the Step Challenge service.

Step data is not used for advertising, profiling, marketing or medical
purposes.

Step Challenge is not a medical device, and neither is HUAWEI Health
Kit: step data, whether it comes from Health Connect or HUAWEI Health
Kit, is for reference only and must not be used as a basis for medical
diagnosis.

Step data obtained through HUAWEI Health Kit is not sold or shared with
third parties for their own advertising or profiling purposes.

## 3. HUAWEI Health Kit

When the user chooses HUAWEI Health as the source of their steps, they
sign in with their HUAWEI account and allow Step Challenge to read their
steps. This sign-in goes through HMS Core, Huawei's services app, and
requests the HUAWEI account identifier, its basic profile, read access
to steps and, if the user accepts it, read access to the steps of the
month before their authorization (without it, HUAWEI Health only gives
the steps recorded since the authorization). Step Challenge does not
request any other HUAWEI Health data.

Steps are read from Huawei's cloud, where the HUAWEI Health app has
synchronized them, through the HUAWEI Health Kit interface. Step
Challenge reads them only while the application is open; it does not
read them in the background. For the curve of a day in the statistics, it also reads that
day's steps hour by hour, when the device counting the steps has sent
them to HUAWEI Health; this detail is shown on the phone and is not sent
to the server.

Reading happens on the phone. The access token issued by Huawei stays
there: it is never sent to the Step Challenge server. Step Challenge
does not keep the HUAWEI account identifier or profile: only daily step
counts are sent to the server, as with Health Connect.

Data processed by Huawei (HUAWEI account, HUAWEI Health, Huawei's cloud)
is governed by Huawei's privacy policy.

The user can withdraw this authorization in Step Challenge (**More →
Step source → Remove access to HUAWEI Health**), through the privacy
and permission settings of HUAWEI Health or of their HUAWEI account, or
by switching back to Health Connect in the Step Challenge settings.

When withdrawing the access in Step Challenge, the user chooses to keep
the steps already saved by Step Challenge, or to delete them: all their
saved daily steps and activity minutes, whatever their source, are then
deleted from the server. Badges already earned are kept.

If permission is denied or withdrawn, Step Challenge will no longer be
able to retrieve new step data from HUAWEI Health Kit. Previously
synchronized data that the user chose to keep remains stored by Step
Challenge until it is deleted according to this policy.

## 4. Synchronization with Step Challenge servers

When synchronization is enabled, Step Challenge sends the user's daily
step counts, and the active, very active and inactive minutes of the
last days, to the Step Challenge backend.

The server stores step counts associated with the user's Step Challenge
account so that the application can:

- Synchronize data between devices;
- Maintain step and activity score history;
- Calculate challenges;
- Provide leaderboards.

The server does not receive the user's complete HUAWEI Health database.
Step Challenge only processes the step information required by the
application.

### Hosting and transfer outside the European Union

The Step Challenge server is hosted by OVHcloud, in **Canada**. The data
it keeps (account, display name, daily step counts and activity
minutes, friendships, reports) is therefore transferred outside the
European Union. This transfer relies on the European Commission's
decision recognizing that Canada provides an adequate level of
protection for personal data.

Database backups are encrypted, then copied to a server located in
**France**, administered by the developer.

Data is not transferred to any other country. HUAWEI Health data other
than daily step counts stays on the user's phone.

## 5. Data sharing

Step Challenge does not sell personal data.

Within the application, a user's display name and daily step counts are
visible only to their friends, as are their badges and level, computed
from their steps. The display name is also shown to anyone
who opens one of the user's invitation links. Active minutes and the
activity score are visible to the user only.

Step Challenge does not share step data with advertisers, data brokers
or other third parties for advertising or profiling.

Step data may be processed by technical service providers required to
operate the application and its infrastructure, where applicable, and
only for purposes necessary to provide the service.

## 6. Data retention

Step Challenge retains synchronized step data only for as long as
necessary to provide the application's features, including step
history, challenges and statistics.

Users can delete their Step Challenge account at any time from the
application: **More → Account → Delete my account**. This immediately
and permanently deletes, on the server, the account, its display name,
its link to the Google account, its sessions, its entire step history
and its badges.
Step data stored in Health Connect or HUAWEI Health on the device is not
affected.

Encrypted database backups are kept for **7 days**, then erased. They
are only used to restore the service after an incident: the data of a
deleted account stays in them for at most 7 days.

Deleting the account also deletes its friendships, the nicknames given
to and by it, its invitations and its blocks.

Processed reports are deleted 12 months after they were processed.
Reports made by or about a deleted account are kept until then, without
any link to the deleted account; they still contain the reported display
name and the comment.

Users who no longer have access to the application can request the
deletion of their account and associated server-side data by email (see
the Contact section). Both procedures are described on the
[account deletion page]({{< relref "/step-challenge/delete-account" >}}).

Data stored locally on the user's device may also be removed by
uninstalling the application or using the application's available
data-deletion functionality.

## 7. Security

Reasonable technical and organizational measures are used to protect
Step Challenge data against unauthorized access, alteration, disclosure
or destruction, including:

- all communication between the application and the server is
  encrypted (HTTPS);
- the session token is kept in the phone's secure storage, and the
  server only keeps a cryptographic hash of it;
- access to the server is restricted (firewall, key-only administrative
  login);
- database backups are encrypted.

## 8. Your rights

Depending on applicable data protection law, users may have rights
including:

- Access to their personal data;
- Correction of inaccurate data;
- Deletion of their personal data;
- Withdrawal of consent where processing is based on consent;
- Restriction or objection to certain processing;
- Data portability where applicable.

Users can download a copy of all the personal data kept by the server
from the application: **More → Account → Export my data** gives a file
(JSON) with their account, step history, friends, invitations, blocks,
reports made, badges and consents. It is the exercise of the rights of
access and portability.

Users can also revoke Step Challenge's access to HUAWEI Health data in
the application (see section 3), or through the relevant HUAWEI Health
or device permission settings.

## 9. Children's privacy

Step Challenge is intended for people aged **16 and over**. It does not
knowingly collect personal information from younger children. If we
learn that an account belongs to a person under 16, it is deleted.

## 10. Changes to this policy

This privacy policy may be updated when Step Challenge introduces new
functionality or when legal or technical requirements change.

The latest version will always be published at the privacy policy URL
provided to users and application platforms.

When the changes are material, the application asks each user to read
and accept the new version before using it again.

## 11. Contact

For questions about this privacy policy, personal data or requests
concerning your data, please contact:

Step Challenge is developed and operated by **Lionel Coquin**, acting as
a private individual, who is the data controller for the personal data
processed by the application and its server.

**Step Challenge — Lionel Coquin**\
Email: **support@architech.lu**

## 12. Open source

The source code of the Step Challenge application and server is public,
under the GNU Affero General Public License (AGPL-3.0), so that anyone
can verify how data is processed:
[github.com/mauvaisetroupe/step-challenge](https://github.com/mauvaisetroupe/step-challenge).
