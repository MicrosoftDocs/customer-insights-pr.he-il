---
title: מדגם SDK Android
description: פרוייקט לדוגמה כדי ללמוד על Android SDK
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 2ee29a98192bb53bd92241d71c1a76ec2b7bf846
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229919"
---
# <a name="run-the-android-sdk-sample"></a>הפעל הדגמת Android SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

פרוייקט Android לדוגמה זה עוזר לך להבין כיצד ה- SDK עובד באפליקציה. לא תצטרך לכתוב קוד. פשוט הוסף את מפתח הקליטה שלך ומיד תוכל לראות אירועים בסביבת העבודה שלך.

## <a name="prerequisites"></a>דרישות מוקדמות

- [Android Studio](https://developer.android.com/studio)
- [מפתח קליטה](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>הורד את מדגם ה- Android SDK

1. [הורד את הדגמת התובנות לגבי מעורבות של Android SDK](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. חלץ את הקובץ הדחוס `ei-android-sample.zip`.
1. פתח את התיקיה שחילצת ב- Android Studio.
1. בקובץ `AndroidManifest.xml`, החלף את המחרוזת `"Your-Ingestion-Key"` עם מפתח קליטת סביבת העבודה שלך מתובנות לגבי מעורבות תחת **מנהל מערכת** > **סביבת עבודה** > **מדריך התקנה**. 

   > [!NOTE]
   > אין צורך להחליף את המקטע `${applicationId}`. הוא מאוכלס באופן אוטומטי.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. בחר **הפעל** כדי להתחיל את הפרוייקט לדוגמה.
1. צפה באירועים בסביבת העבודה שלך.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
