---
title: יצירת סביבה חדשה
description: שלבים ליצירת סביבות ב- Dynamics 365 Customer Insights.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304244"
---
# <a name="create-a-new-environment"></a>יצירת סביבה חדשה

לאחר [רכישת רישיון מינוי עבור Dynamics 365 Customer Insights](paid-license.md), מנהל מערכת הכללי של דייר Microsoft 365 מקבל מייל שמזמין אותו ליצור את הסביבה. עבור אל [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) כדי להתחיל. בתרחיש זה, יש להתחיל ב[שלב 1: אספקת מידע בסיסי](#step-1-provide-basic-information).

לאחר יצירת הסביבה הראשונה, מנהל המערכת הכללי של דייר Microsoft 365 יכול [להוסיף משתמשים מהארגון שלו כמנהלי מערכת](permissions.md). מנהלי מערכת אלה יכולו לנהל משתמשים וסביבות. אם הארגון רוכש יותר מרשיון אחד עובר Customer Insights, [צור קשר עם צוות התמיכה שלנו](https://go.microsoft.com/fwlink/?linkid=2079641) כדי להגדיל את מספר הסביבות הזמינות. למידע נוסף על קיבולת ותוספת קיבולת, עיין ב[מדריך הרישוי של Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). לאחר שתהיה לך את היכולת ליצור סביבות נוספות, עבור אל [התחל את תהליך היצירה של הסביבה](#start-the-environment-creation-process).

> [!TIP]
> אם אתה מעוניין לנסות את השירות, ראה [הגדרת סביבת ניסיון](trial-signup.md).

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

[הרשאות מנהל מערכת](permissions.md) ב- Customer Insights

## <a name="start-the-environment-creation-process"></a>התחל את תהליך יצירת הסביבה

1. פתח את בורר הסביבה ובחר **+ חדש**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="בחר בבורר הסביבות.":::

1. בצע את ההוראות בהחוויה המודרכת המתוארת בסעיפים הבאים כדי לספק את כל המידע הנדרש לסביבה חדשה.

## <a name="step-1-provide-basic-information"></a>שלב 1: ספק מידע בסיסי

1. בחר אם ברצונך ליצור סביבה מאפס או להעתיק נתונים מסביבה אחרת. [להעתקת נתונים מסביבה אחרת](#copy-the-environment-configuration) נדרשים שלבים נוספים.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="דו-שיח ליצירת סביבת Customer Insights חדשה.":::

1. ציין את הפרטים הבאים:

   - **שם**: שם לסביבה זו. שדה זה כבר מלא אם העתקת מסביבה קיימת, אך אתה יכול לשנות אותו.
   - **בחירת העסק**: קהל יעד ראשי לסביבה החדשה: צרכנים בודדים (מעסק לצרכן) או [תיקי לקוחות עסקיים](work-with-business-accounts.md) (מעסק לעסק). אם הארגון שלך עושה עסקים בעיקר עם אנשים פרטיים, כגון קמעונאי או בית קפה, בחר צרכנים בודדים. אם קהל הראשי שלך הוא חברות אחרות, כגון יצרן רכב או חברת נייר, בחר חשבונות עסקיים.
   - **סוג**: סוג הסביבה: ייצור או ארגז חול. סביבות ארגז חול אינן מאפשרות רענון נתונים מתוזמן ומיועדות ליישום מוקדם ולבדיקה. סביבות ארגז חול משתמשות בקהל ראשי זהה לזה של סביבת הייצור שנבחרה כעת.
   - **אזור**: האזור שבו השירות נפרס ומתארח. כדי [להשתמש בחשבון Azure Data Lake Storage משלך](own-data-lake-storage.md) אוֹ כדי [להתחבר לארגון Microsoft Dataverse קיים](customer-insights-dataverse.md), סביבת Customer Insights חייבת להיות באותו אזור.

1. בחר **הבא**.

## <a name="step-2-configure-data-storage"></a>שלב 2: קבע תצורה של אחסון נתונים

1. בחר את המקום שבו יאוחסנו נתוני Customer Insights:

   - **אחסון של Customer Insights**: אחסון הנתונים מנוהל אוטומטית. זוהי אפשרות ברירת המחדל. אלא אם קיימות דרישות ספציפיות לאחסון נתונים בחשבון האחסון משלך, אנו ממליצים להשתמש באפשרות זו.
   - **Azure Data Lake Storage**: חשבון  Azure Data Lake Storage משלך לאחסון הנתונים כך שתהיה לך שליטה מלאה על מיקום אחסון הנתונים. בצע את השלבים ב[השתמש בחשבון Azure Data Lake Storage משלך](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="בחר את האפשרות המועדפת לאחסון הנתונים שלך.":::

1. בחר **הבא**.

## <a name="step-3-connect-to-microsoft-dataverse"></a>שלב 3: התחבר אל Microsoft Dataverse

אם יש לך סביבת Dataverse, חבר את Customer Insights. שיתוף נתונים באמצעות Dataverse לישמוש עם אפליקציות עסקיות המבוססות על Dataverse, כמו Dynamics 365 Marketing או אפליקציות מונחות דגמים ב- Power Apps.

1. בצע את השלבים ב[עבודה עם נתוני Customer Insights ב- Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="שיתוף נתונים עם Microsoft Dataverse מופעל אוטומטית עבור סביבות חדשות ברשת.":::

1. בחר **הבא**.

## <a name="step-4-finalize-the-settings"></a>שלב 4: סיים את ההגדרות

עיין בהגדרות המצוינות. כשהכל נראה מוכן, בחר **צור** כדי להגדיר את הסביבה.

כדי לשנות חלק מההגדרות מאוחר יותר, ראה [ניהול סביבות](manage-environments.md).

## <a name="work-with-your-new-environment"></a>עבודה עם הסביבה החדשה

היעזר במאמרים הבאים כדי להתחיל בהגדרת Customer Insights:

- [הוסף משתמשים נוספים והקצה הרשאות](permissions.md).
- [קלוט את מקורות הנתונים](data-sources.md) והרץ אותם באמצעות [תהליך איחוד נתונים](data-unification.md) כדי לקבל [פרופילי לקוחות מאוחדים](customer-profiles.md).
- [העשיר את פרופילי הלקוחות המאוחדים](enrichment-hub.md) או [הפעל מודלים תחזיתיים](predictions-overview.md).
- [צור פלחים](segments.md) כדי לקבץ לקוחות ו[מדידות](measures.md) לסקירת מחווני KPI.
- הגדר [חיבורים](connections.md) ו[פעולות ייצוא](export-destinations.md) כדי לעבד ערכות משנה של נתונים ביישומים אחרים.

## <a name="copy-the-environment-configuration"></a>העתקת תצורת הסביבה

כמנהל מערכת, אם בחרת להעתיק את התצורה מסביבה קיימת, בחר מרשימת כל הסביבות הזמינות בארגון שלך.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="צילום מסך של אפשרויות ההגדרות בהגדרות הסביבה.":::

הגדרות התצורה הבאות מועתקות:

- מקורות נתונים המיובאים באמצעות Power Query
- תצורת איחוד נתונים
- פלחי שוק
- מדידות
- קשרים
- פעילויות
- אינדקס חיפוש וסינון
- פעולות ייצוא
- רענן לוח זמנים
- העשרות
- מודלי חיזוי
- הקצאת תפקידים

### <a name="set-up-a-copied-environment"></a>הגדרת סביבת שהועתקה

כשאתה מעתיק את תצורת הסביבה, תראה הודעת אישור כשהסביבה החדשה נוצרה. עליך לבצע את השלבים הבאים לאישור האישורים.

1. בחר **עבור למקורות נתונים** כדי לראות את רשימת מקורות הנתונים. כל מקורות הנתונים יציגו את המצב **אישורים נדרשים**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="רשימת מקורות הנתונים שהועתקו וזקוקים לאימות.":::

1. ערוך את מקורות הנתונים והזן את האישורים כדי לרענן אותם. יש ליצור מקורות נתונים מתיקיית Common Data Model ו- Dataverse באופן ידני עם אותו שם כמו בסביבת המקור.

1. לאחר רענון מקורות הנתונים, עבור אל **נתונים** > **איחוד**. כאן תוכל למצוא הגדרות מסביבת המקור. ערוך אותן לפי הצורך או בחר **איחוד** > **איחוד פרופילי לקוח ויחסי תלות** כדי להתחיל את תהליך איחוד הנתונים וליצור את ישות הלקוח המאוחדת.

   > [!TIP]
   > עבור תיקי לקוח ואנשי קשר, בחר **איחוד חשבונות** > **איחוד פרופילים ויחסי תלות**.

1. לאחר איחוד הנתונים, עבור אל **מדידות‬** ואל **פלחים** כדי לרענן אותם.

1. עבור אל **מנהל מערכת** > **חיבורים** כדי לאמת מחדש את הקשרים בסביבה החדשה שלך.

1. עבור אל **נתונים** > **העשרה** ו **נתונים** > **יצוא** כדי להפעיל אותם מחדש.

[!INCLUDE [footer-include](includes/footer-banner.md)]
