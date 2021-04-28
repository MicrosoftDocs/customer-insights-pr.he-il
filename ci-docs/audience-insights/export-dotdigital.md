---
title: ייצוא נתוני Customer Insights אל DotDigital
description: למד כיצד להגדיר את החיבור ולייצא אל DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759960"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a>ייצוא רשימות פלחים אל DotDigital‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל פנקסי הכתובות של DotDigital והשתמש בהם עבור קמפיינים, שיווק בדוא"ל ולבניית פלחי לקוחות עם DotDigital. 

## <a name="prerequisites-for-a-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון DotDigital](https://dotdigital.com/) ואישורי מנהל מערכת מתאימים.
-   קיימים פנקסי כתובות ב- DotDigital ומזהים מתאימים. ניתן למצוא את המזהה בכתובת ה- URL כאשר אתה בוחר ופותח פנקס כתובות. לקבלת מידע נוסף, ראה [פנקסי כתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- עד מיליון פרופילים לייצוא ל- DotDigital.
- הייצוא ל- DotDigital מוגבל לפלחים.
- ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 3 שעות בשל מגבלות בצד הספק. 
- מספר הפרופילים שתוכל לייצא ל- DotDigital תלוי ומוגבל בחוזה שלך עם DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>הגדרת חיבור אל DotDigital

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **DotDigital** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **שם המשתמש והסיסמה של DotDigital**.

1. הזן את **[מזהה פנקס הכתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור אל DotDigital.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור. 

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע DotDigital. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.


1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. חזור על אותם שלבים עבור שדות אופציונליים אחרים כגון **שם פרטי**, **שם משפחה**, **שם מלא**, **מגדר**, ו **מיקוד**.

1. בחר את הפלחים שברצונך לייצא. באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- DotDigital.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 
 
ב- DotDigital, באפשרותך למצוא כעת את הפלחים שלך דרך [פנקסי כתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל DotDigital, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- DotDigital עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
