---
title: ייצוא נתוני Customer Insights אל Marketo
description: למד כיצד להגדיר את החיבור ולייצא אל Marketo.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
---

# <a name="export-segments-to-marketo-preview"></a>ייצוא פלחים ל- Marketo‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Marketo​.

## <a name="prerequisites-for-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון Marketo](https://login.marketo.com/) ואישורי מנהל מערכת מתאימים.
-   יש רשימות קיימות ב- Marketo ומזהים מתאימים. לקבלת מידע נוסף, ראה [רשימות Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   יש לך [פלחים מוגדרים](segments.md).
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- עד מיליון פרופילי לקוחות לייצוא אל Marketo.
- הייצוא ל- Marketo מוגבל לפלחים.
- ייצוא פלחים עם מספר כולל של מיליון פרופילי לקוחות עשוי להימשך עד 3 שעות. 
- מספר פרופילי הלקוחות שתוכל לייצא אל Marketo תלוי בחוזה שלך עם Marketo ומוגבל בהתאם לתנאיו.

## <a name="set-up-connection-to-marketo"></a>הגדרת חיבור אל Marketo

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Marketo** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **[מזהה הלקוח של Marketo, סוד הלקוח ושם מארח של נקודת קצה של REST](https://developers.marketo.com/rest-api/authentication/)**. שם המארח של נקודת הקצה REST הוא שם המארח בלבד, ללא `https://`. דוגמה:`xyz-abc-123.mktorest.com`. 

1. בחר **אני מסכים** כדי לאשר את **פרטיות ותאימות הנתונים** ובחר **התחבר** כדי לאתחל את החיבור אל Marketo.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Marketo. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. הזן את **[מזהה רשימת Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**. מזהה הרשימה הוא ערך מספרי בלבד. לדוגמה, אם מזהה רשימת Marketo שלך הוא ST12345A7, הסר את התו שמופיע לפני ואחרי הספרות והזן `12345`. 

1. במקטע **התאמת נתונים**, בחר לפחות שדה אחד המייצג את כתובת הדואר האלקטרוני של הלקוח או את מזהה ה-Marketo של הלקוח. 

1. לחלופין, באפשרותך לייצא **שם פרטי**, **שם משפחה**, **עיר**, **ארץ** ו **מדינה/אזור** כדי ליצור הודעות דואר מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא. באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Marketo.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). ב- Marketo, באפשרותך למצוא כעת את הפלחים שלך תחת [רשימות Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Marketo, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Marketo עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
