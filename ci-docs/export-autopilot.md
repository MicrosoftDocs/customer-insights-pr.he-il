---
title: ייצוא פלחים ל- Autopilot‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724758"
---
# <a name="export-segments-to-autopilot-preview"></a>ייצוא פלחים ל- Autopilot‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים ל- Autopilot והשתמש בהם עבור שיווק בדוא"ל ב- Autopilot.

## <a name="prerequisites-for-a-connection"></a>דרישות מוקדמות לחיבור

- [חשבון Autopilot](https://www.autopilothq.com/) ואישורי מנהל מערכת מתאימים.
- [מפתח API של AutoPilot](https://autopilot.docs.apiary.io/#)
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- קישור פרטי בשילוב עם Bring your own storage ‏(BYOS) אינו נתמך.
- עד 100,000 פרופילי לקוחות לכל ייצוא אל Autopilot. השלמת הפעולה עשויה להימשך עד כמה שעות. מספר פרופילי הלקוחות שתוכל לייצא אל Autopilot תלוי בחוזה שלך עם Autopilot.
- פלחים בלבד.

## <a name="set-up-connection-to-autopilot"></a>הגדרת חיבור אל Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Autopilot**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את מפתח ה- API של Autopilot שלך.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Autopilot. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. לחלופין, יצא שדות אחרים כגון **שם פרטי** ו **שם משפחה**.

1. בחר את המקטעים שברצונך לייצא שמצייתים למגבלות הידועות.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
