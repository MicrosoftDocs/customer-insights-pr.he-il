---
title: ייצוא נתוני Customer Insights אל Microsoft Advertising
description: למד כיצד להגדיר את החיבור ולייצא אל Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f8a4cbb9590f9c5311789154319283530e0a10343cccbe9c7aec99765b4fbf2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031465"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>ייצוא פלחים אל Microsoft Advertising‏ (Preview)

יצא פלחים של Customer Insights אל ‏Microsoft Advertising כדי ליצור קהלים של Customer Match. השתמש בקהלים אלה עבור הקמפיינים הפרסומיים שלך.

## <a name="prerequisites"></a>דרישות מוקדמות

-   [חשבון Microsoft Advertising](https://ads.microsoft.com/) ואישורי מנהל מערכת מתאימים.
-   אישרת את תנאי השימוש של Customer Match. 
-   [פלחים מוגדרים](segments.md) בתובנות לגבי קהלים.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה עם כתובת דואר אלקטרוני.

## <a name="known-limitations"></a>מגבלות ידועות

- באפשרותך לייצא עד 500,000 פרופילים כדי לייצא אל Microsoft Advertising.
- הייצוא אל Microsoft Advertising מוגבל לפלחים.
- ייצוא של עד 500,000 פרופילים ל- Microsoft Advertising יכול להימשך עד 10 דקות. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>הגדרת החיבור אל Microsoft Advertising

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Microsoft Advertising** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. ברירת המחדל היא מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור אל Microsoft Advertising.

1. בחר **בצע אימות באמצעות Microsoft Advertising** וספק את אישורי מנהל המערכת שלך עבור Microsoft Advertising.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע Microsoft Advertising. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. בחר פלחים לייצוא. הקהלים של Customer Match ב- Microsoft Advertising נוצרים באופן אוטומטי עם שם הפלחים שנבחרו לייצוא. לכל מקטע ייווצר קהל נפרד של Customer Match. 

1. הזן את **מזהה הלקוח ומזהה החשבון של Microsoft Advertising**. באפשרותך לאתר את מזהה הלקוח (`cid`) ומזהה החשבון (`aid`) בפרמטרים של כתובת ה- URL כשאתה מחובר ל- Microsoft Advertising.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח עם כתובת הדואר האלקטרוני של הלקוח. יש לייצא פלחים אל Microsoft Advertising.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Microsoft Advertising, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- Microsoft Advertising עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
