---
title: התחבר לנתונים בתוך אגם נתונים מנוהל של Microsoft Dataverse
description: ייבא נתונים מאגם נתונים מנוהל של Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609796"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>התחבר לנתונים בתוך אגם נתונים מנוהל של Microsoft Dataverse

משתמשי Microsoft Dataverse יכולים להתחבר במהירות לישויות אנליטיות באגם מנוהל על ידי Microsoft Dataverse. רק מקור נתונים אחד של סביבה יכול להשתמש בו-זמנית באותו אגם מנוהל של Dataverse.

> [!NOTE]
> עליך להיות מנהל מערכת בארגון Dataverse כדי להמשיך ולהציג את רשימת הישויות הזמינות באגם המנוהל.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- נתונים המאוחסנים בשירותים מקוונים כגון Azure Data Lake Storage עשויים להיות מאוחסנים במקום אחר שאינו מקום העיבוד או האחסון של הנתונים ב- Dynamics 365 Customer Insights. על-ידי ייבוא או התחברות לנתונים המאוחסנים בשירותים מקוונים, אתה מסכים להעברה ולאחסון של נתונים אלה ב- Dynamics 365 Customer Insights. [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center).

- רק ישויות של Dataverse [שבהן התכונה 'מעקב אחר שינויים' זמינה](/power-platform/admin/enable-change-tracking-control-data-synchronization) יהיו גלויים. ניתן לייצא ישויות אלה אל Data Lake שמנוהל על-ידי Dataverse ולעשות בהן שימוש ב- Customer Insights. בטבלאות Dataverse שמגיעות מוכנות לשימוש, התכונה 'מעקב אחר שינויים' זמינה כברירת מחדל. עליך להפעיל את מעקב אחר שינויים עבור טבלאות מותאמות אישית. כדי לבדוק אם מעקב אחר שינויים זמין בטבלת Dataverse, עבור אל [Power Apps](https://make.powerapps.com)  > **נתונים** > **טבלאות**. מצא את הטבלה שמעניינת אותך ובחר בה. עבור אל **הגדרות** > **אפשרויות מתקדמות** ובדוק את ההגדרה **מעקב אחר שינויים**.

## <a name="connect-to-a-dataverse-managed-lake"></a>התחבר אל אגם נתונים מנוהל של Dataverse

1. עבור אל **נתונים** > **מקורות נתונים**.

1. בחר **הוסף מקור נתונים**.

1. בחר **Microsoft Dataverse**.

1. הזן **שם** עבור מקור הנתונים ו **תיאור** אופציונלי.

1. ספק את **כתובתה שרת** עבור ארגון Dataverse, ובחר **התחברות**.

1. בחר את הטבלאות שברצונך להטמיע כישויות לתוך Customer Insights מהרשימה הזמינה.

   > [!NOTE]
   > אם טבלאות מסוימות כבר נבחרו, הן יכולות לשמש ביישומי Dynamics 365 אחרים (כגון Dynamics 365 Sales Insights או Customer Service Insights). אין באפשרותך לשנות את הבחירה. טבלאות אלה יהיו זמינות כישויות לאחר יצירת מקור הנתונים.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="תיבת דו-שיח המציגה רשימה של ישויות בסביבת Dataverse.":::

1. שמור את הבחירה שלך כדי להתחיל לסנכרן את הטבלאות שנבחרו מ- Dataverse. תמצא את החיבור החדש שנוסף בדף **מקורות מידע**. הוא יעמוד בתור לרענון ויציג את ספירת הישות כ- 0 עד שכל הטבלאות שנבחרו יסונכרנו.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

טעינת נתונים עשויה להימשך זמן מה. לאחר רענון מוצלח, ניתן לסקור את הנתונים שעובדו בדף [**ישויות**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>ערוך מקור נתונים של אגם מנוהל של Dataverse

אתה עורך רק את בחירת הישויות לאחר יצירת מקור נתונים. לדוגמא, אם נוספו ישויות נוספות ל- Dataverse ואתה רוצה לייבא גם אותם.
כדי להתחבר לאגם Dataverse אחר, [צור מקור נתונים חדש](#connect-to-a-dataverse-managed-lake).

1. עבור אל **נתונים** > **מקורות נתונים**.

1. לצד מקור הנתונים שברצונך לעדכן, בחר את **עריכה**.

1. בחר ישויות נוספות מרשימת הישויות הזמינה.

1. יש ללחוץ על **שמור** כדי להחיל את השינויים ולחזור לדף **מקורות נתונים**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>סיבות נפוצות לשגיאות בקליטת אירועים או נתונים פגומים

הבדיקות הבאות מבוצעות עבור הנתונים שנקלטו כדי לחשוף רשומות פגומות:

- ערך השדה אינו תואם את סוג הנתונים של העמודה שלו.
- שדות מכילים תווים שגורמים לעמודות לא להתאים לסכימה הצפויה. לדוגמה, מירכאות בתבנית שגויה, מירכאות ללא תו Escape או תווי שורה חדשה.
- אם מופיעות העמודות datetime/date/datetimeoffset חובה לציין את הפורמט שלהן במודל אם הוא לא תואם לפורמט ISO הסטנדרטי.

### <a name="schema-or-data-type-mismatch"></a>אי התאמה של סכימה או סוג נתונים

אם הנתונים אינם תואמים את הסכימה, הרשומות מסווגות כפגומות. תקן את נתוני המקור או את הסכימה והטמע מחדש את הנתונים.

### <a name="datetime-fields-in-the-wrong-format"></a>התבנית השדה 'תאריך שעה' לא נכונה

שדות התאריך והשעה בישות אינם בפורמט ISO או en-US. פורמט ברירת המחדל של 'תאריך ושעה' ב- Customer Insights הוא פורמט en-US. כל שדות התאריך והשעה בישות חייבים להיות באותו פורמט. האפליקציה Customer Insights תומכת בפורמטים אחרים בתנאי שהערות או תכונות מבוצעות ברמת המקור או הישות במודל או ב- manifest.json. לדוגמה: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  ב- manifes.json, ניתן לציין את פורמט התאריך והשעה ברמת הישות או ברמת התכונה. ברמת הישות, השתמש ב-"exhibitsTraits" בישות ב- ‏‎*.manifest.cdm.json כדי להגדיר את פורמט התאריך והשעה. ברמת התכונה, השתמש ב-"appliedTraits" בתכונה ב- entityname.cdm.json.

**Manifest.json ברמת הישות**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Manifest.json ברמת התכונה**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
