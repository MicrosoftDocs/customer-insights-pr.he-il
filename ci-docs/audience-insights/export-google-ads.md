---
title: ייצוא נתוני Customer Insights אל Google Ads
description: למד כיצד להגדיר את החיבור ולייצא אל Google Ads.
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: ce9579f3d31207e666665237fd8935bb86889f8d
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617924"
---
# <a name="export-segments-to-google-ads-preview"></a>ייצוא פלחים אל Google Ads‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים לרשימת קהלים של Google Ads והשתמש בהם לפרסום בחיפוש Google‏, Gmail, YouTube, ו- Google Display Network. 

> [!IMPORTANT]
> לעת עתה, באפשרותך ליצור חיבור חדש ולייצא נתונים אל Google Ads רק אם כבר יש לך אסימון מפתח מאושר של Google Ads. עקב שינויים במדיניות, נעדכן את הייצוא של Google Ads בקרוב ונספק אפשרות ייצוא שלא תדרוש אסימון מפתח כדי להבטיח את המשכיות החוויה שלך ולפשט את הייצוא אל Google Ads. מומלץ לא להגדיר חיבורים נוספים ל- Google Ads כדי להקל על מעבר פשוט יותר לאפשרות הייצוא החדשה.

## <a name="prerequisites-for-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון Google Ads](https://ads.google.com/) ואישורי מנהל מערכת מתאימים.
-   יש לך [אסימון מפתח Google Ads מאושר](https://developers.google.com/google-ads/api/docs/first-call/dev-token). 
-   אתה מקיים את הדרישות של [מדיניות התאמת הלקוח](https://support.google.com/adspolicy/answer/6299717).
-   אתה מקיים את הדרישות של [גדלי רשימת שיווק מחדש](https://support.google.com/google-ads/answer/7558048).
-   קיימים קהלים ב- Google Ads ומזהים מתאימים. למידע נוסף, ראה [קהלי Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   יש לך [פלחים מוגדרים](segments.md).
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדות המייצגים כתובת דוא"ל, שם פרטי ושם משפחה.

## <a name="known-limitations"></a>מגבלות ידועות

- עד מיליון פרופילי לקוחות לייצוא אל Google Ads.
- הייצוא ל- Google Ads מוגבל לפלחים.
- ייצוא פלחים עם מספר כולל של מיליון פרופילי לקוחות עשוי להימשך עד 5 דקות בשל מגבלות בצד הספק. 
- ההתאמה ב- Google Ads יכולה להימשך עד 48 שעות.

## <a name="set-up-connection-to-google-ads"></a>הגדרת חיבור אל Google Ads

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Google Ads** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **[מזהה הלקוח של Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. הזן את **[אסימון המפתח המאושר של Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **בצע אימות באמצעות Google Ads** וספק את אישורי Google Ads שלך.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור. 

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Google Ads. אם אינך רואה את שם הפלח הזה, אין קשרים זמינים עבורך מסוג זה.

1. הזן את **[מזהה קהל Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ובחר **התחבר** כדי לאתחל את החיבור אל Google Ads.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. בחר את הפלחים שברצונך לייצא. באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Google Ads.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). 

באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Google Ads, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Google Ads עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
