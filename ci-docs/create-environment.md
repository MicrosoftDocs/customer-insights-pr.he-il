---
title: 'כיצד: ליצור סביבה חדשה'
description: שלבים ליצירת סביבות ב- Dynamics 365 Customer Insights.
ms.date: 05/31/2022
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
ms.openlocfilehash: 875cbbd095dfd239ab83c1c80db28ea7c0a04ed0
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245558"
---
# <a name="how-to-create-a-new-environment"></a>כיצד: ליצור סביבה חדשה

לאחר [רכישת רישיון מינוי עבור Dynamics 365 Customer Insights](paid-license.md), מנהל מערכת הכללי של דייר Microsoft 365 מקבל מייל שמזמין אותו ליצור את הסביבה. עבור אל [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) כדי להתחיל. בתרחיש זה, אפשר לעבור ישירות אל [שלב 1: ספק מידע בסיסי](#step-1-provide-basic-information).

לאחר יצירת הסביבה הראשונה, מנהל המערכת הכללי של דייר Microsoft 365 יכול [להוסיף משתמשים מהארגון שלו כמנהלי מערכת](permissions.md). בהמשך, מנהלי מערכת אלה יכולים לנהל משתמשים וסביבות. אם הארגון רוכש יותר מרשיון אחד עובר Customer Insights, [צור קשר עם צוות התמיכה שלנו](https://go.microsoft.com/fwlink/?linkid=2079641) כדי להגדיל את מספר הסביבות הזמינות. למידע נוסף על קיבולת ותוספת קיבולת, עיין ב[מדריך הרישוי של Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> אם אתה מעוניין לנסות את השירות, ראה [הגדרת סביבת ניסיון](trial-signup.md).

## <a name="prerequisites"></a>דרישות מוקדמות

נדרשות [הרשאות מנהל מערכת](permissions.md) ב- Customer Insights כדי ליצור או לנהל סביבות.

## <a name="start-the-environment-creation-process"></a>התחל את תהליך יצירת הסביבה

1. פתח את בורר הסביבה ובחר **+ חדש**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="בחר בבורר הסביבות.":::

1. בצע את ההוראות בהחוויה המודרכת המתוארת בסעיפים הבאים כדי לספק את כל המידע הנדרש לסביבה חדשה. אם הגדרת סביבה קודם לכן, תוכל גם [להעתיק את התצורה](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>שלב 1: ספק מידע בסיסי

בשלב **מידע בסיסי**, בחר אם ברצונך ליצור סביבה מאפס או [להעתיק נתונים מסביבה אחרת](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="דו-שיח ליצירת סביבת Customer Insights חדשה.":::

ציין את הפרטים הבאים:

- **שם**: השם עבור סביבה זו. שדה זה כבר מלא אם העתקת מסביבה קיימת, אך אתה יכול לשנות אותו. אם יש לך יותר מסביבת עבודה אחת, עליך להעניק לכל אחת מהן שם תצוגה שניתן לזהות בקלות.
- **בחר בעסק שלך**: בחר את קהל הראשי עבור הסביבה החדשה. באפשרותך לעבוד עם צרכנים בודדים (עסק לצרכן – B-to-C) או [תיקי לקוחות עסקיים](work-with-business-accounts.md) (עסק לעסק – B-to-B). אם הארגון שלך עושה עסקים בעיקר עם אנשים פרטיים, כגון קמעונאי או בית קפה, בחר צרכנים בודדים. במקרה שקהל העיקרי שלך הוא חברות אחרות, כגון יצרן רכב או חברת נייר, בחר חשבונות עסקיים.
- **סוג**: בחר אם ברצונך ליצור סביבת ייצור או ארגז חול. סביבות ארגז חול אינן מאפשרות רענון נתונים מתוזמן ומיועדות ליישום מוקדם ולבדיקה. סביבות ארגז חול משתמשות בקהל ראשי זהה לזה של סביבת הייצור שנבחרה כעת.
- **אזור**: האזור שבו השירות נפרס ומתארח. כדי [להשתמש בחשבון Azure Data Lake Storage משלך](own-data-lake-storage.md) אוֹ כדי [להתחבר לארגון Microsoft Dataverse קיים](customer-insights-dataverse.md), סביבת Customer Insights חייבת להיות באותו אזור.

## <a name="step-2-configure-data-storage"></a>שלב 2: קבע תצורה של אחסון נתונים

בשלב **אחסון נתונים**, בחר היכן לאחסן את הנתונים של Customer Insights.

באפשרותך לבחור מבין שתי אפשרויות:

- **אחסון של Customer Insights**: אחסון הנתונים מנוהל על ידי צוות Customer Insights. זוהי אפשרות ברירת המחדל. אלא אם קיימות דרישות ספציפיות לאחסון נתונים בחשבון האחסון משלך, אנו ממליצים להשתמש באפשרות זו.
- **Azure Data Lake Storage**: ציין את חשבון ה- Azure Data Lake Storage שלך לאחסון הנתונים כך שתהיה לך שליטה מלאה על מיקום אחסון הנתונים. למידע נוסף, ראה [תשתמש בחשבון Azure Data Lake Storage משלך](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="בחר את האפשרות המועדפת לאחסון הנתונים שלך.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>שלב 3: התחבר אל Microsoft Dataverse

השלב של **Microsoft Dataverse** מאפשר לך לחבר את Customer Insights לסביבת Dataverse. שיתוף נתונים באמצעות Dataverse לישמוש עם אפליקציות עסקיות המבוססות על Dataverse, כמו Dynamics 365 Marketing או אפליקציות מונחות דגמים ב- Power Apps.

השאר שדה זה ריק אם אין לך סביבת Dataverse משלך ואנחנו ניצור לך אחת.

למידע נוסף, ראה [עבודה עם נתוני Customer Insights ב- Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="שיתוף נתונים עם Microsoft Dataverse מופעל אוטומטית עבור סביבות חדשות ברשת.":::

### <a name="step-4-finalize-the-settings"></a>שלב 4: סיים את ההגדרות

בשלב **סקירה**, עבור על כל ההגדרות שצוינו. כשהכל נראה מוכן, בחר **צור** כדי להגדיר את הסביבה.

תוכל לשנות חלק מההגדרות בשלב מאוחר יותר. לקבלת מידע נוסף, ראה [ניהול סביבות](manage-environments.md).

## <a name="work-with-your-new-environment"></a>עבודה עם הסביבה החדשה

היעזר במאמרים הבאים כדי להתחיל בהגדרת Customer Insights:

- [הוסף משתמשים נוספים והקצה הרשאות](permissions.md).
- [קלוט את מקורות הנתונים](data-sources.md) והרץ אותם באמצעות [תהליך איחוד נתונים](data-unification.md) כדי לקבל [פרופילי לקוחות מאוחדים](customer-profiles.md).
- [העשיר את פרופילי הלקוחות המאוחדים](enrichment-hub.md) או [הפעל מודלים תחזיתיים](predictions-overview.md).
- [צור פלחים](segments.md) כדי לקבץ לקוחות ו[מדידות](measures.md) לסקירת מחווני KPI.
- הגדר [חיבורים](connections.md) ו[פעולות ייצוא](export-destinations.md) כדי לעבד ערכות משנה של נתונים ביישומים אחרים.

## <a name="copy-the-environment-configuration"></a>העתקת תצורת הסביבה

כמנהל מערכת, אתה יכול לבחור להעתיק את התצורה מסביבה קיימת בעת יצירת סביבה חדשה.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="צילום מסך של אפשרויות ההגדרות בהגדרות הסביבה.":::

תראה רשימה של כל הסביבות הזמינות בארגון שלך, שממנה אתה יכול להעתיק נתונים.

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

## <a name="set-up-a-copied-environment"></a>הגדרת סביבת שהועתקה

כאשר אתה מעתיק את תצורת הסביבה, אתה צריך לעבור כמה שלבים נוספים כדי לאשר את האישורים:

- פרופילי לקוחות. ראשית, אמת והטמע את מקורות הנתונים שלך והפעל את איחוד הנתונים כדי ליצור מחדש את פרופילי הלקוחות.
- אישורים של מקור נתונים. עליך לספק את האישורים עבור כל מקור נתונים כדי לאמת ולרענן את מקורות הנתונים באופן ידני.
- מקורות נתונים מתיקיית Common Data Model ומ- Dataverse. אתה צריך ליצור את מקורות הנתונים האלה באופן ידני עם אותו שם כמו בסביבת המקור.
- סודות חיבור המשמשים לפעולות ייצוא והעשרה. עליך לאמת מחדש את החיבורים ולאחר מכן להפעיל מחדש העשרות וייצוא.

תראה הודעת אישור כאשר הסביבה המועתקת נוצרה. בחר **עבור למקורות נתונים** כדי לראות את רשימת מקורות הנתונים.

כל מקורות הנתונים יציגו את המצב **אישורים נדרשים**. ערוך את מקורות הנתונים והזן את האישורים כדי לרענן אותם.

:::image type="content" source="media/data-sources-copied.png" alt-text="רשימת מקורות הנתונים שהועתקו וזקוקים לאימות.":::

לאחר רענון מקורות הנתונים, עבור אל **נתונים** > **איחוד**. כאן תוכל למצוא הגדרות מסביבת המקור. ערוך אותן לפי הצורך או בחר **הפעל** כדי להתחיל את תהליך איחוד הנתונים וליצור את ישות הלקוח המאוחדת.

לאחר איחוד הנתונים, עבור אל **מדידות‬** ואל **פלחים** כדי לרענן גם אותם.

לפני שתפעיל מחדש את הייצוא וההעשרות, עבור אל **מנהל מערכת** > **חיבורים** כדי לאמת מחדש את החיבורים בסביבה החדשה שלך.

[!INCLUDE [footer-include](includes/footer-banner.md)]
