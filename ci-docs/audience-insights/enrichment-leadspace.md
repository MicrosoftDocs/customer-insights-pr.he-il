---
title: העשרת פרופילי החברה באמצעות Leadspace העשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895914"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>העשרה של פרופילי חברות באמצעות Leadspace (תצוגה מקדימה)

Leadspace היא חברה למדעי נתונים המספקת פלטפורמת נתוני לקוחות B2B. היא מאפשרת ללקוחות עם פרופילי לקוחות אחידים לחברות להעשיר את הנתונים שלהם. העשרות כוללות תכונות נוספות כגון גודל חברה, מיקום, תעשייה ועוד.

## <a name="prerequisites"></a>דרישות מוקדמות

כדי להגדיר את Leadspace, הדרישות המוקדמות הבאות צריכות להתקיים:

- יש לך רישיון Leadspace פעיל.
- יש לך [פרופילי לקוחות מאוחדים](customer-profiles.md) עבור חברות.
- חיבור Leadspace כבר הוגדר על-ידי מנהל מערכת או שיש לך הרשאות [מנהל מערכת](permissions.md#administrator) ואת ה"מפתח התמידי" (מכונה **אסימון Leadspace**). צור קשר ישירות עם [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) לקבלת פרטים על המוצר שלהם.

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. ב- audience insights, עבור אל **נתונים** > **העשרה**.

1. בחר **העשר את הנתונים שלי** באריח Leadspace ובחר **תחילת העבודה**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="צילום מסך של אריח Leadspace.":::

1. ‏‏בחר [חיבור](connections.md) מהרשימה הנפתחת. צור קשר עם מנהל מערכת אם אין חיבור זמין. אם אתה מנהל מערכת, באפשרותך ליצור חיבור על-ידי בחירת **הוסף חיבור** ובחירת **Leadspace**. 

1. בחר **התחבר ל- Leadspace** כדי לאשר את החיבור.

1. בחר **הבא** ובחר את **ערכת הנתונים של הלקוח** שברצונך להעשיר בנתוני חברה מתוך Leadspace. באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. בחר **הבא** והגדר אילו שדות מתוך הפרופילים המאוחדים של משמשים כדי לחפש נתוני חברה מתאימים מ- Leadspace. השדה **שם חברה** הוא נדרש. לקבלת דיוק התאמות גבוה יותר, ניתן להוסיף עד שני שדות אחרים, **אתר אינטרנט של חברה** ו **מיקום חברה**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="חלונית מיפוי שדה Leadspace.":::

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. ספק שם עבור ההעשרה ובחר **שמור העשרה** לאחר סקירת האפשרויות שלך.


## <a name="configure-the-connection-for-leadspace"></a>קביעת תצורת החיבור עבור Leadspace 

עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים. בחר **הוסף חיבור** בעת קביעת תצורת העשרה *או* עבור אל **ניהול** > **חיבורים** ובחר **הגדר** באריח Leadspace.

1. בחר **תחילת העבודה** 

1. הזן שם עבור החיבור בתיבה **שם תצוגה**.

1. ספק אסימון Leadspace חוקי.

1. סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**

1. בחר **אימות** כדי לאמת את התצורה.

1. לאחר השלמת האימות, בחר **שמור**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="דף תצורת החיבור של Leadspace.":::

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
