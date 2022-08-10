---
title: ייצוא פלחים ל- Iterable ‏(Preview)
description: למד כיצד להגדיר את תצורת החיבור ולייצא ל- Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ccf10b6e3a28a75f9d1bd3d8da3bf870ebc2b1b2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195430"
---
# <a name="export-segments-to-iterable-preview"></a>ייצוא פלחים ל- Iterable ‏(Preview)

ייצא פלחים של פרטי Unified Customer Profile ל- Iterable והשתמש בהם לפעילויות שיווקיות.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Iterable](https://iterable.com/) ואישורי מנהל מערכת תואמים.
- [מפתח API של Iterable](https://support.iterable.com/hc/en-us/articles/360043464871)
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד מיליון פרופילי לקוחות אל Iterable. השלמת הפעולה עשויה להימשך עד 30 דקות. מספר פרופילי הלקוחות שתוכל לייצא אל Iterable תלוי בחוזה שלך עם Iterable.
- פלחים בלבד.

## <a name="set-up-connection-to-iterable"></a>הגדרת חיבור ל- Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Iterable‎**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק את מפתח ה-API של Iterable כדי להמשיך להתחבר.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Iterable. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. הרשימה שנוצרה ב- Iterable תקבל את אותו השם של הפלח שלך ב- Dynamics 365 Customer Insights.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
