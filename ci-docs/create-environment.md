---
title: יצירת סביבות ב- Customer Insights
description: שלבים ליצירת סביבות עם מנוי מורשה עבור Dynamics 365 Customer Insights.
ms.date: 04/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0efda9d2997bcfd069b6d2445b69d159d7d3e59b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646618"
---
# <a name="create-an-environment-in-customer-insights"></a>יצירת סביבה ב- Customer Insights

מאמר זה מסביר כיצד ליצור סביבה חדשה לאחר שהארגון שלך רכש מינוי Dynamics 365 Customer Insights. 

ארגונים יכולים ליצור סביבות מרובות עבור כל רישיון Customer Insights. אם הארגון רוכש יותר מרשיון אחד, [צור קשר עם צוות התמיכה שלנו](https://go.microsoft.com/fwlink/?linkid=2079641) כדי להגדיל את מספר הסביבות הזמינות. למידע נוסף על קיבולת ותוספת קיבולת, עיין ב[מדריך הרישוי של Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> אם אתה מעוניין לנסות את השירות, ראה [הגדרת סביבת ניסיון](trial-signup.md).

## <a name="create-a-new-environment"></a>יצירת סביבה חדשה

לאחר רכישת רישיון למינוי על Customer Insights, מנהל המערכת הגלובלי של דייר Microsoft 365 יקבל הודעת דואר אלקטרוני שתזמין אותו ליצור את הסביבה. עבור אל [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) כדי להתחיל. 

חוויה מודרכת מסייעת לבצע את השלבים לאיסוף כל המידע הנדרש עבור סביבה חדשה. נדרשות [הרשאות מנהל מערכת](permissions.md) ב- Customer Insights כדי ליצור או לנהל סביבות.

1. פתח את בורר הסביבה ובחר **+ חדש**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="בחר בבורר הסביבות.":::

1. עקוב אחר החוויה המודרכת המתוארת בסעיפים הבאים.

### <a name="step-1-provide-environment-information"></a>שלב 1: ספק מידע על הסביבה

בשלב **מידע בסיסי**, בחר אם ברצונך ליצור סביבה מאפס או [להעתיק נתונים מסביבה אחרת](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="דו-שיח ליצירת סביבת Customer Insights חדשה.":::

ציין את הפרטים הבאים:
   - **שם**: השם עבור סביבה זו. שדה זה כבר מלא אם העתקת מסביבה קיימת, אך אתה יכול לשנות אותו.
   - **בחר בעסק שלך**: בחר את קהל הראשי עבור הסביבה החדשה. באפשרותך לעבוד עם צרכנים בודדים (עסק לצרכן – B-to-C) או [תיקי לקוחות עסקיים](work-with-business-accounts.md) (עסק לעסק – B-to-B).
   - **סוג**: בחר אם ברצונך ליצור סביבת ייצור או ארגז חול. סביבות ארגז חול אינן מאפשרות רענון נתונים מתוזמן ומיועדות ליישום מוקדם ולבדיקה. סביבות ארגז חול משתמשות בקהל ראשי זהה לזה של סביבת הייצור שנבחרה כעת.
   - **אזור**: האזור שבו השירות נפרס ומתארח.

### <a name="step-2-configure-data-storage"></a>שלב 2: קבע תצורה של אחסון נתונים

בשלב **אחסון נתונים**, בחר היכן לאחסן את הנתונים של Customer Insights.

יהיו לך שתי אפשרויות: **אחסון של Customer Insights** (אגם נתונים של ‏Azure המנוהל על-ידי צוות Customer Insights) ו- **Azure Data Lake Storage** (Azure Data Lake Storage משלך). כברירת מחדל, אפשרות האחסון של Customer Insights נבחרת.

:::image type="content" source="media/data-storage-environment.png" alt-text="בחר את Azure Data Lake Storage כדי לאחסן את הנתונים שלך.":::

בכך שאתה שומר נתונים ב- Azure Data Lake Storage, אתה מסכים לכך שהנתונים יועברו ויישמרו במיקום הגיאוגרפי המתאים עבור אותו חשבון אחסון של Azure. מיקום זה עשוי להיות שונה מהמיקום שבו הנתונים מאוחסנים ב- Dynamics 365 Customer Insights. קבל מידע נוסף ב[מרכז יחסי האמון של Microsoft](https://www.microsoft.com/trust-center).

> [!NOTE]
> Customer Insights תומך כעת בפריטים הבאים:
> - ישויות מעובדות מזרימות נתונים של Power BI המאוחסנות ב- Data Lake מנוהל של Microsoft Dataverse.  
> - חשבונות Azure Data Lake Storage מאותו אזור של Azure שבחרת בעת יצירת הסביבה.
> - חשבונות Azure Data Lake Storage שהם Gen2 ואשר *מרחב השמות ההיררכי*  שלהם מופעל. חשבונות Azure Data Lake Gen1 storage לא נתמכים.

בשביל אפשרות ה- Azure Data Lake Storage, תוכל לבחור בין אפשרות מבוססת משאבים לבין אפשרות מבוססת מנוי לאימות. לקבלת מידע נוסף, ראה [התחברות לחשבון Azure Data Lake Storage באמצעות מנהל שירות של Azure](connect-service-principal.md). מיכל בשם `customerinsights` חייב להתקיים בחשבון האחסון.

כאשר תהליכי מערכת, כמו עיבוד נתונים, מסתיימים, המערכת יוצרת תיקיות מתאימות בחשבון האחסון שציינת. קבצי נתונים וקבצי *model.json* נוצרים ונוספים לתיקיות בהתאם לשם התהליך.

אם אתה יוצר סביבות מרובות של Customer Insights ובוחר לשמור את ישויות הפלט מסביבות אלה בחשבון האחסון שלך, Customer Insights יוצר תיקיות נפרדות לכל סביבה עם `ci_environmentID` בגורם המכיל.

### <a name="step-3-connect-to-microsoft-dataverse"></a>שלב 3: התחבר אל Microsoft Dataverse
   
השלב של **Microsoft Dataverse** מאפשר לך לחבר את Customer Insights לסביבת Dataverse.

ספק סביבת Microsoft Dataverse משלך לשיתוף נתונים (פרופילים ותובנות) עם אפליקציות עסקיות המבוססות על Dataverse, כמו Dynamics 365 Marketing או אפליקציות מונחות דגמים ב- Power Apps. השאר שדה זה ריק אם אין לך סביבת Dataverse משלך ואנחנו נספק לך אחת.

חיבור אל סביבת Dataverse משלך גם מאפשר לך [לקלוט נתונים ממקורות נתונים מקומיים באמצעות זרימות נתונים ושערים של Power Platform](data-sources.md#add-data-from-on-premises-data-sources). אפשר גם להשתמש ב- [דגמי חיזוי מוכנים לשימוש](predictions-overview.md?tabs=b2c#out-of-box-models) על ידי חיבור לסביבת Dataverse.

> [!IMPORTANT]
> 1. Customer Insights ו- Dataverse צריכים להיות באותו אזור כדי לאפשר שיתוף נתונים.
> 1. נדרש לך תפקיד מנהל מערכת גלובלי בסביבת Dataverse. ודא אם [סביבת Dataverse זו משוייכת](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) לקבוצות אבטחה מסוימות וודא שאתה מתווסף לקבוצות אבטחה אלה.
> 1. אף סביבה קיימת של Customer Insights לא משויכת לסביבת Dataverse זו. למד כיצד [להסיר חיבור קיים לסביבת Dataverse](manage-environments.md#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="שיתוף נתונים עם Microsoft Dataverse מופעל אוטומטית עבור מופעים חדשים ברשת.":::

למידע נוסף על הפיכת שיתוף נתונים מ- Azure Data Lake Storage משלך באמצעות Microsoft Dataverse לזמין, ראה [ התחברות ל- Microsoft Dataverse](manage-environments.md#connect-to-microsoft-dataverse).

Customer Insights אינו תומך בתרחישי שיתוף הנתונים הבאים:
- אם תאפשר שיתוף נתונים עם אגם נתונים מנוהל של Dataverse, לא תוכל [ליצור ערכים חזויים או חסרים בישות](predictions.md).

### <a name="step-4-finalize-the-settings"></a>שלב 4: סיים את ההגדרות

בשלב **סקירה**, עבור אל כל ההגדרות שצוינו. כשהכל נראה מוכן, בחר **צור** כדי להגדיר את הסביבה. 

תוכל גם לשנות את רוב ההגדרות בשלב מאוחר יותר. לקבלת מידע נוסף, ראה [ניהול סביבות](manage-environments.md).

## <a name="work-with-your-new-environment"></a>עבודה עם הסביבה החדשה

היעזר במאמרים הבאים כדי להתחיל בהגדרת Customer Insights: 

- [הוסף משתמשים נוספים והקצה הרשאות](permissions.md).
- [קלוט את מקורות הנתונים](data-sources.md) והרץ אותם באמצעות [תהליך איחוד נתונים](data-unification.md) כדי לקבל [פרופילי לקוחות מאוחדים](customer-profiles.md).
- [העשיר את פרופילי הלקוחות המאוחדים](enrichment-hub.md) או [הפעל מודלים תחזיתיים](predictions-overview.md).
- [צור פלחים](segments.md) כדי לקבץ לקוחות ו[מדידות](measures.md) לסקירת מחווני KPI.
- הגדר [חיבורים](connections.md) ו[פעולות ייצוא](export-destinations.md) כדי לעבד ערכות משנה של נתונים ביישומים אחרים.