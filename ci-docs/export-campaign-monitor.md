---
title: ייצוא נתוני Customer Insights אל Campaign Monitor
description: למד כיצד להגדיר את החיבור ולייצא אל Campaign Monitor.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b351e491ee830b6360d4efe33d32a726c2e553ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646669"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>ייצוא פלחים אל Campaign Monitor‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל Campaign Monitor והשתמש בהם עבור פעילויות שיווק.

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון Campaign Monitor](https://www.campaignmonitor.com/) ואישורי מנהל מערכת מתאימים.
-   יש לך הרשאות [פלחים מוגדרים](segments.md) ב- Customer Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- באפשרותך לייצא עד מיליון פרופילי לקוחות לכל ייצוא אל Campaign Monitor.
- הייצוא ל- Campaign Monitor מוגבל לפלחים.
- ייצוא של עד מיליון פרופילי לקוחות אל Campaign Monitor עשוי להימשך עד 20 דקות. 
- מספר פרופילי הלקוחות שתוכל לייצא אל Campaign Monitor תלוי בחוזה שלך עם Campaign Monitor ומוגבל בהתאם לתנאיו.

## <a name="set-up-connection-to-campaign-monitor"></a>הגדרת חיבור ל- Campaign Monitor

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Campaign Monitor** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל- Campaign Monitor.

1. בחר **בצע אימות מול Campaign Monitor** וספק את אישורי מנהל המערכת שלך עבור Campaign Monitor.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Campaign Monitor. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. הזן את [**מזהה רשימת Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) שלך.    
   [צור את מפתח ה- API](https://www.campaignmonitor.com/api/getting-started/) דרך **הגדרות חשבון** ב- Campaign Monitor תחילה כדי להציג את מזהה רשימת ה- API.  

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. יש לייצא פלחים אל Campaign Monitor.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Campaign Monitor, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- Campaign Monitor עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
