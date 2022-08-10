---
title: ייצוא פלחים אל Snapchat‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195383"
---
# <a name="export-segments-to-snapchat-preview"></a>ייצוא פלחים אל Snapchat‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל Snapchat והשתמש בהם עבור פרסום.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון עסקי של Snapchat](https://business.snapchat.com/), [חשבון Snapchat Ads](https://ads.snapchat.com/) ואישורי מנהל מערכת תואמים. עליך להיות לפחות חבר בחשבון ארגון ומנהל נתונים של חשבון מודעות ספציפי.
- לפחות קהל אחד במנהל קהל Snapchat מסוג SAM ‏(התאמת קהל מסוג Snap).
- [פלח Snapchat/מזהה קהל](https://businesshelp.snapchat.com/s/article/custom-audiences). ניתן למצוא את המזהה של קהל בכתובת האתר לאחר בחירת הקהל במנהל הקהל של Snapchat.
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד מיליון פרופילי לקוחות. השלמת הפעולה עשויה להימשך עד 15 דקות.
- פלחים בלבד.

## <a name="set-up-connection-to-snapchat"></a>הגדרת חיבור אל Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Snapchat‎**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **בצע אימות באמצעות Snapchat** וספק את אישורי מנהל המערכת שלך עבור Snapchat.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Snapchat. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את **פלח Snapchat/מזהה קהל**.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
