---
title: ייצוא נתוני Customer Insights אל SendGrid
description: למד כיצד לקבוע את תצורת החיבור אל SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597282"
---
# <a name="connector-for-sendgrid-preview"></a>מחבר עבור SendGrid‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים לרשימות אנשי הקשר של SendGrid והשתמש בהם עבור קמפיינים ושיווק בדוא"ל ב- SendGrid. 

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון SendGrid](https://sendgrid.com/) ואישורי מנהל מערכת מתאימים.
-   יש רשימות אנשי קשר קיימות ב- SendGrid ומזהים מתאימים. למידע נוסף, ראה [SendGrid - ניהול אנשי קשר](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="connect-to-sendgrid"></a>התחבר ל- SendGrid

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. תחת **SendGrid**, בחר **הגדר**.

1. תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="חלונית תצורת הייצוא של SendGrid.":::

1. הזן את **מפתח API של SendGrid** [מפתח API של SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. הזן את **[מזהה רשימת SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור אל SendGrid.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **הבא** להגדרת התצורה של הייצוא.

## <a name="configure-the-connector"></a>קביעת תצורת המחבר

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. חזור על אותם שלבים עבור שדות אופציונליים אחרים כגון **שם פרטי**, **שם משפחה**, **מדינה/אזור**, **מחוז**, **עיר** ו **מיקוד**.

1. בחר את הפלחים שברצונך לייצא. אנחנו **ממליצים בחום לא לייצא יותר מ- 100,000 פרופילי לקוחות בסך הכל** אל SendGrid. 

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).

## <a name="known-limitations"></a>מגבלות ידועות

- עד 100,000 פרופילים בסך הכל ל- SendGrid.
- הייצוא ל- SendGrid מוגבל לפלחים.
- ייצוא של עד 100,000 פרופילים ל- SendGrid יכול להימשך עד מספר שעות. 
- מספר הפרופילים שתוכל לייצא ל- SendGrid תלוי ומוגבל בחוזה שלך עם SendGrid.

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל SendGrid, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- SendGrid עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]