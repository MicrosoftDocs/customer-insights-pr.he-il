---
title: ייצוא נתוני Customer Insights אל Mailchimp
description: למד כיצד להגדיר את החיבור ולייצא אל Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759879"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a>ייצוא רשימות פלחים אל Mailchimp‏ (Preview)

יצא מקטעים של פרופיל לקוח מאוחדים אל Mailchimp כדי ליצור ידיעונים וקמפיינים בדוא"ל.

## <a name="prerequisites-for-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון Mailchimp](https://mailchimp.com/) ואישורי מנהל מערכת מתאימים.
-   קיימים קהלים ב- Mailchimp ומזהים מתאימים. למידע נוסף, ראה [קהלי Mailchimp](https://mailchimp.com/help/create-audience/).
-   יש לך [פלחים מוגדרים](segments.md)
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- עד מיליון פרופילים לייצוא ל- Mailchimp.
- הייצוא ל- Mailchimp מוגבל לפלחים.
- ייצוא פלחים עם מיליון פרופילים יכול להימשך עד שלוש שעות. 
- מספר הפרופילים שתוכל לייצא ל- Mailchimp תלוי ומוגבל בחוזה שלך עם Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>הגדרת חיבור אל Mailchimp

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Autopilot** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל- Mailchimp.

1. בחר **בצע אימות באמצעות Mailchimp** וספק את אישורי Mailchimp שלך.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור. 

## <a name="configure-the-connector"></a>קביעת תצורת המחבר

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים**> **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Mailchimp. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. הזן את **[מזהה קהל Mailchimp](https://mailchimp.com/help/find-audience-id/)** שלך

3. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. 

1. לחלופין, באפשרותך לייצא **שם פרטי** ו **שם משפחה** כדי ליצור הודעות דואר מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא. באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Mailchimp.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Mailchimp, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Mailchimp עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
