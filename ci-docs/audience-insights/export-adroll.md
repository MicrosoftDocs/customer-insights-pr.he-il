---
title: ייצוא נתוני Customer Insights אל AdRoll
description: למד כיצד להגדיר את החיבור ולייצא אל AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e48f67ec21bb9b883dd30544ccf4dcfbf487acb1abaf0a0557764bc3d955e41a
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032072"
---
# <a name="export-segments-to-adroll-preview"></a>ייצוא פלחים אל AdRoll‏ (Preview)

יצא פלחים של פרופילי לקוח מאוחדים אל AdRoll והשתמש בהם עבור פרסום. 

## <a name="prerequisites-for-a-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון AdRoll](https://www.adroll.com/) ואישורי מנהל מערכת מתאימים.
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- באפשרותך לייצא ל- AdRoll עד 250,000 פרופילים בכל פעם.
- אין באפשרותך לייצא פלחים עם פחות מ- 100 פרופילים ל- AdRoll. 
- הייצוא ל- AdRoll מוגבל לפלחים.
- ייצוא של עד 250,000 פרופילים ל- AdRoll יכול להימשך עד 10 דקות. 
- מספר הפרופילים שתוכל לייצא ל- AdRoll תלוי בחוזה שלך עם AdRoll.

## <a name="set-up-connection-to-adroll"></a>הגדרת חיבור אל AdRoll

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **AdRoll** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור אל AdRoll.

1. בחר **בצע אימות באמצעות AdRoll** וספק את אישורי מנהל המערכת שלך עבור AdRoll. 

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע AdRoll. אם אינך רואה את שם הפלח הזה, אין קשרים זמינים עבורך מסוג זה.

1. הזן את **מזהה מפרסם AdRoll** שלך. למידע נוסף עיין ב[פרופילים של מפרסמי AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. ייצוא פלחים אל AdRoll הוא הכרחי.

1. בחר את הפלחים שברצונך לייצא. בחר פלח עם 100 חברים לפחות. אין באפשרותך לייצא פלחים קטנים יותר. בנוסף, הגודל המרבי של פלח לייצוא הוא 250,000 חברים לכל ייצוא. 

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). 

באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל AdRoll, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- AdRoll עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
