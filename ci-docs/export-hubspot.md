---
title: ייצוא נתוני Customer Insights אל HubSpot
description: למד כיצד להגדיר את החיבור ולייצא ל- HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0281be288b2c4d9e5da7ad8e2ed25f7b51b8498e
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588907"
---
# <a name="export-segments-to-hubspot-preview"></a>ייצוא פלחים ל- HubSpot‏ (Preview)

ייצא פלחים של פרטי Unified Customer Profile ל-HubSpot והשתמש בהם לפעילויות שיווקיות בדואר אלקטרוני.

## <a name="prerequisites-for-a-connection"></a>דרישות מוקדמות לחיבור

- [חשבון HubSpot](https://www.hubspot.com/) ואישורי מנהל מערכת מתאימים.
- [מפתח API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) מ- HubSpot.
- [פלחים מוגדרים](segments.md) ב- Customer Insights.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד 100,000 פרופילי לקוחות לכל ייצוא ל- HubSpot, אשר עשוי להימשך עד 15 דקות. מספר פרופילי הלקוחות שתוכל לייצא אל HubSpot תלוי בחוזה שלך עם HubSpot ומוגבל בהתאם לתנאיו.
- פלחים בלבד.

## <a name="set-up-connection-to-hubspot"></a>הגדרת חיבור אל HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **HubSpot** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. כאשר תתבקש, הקלד את אישורי ה- HubSpot.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל- HubSpot.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע HubSpot. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. חזור על אותם שלבים עבור שדות אופציונליים אחרים.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
