---
title: תרחישים מתקדמים עבור SDK לאינטרנט
description: תרחישים מתקדמים שיש לקחת בחשבון בעת אינסטרומנטציה של האתר שלך באמצעות SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227199"
---
# <a name="advanced-web-sdk-instrumentation"></a>אינסטרומנטציה מתקדמת באמצעות SDK לאינטרנט

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

מאמר זה מציג בפניך תרחישים מתקדמים שיש לקחת בחשבון בעת [האינסטרומנטציה של האתר שלך](instrument-website.md) באמצעות SDK של יכולת תובנות על מעורבות של Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>הגדרת פרטי משתמש עבור האירוע שלך

SDK מאפשר לך להגדיר פרטי משתמש שניתן לשלוח עם כל אירוע. תוכל לציין את פרטי המשתמש בתוך מאפיין הנקרא `user` (הנתונים הצפויים עבור מאפיין זה הוא האובייקט `IUser`), דומה ל- `src`, `name`, ו- `cfg` בתצורת מקטע הקוד.

האובייקט `IUser` מכיל את מאפייני המחרוזת הבאים:

- **localId**: המזהה המקומי של המשתמש.
- **authId**: מזהה המשתמש המאומת.
- **authType**: סוג האימות המשמש לקבלת מזהה המשתמש המאומת.
- **שם**: שם המשתמש.
- **דואר**: כתובת הדואר האלקטרוני של המשתמש.

הדוגמה הבאה מציגה מקטע קוד השולח פרטי משתמש. במקומות שבהם אתה רואה פונקציות שלפניהן סמל כוכבית *, החלף את הפונקציה ביישום המותאם אישית שלך:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

באפשרותך גם לציין פרטי משתמש על-ידי קריאה ל- API `setUser(user: IUser)`. מדידת השימוש שתישלח אחרי הקריאה ל- API `setUser`, תכיל את פרטי המשתמש.

## <a name="adding-custom-properties-for-each-event"></a>הוספת מאפיינים מותאמים אישית לכל אירוע

SDK מאפשר לך לציין מאפיינים מותאמים אישית שניתן לשלוח עם כל אירוע. באפשרותך לציין את המאפיינים המותאמים אישית כאובייקט המכיל זוגות מפתח-ערך (הערך יכול להיות מסוג `string | number | boolean`). באפשרותך להוסיף את האובייקט במאפיין הנקרא `props`, בדומה ל- `src`, `name` ו- `cfg` בתצורת מקטע הקוד.

הדוגמה הבאה מציגה מקטע קוד השולח מאפיינים מותאמים אישית:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

באפשרותך גם לציין מאפיינים מותאמים אישית בנפרד על-ידי קריאה ל- API `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>שליחת אירועים מותאמים אישית

באפשרותך להשתמש ב- SDK כדי לשלוח אירועים מותאמים אישית. יש לציין את שם האירוע ואת המאפיינים שיישלחו עם האירוע.

הדוגמה הבאה מציגה מקטע קוד העוקב אחר אירוע מותאם אישית. "NAME" הוא הערך במפתח `name` שבתצורת מקטע הקוד. זהו גם שם המשתנה באובייקט החלון שבו נטען ה- SDK.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
