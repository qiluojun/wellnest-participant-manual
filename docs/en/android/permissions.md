---
layout: default
title: Grant Permissions
parent: English Android Manual
nav_order: 3
permalink: /en/android/permissions/
---

# Grant Permissions

When you open **WellNest** for the first time, you will see the **Permission configuration page**. Please follow the on-screen instructions and grant each permission in order.

![Screenshot: Red exclamation mark beside the Permissions icon]({{ '/assets/images/permissions-alert-main-screen.png' | relative_url }})


## General workflow

1. Tap each item on the page.
2. Follow the app and Android system prompts.
3. Continue until every required item is complete.

![Screenshot: Permission configuration page]({{ '/assets/images/permission-configuration-page.png' | relative_url }})



## Notification settings {#notification-settings}

Notification permission is especially important because WellNest sends reminders when surveys are available.

You will usually receive two survey reminders each day:

- A Morning Survey reminder.
- An Evening Survey reminder.

Allow notifications from the app when Android asks.

![Screenshot: Notification permission prompt]({{ '/assets/images/notification-permission-prompt.png' | relative_url }})

If the app asks you to open notification settings, check that the WellNest notification categories are enabled.

![Screenshot: Android notification categories for WellNest]({{ '/assets/images/notification-settings-open.png' | relative_url }})

![Screenshot: Android notification categories for WellNest]({{ '/assets/images/android-notification-categories.png' | relative_url }})

Please make sure these notification categories are enabled:

- App Close Warning
- Survey Reminders (Scheduled)
- Survey Reminders





![Screenshot]({{ '/assets/images/app-close-warning-category.png' | relative_url }})
![Screenshot]({{ '/assets/images/app-close-warning-default.png' | relative_url }})

If you use Do Not Disturb or a similar mode, we recommend allowing survey reminders to bypass Do Not Disturb so you do not miss the survey windows.

![Screenshot: Override Do Not Disturb setting]({{ '/assets/images/override-do-not-disturb.png' | relative_url }})

![Screenshot: Survey reminder notification categories]({{ '/assets/images/survey-reminder-notification-categories.png' | relative_url }})

## Other permission items

After **Notification settings**, continue with the next permission items shown on the Permission configuration page until you reach **Past Health Data**. For items 3 through 6, please follow the instructions on the screen. In most cases, the basic flow is to tap the **Allow** button, then grant the requested permission in the Android system pop-up.

NOTE: Location data is recorded only as relative coordinates from a base point that differs for each individual. Absolute location information (i.e., latitude and longitude) is not recorded. The base point information is stored only on this device.
{: .privacy-note }

## Past Health Data

The last item will automatically open **WellNest Health**. Follow the instructions shown in WellNest Health to finish that part of setup.

![Screenshot: WellNest Health initial screen]({{ '/assets/images/wellnest-health-initial-screen.png' | relative_url }})

Follow the on-screen instructions and tap the upload or permission button shown in the companion app.

When the companion app shows a success status, return to WellNest. Then, you may close the permissions setting page.

![Screenshot: Past Health Data permission step]({{ '/assets/images/past-health-data-permission.png' | relative_url }})


## How to confirm permissions are complete {#how-to-confirm-permissions-are-complete}

Permission setup is complete only when the red exclamation mark beside the Permissions icon has disappeared in WellNest.

![Screenshot: Permission status not finished]({{ '/assets/images/main-app-permission-status-not-finished.png' | relative_url }})

![Screenshot: Permission status finished]({{ '/assets/images/main-app-permission-status-finished.png' | relative_url }})

If the red exclamation mark is still visible:

1. Return to the **Permission configuration page**.
2. Check which item is incomplete.
3. Tap the incomplete item and try again.

## When can I uninstall WellNest Health? {#when-can-i-uninstall-wellnest-health}

You may uninstall **WellNest Health** only after:

- You have completed the permission setup in WellNest.
- The red exclamation mark beside the Permissions icon has disappeared.

Do not uninstall WellNest Health before that point. If you uninstall it too early, permission setup may not be complete.

## Next
{: .next-step-heading }

After permissions are complete, continue to [Surveys]({{ '/en/android/surveys/' | relative_url }}), especially [Pre-Study Survey]({{ '/en/android/surveys/#pre-study-survey' | relative_url }}).
{: .next-step }
