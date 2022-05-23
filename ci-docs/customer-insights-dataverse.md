---
title: נתונים של Customer Insights ב- Microsoft Dataverse
description: השתמש בישויות של Customer Insights כטבלאות ב- Microsoft Dataverse.
ms.date: 04/05/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 1e629cd218b104b115f74f59a53a14e9d60fcc8a
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741366"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>עבודה עם נתונים של Customer Insights ב- Microsoft Dataverse

Customer Insights מציע את האפשרות להפוך ישויות פלט לזמינות ב- [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). שילוב זה מאפשר שיתוף נתונים קל ופיתוח מותאם אישית באמצעות גישה לקוד בסיסי/ללא קוד. [ישויות הפלט](#output-entities) זמינות כטבלאות בסביבת Dataverse. אתה יכול להשתמש בנתונים עבור כל יישום אחר המבוסס על טבלאות Dataverse. טבלאות אלה הופכות תרחישים כמו זרימות עבודה אוטומטיות דרך Power Automate או בניית אפליקציות באמצעות Power Apps לזמינים. היישום הנוכחי תומך בעיקר בחיפושי מידע שבהם ניתן לאחזר את הישויות הזמינות של Customer Insights עבור מזהה לקוח נתון.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>צירוף סביבת Dataverse ל- Customer Insights

**ארגון קיים**

מנהלי מערכת יכולים להגדיר את Customer Insights ל[שימוש בסביבת Dataverse קיימת](create-environment.md) כאשר הם יוצרים סביבת Customer Insights. על ידי מתן כתובת האתר לסביבת Dataverse, היא מתחברת לסביבת Customer Insights החדשה שלהם. סביבות Customer Insights ו- Dataverse חייבות להתארח באותו אזור. 

אם אתה לא רוצה להשתמש בסביבת Dataverse קיימת, המערכת יוצרת סביבה חדשה עבור נתוני Customer Insights בדייר שלך. 

> [!NOTE]
> אם הארגונים שלך כבר משתמשים ב- Dataverse בדייר שלהם, חשוב לזכור [שיצירת סביבות ב- Dataverse נשלטת על ידי מנהל מערכת](/power-platform/admin/control-environment-creation) . לדוגמה, אם אתה מגדיר סביבת Customer Insights חדשה באמצעות החשבון הארגוני שלך והמנהל השבית את היצירה של סביבות ניסיון של Dataverse לכולם מלבד מנהלי מערכת, לא תוכל ליצור סביבת ניסיון חדשה.
> 
> סביבות הניסיון של Dataverse שנוצרו ב- Customer Insights כוללות אחסון בנפח ‎3 GB שלא יחשבו כחלק מהקיבולת הכוללת שהדייר זכאי לה. מנויים בתשלום מקבלים זכאות של ‎‎15 GB עבור מסדי נתונים ו- ‎20 GB לאחסון קבצים ב- Dataverse.

**ארגון חדש**

אם אתה יוצר ארגון חדש בעת הגדרת Customer Insights, המערכת יוצרת אוטומטית סביבת Dataverse חדשה בארגון שלך.

## <a name="output-entities"></a>ישויות פלט

ישויות פלט מסוימות מ- Customer Insights זמינות כטבלאות ב- Dataverse. הסעיפים הבאים מתארים את הסכימה הצפויה של טבלאות אלה.

- [CustomerProfile](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [העשרה](#enrichment)
- [חיזוי](#prediction)
- [חברות בפלח](#segment-membership)


### <a name="customerprofile"></a>CustomerProfile

טבלה זו מכילה את פרופיל הלקוח המאוחד מ- Customer Insights. הסכימה עבור פרופיל לקוח מאוחד תלויה בישויות ובתכונות המשמשות בתהליך איחוד הנתונים. סכימת פרופיל לקוח מכילה בדרך כלל קבוצת משנה של תכונות מ[הגדרת Common Data Model של CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

הטבלה AlternateKey מכילה מפתחות של ישויות שהשתתפו בתהליך האיחוד.

|Column  |סוג  |תיאור  |
|---------|---------|---------|
|DataSourceName    |String         | שם מקור הנתונים. לדוגמה: `datasource5`        |
|EntityName        | String        | שם הישות ב- Customer Insights. לדוגמה: `contact1`        |
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

### <a name="segment-membership"></a>חברות בפלח

טבלה זו מכילה מידע על חברות בפלח של פרופילי הלקוחות.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| מזהה לקוח        | String       | מזהה פרופיל לקוח        |
| SegmentProvider      | String       | יישום שמפרסם את הפלחים.      |
| SegmentMembershipType | String       | סוג הלקוח ברשומת חברות זו בפלח. תומך בסוגים מרובים, כגון לקוח, איש קשר או תיק לקוח. ברירת מחדל: לקוח  |
| פלחי שוק       | מחרוזת JSON  | רשימת פלחים ייחודיים שפרופיל הלקוח חבר בהם      |
| msdynci_identifier  | String   | המזהה הייחודי של רשומת החברות בפלח. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | Guid      | GUID דטרמיניסטי שנוצר מתוך `msdynci_identifier`          |
