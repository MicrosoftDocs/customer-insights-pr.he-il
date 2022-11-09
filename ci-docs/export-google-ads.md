---
title: ייצוא פלחים אל Google Ads‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725079"
---
# <a name="export-segments-to-google-ads-preview"></a>ייצוא פלחים אל Google Ads‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים לרשימת קהלים של Google Ads והשתמש בהם לפרסום בחיפוש Google‏, Gmail, YouTube, ו- Google Display Network.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Google Ads](https://ads.google.com/) ואישורי מנהל מערכת תואמים.
- [מזהה לקוח של Google Ads](https://support.google.com/google-ads/answer/1704344).
- הדרישות של [מדיניות Customer Match](https://support.google.com/adspolicy/answer/6299717) מתקיימות.
- הדרישות של [גדלי רשימת שיווק מחדש](https://support.google.com/google-ads/answer/7558048) מתקיימות.
- [פלחים מוגדרים](segments.md).
- פרטי Unified customer profiles בפלחים המיוצאים מכילים שדות המייצגים כתובת דוא"ל, טלפון, מזהה מפרסם במכשירים ניידים, מזהה משתמש של צד שלישי או כתובת.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- קישור פרטי בשילוב עם Bring your own storage ‏(BYOS) אינו נתמך.
- יצא עד מיליון פרופילי לקוחות לכל ייצוא אל Google Ads. השלמת הפעולה עשויה להימשך עד 30 דקות עקב מגבלות בצד הספק.
- פלחים בלבד.
- התאמה ב- Google Ads יכולה להימשך עד 48 שעות.

## <a name="set-up-connection-to-google-ads"></a>הגדרת חיבור אל Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Google Ads**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את מזהה הלקוח של Google Ads.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **בצע אימות באמצעות Google Ads** וספק את אישורי Google Ads שלך.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Google Ads. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. בחר םא להשתמש בקהל קיים או אם ליצור קהל חדש:
   - כדי לעדכן קהל קיים של Google Ads, הזן [מזהה קהל Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns) שלך.
   - כדי ליצור קהל חדש, השאר ריק את השדה של מזהה קהל Google. Customer Insights ייצור אוטומטית קהל חדש בחשבון Google Ads שלך ונשתמש בשם הפלח המיוצא.

1. במקטע **התאמת נתונים**, בחר שדה נתונים אחד או יותר לייצוא, ובחר את השדה המייצג את שדות הנתונים התואמים ב- Customer Insights.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
