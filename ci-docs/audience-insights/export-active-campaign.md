---
title: ייצוא נתוני Customer Insights ל- ActiveCampaign
description: למד כיצד להגדיר את החיבור ולייצא ל- ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 14d420205a5c60d471ef21a04ab6d02295a65ca8fd5205ba782a300703b06102
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032210"
---
# <a name="export-segments-to-activecampaign-preview"></a>ייצוא פלחים ל- ActiveCampaign‏ (Preview)

ייצא פלחים של פרופילי לקוחות מאוחדים ל- ActiveCampaign והשתמש בהם לצורך פעילויות שיווק.

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון ActiveCampaign](https://www.activecampaign.com/) ואישורי מנהל מערכת תואמים.
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה עם כתובת דואר אלקטרוני.

## <a name="known-limitations"></a>מגבלות ידועות

- ניתן לייצוא עם מיליון פרופילים בכל ייצוא ל- ActiveCampaign והפעולה יכולה להימשך עד 90 דקות.
- הייצוא ל- ActiveCampaign מוגבל לפלחים.
- מספר הפרופילים שתוכל לייצא ל- ActiveCampaign תלוי בחוזה שלך עם ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>הגדר חיבור ל- ActiveCampaign

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ולאחר מכן בחר **ActiveCampaign** כדי להגדיר את החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את [מפתח API של ActiveCampaign ואת שם המחשב המארח של נקודת הקצה של REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). שם המארח של נקודת הקצה REST הוא שם המארח בלבד, ללא https://. 

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל- ActiveCampaign.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורה של ייצוא אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מהמקטע ActiveCampaign. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. הזן את [**מזהה רשימת ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) שלך.    

3. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. זה נדרש כדי לייצא פלחים ל- ActiveCampaign. לחלופין, אתה יכול לייצא שם פרטי, שם משפחה, וטלפון ליצירת הודעות דואר אלקטרוני מותאמות אישית יותר. בחר הוסף תכונה כדי למפות שדות אלה.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים ל- ActiveCampaign, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעלולים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהוראתך, אבל אתה אחראי להבטיח ש- ActiveCampaign עומדת בכל התחייבויות הפרטיות והאבטחה שלך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
