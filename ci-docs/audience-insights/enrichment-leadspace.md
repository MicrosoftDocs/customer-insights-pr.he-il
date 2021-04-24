---
title: העשרת פרופילי החברה באמצעות Leadspace העשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות Leadspace.
ms.date: 11/24/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 41c56aece043c2d7658fd2655713e1e98775edec
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597650"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>העשרה של פרופילי חברות באמצעות Leadspace (תצוגה מקדימה)

Leadspace היא חברה למדעי נתונים המספקת פלטפורמת נתוני לקוחות B2B. היא מאפשרת ללקוחות עם פרופילי לקוחות אחידים לחברות להעשיר את הנתונים שלהם. העשרות כוללות תכונות נוספות כגון גודל חברה, מיקום, ענף ועוד.

## <a name="prerequisites"></a>דרישות מוקדמות

כדי להגדיר את Leadspace, הדרישות המוקדמות הבאות צריכות להתקיים:

- יש לך רישיון Leadspace פעיל ו"מפתח קבוע" (מכונה **אסימון Leadspace**). צור קשר ישירות עם [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) לקבלת פרטים על המוצר שלהם.
- יש לך הרשאות [מנהל מערכת](permissions.md#administrator).
- יש לך [פרופילי לקוחות מאוחדים](customer-profiles.md) עבור חברות.

## <a name="configuration"></a>תצורה

1. ב- audience insights, עבור אל **נתונים** > **העשרה**.

1. בחר **העשר את הנתונים שלי** באריח Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="צילום מסך של אריח Leadspace.":::

1. בחר **תחילת העבודה** והזן **אסימון Leadspace** פעיל (מפתח קבוע). סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**. אשר את שני ערכי הקלט על-ידי בחירת **התחבר ל- Leadspace**.

1. בחר **מפה נתונים** ובחר את ערכת הנתונים שברצונך להעשיר בנתוני החברה מתוך Leadspace. באפשרותך לבחור את הישות *לקוח* כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="בחר בין פרופיל לקוח להעשרת פלח.":::

1. לחץ על **הבא** והגדר באילו שדות מהפרופילים המאוחדים שלך יש להשתמש כדי לחפש נתוני חברה תואמים מ- Leadspace. השדה **שם חברה** הוא נדרש. לקבלת דיוק התאמות גבוה יותר, ניתן להוסיף עד שני שדות אחרים, **אתר אינטרנט של חברה** ו **מיקום חברה**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="חלונית מיפוי שדה Leadspace.":::
   
1. בחר **החל** להשלמת מיפוי השדה.

1. בחר **הפעל** כדי להעשיר את פרופילי החברה. משך הזמן הדרוש להעשרה תלוי במספר פרופילי הלקוחות המאוחדים.

## <a name="enrichment-results"></a>תוצאות העשרה

לאחר רענון ההעשרה תוכל לסקור את נתוני החברה שהועשרו לאחרונה מתחת ל[העשרות שלי](enrichment-hub.md). תוכל למצוא את זמן העדכון האחרון ואת מספר הפרופילים המועשרים.

אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.

לקבלת מידע נוסף, ראה [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>השלבים הבאים

בנה על נתוני הלקוחות המועשרים שלך. צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Leadspace, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Leadspace עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]