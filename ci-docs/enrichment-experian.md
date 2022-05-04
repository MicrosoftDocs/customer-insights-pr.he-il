---
title: העשרה באמצעות Experian העשרה של צד שלישי
description: מידע כללי על העשרת צד שלישי של Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f5aa45316b9e0e99c7ba4389353063e9d3ce06c
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646499"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>העשר פרופילי לקוחות באמצעות נתונים דמוגרפיים מ- Experian ‏(Preview)

Experian הינה מובילה עולמית בתחום שירותי דיווח ושיווק של אשראי צרכני ועסקי. באמצעות שירותי העשרת הנתונים של Experian, תוכל לבנות הבנה עמוקה יותר של הלקוחות שלך על-ידי העשרת פרופילי הלקוחות בנתונים דמוגרפיים כמו גודל משק בית, הכנסה ועוד.

## <a name="prerequisites"></a>דרישות מוקדמות

כדי לקבוע את תצורת Experian, יש לקיים את הדרישות המוקדמות הבאות:

- צריך להיות לך מינוי Experian פעיל. כדי לקבל מינוי, [פנה ישירות ל- Experian](https://www.experian.com/marketing-services/contact). [קבל מידע נוסף על Experian העשרת נתונים](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- חיבור Experian כבר הוגדר על-ידי מנהל מערכת *או* שיש לך הרשאות [מנהל מערכת](permissions.md#admin). אתה צריך גם מזהה משתמש, מזהה צד ומספר מודל עבור חשבון Secure Transport‏ (ST) התומך ב- SSH ש- Experian יצרה עבורך.

## <a name="supported-countriesregions"></a>מדינות/אזורים נתמכים

נכון לעכשיו אנחנו תומכים בהעשרת פרופילי לקוחות בארצות הברית בלבד.

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי** באריח Experian.

   > [!div class="mx-imgBorder"]
   > ![אריח Experian.](media/experian-tile.png "Experian tile")
   > 

1. בחר [חיבור](connections.md) מהרשימה הנפתחת. צור קשר עם מנהל מערכת אם אין חיבור זמין. אם אתה מנהל מערכת, אתה יכול ליצור חיבור על ידי בחירת **הוסף חיבור** ובחירת Experian מהרשימה הנפתחת. 

1. בחר **התחבר ל- Experian** כדי לאשר את בחירת החיבור.

1.  בחר **הבא** ובחר את **ערכת נתוני הלקוח** שברצונך להעשיר בנתונים דמוגרפיים מ- Experian. באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. בחר **הבא** והגדר באיזה סוג של שדות מהפרופילים המאוחדים שלך יש להשתמש לצורך חיפוש נתונים דמוגרפיים מתאימים מ- Experian. לפחות אחד מהשדות **שם וכתובת**, **טלפון** או **דואר** נדרש. לקבלת דיוק התאמה גבוה יותר, ניתן להוסיף עד שני שדות אחרים. בחירה זו תשפיע על שדות המיפוי שאליהם יש לך גישה בשלב הבא.

    > [!TIP]
    > תכונות מזהות רבות יותר הנשלחות ל- Experian יניבו, ככל הנראה, שיעור התאמה גבוה יותר.

1. בחר **הבא** כדי להפעיל את מיפוי השדה.

1. הגדר באיזה סוג של שדות מהפרופילים המאוחדים שלך יש להשתמש לצורך חיפוש נתונים דמוגרפיים מתאימים מ- Experian. השדות הנדרשים מסומנים.

1. ספק שם עבור ההעשרה ושם עבור ישות הפלט.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

## <a name="configure-the-connection-for-experian"></a>קבע את תצורת החיבור של Experian 

עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים. בחר **הוסף חיבור** בעת הגדרת העשרה *או* עבור אל **מנהל מערכת** > **חיבורים** ובחר **הגדר** באריח Experian.

1. בחר **תחילת העבודה**.

1. הזן שם עבור החיבור בתיבה **שם תצוגה**.

1. הזן מזהה משתמש, מזהה צד ומספר מודל חוקיים עבור חשבון Experian Secure Transport שלך.

1. סקור את **פרטיות ותאימות נתונים** ותן את הסכמתך על-ידי בחירת **אני מסכים**.

1. בחר **אימות** כדי לאמת את התצורה.

1. לאחר השלמת האימות, בחר **שמור**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian חלונית תצורת החיבור.":::

## <a name="enrichment-results"></a>תוצאות העשרה

כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות. ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab). זמן העיבוד יהיה תלוי בגודל נתוני הלקוחות ובתהליכי ההעשרה שהוגדרו עבור חשבונך על-ידי Experian.

לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**. בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.

אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.

## <a name="next-steps"></a>השלבים הבאים

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים ל- Experian, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעלולים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהוראתך, אבל אתה אחראי להבטיח ש- Experian עומדת בכל התחייבויות הפרטיות והאבטחה שלך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE [footer-include](includes/footer-banner.md)]