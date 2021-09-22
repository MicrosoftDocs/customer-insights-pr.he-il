---
title: תחילת העבודה עם iOS SDK
description: למד כיצד להתאים אישית את ה- SDK של iOS ולהפעיל אותו
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: de8291fc429ae6433301a47bfdf9a3271b1b77294fd58448c7aa6bd0783edc97
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036874"
---
# <a name="get-started-with-the-ios-sdk"></a>תחילת העבודה עם iOS SDK

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

ערכת לימוד זו מנחה אותך לאורך האינסטרומנטציה של אפליקציית iOS שלך עם Dynamics 365 Customer Insights ה- SDK של תובנות לגבי מעורבות. תתחיל לראות אירועים בפורטל שלך בעוד חמש דקות או לפני כן.

## <a name="configuration-options"></a>אפשרויות תצורה

את אפשרויות התצורה הבאות ניתן להעביר ל- SDK באמצעות קובץ `EIConfig.plist` המצורף:

- **ingestionKey**: מפתח הקליטה המשמש לשליחת אירועים לפרוייקט שלך.
- **autocollectAction**: ערך בוליאני להפיכת המכשור האוטומטי של אירוע הפעולה לזמין או לא זמין.
- **autocollectView**: ערך בוליאני להפיכת המכשור האוטומטי של אירוע הצפייה לזמין או לא זמין.
- **endpointUrl**: כתובת ה- URL של נקודת הקצה אליה יופנו האירועים.

## <a name="prerequisites"></a>דרישות מוקדמות

- Xcode גירסה 9+
- iOS גירסה 8.2+
- מפתח קליטה (עיין בהוראות למטה כדי להשיגו)

## <a name="integrate-the-sdk-into-your-application"></a>שלב את ה- SDK ביישום שלך

התחל את התהליך על-ידי בחירת סביבת עבודה לעבוד בה, בחירת הפלטפורמה הניידת של iOS והורדת ה- SDK.

- השתמש במחליף סביבת העבודה בחלונית הניווט השמאלית כדי לבחור את סביבת העבודה שלך.

- אם אין לך סביבת עבודה קיימת, בחר  **סביבת עבודה חדשה** ופעל לפי השלבים ליצירת [סביבת עבודה חדשה](create-workspace.md).

## <a name="configure-the-sdk"></a>קביעת התצורה של SDK

לאחר שתוריד את ה- SDK, תוכל לעבוד איתו ב- Xcode כדי לאפשר אירועים ולהגדיר אותם.

1. לאחר שתיצור סביבת עבודה, עבור אל **מנהל מערכת** > **סביבת עבודה** ולאחר מכן בחר **מדריך התקנה**.

1. הורד את [ה- iOS SDK של תובנות לגבי מעורבות‬](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip), ומקם את קובץ `EIObjC.xcframework` בתיקייה `Frameworks`.

1. אם התיקייה `Frameworks` לא קיימת, צור אותה בתיקיית הפרוייקט.

## <a name="enable-auto-instrumentation"></a>הפעל מכשור אוטומטי
 
ניתן להפעיל בקלות מכשור אוטומטי ללא כתיבת קוד. כאשר הפרוייקט פועל, הוא יעקוב באופן אוטומטי אחר האירועים `view` ו- `action` באמצעות מפתח הקליטה שתצורתו נקבעה. 

1. בצע עדכון וכלול את קובץ `EIConfig.plist` המצורף בתיקיית ספריית הפרוייקט שלך עבור השדות הבאים:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = כן
    - autocollectAction = כן

2. ולאחר מכן הוסף את הקובץ `EIConfig.plist` לפרוייקט שלך ב- Xcode. 



כדי להפוך המכשור האוטומטי ללא זמין, עדכן את השדות הבאים בקובץ `EIConfig.plist` הכלול בתיקיית ספריית הפרוייקט שלך. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>יישם אירועים בהתאמה אישית

1. פתח את הפרוייקט שלך ב- Xcode ונווט אל ההגדרות **כללי**. 
1. הוסף את `EIObjC.xcframework` לפרוייקט תחת המקטע 'Frameworks, Libraries, and Embedded Content' (מסגרות, ספריות ותוכן מוטבע).‬

1. יבא את קובץ הכותרת של המסגרת ב- AppDelegate.m עם המקטע הבא:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. אתחל את ה- SDK של תובנות לגבי מעורבות מהיישום: didFinishLaunchingWithOptions.
1. העתק את מקטע ה- XML מ **מדריך ההתקנה**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. עקוב אחר אירוע:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>הגדר את פרטי משתמש לאירוע שלך

SDK מאפשר לך להגדיר פרטי משתמש שניתן לשלוח עם כל אירוע. באפשרותך לציין את פרטי המשתמש על-ידי ביצוע קריאה לממשק API `setUser:(nonnull EIUser *)user` ב- SDK.

ציון פרטי המשתמש ברמת ה- `Analytics` פירושו שמידע זה יהיה בכל מדידת שימוש‬. עם זאת, אם אתה מציין ברמת האירוע על-ידי ביצוע קריאה ל- API של `setUser:(nonnull EIUser *)user` באובייקט EIEvent, רק האירוע הספציפי הזה יכיל את המידע.

מחלקת הנתונים `EIUser` מכילה את המאפיינים הבאים של NSString:

- **localId**: המזהה המקומי של המשתמש.
- **authId**: מזהה המשתמש המאומת.
- **authType**: סוג האימות המשמש לקבלת מזהה המשתמש המאומת.
- **שם**: שם המשתמש.
- **דואר**: כתובת הדואר האלקטרוני של המשתמש.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
