---
title: העשרת פרופילי לקוחות באמצעות יבוא מותאם אישית של SFTP ‏(Preview)
description: מידע כללי אודות העשרת ייבוא מותאם אישית של SPTF.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 81ef6c62240e26cb5c9475e6306e08edc7e5eb31
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195797"
---
# <a name="enrich-customer-profiles-with-sftp-custom-import-preview"></a>העשרת פרופילי לקוחות באמצעות יבוא מותאם אישית של SFTP ‏(Preview)

ייבוא מותאם אישית באמצעות Secure File Transfer Protocol‏ (SFTP) מאפשר לך לייבא נתונים שלא צריכים לעבור את תהליך איחוד הנתונים. זו דרך גמישה, מאובטחת וקלה להכנסת הנתונים שלך. ניתן להשתמש בייבוא מותאם אישית של SFTP בשילוב עם [ייצוא SFTP](export-sftp.md) המאפשר לך לייצא את נתוני פרופיל הלקוח הדרושים להעשרה. לאחר מכן ניתן לעבד ולהעשיר את הנתונים, וניתן להשתמש בייבוא SFTP מותאם אישית כדי להחזיר את הנתונים המועשרים אל Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>דרישות מוקדמות

- שם הקובץ והמיקום (נתיב) של הקובץ לייבוא במארח ה-SFTP ידועים.

- קובץ *model.json* המציין את סכימת Common Data Model עבור הנתונים המיועדים ליבוא זמין. קובץ זה חייב להיות באותה ספריה שבה נמצא הקובץ לייבוא.

- [חיבור](connections.md)SFTP[ מוגדר](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>דוגמה לקובץ סכימה

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>קביעת תצורת החיבור עבור ייבוא מותאם אישית של SFTP

עליך להיות [מנהל מערכת](permissions.md#admin) ב- Customer Insights וקבל את אישורי המשתמש, כתובת ה- URL ומספר היציאה עבור מיקום ה-SFTP שממנו ברצונך לייבא נתונים.

1. בחר **הוסף חיבור** בעת קביעת תצורת העשרה או עבור אל **מנהל מערכת** > **חיבורים** ובחר **הגדרה** באריח 'ייבוא מותאם אישית'.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="דף הגדרת חיבור עבור חיבור 'ייבוא מותאם אישית'.":::

1. הזן שם עבור החיבור.

1. הזן שם משתמש, סיסמה וכתובת אתר תקפים עבור שרת ה- SFTP שבו נמצאים הנתונים שיש לייבא.

1. סקור את [פרטיות ותאימות נתונים](#data-privacy-and-compliance) ותן את הסכמתך על-ידי בחירת **אני מסכים**.

1. בחר **אמת** כדי לאמת את התצורה ולאחר מכן בחר **שמור**.

### <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים באמצעות 'ייבוא מותאם אישית', אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אך אתה אחראי להבטיח שהנתונים האלה עומדים בכל מחויבויות הפרטיות או האבטחה שלקחת על עצמך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.

## <a name="configure-the-import"></a>קביעת תצורת הייבוא

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי** באריח **יבוא מותאם אישית של SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="אריח של ייבוא מותאם אישית של SFTP.":::

1. בדוק את הסקירה הכללית ולאחר מכן בחר **הבא**.

1. בחר את החיבור. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. בחר את **ערכת הנתונים של הלקוח** ולאחר בחר בפרופיל או בפלח שברצונך להעשיר. הישות *לקוח* מעשיר את כל פרופילי הלקוחות שלך בעוד שפלח מעשיר רק פרופילי לקוחות הנכללים באותו פלח.

1. בחר **הבא**.

1. הזן את ה **נתיב** ואת **שם הקובץ** של קובץ הנתונים שברצונך לייבא.

1. בחר **הבא**.

1. ספק **שם** עבור ההעשרה ועבור **שם ישות הפלט**.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

1. בחר **הפעל** כדי להתחיל את תהליך ההעשרה או לסגור כדי לחזור אל דף **העשרה**.

## <a name="view-enrichment-results"></a>הצג תוצאות העשרה

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>‏‫השלבים הבאים‬

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
