---
title: ייצוא נתוני Customer Insights ל-Klaviyo
description: למד כיצד להגדיר את החיבור ולייצא ל-Klaviyo.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385789"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>ייצוא רשימות פלחים ל- Klaviy (תצוגה מקדימה)

ייצא פלחים של פרופילי לקוחות מאוחדים ל-Klaviyo והשתמש בהם לצורך פעילויות שיווק.

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון Klaviyo](https://www.klaviyo.com/) ואישורי מנהל מערכת תואמים.
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- תוכל לייצא עד 100'000 פרופילים לכל יצוא ל-Klaviyo.
- הייצוא ל-Klaviyo מוגבל לפלחים.
- השלמת ייצוא של עד מיליון פרופילים ל-Klaviyo יכולה להימשך עד 20 דקות. 
- מספר הפרופילים שתוכל לייצא ל-Klaviyo תלוי בחוזה שלך עם Klaviyo ומוגבל על ידו.

## <a name="set-up-connection-to-klaviyo"></a>הגדרת חיבור ל-Klaviyo

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ולאחר מכן בחר **Klaviyo** כדי להגדיר את החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק את [מפתח API של Klaviyo שלך](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) כדי להמשיך בכניסה. 

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל-Klaviyo.

1. בחר **אימות באמצעות Klaviyo** וספק את אישורי מנהל המערכת עבור Klaviyo.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מהמקטע Klaviyo. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. הזן את [**מזהה רשימת Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID) שלך.     

3. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. זה נדרש כדי לייצא פלחים ל-Klaviyo.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל-Dynamics 365 Customer Insights להפיץ נתונים ל-Klaviyo, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעלולים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי להבטיח ש-Klaviyo עומד בכל התחייבויות הפרטיות והאבטחה שלך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
