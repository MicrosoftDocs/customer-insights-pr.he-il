---
title: ייצוא פלחים אל DotDigital‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f3e3378dce9177c6645b91140884ae135540243
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724987"
---
# <a name="export-segments-to-dotdigital-preview"></a>ייצוא פלחים אל DotDigital‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל פנקסי הכתובות של DotDigital והשתמש בהם עבור קמפיינים, שיווק בדוא"ל ולבניית פלחי לקוחות עם DotDigital.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון DotDigital](https://dotdigital.com/) ו[משתמש API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- מזהה DotDigital מפנקס כתובות [חדש](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) או קיים ב- DotDigital. ניתן למצוא את המזהה בכתובת ה- URL כאשר אתה בוחר ופותח פנקס כתובות.
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- קישור פרטי בשילוב עם Bring your own storage ‏(BYOS) אינו נתמך.
- עד מיליון פרופילי לקוחות לכל ייצוא אל DotDigital. השלמת הפעולה עשויה להימשך עד שלוש שעות עקב מגבלות בצד הספק. מספר פרופילי הלקוחות שתוכל לייצא אל DotDigital תלוי בחוזה שלך עם DotDigital.
- פלחים בלבד.

## <a name="set-up-connection-to-dotdigital"></a>הגדרת חיבור אל DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **DotDigital**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **שם משתמש ה- API והסיסמה של DotDigital**.

1. הזן את **מזהה פנקס הכתובות של DotDigital**.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע DotDigital. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. לחלופין, יצא **שם פרטי**, **שם משפחה**, **שם מלא**, **מגדר** ו **מיקוד**.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

ב- DotDigital, מצא את הפלחים שלך דרך [פנקסי כתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
