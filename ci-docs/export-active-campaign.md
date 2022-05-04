---
title: ייצוא נתוני Customer Insights ל- ActiveCampaign
description: למד כיצד להגדיר את החיבור ולייצא ל- ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646939"
---
# <a name="export-segments-to-activecampaign-preview"></a>ייצוא פלחים ל- ActiveCampaign‏ (Preview)

ייצא פלחים של פרופילי לקוחות מאוחדים ל- ActiveCampaign והשתמש בהם לצורך פעילויות שיווק.

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון ActiveCampaign](https://www.activecampaign.com/) ואישורי מנהל מערכת תואמים.
-   יש לך הרשאות [פלחים מוגדרים](segments.md) ב- Customer Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה עם כתובת דואר אלקטרוני.

## <a name="known-limitations"></a>מגבלות ידועות

- באפשרותך לייצא עד מיליון פרופילי לקוחות בכל ייצוא אל ActiveCampaign ופעולה זו עשויה להימשך עד 90 דקות.
- הייצוא ל- ActiveCampaign מוגבל לפלחים.
- מספר פרופילי הלקוחות שתוכל לייצא אל ActiveCampaign תלוי בחוזה שלך עם ActiveCampaign.

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

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. זה נדרש כדי לייצא פלחים ל- ActiveCampaign. לחלופין, אתה יכול לייצא שם פרטי, שם משפחה, וטלפון ליצירת הודעות דואר אלקטרוני מותאמות אישית יותר. בחר הוסף תכונה כדי למפות שדות אלה.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים ל- ActiveCampaign, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעלולים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהוראתך, אבל אתה אחראי להבטיח ש- ActiveCampaign עומדת בכל התחייבויות הפרטיות והאבטחה שלך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
