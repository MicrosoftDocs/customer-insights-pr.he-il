---
title: תחילת העבודה עם SDK ל- Android
description: למד כיצד להתאים אישית ולהפעיל את SDK ל- Android
author: britl
ms.reviewer: mhart
ms.custom: intro-internal
ms.author: britl
ms.date: 10/19/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: b06822b2c2d6a859bdf808f7800baef43c4ab874
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226170"
---
# <a name="get-started-with-the-android-sdk"></a>תחילת העבודה עם ה- SDK ל- Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ערכת לימוד זו מנחה אותך לאורך תהליך האינסטרומנטציה של אפליקציית Android עם SDK של תובנות לגבי מעורבות לקוחות של Dynamics 365 Customer Insights. תתחיל לראות אירועים בפורטל שלך בעוד חמש דקות או לפני כן.

## <a name="configuration-options"></a>אפשרויות תצורה
את אפשרויות התצורה הבאות ניתן להעביר ל- SDK:

- **ingestionKey**: מפתח הקליטה משמש לשליחת אירועים סביבת העבודה שלך.

## <a name="prerequisites"></a>דרישות מוקדמות

- ‏‏Android Studio

- רמת API מינימלית של Android: ‏16 (‏Jelly Bean)

- מפתח קליטה (ראה למטה הוראות כיצד להשיגו)

## <a name="integrate-the-sdk-into-your-application"></a>שלב את ה- SDK ביישום שלך
התחל את התהליך על-ידי בחירת סביבת עבודה, בחירת הפלטפורמה הניידת של Android והורדת ה- SDK עבור Android.

- השתמש במחליף סביבת העבודה בחלונית הניווט השמאלית כדי לבחור את סביבת העבודה שלך.

- אם אין לך סביבת עבודה קיימת, בחר  **סביבת עבודה חדשה** ופעל לפי השלבים ליצירת [סביבת עבודה חדשה](create-workspace.md).

- לאחר שתיצור סביבת עבודה, עבור אל **מנהל מערכת** > **סביבת עבודה** ולאחר מכן בחר **מדריך התקנה**.

## <a name="configure-the-sdk"></a>קביעת התצורה של SDK

לאחר שתוריד את ה- SDK, תוכל לעבוד איתו ב- Android Studio כדי לאפשר אירועים ולהגדיר אותם. קיימות שתי דרכים לעשות זאת:
### <a name="option-1-use-jitpack-recommended"></a>אפשרות 1: השתמש ב- JitPack (מומלץ)
1. הוסף את מאגר JitPack ל- `build.gradle` המשמש כבסיס שלך:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. הוסף את התלות:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:v1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-use-download-link"></a>אפשרות 2: השתמש בקישור להורדה
1. הורד את [Android SDKשל התובנות לגבי מעורבות](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip), ומקם את הקובץ `eiandroidsdk-debug.aar` בתיקיה `libs`.

1. פתח את הקובץ `build.gradle` ברמת הפרוייקט והוסף את המקטעים הבאים:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

## <a name="enable-auto-instrumentation"></a>הפעל מכשור אוטומטי

1. הוסף הרשאה לרשת ולאינטרנט בקובץ `AndroidManifest.xml` שלך הממוקם תחת התיקיה `manifests`.
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```

1. הגדר את ה- SDK של התובנות לגבי מעורבות באמצעות הקובץ `AndroidManifest.xml`.

1. העתק את מקטע ה- XML מ **מדריך ההתקנה**. `Your-Ingestion-Key` צריך להיות מאוכלס באופן אוטומטי.

   > [!NOTE]
   > אין צורך להחליף את המקטע `${applicationId}`. הוא מאוכלס באופן אוטומטי.


   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. הפוך את הלכידה האוטומטית של אירועי `View` לזמינה או ללא זמינה על-ידי הגדרת השדה `autoCapture` שלעיל כ- `true` או `false`. 

   >[!NOTE]
   >אירועי `Action` יש להוסיף ידנית.

1. (אופציונלי) תצורות אחרות כוללות את הגדרת כתובת ה- URL של מלקט נקודות הקצה. ניתן להוסיף אותן מתחת למטה-נתונים של מפתח הקליטה ב- `AndroidManifest.xml`.

   ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
   ```

## <a name="implement-custom-events"></a>יישם אירועים בהתאמה אישית

לאחר אתחול ה- SDK, תוכל לעבוד עם אירועים והמאפיינים שלהם בסביבת `MainActivity`.


Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>הגדרת מאפיין לכל האירועים (אופציונלי)

Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

הסוגים הבאים נתמכים עבור מאפייני אירועי הקשר:
- String
- תאריך
- כפול
- Long
- בוליאני‬
- UUID

### <a name="track-an-event"></a>עקוב אחר אירוע

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>הגדר את פרטי משתמש לאירוע שלך (אופציונלי)

SDK מאפשר לך להגדיר פרטי משתמש שניתן לשלוח עם כל אירוע. באפשרותך לציין את פרטי המשתמש על-ידי קריאה לממשק API `setUser(user: User)` ברמת `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

מחלקת הנתונים `User` מכילה את מאפייני המחרוזת הבאים:

- **localId**: המזהה המקומי של המשתמש.
- **authId**: מזהה המשתמש המאומת.
- **authType**: סוג האימות המשמש לקבלת מזהה המשתמש המאומת.
- **שם**: שם המשתמש.
- **דואר**: כתובת הדואר האלקטרוני של המשתמש.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
