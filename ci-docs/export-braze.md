---
title: ייצוא פלחים ל- Braze ‏(Preview)
description: למד כיצד להגדיר את תצורת החיבור ולייצא ל- Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725217"
---
# <a name="export-segments-to-braze-preview"></a>ייצוא פלחים ל- Braze ‏(Preview)

ייצא פלחים של פרטי Unified Customer Profile ל-Braze והשתמש בהם לפעילויות שיווקיות.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Braze](https://www.braze.com/) ואישורי מנהל מערכת התואמים.
- [מפתח API של Braze](https://www.braze.com/docs/api/basics/)
- [נקודת הקצה של Braze REST שלך](https://www.braze.com/docs/api/basics/#api-definitions) 
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרטי unified customer profile בפלחים המיוצאים מכילים שדה המייצג כתובת אימייל ומזהה לקוח של Braze.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- קישור פרטי בשילוב עם Bring your own storage ‏(BYOS) אינו נתמך.
- עד מיליון פרופילי לקוחות אל Braze. השלמת הפעולה עשויה להימשך עד 40 דקות. מספר פרופילי הלקוחות שתוכל לייצא אל Braze תלוי בחוזה שלך עם Braze.
- פלחים בלבד.
- קישור פרטי ב- Azure לא נתמך לצורך ייצוא Braze.

## <a name="set-up-connection-to-braze"></a>הגדרת חיבור ל- Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Braze**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק את מפתח ה-API של Braze כדי להמשיך להתחבר.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Braze. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן את נקודת הקצה REST שלך בשדה **שם מארח** בפורמט הבא: `rest.iad-03.braze.com`.

1. הזן שם עבור הייצוא.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. בשדה **מזהה לקוח** בחר את השדה שמייצג את מזהה Braze של הלקוח. הפלחים ב-Braze יווצרו עם אותו שם מקטע כמו ב- Dynamics 365 Customer Insights. אפשר לבחור שדות נוספים ואופציונליים להתאמת נתונים.

1. בחר את הישויות או הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
