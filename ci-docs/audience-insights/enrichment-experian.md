---
title: העשרה באמצעות Experian להעשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597788"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>העשר פרופילי לקוחות בדמוגרפיה של Experian ‏(Preview)

Experian הינה מובילה עולמית בתחום שירותי דיווח ושיווק אשראי צרכני ועסקי. באמצעות שירותי העשרת הנתונים של Experian, תוכל לגבש הבנה מעמיקה יותר של לקוחותיך על ידי העשרת פרופילי הלקוחות בנתונים דמוגרפיים כגון גודל משק הבית, הכנסה ועוד.

## <a name="prerequisites"></a>דרישות מוקדמות

לקביעת התצורה של Experian, יש לעמוד בדרישות המקדימות הבאות:

- יש לך מנוי פעיל ל-Experian. כדי לקבל מנוי, [צור קשר עם Experian](https://www.experian.com/marketing-services/contact) בצורה ישירה. [למידע נוסף על העשרת נתונים של Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- יש לך את מזהה משתמש, מזהה צד ומספר דגם עבור חשבון התעבורה המאובטחת (ST) התומך SSH שלך שיצר עבורך Experian.
- יש לך הרשאות [מנהל מערכת](permissions.md#administrator) ב- Audience Insights.

## <a name="configuration"></a>תצורה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשיר את הנתונים שלי** על אריח Experian.

   > [!div class="mx-imgBorder"]
   > ![אריח Experian](media/experian-tile.png "אריח Experian")

1. בחר באפשרות **תחילת העבודה** והזן את מזהה המשתמש, מזהה הצד ומספר הדגם עבור חשבון התעבורה המאובטחת שלך. סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**. לאישור כל יחידות הקלט על ידי בחר **הגש**.

## <a name="map-your-fields"></a>מיפוי השדות שלך

1.  בחר **הוסף נתונים** ובחר את **ערכת נתוני הלקוח** שברצונך להעשיר בנתונים דמוגרפיים מתוך Experian. באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.

1. בחר את המזהים העיקריים שלך מתוך **שם וכתובת**, **דואר אלקטרוני** או **טלפון** כדי לשלוח אותם אל Experian לצורך פענוח זהות.

   > [!TIP]
   > ככל שישלחו יותר תכונות מזהה מפתח ל-Experian כך גדל הסיכוי לשיעור התאמה גבוה יותר.

1. בחר באפשרות **הבא** ומפה את התכונות התואמות מישות הלקוחות המאוחד שלך עבור שדות מזהה המפתח שנבחרו.

1. בחר **הוסף תכונה** כדי למפות תכונות נוספות שברצונך לשלוח ל-Experian.

1.  בחר **שמור** כדי להשלים את מיפוי השדות.

    > [!div class="mx-imgBorder"]
    > ![מיפוי שדות של Experian](media/experian-field-mapping.png "מיפוי שדות של Experian")

## <a name="enrichment-results"></a>תוצאות העשרה

כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות. ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab). זמן העיבוד יהיה תלוי בגודל נתוני הלקוחות שלך ובתהליכי העשרה שהגדרו עבור חשבונך על ידי Experian.

לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**. בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.

אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.

## <a name="next-steps"></a>השלבים הבאים

בנה על נתוני הלקוחות המועשרים שלך. צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Experian, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Experian עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]