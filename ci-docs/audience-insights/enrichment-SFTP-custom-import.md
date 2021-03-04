---
title: העשרה עם ייבוא מותאם אישית של SPTF
description: מידע כללי אודות העשרת ייבוא מותאם אישית של SPTF.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f25dcc08d96d36507e47af0d7b184003ae095819
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269607"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>העשרת פרופילי לקוחות עם נתונים מותאמים אישית (Preview)

ייבוא מותאם אישית באמצעות Secure File Transfer Protocol‏ (SFTP) מאפשר לך לייבא נתונים שלא צריכים לעבור את תהליך איחוד הנתונים. זו דרך גמישה, מאובטחת וקלה להכנסת הנתונים שלך. ניתן להשתמש בייבוא מותאם אישית של SFTP בשילוב עם [ייצוא SFTP](export-sftp.md) המאפשר לך לייצא את נתוני פרופיל הלקוח הדרושים להעשרה. לאחר מכן ניתן לעבד את הנתונים, להעשיר אותם ולבצע ייבוא מותאם אישית של SFTP כדי להחזיר את הנתונים המועשרים ליכולת תובנות הקהל של Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>דרישות מוקדמות

כדי לקבוע את תצורת הייבוא המותאם אישית של SFTP, יש לעמוד בתנאים המוקדמים הבאים:

- יש לך אישורי משתמש (שם משתמש וסיסמה) עבור מיקום ה- SFTP שממנו יתבצע ייבוא הנתונים.
- יש לך את כתובת ה- URL ומספר היציאה (בדרך כלל 22) עבור מארח STFP.
- יש לך את שם הקובץ ואת המיקום של הקובץ המיובא במארח ה- SFTP.
- קיים קובץ *model.json* המציין את הסכימה עבור הנתונים המיועדים לייבוא. קובץ זה חייב להיות באותה ספריה שבה נמצא הקובץ לייבוא.
- יש לך הרשאת [מנהל מערכת](permissions.md#administrator).

## <a name="configuration"></a>תצורה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. ב **אריח ייבוא מותאם אישית של SPTF**, בחר **העשר את הנתונים שלי**.

   > [!div class="mx-imgBorder"]
   > ![אריח של ייבוא מותאם אישית של SPTF](media/SFTP_Custom_Import_tile.png "אריח של ייבוא מותאם אישית של SPTF")

1. בחר **תחילת העבודה** וספק את האישורים ואת הכתובת עבור שרת SPTF. לדוגמה, sftp://mysftpserver.com:22.

1. הזן את שם הקובץ שמכיל את הנתונים ואת הנתיב לקובץ בשרת SFTP אם הוא לא נמצא בתיקיית הבסיס.

1. אשר את כל פריטי הקלט על-ידי בחירת **התחבר לייבוא מותאם אישית**.

   > [!div class="mx-imgBorder"]
   > ![תפריט נשלף של תצורת ייבוא מותאם אישית של SPTF](media/SFTP_Custom_Import_Configuration_flyout.png "תפריט נשלף של תצורת ייבוא מותאם אישית של SPTF")

## <a name="defining-field-mappings"></a>הגדרת מיפויי שדות 

הספריה המכילה את הקובץ המיועד לייבוא בשרת SPTF מוכרחה גם לכלול קובץ *model.json*. קובץ זה מגדיר את הסכימה לשימוש עבור ייבוא הנתונים. יש להשתמש בסכימה [Common Data Model](https://docs.microsoft.com/common-data-model/) כדי לציין את מיפוי השדה. דוגמה פשוטה לקובץ model.json נראית כך:

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