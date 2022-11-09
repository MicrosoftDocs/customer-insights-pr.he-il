---
title: ייצוא פלחים אל Constant Contact‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Constant Contact.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c0affd3ed45f462696850813bd50331061dde780
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724502"
---
# <a name="export-segments-to-constant-contact-preview"></a>ייצוא פלחים אל Constant Contact‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל Constant Contact והשתמש בהם עבור פעילויות שיווק.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Constant Contact](https://www.constantcontact.com/account-home) ואישורי מנהל מערכת תואמים.
- [מזהה רשימה של Constant Contact](https://app.constantcontact.com/pages/contacts/ui#lists). פתח רשימה ב- Constant Contact כדי למצוא את מזהה הרשימה בכתובת ה- URL.
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- קישור פרטי בשילוב עם Bring your own storage ‏(BYOS) אינו נתמך.
- עד מיליון פרופילי לקוחות לכל ייצוא אל Constant Contact. השלמת הפעולה עשויה להימשך עד שעה אחת. מספר פרופילי הלקוחות שתוכל לייצא אל Constant Contact תלוי בחוזה שלך עם Constant Contact.
- פלחים בלבד.

## <a name="set-up-connection-to-constant-contact"></a>הגדרת חיבור ל- Constant Contact

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Constant Contact**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **אימות באמצעות Constant Contact** וספק את אישורי מנהל המערכת עבור Constant Contact.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Constant Contact. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את **מזהה הרשימה של Constant Contact** שלך.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. לחלופין, יצא **שם פרטי** ו **שם משפחה** כשדות נוספים כדי ליצור הודעות דואר אלקטרוני מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
