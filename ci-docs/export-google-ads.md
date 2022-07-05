---
title: ייצוא פלחים אל Google Ads‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b7f08936d7d90322cb4e62396a2961fe06273b76
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081640"
---
# <a name="export-segments-to-google-ads-preview"></a>ייצוא פלחים אל Google Ads‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים לרשימת קהלים של Google Ads והשתמש בהם לפרסום בחיפוש Google‏, Gmail, YouTube, ו- Google Display Network. 


## <a name="prerequisites-for-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון Google Ads](https://ads.google.com/) ואישורי מנהל מערכת מתאימים.
-   אתה מקיים את הדרישות של [מדיניות התאמת הלקוח](https://support.google.com/adspolicy/answer/6299717).
-   אתה מקיים את הדרישות של [גדלי רשימת שיווק מחדש](https://support.google.com/google-ads/answer/7558048).
-   יש לך [פלחים מוגדרים](segments.md).
-   פרטי Unified customer profiles בפלחים המיוצאים מכילים שדות המייצגים כתובת דוא"ל, טלפון, מזהה מפרסם במכשירים ניידים, מזהה משתמש של צד שלישי או כתובת.

## <a name="known-limitations"></a>מגבלות ידועות

- הייצוא ל- Google Ads מוגבל לפלחים.
- ייצוא פלחים עם מספר כולל של מיליון פרופילי לקוחות עשוי להימשך עד 30 דקות בשל מגבלות בצד הספק. 
- ההתאמה ב- Google Ads יכולה להימשך עד 48 שעות.

## <a name="set-up-connection-to-google-ads"></a>הגדרת חיבור אל Google Ads

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Google Ads** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **[מזהה הלקוח של Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **בצע אימות באמצעות Google Ads** וספק את אישורי Google Ads שלך.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור. 

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Google Ads. אם אינך רואה את שם הפלח הזה, אין קשרים זמינים עבורך מסוג זה.

1. אם ברצונך ליצור קהל חדש, השאר ריק את השדה של מזהה קהל Google. אנו ניצור אוטומטית קהל חדש בחשבון Google Ads שלך ונשתמש בשם הפלח המיוצא. אם אתה רוצה לעדכן קהל קיים של Google Ads, הזן את [מזהה קהל Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.) שלך

1. במקטע **התאמת נתונים**, בחר שדה נתונים אחד או יותר לייצוא, ובחר את השדה המייצג את שדות הנתונים התואמים ב- Customer Insights.

1. בחר את הפלחים שברצונך לייצא. 

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). 

באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Google Ads, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Google Ads עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE [footer-include](includes/footer-banner.md)]
