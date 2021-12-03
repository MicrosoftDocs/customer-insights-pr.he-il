---
title: ייצוא נתוני Customer Insights אל LinkedIn Ads
description: למד כיצד להגדיר את החיבור ולייצא אל LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 867a6541734746f75a35faaa8d3861e0479d6114
ms.sourcegitcommit: 9558ff772ee6c944fcb8db4bfc8cda13b38a1bff
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/29/2021
ms.locfileid: "7866889"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>ייצוא פלחים אל LinkedIn Ads ‏(Preview)

ייצא פלחים של פרופילי לקוחות מאוחדים אל LinkedIn Ads כדי ליצור קהלים תואמים. השתמש בקהלים תואמים ל- Company Targeting ול- Contact Targeting.

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) ואישורי מנהל מערכת מתאימים.
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוח בפלחים המיוצאים מכילים שדה עם כתובת דואר אלקטרוני.

## <a name="known-limitations"></a>מגבלות ידועות

- הפלח שלך ב- Customer Insights צריך להכיל לפחות 300 פרופילים ייחודיים. 
- באפשרותך לייצא עד 100,000 פרופילי לקוחות לכל ייצוא אל LinkedIn Ads.
- הייצוא אל LinkedIn Ads מוגבל לפלחים.
- ייצוא של עד 100,000 פרופילי לקוחות אל LinkedIn Ads עשוי להימשך עד 10 דקות. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>הגדרת החיבור אל LinkedIn Ads

1. בתובנות קהלים, עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **LinkedIn Ads** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל היא מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק את [מזהה החשבון של LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל- Campaign Monitor.

1. בחר **בצע אימות באמצעות LinkedIn** וספק את אישורי מנהל המערכת שלך עבור LinkedIn Campaign Manager.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורה של ייצוא אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע LinkedIn Ads. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. בחר אם ברצונך לייצא נתונים לשימוש ב- [Contact Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) או ב- [Company Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) ב- LinkedIn. 

1. למיקוד אנשי קשר, במקטע **התאמת נתונים**, בחר שדה אחד לפחות שמייצג כתובת דואר אלקטרוני של לקוח, Apple Ad ID,‏ Google Ad ID, מזהה משתמש של Google או שם פרטי ושם משפחה. אם תבחר מיקוד לחברה, בחר לפחות שדה אחד שמייצג שם חברה, תחום דואר אלקטרוני, כתובת URL של דף LinkedIn, סמל מניה או אתר אינטרנט. ניתן לבחור שדות נוספים להגדרת הייצוא. 

1. בחר את הפלחים שברצונך לייצא. הקהלים התואמים ב- LinkedIn Campaign Manager ייווצרו באופן אוטומטי עם שם הפלחים שבחרת לייצא. לכל מקטע ייווצר קהל תואם נפרד. 

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל LinkedIn Ads, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- LinkedIn Ads עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
