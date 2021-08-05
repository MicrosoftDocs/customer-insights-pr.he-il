---
title: נתונים של Customer Insights ב- Microsoft Dataverse
description: השתמש בישויות של Customer Insights כטבלאות ב- Microsoft Dataverse.
ms.date: 06/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 220e01a06711a5d35b8df09e265017a6d8fd0490
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650043"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>עבודה עם נתונים של Customer Insights ב- Microsoft Dataverse

Customer Insights מציע את האפשרות להפוך ישויות פלט לזמינות ב- [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). שילוב זה מאפשר שיתוף נתונים קל ופיתוח מותאם אישית באמצעות גישה לקוד בסיסי/ללא קוד. ישויות הפלט יהיו זמינות כטבלאות ב- Dataverse. טבלאות אלה מאפשרות תרחישים כמו [זרימות עבודה אוטומטיות באמצעות Power Automate](/power-automate/getting-started), [יישומים מונחי-דגמים](/powerapps/maker/model-driven-apps/) ו[יישומי בד ציור](/powerapps/maker/canvas-apps/) באמצעות Power Apps. באפשרותך להשתמש בנתונים עבור כל יישום אחר שמבוסס על טבלאות Dataverse. היישום הנוכחי תומך בעיקר בבדיקות מידע שבהן ניתן להביא ישויות זמינות של תובנות לגבי קהלים עבור מזהה לקוח נתון.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>צירוף סביבת Dataverse ל- Customer Insights

**ארגונים עם סביבות Dataverse קיימות**

ארגונים שכבר משתמשים ב- Dataverse יכולים [להשתמש באחת מסביבות Dataverse הקיימות שלהם](get-started-paid.md) כאשר מנהל מערכת מגדיר תובנות לגבי קהלים. אספקת כתובת URL לסביבת Dataverse מצרפת אותה לסביבה החדשה של תובנות לגבי קהלים. כדי להבטיח את הביצועים הטובים ביותר שאפשר, יש לארח סביבות של Customer Insights ושל Dataverse באותו אזור.

כדי לצרף סביבה של Dataverse, הרחב את **הגדרות מתקדמות** בעת יצירת סביבת התובנות לגבי קהלים. ספק את **כתובת ה- URL של סביבת Microsoft Dataverse** ובחר בתיבת הסימון **הפוך שיתוף נתונים לזמין‬‏‫**.

:::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Alt.":::

**ארגון חדש**

אם אתה יוצר ארגון חדש בעת הגדרת Customer Insights, תקבל באופן אוטומטי סביבת Dataverse חדשה.

> [!NOTE]
> אם הארגונים כבר משתמשים ב- Dataverse בדייר שלהם, חשוב לזכור כי [יצירת סביבה של Dataverse מתבצעת בפיקוחו של מנהל מערכת](/power-platform/admin/control-environment-creation.md). לדוגמה, אם אתה מגדיר סביבה חדשה של תובנות לגבי קהלים עם החשבון הארגוני שלך, והמנהל השבית את היצירה של סביבות ניסיון של Dataverse לכולם פרט למנהלי מערכת, לאתוכל ליצור סביבת ניסיון חדשה.
> 
> סביבות הניסיון של Dataverse שנוצרו ב- Customer Insights כוללות אחסון בנפח ‎3 GB שלא יחשבו כחלק מהקיבולת הכוללת שהדייר זכאי לה. מנויים בתשלום מקבלים זכאות של ‎‎15 GB עבור מסדי נתונים ו- ‎20 GB לאחסון קבצים ב- Dataverse.

## <a name="output-entities"></a>ישויות פלט

