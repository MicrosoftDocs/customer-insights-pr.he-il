---
title: ייצוא נתוני Customer Insights אל Google Ads
description: למד כיצד לקבוע את תצורת החיבור אל Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568445"
---
# <a name="connector-for-google-ads-preview"></a>מחבר עבור Google Ads‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל רשימת קהלים של Google Ads והשתמש בהם כדי לפרסם ב- Google Search‏, Gmail, YouTube, ו- Google Display Network. 

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון Google Ads](https://ads.google.com/) ואישורי מנהל מערכת מתאימים.
-   קיימים קהלים ב- Google Ads ומזהים מתאימים. למידע נוסף, ראה [קהלי Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   יש לך [פלחים מוגדרים](segments.md)
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדות המייצגים כתובת דוא"ל, שם פרטי ושם משפחה

## <a name="connect-to-google-ads"></a>התחבר ל- Google Ads

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. תחת **Google Ads**, בחר **הגדר**.

1. תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. הזן את **[מזהה הלקוח של Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. הזן את **[אסימון המפתח המאושר של Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. הזן את **[מזהה קהל Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ובחר **התחבר** כדי לאתחל את החיבור אל Google Ads.

1. בחר **בצע אימות באמצעות Google Ads** וספק את אישורי Google Ads שלך.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="יצא צילום מסך עבור חיבור Google Ads":::

1. בחר **הבא** להגדרת התצורה של הייצוא.

## <a name="configure-the-connector"></a>קביעת תצורת המחבר

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. חזור על אותם שלבים עבור השדות **שם פרטי** ו **שם משפחה**.

1. בחר את הפלחים שברצונך לייצא. באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Google Ads.

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab). ב- Google Ads, באפשרותך למצוא כעת את הפלחים שלך תחת [קהלי Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>מגבלות ידועות

- עד מיליון פרופילים לייצוא ל- Google Ads.
- הייצוא ל- Google Ads מוגבל לפלחים.
- ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד חמש דקות בשל מגבלות בצד הספק. 
- ההתאמה ב- Google Ads יכולה להימשך עד 48 שעות.

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Google Ads, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Google Ads עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
