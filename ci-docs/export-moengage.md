---
title: ייצוא פלחים אל MoEngage
description: למד כיצד להגדיר את תצורת החיבור ולייצא ל- MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199117"
---
# <a name="export-segments-to-moengage-preview"></a>ייצוא פלחים ל- MoEngage‎‎‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים ל- MoEngage והשתמש בהם עבור שיווק בדואר אלקטרוני ב- MoEngage.

## <a name="prerequisites-for-a-connection"></a>דרישות מוקדמות לחיבור

- [חשבון MoEngage](https://www.moengage.com/) ואישורי מנהל מערכת תואמים.
- מפתח API של MoEngage מ'הגדרות' > 'API ב- MoEngage'.
- [פלחים מוגדרים](segments.md) ב- Customer Insights.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד 100,000 פרופילי לקוחות לכל ייצוא אל MoEngage. הפעולה עשויה להימשך עד 15 דקות. מספר פרופילי הלקוחות שתוכל לייצא אל MoEngage תלוי בחוזה שלך עם MoEngage.
- פלחים בלבד.

## <a name="set-up-connection-to-moengage"></a>הגדרת חיבור אל MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **MoEngage** כדי להגדיר את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את [מפתח ה- API ומזהה ה- API של נתוני MoEngage](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל- MoEngage.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע MoEngage. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. חזור על אותם שלבים עבור שדות אופציונליים אחרים.

1. בחר את הפלחים שברצונך לייצא. אנחנו ניצור פלח אחד או יותר עם שם זהה לפלחים שנבחרו ב- MoEngage תחת **פלחים** > **פלחים מותאמים אישית**.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
