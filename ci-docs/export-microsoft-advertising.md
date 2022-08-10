---
title: ייצוא פלחים אל Microsoft Advertising‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196533"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>ייצוא פלחים אל Microsoft Advertising‏ (Preview)

יצא פלחים של Customer Insights אל ‏Microsoft Advertising כדי ליצור קהלים של Customer Match. השתמש בקהלים אלה עבור הקמפיינים הפרסומיים שלך.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Microsoft Advertising](https://ads.microsoft.com/) ואישורי מנהל מערכת מתאימים.
- מזהה הלקוח ומזהה החשבון של Microsoft Advertising. אתר את מזהה הלקוח (`cid`) ומזהה החשבון (`aid`) בפרמטרים של כתובת ה- URL כשאתה מחובר ל- Microsoft Advertising.
- תנאי השימוש של Customer Match מקובלים.
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד 500,000 פרופילי לקוחות לכל ייצוא אל Microsoft Advertising. הפעולה עשויה להימשך עד 10 דקות.
- פלחים בלבד.

## <a name="set-up-connection-to-microsoft-advertising"></a>הגדרת חיבור אל Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Microsoft Advertising**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. ברירת המחדל היא מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **מזהה הלקוח של Microsoft Advertising**.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **בצע אימות באמצעות Microsoft Advertising** וספק את אישורי מנהל המערכת שלך עבור Microsoft Advertising.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע Microsoft Advertising. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. בחר פלחים לייצוא. הקהלים של Customer Match ב- Microsoft Advertising נוצרים באופן אוטומטי עם שם הפלחים שנבחרו לייצוא. לכל מקטע ייווצר קהל נפרד של Customer Match.

1. הזן את **מזהה הלקוח ומזהה החשבון של Microsoft Advertising**.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה עם כתובת דואר אלקטרוני של לקוח.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