ישויות פלט מסוימות מתובנות לגבי קהלים זמינות כטבלאות ב- Dataverse. הסעיפים הבאים מתארים את הסכימה הצפויה של טבלאות אלה.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [העשרה](#enrichment)
- [חיזוי](#prediction)


### <a name="customerprofile"></a>CustomerProfile

טבלה זו מכילה את פרופיל הלקוח המאוחד מ- Customer Insights. הסכימה עבור פרופיל לקוח מאוחד תלויה בישויות ובתכונות שנמצאות בשימוש בתהליך המיזוג. סכימת פרופיל לקוח מכילה בדרך כלל קבוצת משנה של תכונות מ[הגדרת Common Data Model של CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

הטבלה AlternateKey מכילה מפתחות של ישויות שהשתתפו בתהליך האיחוד.

|Column  |סוג  |תיאור  |
|---------|---------|---------|
|DataSourceName    |String         | שם מקור הנתונים. לדוגמה: `datasource5`        |
|EntityName        | String        | שם הישות בתובנות לגבי קהלים. לדוגמה: `contact1`        |
|AlternateValue    |String         |מזהה חלופי שממופה למזהה הלקוח. דוגמה: `cntid_1078`         |
|KeyRing           | טקסט בכמה שורות        | ערך JSON  </br> דוגמה: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|מזהה לקוח         | String        | מזהה פרופיל הלקוח המאוחד.         |
|AlternateKeyId     | GUID         |  GUID דטרמיניסטי של AlternateKey מבוסס על msdynci_identifier       |
|msdynci_identifier |   String      |   `DataSourceName|EntityName|AlternateValue`  </br> דוגמה: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

טבלה זו מכילה פעילויות של משתמשים הזמינות ב- Customer Insights.

| Column            | סוג        | תיאור                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| מזהה לקוח        | String      | מזהה פרופיל לקוח                                                                      |
| ActivityId        | String      | מזהה פנימי של פעילות הלקוח (מפתח ראשי)                                       |
| SourceEntityName  | String      | שם ישות המקור                                                                |
| SourceActivityId  | String      | מפתח ראשי מישות המקור                                                       |
| ActivityType      | String      | סוג הפעילות הסמנטית או שם הפעילות המותאמת אישית                                        |
| ActivityTimeStamp | DATETIME    | חותמת זמן של פעילות                                                                      |
| תפקיד             | String      | כותרת או שם של הפעילות                                                               |
| תיאור       | String      | תיאור פעילות                                                                     |
| כתובת URL               | String      | קישור לכתובת URL חיצונית ספציפית לפעילות                                         |
| SemanticData      | מחרוזת JSON | כוללת רשימה של זוגות מפתח-ערך עבור שדות מיפוי סמנטיים ספציפית לסוג הפעילות |
| RangeIndex        | String      | חותמת זמן של Unix המשמשת למיון ציר זמן של פעילות ושאילתות טווח יעילות |
| mydynci_unifiedactivityid   | GUID | מזהה פנימי של פעילות הלקוח (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

טבלה זו מכילה את נתוני הפלט של מדדים מבוססי תכונות של לקוח.

| Column             | סוג             | תיאור                 |
|--------------------|------------------|-----------------------------|
| מזהה לקוח         | String           | מזהה פרופיל לקוח        |
| מדידים           | מחרוזת JSON      | כולל רשימה של זוגות מפתח-ערך עבור השם והערכים של המדד ללקוח הנתון | 
| msdynci_identifier | String           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | מזהה פרופיל לקוח |


### <a name="enrichment"></a>העשרה

טבלה זו מכילה את הפלט של תהליך ההעשרה.

| Column               | סוג             |  תיאור                                          |
|----------------------|------------------|------------------------------------------------------|
| מזהה לקוח           | String           | מזהה פרופיל לקוח                                 |
| EnrichmentProvider   | String           | שם הספק להעשרה                                  |
| EnrichmentType       | String           | סוג ההעשרה                                      |
| ערכים               | מחרוזת JSON      | רשימת התכונות שנוצרו על-ידי תהליך ההעשרה |
| msdynci_enrichmentid | GUID             | GUID דטרמיניסטי שנוצר מ- msdynci_identifier |
| msdynci_identifier   | String           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>חיזוי

טבלה זו מכילה את הפלט של חיזויי המודל.

| Column               | סוג        | תיאור                                          |
|----------------------|-------------|------------------------------------------------------|
| מזהה לקוח           | String      | מזהה פרופיל לקוח                                  |
| ModelProvider        | String      | שם ספק המודל                                      |
| מודל                | String      | שם מודל                                                |
| ערכים               | מחרוזת JSON | רשימת התכונות שנוצרו על-ידי המודל |
| msdynci_predictionid | GUID        | GUID דטרמיניסטי שנוצר מ- msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |
