---
title: ייצוא נתוני Customer Insights ל- Criteo
description: למד כיצד להגדיר את תצורת החיבור ולייצא ל- Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 854f5f0c53f053fc5d742d69a045db1926fec00c
ms.sourcegitcommit: bf65bc0a54cdab71680e658e1617bee7b2c2bb68
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/27/2022
ms.locfileid: "8808769"
---
# <a name="export-segments-to-criteo-preview"></a>ייצוא פלחים ל- Criteo (תצוגה מקדימה)

יצא פלחים של פריטי unified customer profile כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Criteo.

## <a name="prerequisites-for-connection"></a>דרישות מוקדמות לחיבור

-   יש לך [חשבון Criteo Dynamics Retargeting](https://www.criteo.com/login/) ואישורי מנהל מערכת התואמים.
-   יש לך [פלחים מוגדרים](segments.md).
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>מגבלות ידועות

- עד מיליון פרופילי לקוחות בכל ייצוא אל Criteo.
- הייצוא ל- Criteo מוגבל לפלחים.
- ייצוא פלחים עם מספר כולל של מיליון פרופילי לקוחות עשוי להימשך עד 30 דקות. 
- מספר פרופילי הלקוחות שתוכל לייצא אל Criteo תלוי בחוזה שלך עם Criteo ומוגבל בהתאם לתנאיו.

## <a name="set-up-connection-to-criteo"></a>הגדרת חיבור ל- Criteo

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Criteo** כדי להגדיר את החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר **אני מסכים** כדי לאשר את **פרטיות נתונים ותאימות** ובחר **חיבור** כדי לאתחל את החיבור ל- Criteo.

1. בחר **אימות באמצעות Criteo** וספק את שם המשתמש והאישורים שלך כמנהל המערכת עבור Criteo. 

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור עבור ייצוא**, בחר חיבור מתוך מקטע Criteo. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך. 

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח. 

1. לחלופין, אתה יכול לייצא **מזהה מפרסם** ו **שם**

1. בחר את הפלחים שברצונך לייצא. 

1. בחר **Save**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Criteo, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אך אתה אחראי להבטיח ש- Criteo עומד בכל מחויבויות הפרטיות או האבטחה שלקחת על עצמך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](includes/footer-banner.md)]
