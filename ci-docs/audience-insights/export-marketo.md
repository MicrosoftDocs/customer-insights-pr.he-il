---
title: ייצוא נתוני Customer Insights אל Marketo
description: למד כיצד לקבוע את תצורת החיבור אל Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570404"
---
# <a name="connector-for-marketo-preview"></a>מחבר עבור Marketo‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Marketo​.

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון Marketo](https://login.marketo.com/) ואישורי מנהל מערכת מתאימים.
-   יש רשימות קיימות ב- Marketo ומזהים מתאימים. לקבלת מידע נוסף, ראה [רשימות Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   יש לך [פלחים מוגדרים](segments.md).
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="connect-to-marketo"></a>התחבר ל- Marketo

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. תחת **Marketo**, בחר **הגדר**.

1. תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. הזן את **[מזהה הלקוח של Marketo, סוד הלקוח ושם מארח של נקודת קצה של REST](https://developers.marketo.com/rest-api/authentication/)**.

1. הזן את **[מזהה רשימת Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. בחר **אני מסכים** כדי לאשר את **פרטיות ותאימות הנתונים** ובחר **התחבר** כדי לאתחל את החיבור אל Marketo.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="יצא צילום מסך עבור חיבור Marketo":::

1. בחר **הבא** להגדרת התצורה של הייצוא.

## <a name="configure-the-connector"></a>קביעת תצורת המחבר

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. 

1. אם תרצה בכך, תוכל לייצא את **שם פרטי**, **שם משפחה**, **עיר**, **ארץ** ו **מדינה/אזור** כשדות נוספים ליצירת הודעות דוא"ל מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא. באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="בחר שדות ופלחים לייצוא ל- Marketo":::

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab). ב- Marketo, באפשרותך למצוא כעת את הפלחים שלך תחת [רשימות Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>מגבלות ידועות

- עד מיליון פרופילים לייצוא ל- Marketo.
- הייצוא ל- Marketo מוגבל לפלחים.
- ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 3 שעות. 
- מספר הפרופילים שתוכל לייצא ל- Marketo תלוי ומוגבל בחוזה שלך עם Marketo.

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Marketo, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Marketo עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
