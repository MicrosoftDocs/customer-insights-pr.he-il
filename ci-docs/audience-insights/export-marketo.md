---
title: ייצוא נתוני Customer Insights אל Marketo
description: למד כיצד להגדיר את החיבור ולייצא אל Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759822"
---
# <a name="export-segments-to-marketo-preview"></a>ייצוא פלחים ל- Marketo‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Marketo​.

## <a name="prerequisites-for-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון Marketo](https://login.marketo.com/) ואישורי מנהל מערכת מתאימים.
-   יש רשימות קיימות ב- Marketo ומזהים מתאימים. לקבלת מידע נוסף, ראה [רשימות Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   יש לך [פלחים מוגדרים](segments.md).
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- עד מיליון פרופילים לייצוא ל- Marketo.
- הייצוא ל- Marketo מוגבל לפלחים.
- ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 3 שעות. 
- מספר הפרופילים שתוכל לייצא ל- Marketo תלוי ומוגבל בחוזה שלך עם Marketo.

## <a name="set-up-connection-to-marketo"></a>הגדרת חיבור אל Marketo

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Marketo** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **[מזהה הלקוח של Marketo, סוד הלקוח ושם מארח של נקודת קצה של REST](https://developers.marketo.com/rest-api/authentication/)**.

1. בחר **אני מסכים** כדי לאשר את **פרטיות ותאימות הנתונים** ובחר **התחבר** כדי לאתחל את החיבור אל Marketo.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Marketo. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. הזן את **[מזהה רשימת Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. 

1. לחלופין, באפשרותך לייצא **שם פרטי**, **שם משפחה**, **עיר**, **ארץ** ו **מדינה/אזור** כדי ליצור הודעות דואר מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא. באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Marketo.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). ב- Marketo, באפשרותך למצוא כעת את הפלחים שלך תחת [רשימות Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Marketo, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Marketo עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]