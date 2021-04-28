---
title: העשרה עם ייבוא מותאם אישית של SPTF
description: מידע כללי אודות העשרת ייבוא מותאם אישית של SPTF.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896282"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>העשרת פרופילי לקוחות עם נתונים מותאמים אישית (Preview)

ייבוא מותאם אישית באמצעות Secure File Transfer Protocol‏ (SFTP) מאפשר לך לייבא נתונים שלא צריכים לעבור את תהליך איחוד הנתונים. זו דרך גמישה, מאובטחת וקלה להכנסת הנתונים שלך. ניתן להשתמש בייבוא מותאם אישית של SFTP בשילוב עם [ייצוא SFTP](export-sftp.md) המאפשר לך לייצא את נתוני פרופיל הלקוח הדרושים להעשרה. לאחר מכן ניתן לעבד את הנתונים, להעשיר אותם ולבצע ייבוא מותאם אישית של SFTP כדי להחזיר את הנתונים המועשרים ליכולת תובנות הקהל של Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>דרישות מוקדמות

כדי לקבוע את תצורת הייבוא המותאם אישית של SFTP, יש לעמוד בתנאים המוקדמים הבאים:

- יש לך את שם הקובץ ואת המיקום (הנתיב) של הקובץ שיש לייבא במארח SFTP.
- קיים קובץ *model.json* שמציין את [סכימת Common Data Model](/common-data-model/) עבור הנתונים שיש לייבא. קובץ זה חייב להיות באותה ספריה שבה נמצא הקובץ לייבוא.
- חיבור SFTP כבר הוגדר על-ידי מנהל מערכת *או* שיש לך הרשאות [מנהל מערכת](permissions.md#administrator). תזדקק לאישורי המשתמש, לכתובת ה- URL ולמספר היציאה עבור מיקום ה- SFTP שממנו ברצונך לייבא נתונים.


## <a name="configure-the-import"></a>קביעת תצורת הייבוא

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. ב **אריח ייבוא מותאם אישית של SFTP**, בחר **העשר את הנתונים שלי** ובחר **תחילת העבודה**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="אריח של ייבוא מותאם אישית של SFTP.":::

1. ‏‏בחר [חיבור](connections.md) מהרשימה הנפתחת. צור קשר עם מנהל מערכת אם אין חיבור זמין. אם אתה מנהל מערכת, באפשרותך ליצור חיבור על-ידי בחירת **הוסף חיבור** ובחירת **ייבוא מותאם אישית של SFTP** מתוך התפריט הנפתח.

1. בחר **התחבר לייבוא מותאם אישית** כדי לאשר את החיבור שנבחר.

1.  בחר **הבא** והזן את **שם הקובץ** ואת **הנתיב** של קובץ הנתונים שברצונך לייבא.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="צילום מסך בעת הזנת מיקום הנתונים.":::

1. בחר **הבא** וספק שם עבור ההעשרה ושם עבור ישות הפלט. 

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

## <a name="configure-the-connection-for-sftp-custom-import"></a>קביעת תצורת החיבור עבור ייבוא מותאם אישית של SFTP 

עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים. בחר **הוסף חיבור** בעת קביעת תצורת העשרה *או* עבור אל **ניהול** > **חיבורים** ובחר **הגדר** באריח 'ייבוא מותאם אישית'.

1. הזן שם עבור החיבור בתיבה **שם תצוגה**.

1. הזן שם משתמש חוקי, סיסמה וכתובת URL של אתר מארח עבור שרת SFTP שהנתונים שיש לייבא שוכנים בו.

1. סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.

1. בחר **אימות** כדי לאמת את התצורה.

1. לאחר השלמת האימות, ניתן לשמור את החיבור על-ידי לחיצה על **שמור**.

> [!div class="mx-imgBorder"]
   > ![דף תצורת החיבור של Experian](media/enrichment-SFTP-connection.png "דף תצורת החיבור של Experian")


## <a name="defining-field-mappings"></a>הגדרת מיפויי שדות 

הספריה המכילה את הקובץ המיועד לייבוא בשרת SPTF מוכרחה גם לכלול קובץ *model.json*. קובץ זה מגדיר את הסכימה לשימוש עבור ייבוא הנתונים. יש להשתמש בסכימה [Common Data Model](/common-data-model/) כדי לציין את מיפוי השדה. דוגמה פשוטה לקובץ model.json נראית כך:

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a>תוצאות העשרה

כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות. ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab). זמן העיבוד יהיה תלוי בגודל הנתונים לייבוא ובחיבור לשרת SPTF.

לאחר סיום תהליך ההעשרה, תוכל לסקור את נתוני ההעשרה המותאמים אישית שלך שיובאו לאחרונה תחת **ההעשרות שלי**. בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.

אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.

## <a name="next-steps"></a>השלבים הבאים

בנה על נתוני הלקוחות המועשרים שלך. צור [פלחים](segments.md), [מדידות](measures.md) ו[יצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
