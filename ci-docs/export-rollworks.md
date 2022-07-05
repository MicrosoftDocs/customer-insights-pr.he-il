---
title: ייצוא פלחים אל RollWorks‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל RollWorks.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 83c3f2437b9822d29d1d2f99ead96815b1b0881a
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055169"
---
# <a name="export-segments-to-rollworks-preview"></a>ייצוא פלחים אל RollWorks‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל RollWorks והשתמש בהם עבור פרסום. 

## <a name="prerequisites-for-a-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון RollWorks](https://www.rollworks.com/) ואישורי מנהל מערכת מתאימים.
-   יש לך הרשאות [פלחים מוגדרים](segments.md) ב- Customer Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- באפשרותך לייצא עד 250,000 פרופילי לקוחות לכל ייצוא אל RollWorks.
- לא ניתן לייצא פלחים עם פחות מ- 100 פרופילי לקוחות אל RollWorks. 
- הייצוא אל RollWorks מוגבל לפלחים.
- ייצוא של עד 250,000 פרופילי לקוחות אל RollWorks עשוי להימשך עד 10 דקות. 
- מספר פרופילי הלקוחות שתוכל לייצא אל RollWorks תלוי בחוזה שלך עם RollWorks ומוגבל בהתאם לתנאיו.

## <a name="set-up-connection-to-rollworks"></a>הגדרת חיבור אל RollWorks

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **RollWorks** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל- RollWorks.

1. בחר **בצע אימות מול RollWorks** וספק את אישורי מנהל המערכת שלך עבור RollWorks.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע RollWorks. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. הזן את **מזהה מפרסם RollWorks** [פריט ניתן לפרסום של RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. יש לייצא פלחים אל RollWorks.

1. בחר את הפלחים שברצונך לייצא. בחר פלח עם 100 חברים לפחות. אין באפשרותך לייצא פלחים קטנים יותר. בנוסף, הגודל המרבי של פלח לייצוא הוא 250,000 חברים לייצוא. 

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל RollWorks, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- RollWorks עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
