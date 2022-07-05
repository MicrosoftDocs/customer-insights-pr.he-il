---
title: ייצוא פלחים ל- Braze ‏(Preview)
description: למד כיצד להגדיר את תצורת החיבור ולייצא ל- Braze.
ms.date: 06/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 314a61f82c4040a8dbd6dff1dd5d92e20464f82a
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081497"
---
# <a name="export-segments-to-braze-preview"></a>ייצוא פלחים ל- Braze ‏(Preview)

ייצא פלחים של פרטי Unified Customer Profile ל-Braze והשתמש בהם לפעילויות שיווקיות.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Braze](https://www.braze.com/) ואישורי מנהל מערכת התואמים.
- [פלחים קיימים ב- Braze](https://www.braze.com/docs/user_guide/engagement_tools/segments/creating_a_segment/).
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרטי unified customer profile בפלחים המיוצאים מכילים שדה המייצג כתובת אימייל ומזהה לקוח של Braze.

## <a name="known-limitations"></a>מגבלות ידועות

- הייצוא ל-Braze מוגבל לפלחים.
- ייצוא של עד מיליון פרופילי לקוחות אל Braze עשוי להימשך עד 40 דקות.
- מספר פרופילי הלקוחות שתוכל לייצא אל Braze תלוי בחוזה שלך עם Braze ומוגבל בהתאם לתנאיו.

## <a name="set-up-connection-to-braze"></a>הגדרת חיבור ל- Braze

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Braze** כדי להגדיר את החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק את [מפתח ה-API של Braze](https://www.braze.com/docs/api/basics/) כדי להמשיך להתחבר.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **חבר** כדי לאתחל את החיבור ל- Braze.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Braze. אם אינך רואה את המקטע הזה, אין חיבורים מסוג זה שזמינים עבורך.  

1. הוסף **שם תצוגה** עבור היצוא שלך.

1. הוסף את מזהה ה-API של פלח Braze שאליו אתה רוצה לייצא בשדה **מזהה API של פלח Braze**. אתה יכול למצוא את המזהה בפרטי הפלחים בפלטפורמת Braze.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. בשדה **מזהה לקוח** בחר את השדה שמייצג את מזהה Braze של הלקוח. פריט זה נדרש לייצא פלחים ל- Braze. ניתן לבחור שדות נוספים באופן אופציונלי.

1. בחר **Save**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Braze, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אך אתה אחראי להבטיח ש- Braze עומד בכל מחויבויות הפרטיות או האבטחה שלקחת על עצמך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
