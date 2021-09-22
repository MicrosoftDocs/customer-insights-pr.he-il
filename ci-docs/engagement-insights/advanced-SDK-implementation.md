---
title: תרחישים מתקדמים עבור SDK לאינטרנט
description: תרחישים מתקדמים שיש לקחת בחשבון בעת אינסטרומנטציה של האתר שלך באמצעות SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 11/12/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 7455d276035bfaf1f8a93d0e3b0b0884353a4010715c05d1d696309f7eb4b233
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036329"
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
    
הדוגמה הבאה מציגה מקטע קוד השולח פרטי משתמש. היכן שפונקציות מסומנות ב- *, החלף אותן בהטמעה שלך של קריאה לערכים אלה:  

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

ניתן גם לציין פרטי משתמש על ידי קריאה ל- API `setUser(user: IUser)` ב- SDK. מדידת השימוש שתישלח אחרי הקריאה ל- `setUser API`, תכיל את פרטי המשתמש.

## <a name="adding-custom-properties-for-each-event"></a>הוספת מאפיינים מותאמים אישית לכל אירוע

SDK מאפשר לך לציין מאפיינים מותאמים אישית שניתן לשלוח עם כל אירוע. באפשרותך לציין את המאפיינים המותאמים אישית כאובייקט המכיל זוגות מפתח-ערך (הערך יכול להיות מסוג `string | number | boolean`). ניתן להוסיף את האובייקט במאפיין שנקרא `props`, דומה ל- `src`, `name` ו- `cfg` בתצורת מקטע הקוד. 

הדוגמה הבאה מציגה מקטע קוד השולח מאפיינים מותאמים אישית:

```
[…]
window, document 
{
    src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js", 
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

ניתן גם לציין מאפיינים מותאמים אישית בנפרד על ידי קריאה לממשק ה- API `setProperty(name: string, value: string | number | boolean)` ב- SDK.

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