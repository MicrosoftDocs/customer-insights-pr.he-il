---
title: ייצוא נתוני Customer Insights אל Constant Contact
description: למד כיצד להגדיר את החיבור ולייצא אל Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760541"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a>ייצוא רשימות פלחים אל Constant Contact‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל Constant Contact והשתמש בהם עבור פעילויות שיווק. 

## <a name="prerequisites-for-a-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון Constant Contact](https://www.constantcontact.com/account-home) ואישורי מנהל מערכת מתאימים.
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- באפשרותך לייצא עד מיליון פרופילים לכל ייצוא אל Constant Contact.
- הייצוא אל Constant Contact מוגבל לפלחים.
- ייצוא של עד מיליון פרופילים ל- Constant Contact יכול להימשך עד שעה אחת. 
- מספר הפרופילים שבאפשרותך לייצא ל- Constant Contact תלוי ומוגבל בחוזה שלך עם Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>הגדרת חיבור ל- Constant Contact

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Constant Contact** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור ל- Constant Contact.

1. בחר **אימות באמצעות AdRoll** וספק את אישורי מנהל המערכת שלך עבור Constant Contact. 

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Constant Contact. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. הזן את [**מזהה הרשימה של Constant Contact שלך**](https://app.constantcontact.com/pages/contacts/ui#lists). פתח רשימה ב- Constant Contact כדי למצוא את מזהה הרשימה בכתובת ה- URL.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. יש לייצא פלחים אל Constant Contact.

1. אם תרצה בכך, תוכל לייצא את שם פרטי ושם משפחה כשדות נוספים כדי ליצור הודעות דוא"ל מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Constant Contact, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- Constant Contact עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
