---
title: יצירה והגדרה של רישיון Customer Insights בתשלום
description: שלבים כדי לקבל מינוי מורשה ל- Dynamics 365 Customer Insights ולהגדיר אותו.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034453"
---
# <a name="get-started-with-a-paid-subscription"></a>תחילת העבודה עם מינוי בתשלום

מאמר זה מסביר כיצד ליצור סביבה חדשה לאחר שהארגון שלך רכש מינוי Dynamics 365 Customer Insights. אם ברצונך לרכוש Customer Insights, אפשרויות יצירת הקשר שלנו מופיעות באתר [Dynamics 365 Customer Insights ](https://dynamics.microsoft.com/ai/customer-insights/). 

אם אתה מעוניין לנסות את השירות ואת התכונות, ראה [הגדרת סביבת ניסיון](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>יצירת סביבה בארגון קיים

לאחר רכישת רישיון מינוי ל- Customer Insights, המנהל הכללי של דייר Microsoft 365 יקבל דואר שמזמין אותו ליצור את הסביבה. עבור אל [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) כדי להתחיל. 

רישיון Customer Insights לא ניתן לכל משתמש בנפרד, כך שהוא לא יופיע באזור הרישיונות. אם אתה מחפש את הרישיון במרכז הניהול של Microsoft 365, עבור אל **המוצרים שלך**. 

> [!NOTE]
> ארגונים יכולים ליצור *שתי* סביבות עבור כל רישיון Customer Insights. אם הארגון שלך רוכש יותר מרישיון אחד, [צור קשר עם צוות התמיכה שלנו](https://go.microsoft.com/fwlink/?linkid=2079641) כדי להגדיל את מספר הסביבות הזמינות. למידע נוסף אל קיבולת וקיבולת הרחבה, הורד את [מדריך הרישוי של Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

כדי ליצור סביבה:

1. בדו-שיח **צור סביבה**, בחר **סביבה חדשה**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="דו-שיח ליצירת סביבת Customer Insights חדשה.":::

   אנחנו ממליצים להתחיל בהגדרת סביבה מאפס. עם זאת, אם אתה מנהל מערכת או חבר בסביבת ניסיון, תוכל [להעתיק נתונים מסביבה אחרת](manage-environments.md#copy-the-environment-configuration), על-ידי בחירת **העתקה מסביבה קיימת**. תראה רשימה של כל הסביבות הזמינות בארגון שלך, שממנה אתה יכול להעתיק נתונים.

1. ציין את הפרטים הבאים:
   - **שם**: השם עבור סביבה זו. שדה זה כבר מלא אם העתקת מסביבה קיימת, אך אתה יכול לשנות אותו.
   - **אזור**: האזור שבו השירות נפרס ומתארח.
   - **סוג**: בחר אם ברצונך ליצור סביבת ייצור או ארגז חול. סביבות ארגז חול אינן מאפשרות רענון נתונים מתוזמן ומיועדות ליישום מוקדם ולבדיקה.
   
1. באופן אופציונלי, באפשרותך לבחור **הגדרות מתקדמות**:

   - **שמור את כל הנתונים ב-**: מציין היכן ברצונך לאחסן את נתוני הפלט שנוצרים מ- Customer Insights. יהיו לך שתי אפשרויות: **אחסון של Customer Insights** (‏Azure Data Lake המנוהל על-ידי צוות Customer Insights) ו- **Azure Data Lake Storage** (Azure Data Lake Storage משלך). כברירת מחדל, אפשרות האחסון של Customer Insights נבחרת.

     > [!NOTE]
     > על-ידי שמירת הנתונים ב- Azure Data Lake Storage, אתה מסכים שהנתונים יועברו ויאוחסנו במיקום הגיאוגרפי המתאים עבור חשבון אחסון זה של Azure, שעשוי להיות שונה מהמקום שבו הנתונים מאוחסנים ב- Dynamics 365 Customer Insights. [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center)
     >
     > נכון לעכשיו, ישויות שנקלטו מזרימות נתונים של Power BI מאוחסנות ב- Data Lake מנוהל של Microsoft Dataverse. 
     > 
     > אנו תומכים בחשבונות Azure Data Lake Storage בלבד שמגיעים מאותו אזור Azure שבחרת בעת יצירת הסביבה. 
     > 
     > אנו תומכים בחשבונות Azure Data Lake Storage בלבד שמופעל בהם מרחב שמות היררכי.


   - בשביל אפשרות ה- Azure Data Lake Storage, תוכל לבחור בין אפשרות מבוססת משאבים לבין אפשרות מבוססת מנוי לאימות. לקבלת מידע נוסף, ראה [חיבור audience insights לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות של Azure](connect-service-principal.md). לא ניתן לשנות את שם **הגורם המכיל** והשם יהיה `customerinsights`.
   
   - אם ברצונך להשתמש ב [מודלים מוכנים לשימוש](predictions-overview.md#out-of-box-models), הגדר שיתוף נתונים עם Microsoft Dataverse, או אפשר קליטת נתונים ממקורות נתונים מקומיים, הזן את כתובת ה- URL של סביבת Microsoft Dataverse תחת **הגדר שיתוף נתונים עם Microsoft Dataverse ואפשר יכולות נוספות**. בחר **הפוך שיתוף נתונים לזמין** כדי לשתף נתוני פלט של Customer Insights עם Data Lake מנוהל של Microsoft Dataverse.

     > [!NOTE]
     > - שיתוף נתונים עם Data Lake מנוהל של Microsoft Dataverse אינו נתמך כעת כשאתה שומר את כל הנתונים ב- Azure Data Lake Storage שלך.
     > - [חיזוי של ערכים חסרים בישות](predictions.md) אינו נתמך כעת כשאתה הופך לזמין שיתוף נתונים עם Data Lake מנוהל של Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="אפשרויות קביעת תצורה כדי להפוך שיתוף נתונים לזמין עם Microsoft Dataverse.":::

   עם השלמת תהליכי מערכת כגון קליטת נתונים, המערכת תיצור תיקיות מתאימות בחשבון האחסון שציינת. קובצי נתונים וקובצי model.json נוצרים ומתווספים לתיקיות בהתאם לשם התהליך.

   אם אתה יוצר סביבות מרובות של Customer Insights ובוחר לשמור את ישויות הפלט מסביבות אלה בחשבון האחסון שלך, תיקיות נפרדות ייווצרו עבור כל סביבה עם ci_<environmentid> בגורם המכיל.

1. בחר **צור** כדי להגדיר את הסביבה. 

## <a name="configure-an-environment"></a>קביעת התצורה של סביבה

עיין במאמרים הבאים שיעזרו לך להתחיל לקבוע את תצורת Customer Insights. 

- [הוסף משתמשים נוספים והקצה הרשאות](permissions.md).
- [קלוט את מקורות הנתונים](data-sources.md) והרץ אותם באמצעות [תהליך איחוד נתונים](data-unification.md) כדי לקבל [פרופילי לקוחות מאוחדים](customer-profiles.md).
- [העשיר את פרופילי הלקוחות המאוחדים](enrichment-hub.md) או [הפעל מודלים תחזיתיים](predictions-overview.md).
- צור [מקטעים](segments.md) כדי לקבץ לקוחות ומחווני KPI של סקירת [מדידות](measures.md).
- הגדר [חיבורים](connections.md) ו[פעולות ייצוא](export-destinations.md) כדי לעבד ערכות משנה של נתונים ביישומים אחרים.
