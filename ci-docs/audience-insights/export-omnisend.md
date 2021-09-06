---
title: ייצוא נתונים של Customer Insights אל Omnisend
description: למד כיצד להגדיר את החיבור ולייצא אל Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58b54dc24f4656f9dd376415a701539c8796e83e6d4e3c6754f5627ce77c5685
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031767"
---
# <a name="export-segments-to-omnisend-preview"></a>ייצוא פלחים ל- Omnisend ‏(Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל Omnisend והשתמש בהם עבור פעילויות שיווק.

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון Omnisend](https://www.omnisend.com/) ואישורי מנהל מערכת מתאימים.
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- ניתן לייצא עד מיליון פרופילים בכל פעולת ייצוא ל- Omnisend ופעולה זו יכולה להימשך עד 4 שעות.
- הייצוא אל Omnisend מוגבל לפלחים.
- מספר הפרופילים שתוכל לייצא אל Omnisend תלוי בחוזה שלך עם Omnisend.

## <a name="set-up-connection-to-omnisend"></a>הגדרת חיבור אל Omnisend

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Omnisend** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת אפשריים. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את [מפתח ה- API של Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key) שלך.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל- Omnisend.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע Omnisend. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. יש לייצא פלחים אל Omnisend. לחלופין, באפשרותך לייצא שם פרטי, שם משפחה, כתובת, ארץ/אזור, מדינה, עיר ומיקוד כדי ליצור הודעות דואר מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Ommisend, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- Ommisend עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
