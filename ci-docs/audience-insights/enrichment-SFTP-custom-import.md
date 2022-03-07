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
ms.openlocfilehash: b67aa7477033222b0bc9512a962a1580edd973b4882ce925620ff5ec14f83fe3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032713"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>העשרת פרופילי לקוחות עם נתונים מותאמים אישית (Preview)

ייבוא מותאם אישית באמצעות Secure File Transfer Protocol‏ (SFTP) מאפשר לך לייבא נתונים שלא צריכים לעבור את תהליך איחוד הנתונים. זו דרך גמישה, מאובטחת וקלה להכנסת הנתונים שלך. ניתן להשתמש בייבוא מותאם אישית של SFTP בשילוב עם [ייצוא SFTP](export-sftp.md) המאפשר לך לייצא את נתוני פרופיל הלקוח הדרושים להעשרה. לאחר מכן ניתן לעבד ולהעשיר את הנתונים, וניתן להשתמש ביבוא מותאם אישית באמצעות SFTP כדי להחזיר את הנתונים המועשרים ליכולת התובנות לגבי קהלים של Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>דרישות מוקדמות

כדי לקבוע את תצורת הייבוא המותאם אישית של SFTP, יש לעמוד בתנאים המוקדמים הבאים:

- יש לך את שם הקובץ ואת המיקום (הנתיב) של הקובץ שיש לייבא למארח SFTP.
- קיים קובץ *model.json* שמציין את [סכימת Common Data Model](/common-data-model/) עבור הנתונים שיש לייבא. קובץ זה חייב להיות באותה ספריה שבה נמצא הקובץ לייבוא.
- חיבור SFTP כבר הוגדר על-ידי מנהל מערכת *או* שיש לך הרשאות [מנהל מערכת](permissions.md#administrator). תזדקק לאישורי המשתמש, לכתובת ה- URL ולמספר היציאה עבור מיקום ה- SFTP שממנו ברצונך לייבא נתונים.


## <a name="configure-the-import"></a>קביעת תצורת הייבוא

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. ב **אריח ייבוא מותאם אישית של SFTP**, בחר **העשר את הנתונים שלי** ובחר **תחילת העבודה**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="אריח של ייבוא מותאם אישית של SFTP.":::

1. בחר [חיבור](connections.md) מהרשימה הנפתחת. צור קשר עם מנהל מערכת אם אין חיבור זמין. אם אתה מנהל מערכת, אתה יכול ליצור חיבור על ידי בחירת **הוסף חיבור** ובחירת **ייבוא מותאם אישית באמצעות SFTP** מהרשימה הנפתחת.

1. בחר **התחבר לייבוא מותאם אישית** כדי לאשר את החיבור שנבחר.

1.  בחר **הבא** והיכנס אל **נתיב** ואל **שם הקובץ** של קובץ הנתונים שברצונך לייבא.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="צילום מסך בעת הזנת מיקום הנתונים.":::

1. בחר **הבא** וספק שם עבור ההעשרה ושם עבור ישות הפלט. 

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

## <a name="configure-the-connection-for-sftp-custom-import"></a>קביעת תצורת החיבור עבור ייבוא מותאם אישית של SFTP 

עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים. בחר **הוסף חיבור** בעת קביעת תצורת העשרה *או* עבור אל **ניהול** > **חיבורים** ובחר **הגדר** באריח 'ייבוא מותאם אישית'.

1. הזן שם עבור החיבור בתיבה **שם תצוגה**.

1. הזן שם משתמש, סיסמה וכתובת אתר תקפים עבור שרת ה- SFTP שבו נמצאים הנתונים שיש לייבא.

1. סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.

1. בחר **אימות** כדי לאמת את התצורה.

1. לאחר השלמת האימות, ניתן לשמור את החיבור על ידי בחירת **שמור**.

   > [!div class="mx-imgBorder"]
   > ![Experian דף תצורת החיבור.](media/enrichment-SFTP-connection.png "Experian דף תצורת חיבור")


## <a name="defining-field-mappings"></a>הגדרת מיפויי שדות 

הספריה המכילה את הקובץ המיועד לייבוא בשרת SPTF מוכרחה גם לכלול קובץ *model.json*. קובץ זה מגדיר את הסכימה לשימוש עבור ייבוא הנתונים. על הסכימה להשתמש ב[Common Data Model](/common-data-model/) כדי לציין את מיפוי השדות. דוגמה פשוטה לקובץ model.json נראית כך:

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

בנה על נתוני הלקוחות המועשרים שלך. צור [פלחים](segments.md) ו[מדידות](measures.md), ו[יצא את הנתונים](export-destinations.md) כדי להעניק ללקוחות שלך חוויות מותאמות אישית.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
