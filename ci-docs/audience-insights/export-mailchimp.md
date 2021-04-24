---
title: ייצוא נתוני Customer Insights אל Mailchimp
description: למד כיצד לקבוע את תצורת החיבור אל Mailchimp.
ms.date: 10/26/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9f86616731c3cc3d26370727103ea9c5d4288c8d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598202"
---
# <a name="connector-for-mailchimp-preview"></a>מחבר עבור Mailchimp‏ (Preview)

יצא מקטעים של פרופיל לקוח מאוחדים אל Mailchimp כדי ליצור ידיעונים וקמפיינים בדוא"ל.

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון Mailchimp](https://mailchimp.com/) ואישורי מנהל מערכת מתאימים.
-   קיימים קהלים ב- Mailchimp ומזהים מתאימים. למידע נוסף, ראה [קהלי Mailchimp](https://mailchimp.com/help/create-audience/).
-   יש לך [פלחים מוגדרים](segments.md)
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="connect-to-mailchimp"></a>התחבר ל- Mailchimp

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. תחת **Mailchimp**, בחר **הגדר**.

1. תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. הזן את **[מזהה קהל Mailchimp](https://mailchimp.com/help/find-audience-id/)** ובחר **התחבר** כדי לאתחל את החיבור אל Mailchimp.

1. בחר **בצע אימות באמצעות Mailchimp** וספק את אישורי Mailchimp שלך.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="יצא צילום מסך עבור חיבור Mailchimp":::

1. בחר **הבא** להגדרת התצורה של הייצוא.

## <a name="configure-the-connector"></a>קביעת תצורת המחבר

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. 

1. אם תרצה בכך, תוכל לייצא את **שם פרטי** ו **שם משפחה** כשדות נוספים כדי ליצור הודעות דוא"ל מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא. באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="בחר שדות ופלחים לייצוא ל- Mailchimp":::

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab). ב- Mailchimp, באפשרותך למצוא כעת את הפלחים שלך תחת [קהלי Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>מגבלות ידועות

- עד מיליון פרופילים לייצוא ל- Mailchimp.
- הייצוא ל- Mailchimp מוגבל לפלחים.
- ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד שלוש שעות בשל מגבלות בצד הספק. 
- מספר הפרופילים שתוכל לייצא ל- Mailchimp תלוי ומוגבל בחוזה שלך עם Mailchimp.

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Mailchimp, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Mailchimp עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]