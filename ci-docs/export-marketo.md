---
title: ייצוא פלחים ל- Marketo‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f57cdfbb24df8a8ffa1670b426d50dbba2c5f40f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195245"
---
# <a name="export-segments-to-marketo-preview"></a>ייצוא פלחים ל- Marketo‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Marketo​.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Marketo](https://login.marketo.com/) ואישורי מנהל מערכת תואמים.
- [מזהה לקוח של Marketo, סוד לקוח ושם מארח של נקודת קצה של REST](https://developers.marketo.com/rest-api/authentication/).
- [רשימות קיימות ב- Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) והמזהים התואמים.
- [פלחים מוגדרים](segments.md).
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד מיליון פרופילי לקוחות בכל ייצוא אל Marketo. פעולה זו עשויה להימשך עד 3 שעות. מספר פרופילי הלקוחות שתוכל לייצא אל Marketo תלוי בחוזה שלך עם Marketo.
- פלחים בלבד.

## <a name="set-up-connection-to-marketo"></a>הגדרת חיבור אל Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Marketo‎**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **מזהה הלקוח של Marketo, סוד הלקוח ושם מארח של נקודת קצה של REST**. שם המארח של נקודת הקצה REST הוא שם המארח בלבד, ללא https://. דוגמה: xyz-abc-123.mktorest.com.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Marketo. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את **מזהה רשימת ה- Marketo**. מזהה הרשימה הוא ערך מספרי בלבד. לדוגמה, אם מזהה רשימת Marketo שלך הוא ST12345A7, הסר את התו שמופיע לפני ואחרי הספרות והזן *12345*.

1. במקטע **התאמת נתונים**, בחר לפחות שדה אחד המייצג את כתובת הדואר האלקטרוני של הלקוח או את מזהה ה-Marketo של הלקוח.

1. לחלופין, יצא **שם פרטי**, **שם משפחה**, **עיר**, **ארץ** ו **מדינה/אזור** כדי ליצור הודעות דואר אלקטרוני מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

ב- Marketo, חפש את הפלחים שלך תחת [רשימות Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
