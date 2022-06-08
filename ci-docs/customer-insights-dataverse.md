---
title: עבודה עם נתונים של Customer Insights ב- Microsoft Dataverse
description: למד כיצד לחבר בין Customer Insights לבין Microsoft Dataverse ולהבין את ישויות הפלט שמיוצאות אל Dataverse.
ms.date: 05/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 3848e143bc7cb2f345bc698a274b92148ef00669
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833677"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>עבודה עם נתונים של Customer Insights ב- Microsoft Dataverse

Customer Insights מספקת אפשרות להפוך ישויות פלט לזמינות בתור [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). שילוב זה מאפשר שיתוף נתונים קל ופיתוח מותאם אישית באמצעות גישה לקוד בסיסי/ללא קוד. [ישויות הפלט](#output-entities) זמינות כטבלאות בסביבת Dataverse. אתה יכול להשתמש בנתונים עבור כל יישום אחר המבוסס על טבלאות Dataverse. טבלאות אלה הופכות תרחישים כמו זרימות עבודה אוטומטיות דרך Power Automate או בניית אפליקציות באמצעות Power Apps לזמינים.

חיבור אל סביבת Dataverse משלך גם מאפשר לך [לקלוט נתונים ממקורות נתונים מקומיים באמצעות זרימות נתונים ושערים של Power Platform](data-sources.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>דרישות מוקדמות

- סביבות Customer Insights ו- Dataverse חייבות להתארח באותו אזור.
- נדרש לך תפקיד מנהל מערכת גלובלי בסביבת Dataverse. עליך לוודא ש[סביבת Dataverse זו משוייכת](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) לקבוצות אבטחה מסוימות ולוודא שאתה מתווסף לקבוצות אבטחה אלה.
- אף סביבה אחרת של Customer Insights לא משויכת לסביבת Dataverse שברצונך לחבר. למד כיצד [להסיר חיבור קיים לסביבת Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Microsoft Dataverse סביבה יכולה להתחבר רק לחשבון אחסון יחיד. דבר זה חל רק אם אתה מגדיר את הסביבה [לשימוש ב- Azure Data Lake Storage שלך](own-data-lake-storage.md).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>חבר סביבת Dataverse אל Customer Insights

השלב של **Microsoft Dataverse** מאפשר לך לחבר את Customer Insights אל סביבת ה- Dataverse שלך תוך כדי [יצירת סביבת Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="שיתוף נתונים עם Microsoft Dataverse מופעל אוטומטית עבור סביבות חדשות ברשת.":::

מנהלי מערכת יכולים להגדיר את Customer Insights להתחבר אל סביבת Dataverse קיימת. על ידי מתן כתובת האתר לסביבת Dataverse, היא מתחברת לסביבת Customer Insights החדשה שלהם.

אם אתה לא רוצה להשתמש בסביבת Dataverse קיימת, המערכת יוצרת סביבה חדשה עבור נתוני Customer Insights בדייר שלך. [מנהלי Power Platform יכולים לקבוע מי יכול ליצור ולנהל סביבות](/power-platform/admin/control-environment-creation). כאשר אתה מגדיר סביבת Customer Insights חדשה והמנהל המערכת השבית את היצירה של סביבות Dataverse לכולם מלבד למנהלי מערכת, ייתכן שלא תוכל ליצור סביבה חדשה.

**הפוף שיתוף נתונים לזמין** באמצעות Dataverse על ידי בחירה בתיבת הסימון של שיתוף הנתונים.

אם אתה משתמש בחשבון Data Lake Storage משלך, תצטרך את **מזהה ההרשאות**. למידע נוסף על אופן קבלת מזהה ההרשאה, עיין בסעיף הבא.

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>הפוך שיתוף נתונים מ- Azure Data Lake Storage משלך לזמין באמצעות Dataverse ‏(Preview)

הפיכת שיתוף נתונים באמצעות Microsoft Dataverse לזמין כאשר הסביבה שלך [משתמשת בחשבון Azure Data Lake Storage משלך](own-data-lake-storage.md) מצריכה קונפיגורציה נוספת. למשתמש שמגדיר את סביבת Customer Insights נדרשות לפחות הרשאות **קורא נתונים של Blob אחסון** בגורם המכיל בחשבון *CustomerInsights* בחשבון Azure Data Lake Storage.

1. צור שתי קבוצות אבטחה במנוי Azure שלך - קבוצת אבטחה אחת מסוג **קורא** וקבוצת אבטחה אחת מסוג **משתתף** והגדר את שירות Microsoft Dataverse כבעלים של שתי קבוצות האבטחה.
2. נהל את רשימת בקרת הגישה (ACL) בגורם המכיל של CustomerInsights בחשבון האחסון שלך באמצעות קבוצות אבטחה אלה. תוסיף את שירות Microsoft Dataverse וכל אפליקציה עסקית מבוססי Dataverse כמו Dynamics 365 Marketing לקבוצה האבטחה **קורא** עם הרשאות **קריאה בלבד**. הוסף *רק* האפליקציית Customers Insights לקבוצת האבטחה **משתתף** כדי להעניק לה הרשאות **קריאה וכתיבה** לכתיבת פרופילים ותובנות.

### <a name="limitations"></a>מגבלות

ישנן שתי מגבלות בעת השימוש ב- Dataverse בחשבון Azure Data Lake Storage משלך:

- יש מיפוי אחד לאחד בין ארגון Dataverse וחשבון Azure Data Lake Storage. לאחר חיבור ארגון Dataverse לחשבון אחסון, הוא לא יכול להתחבר לחשבון אחסון אחר. מגבלה זו מונעת אכלוס מספר חשבונות אחסון על-ידי Dataverse.
- שיתוף נתונים לא יעבוד אם יש צורך בהגדרה של Azure Private Link כדי לגשת לחשבון Azure Data Lake storage מכיוון שהוא נמצא מאחורי חומת אש. נכון לעכשיו Dataverse אינו תומך בחיבור לנקודות קצה פרטיות דרך קישור פרטי.

### <a name="set-up-powershell"></a>הגדרת PowerShell

כדי להפעיל את הסקריפטים של PowerShell, תחילה עליך להגדיר את PowerShell בהתאם.

1. התקן את הגירסה העדכנית ביותר של [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. במחשב שלך, בחר את מקש Windows במקלדת וחפש **Windows PowerShell‎** ובחר **הפעל בתור מנהל מערכת**.
   1. בחלון PowerShell שנפתח, הזן `Install-Module AzureAD`.
2. ייבא שלושה מודולים.
    1. בחלון PowerShell, הזן את `Install-Module -Name Az.Accounts` ובצע את הצעדים הבאים.
    1. חזור על הפעולה עבור `Install-Module -Name Az.Resources` ועובר `Install-Module -Name Az.Storage`.

### <a name="configuration-steps"></a>שלבי קביעת תצורה

1. הורד את שני הסקריפטים של PowerShell שאתה צריך להפעיל [ממאגר GitHub](https://github.com/trin-msft/byol) של המנהדס שלנו.
    1. `CreateSecurityGroups.ps1`
       - כדי להפעיל סקריפט PowerShell זה, דרושות לך הרשאות של *מנהל דייר* .
       - סקריפט PowerShell זה יוצר שתי קבוצות אבטחה במנוי Azure שלך. אחד לקבוצת 'קורא' ואחר לקבוצת 'משתתף' ויהפוך את שירות Microsoft Dataverse לבעלים של שתי קבוצות האבטחה האלו.
       - בצע סקריפט PowerShell זה ב-Windows PowerShell על ידי מתן מזהה המנוי של Azure המכיל את Azure Data Lake Storage שלך. פתח את סקריפט ה- PowerShell בעורך כדי לסקור מידע נוסף ואת הלוגיקה שיושמה.
       - שמור את שני ערכי מזהי קבוצת האבטחה שנוצרו על ידי הסקריפט הזה מכיוון שנשתמש בהם בסקריפט `ByolSetup.ps1`.

        > [!NOTE]
        > ניתן להשבית יצירת קבוצת אבטחה בדייר שלך. במקרה כזה, יהיה צורך בהגדרה ידנית ומנהל מערכת Azure AD יצטרך[ להפוך יצירת קבוצת אבטחה לזמינה](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - דרושות לך הרשאות *בעל נתונים של Blob האחסון* ברמת גורם מכיל/חשבון האחסון על מנת להפעיל את הסקריפט הזה או שהסקריפט הזה יצור אחד עבורך. ניתן להסיר את הקצאת התפקיד שלך באופן ידני לאחר הפעלה מוצלחת של הסקריפט.
        - סקריפט PowerShell זה מוסיף את בקרת הגישה מבוססת התפקיד הנדרשת (RBAC) עבור שירות Microsoft Dataverse  וכל אפליקציה עסקית מבוססת Dataverse. הסקריפט גם מעדכן את רשימת בקרת הגישה (ACL) בגורם המכיל של CustomerInsights עבור קבוצות האבטחה שנוצרו באמצעות הסקריפט `CreateSecurityGroups.ps1`. לקבוצה 'משתתף' תהיה הרשאת *rwx* ולקבוצת 'קוראים' תהיה הרשאת *r-x* בלבד.
        - בצע סקריפט זה של PowerShell ב- Windows PowerShell על ידי מתן מזהה המנוי של Azure המכיל את Azure Data Lake Storage, שם חשבון האחסון, שם קבוצת משאבים וערכי מזהי קבוצות האבטחה 'קורא' ו'משתתף'. פתח את סקריפט ה- PowerShell בעורך כדי לסקור מידע נוסף ואת הלוגיקה שיושמה.
        - העתק את מחרוזת הפלט לאחר הפעלה מוצלחת של הסקריפט. מחרוזת הפלט נראית כך: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

2. הזן את מחרוזת הפלט שהועתקה מלמעלה לשדה **מזהה הרשאות** של שלב הגדרת התצורה של הסביבה עבור Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="אפשרויות הגדרת תצורה להפיכת שיתוף נתונים מ- Azure Data Lake Storage משלך באמצעות Microsoft Dataverse לזמין.":::

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>הסרת חיבור קיים לסביבת Dataverse

כאשר מתחברים לסביבת Dataverse, משמעותה של הודעת השגיאה **ארגון CDS זה כבר מחובר למופע אחר של Customer Insights** היא שסביבת Dataverse כבר נמצאת בשימוש בסביבת Customer Insights. אפשר להסיר את החיבור הקיים כמנהל מערכת גלובלי בסביבת Dataverse. אכלוס השינויים עשוי לקחת כמה שעות.

1. עבור אל [Power Apps](https://make.powerapps.com).
1. בחר את הסביבה מבורר הסביבה.
1. עבור ל **פתרונות** 
1. הסר או מחק את הפתרון בשם **תוסף לכרטיס לקוח של Dynamics 365 Customer Insights ‏(Preview‏‏‏)**.

או

1. פתח את סביבת Dataverse.
1. עבור אל **הגדרות מתקדמות** > **פתרונות**.
1. הסר את ההתקנה של פתרון **CustomerInsightsCustomerCard**.

אם הסרת החיבור נכשלת בגלל יחסי תלות, עליך להסיר גם את יחסי התלות. למידע נוסף, ראה [הסרת יחסי תלות](/power-platform/alm/removing-dependencies).

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

<!--
## FAQ: Update existing environments to use Microsoft Dataverse

Between mid-May 2022 and June 13, 2022, administrators can update the environment settings with a Dataverse environment that Customer Insights can use. On June 13, 2022, your environment will be updated automatically and we'll create a Dataverse environment on your tenant for you.

1. My environment uses my own Azure Data Lake Storage account. Do I still need to update?

   If there's already a Dataverse environment configured in your environment, the update isn't required. If no Dataverse is environment configured, the **Update now** button will create a Dataverse environment and update from the Customer Insights database to a Dataverse database.

1. Will we get extra Dataverse capacity, or will the update use my existing Dataverse capacity?

   - If there's already a Dataverse environment configured in your Customer Insights environment, or connected with other Dynamics 365 or Power Apps applications, the capacity remains unchanged.
   - If the Dataverse environment is new, it will add new storage and database capacity. The capacity added varies per environment and entitlements. You'll get 3 GB for trial and sandbox environment. Production environments get 15 GB.

1. I proceeded with the update and it seems like nothing happened. Is the update complete?

   If the notification in Customer Insights doesn't show anymore, the update is complete. You can check the status of the update by reviewing your environment settings.

1. Why do I still see the banner after completing the update steps?

   It can happen due to an upgrade or refresh failure. Contact support.

1. I received a "Failed to provision Dataverse environment" error after starting the update. What happened?

   It can happen due to an upgrade or refresh failure. Contact support.
   Common causes:
    - Insufficient capacity. There's no more capacity to create more environments. For more information, see [Manage capacity action](/power-platform/admin/capacity-storage#actions-to-take-for-a-storage-capacity-deficit).
    - Region mismatch between tenant region and Customer Insights environment region in the Australia and India regions.
    - Insufficient privileges to provision Dataverse. The users starting the update needs a Dynamics 365 admin role.
    - -->
