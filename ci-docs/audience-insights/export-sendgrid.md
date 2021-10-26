---
title: ייצוא נתוני Customer Insights אל SendGrid
description: למד כיצד להגדיר את החיבור ולייצא אל SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: da3da5ea68d178deab3b9ab31dd810dee610f607
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/08/2021
ms.locfileid: "7617832"
---
# <a name="export-segments-to-sendgrid-preview"></a>ייצוא פלחים ל- SendGrid‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים לרשימות אנשי הקשר של SendGrid והשתמש בהם עבור קמפיינים ושיווק בדוא"ל ב- SendGrid. 

## <a name="prerequisites-for-a-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון SendGrid](https://sendgrid.com/) ואישורי מנהל מערכת מתאימים.
-   יש רשימות אנשי קשר קיימות ב- SendGrid ומזהים מתאימים. למידע נוסף, ראה [SendGrid - ניהול אנשי קשר](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- עד 100,000 פרופילי לקוחות בסה"כ ל- SendGrid.
- הייצוא ל- SendGrid מוגבל לפלחים.
- ייצוא של עד 100,000 פרופילי לקוחות אל SendGrid עשוי להימשך עד כמה שעות. 
- מספר פרופילי הלקוחות שתוכל לייצא אל SendGrid תלוי בחוזה שלך עם SendGrid ומוגבל בהתאם לתנאיו.

## <a name="set-up-connection-to-sendgrid"></a>הגדרת חיבור אל SendGrid

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **SendGrid** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **מפתח API של SendGrid** [מפתח API של SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור אל SendGrid.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע SendGrid. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. הזן את **[מזהה רשימת SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. חזור על אותם שלבים עבור שדות אופציונליים אחרים כגון **שם פרטי**, **שם משפחה**, **מדינה/אזור**, **מחוז**, **עיר** ו **מיקוד**.

1. בחר את הפלחים שברצונך לייצא. אנחנו **ממליצים בחום לא לייצא יותר מ- 100,000 פרופילי לקוחות בסך הכל** אל SendGrid. 

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל SendGrid, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- SendGrid עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
