---
title: עבודה עם נתונים של Customer Insights ב- Microsoft Dataverse
description: למד כיצד לחבר בין Customer Insights לבין Microsoft Dataverse ולהבין את ישויות הפלט שמיוצאות אל Dataverse.
ms.date: 08/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9433c411a2c7eb0db137c6392578993d47be82a2
ms.sourcegitcommit: 8559ca47a22d1d7cd9be13531c2eaf0c1083942b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/12/2022
ms.locfileid: "9671252"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>עבודה עם נתונים של Customer Insights ב- Microsoft Dataverse

Customer Insights מציע את האפשרות להפוך ישויות פלט לזמינות ב- [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). שילוב זה מאפשר שיתוף נתונים קל ופיתוח מותאם אישית באמצעות גישה לקוד בסיסי/ללא קוד. [ישויות הפלט](#output-entities) זמינות כטבלאות בסביבת Dataverse. אתה יכול להשתמש בנתונים עבור כל יישום אחר המבוסס על טבלאות Dataverse. טבלאות אלה הופכות תרחישים כמו זרימות עבודה אוטומטיות דרך Power Automate או בניית אפליקציות באמצעות Power Apps לזמינים.

חיבור אל סביבת Dataverse משלך גם מאפשר לך [לקלוט נתונים ממקורות נתונים מקומיים באמצעות זרימות נתונים ושערים של Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>דרישות מוקדמות

- סביבות Customer Insights ו- Dataverse חייבות להתארח באותו אזור.
- תפקיד מנהל מערכת כללי מוגדר בסביבת Dataverse. עליך לוודא ש[סביבת Dataverse זו משוייכת](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) לקבוצות אבטחה מסוימות ולוודא שאתה מתווסף לקבוצות אבטחה אלה.
- אף סביבה אחרת של Customer Insights לא משויכת לסביבת Dataverse שברצונך לחבר. למד כיצד [להסיר חיבור קיים לסביבת Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- סביבת Microsoft Dataverse המחוברת לחשבון אחסון יחיד אם הגדרת את הסביבה [לשימוש ב- Azure Data Lake Storage שלך](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>סביבת קיבולת אחסון של Dataverse

מינוי של Customer Insights מאפשר לך לקבל קיבולת נוספת עבור [קיבולת אחסון קיימת של Dataverse](/power-platform/admin/capacity-storage) של הארגון. הקיבולת הנוספת תלויה במספר הפרופילים שבהם משתמש המינוי שלך.

**דוגמה:**

בהנחה שאתה מקבל אחסון בנפח ‎15 ‎GB‎ למסד נתונים ואחסון קבצים בנפח ‎20 GB‎ לכל 100,000 פרופילי לקוחות. אם המנוי שלך כולל 300,000 פרופילי לקוחות, קיבולת האחסון הכוללת שלך היא 45 ג"ב ‏(3 x‏ 15‏ ג"ב) אחסון במסד נתונים ו-60 ג"ב לאחסון קבצים (3‏ x‎‏ 20 ג"ב). באופן דומה, אם יש לך מנוי 'מעסק לעסק' עם 30 אלף תיקי לקוח, קיבולת האחסון הכוללת שלך היא 45 ג"ב (3‏ x‏ 15 ג"ב) לאחסון מסד נתונים ו-60 ג"ב לאחסון קבצים (3‏ x‏ 20 ג"ב).

קיבולת היומן אינה מצטברת וקבועה עבור הארגון שלך.

לקבלת מידע נוסף על זכאויות הקיבולת המפורטות, עיין ב[מדריך הרישוי ל- Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>חבר סביבת Dataverse אל Customer Insights

השלב של **Microsoft Dataverse** מאפשר לך לחבר את Customer Insights אל סביבת ה- Dataverse שלך תוך כדי [יצירת סביבת Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="שיתוף נתונים עם Microsoft Dataverse מופעל אוטומטית עבור סביבות חדשות.":::

1. ספק את כתובת ה- URL לסביבת Dataverse שלך או השאר ריק ליצירת כתובות עבורך.

   > [!NOTE]
   > לאחר יצירת החיבור בין Customer Insights ל- Dataverse, אל תשנה את שם הארגון עבור סביבת Dataverse. שם הארגון נמצא בשימוש בכתובת ה- URL של Dataverse ושם שונה מנתק את החיבור עם Customer Insights.

   [מנהלי Power Platform יכולים לקבוע מי יכול ליצור ולנהל סביבות Dataverse](/power-platform/admin/control-environment-creation). כאשר אתה מנסה מגדיר סביבת Customer Insights חדשה ולא מצליח, ייתכן שהמנהל המערכת השבית את היצירה של סביבות Dataverse לכולם מלבד למנהלי מערכת.

1. אם אתה משתמש בחשבון Data Lake Storage משלך:
   1. בחר **אפשר שיתוף נתונים** עם Dataverse.
   1. יש להזין את **מזהה ההרשאות**. לקבלת [מזהה ההרשאות  עליך להפוך שיתוף נתונים עם Dataverse מ- Azure Data Lake Storage משלך לזמין](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>הפוך שיתוף נתונים מ- Azure Data Lake Storage משלך עם Dataverse לזמין ‏(Preview)

[בחשבון Azure Data Lake Storage שלך](own-data-lake-storage.md), אמת שהגדרת המשתמש ב- Customer Insights כוללת לפחות הרשאות **קורא נתונים של Blob אחסון** בגורם המכיל בחשבון `customerinsights` בחשבון האחסון.

> [!NOTE]
> שיתוף נתונים ישים רק אם אתה משתמש בחשבון Azure Data Lake Storage משלך. הגדרה זו אינה זמינה אם סביבת Customer Insights משתמשת באחסון בברירת המחדל של Dataverse.

### <a name="limitations"></a>הגבלות

- קיים רק מיפוי אחד לאחד בין ארגון Dataverse וחשבון Azure Data Lake Storage. לאחר חיבור ארגון Dataverse לחשבון אחסון, הוא לא יכול להתחבר לחשבון אחסון אחר. מגבלה זו מונעת אכלוס מספר חשבונות אחסון על-ידי Dataverse.
- שיתוף נתונים לא יעבוד אם יש צורך בהגדרה של Azure Private Link כדי לגשת לחשבון Azure Data Lake Storage מכיוון שהוא נמצא מאחורי חומת אש. נכון לעכשיו Dataverse אינו תומך בחיבור לנקודות קצה פרטיות דרך קישור פרטי.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>הגדר קבוצות אבטחה ב- Azure Data Lake Storage משלך

1. צור שתי קבוצות אבטחה במנוי Azure שלך - קבוצת אבטחה אחת מסוג **קורא** וקבוצת אבטחה אחת מסוג **משתתף** והגדר את שירות Microsoft Dataverse כבעלים של שתי קבוצות האבטחה.

1. נהל את רשימת בקרת הגישה (ACL) בגורם המכיל של `customerinsights` בחשבון האחסון שלך באמצעות קבוצות אבטחה אלה.
   1. תוסיף את שירות Microsoft Dataverse וכל אפליקציה עסקית מבוססי Dataverse כמו Dynamics 365 Marketing לקבוצה האבטחה **קורא** עם הרשאות **קריאה בלבד**.
   1. הוסף *רק* האפליקציית Customers Insights לקבוצת האבטחה **משתתף** כדי להעניק לה הרשאות **קריאה וכתיבה** לכתיבת פרופילים ותובנות.

### <a name="set-up-powershell"></a>הגדרת PowerShell

הגדר את PowerShell לביצוע סקריפטים של PowerShell.

1. התקן את הגירסה העדכנית ביותר של [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. במחשב שלך, בחר את מקש Windows במקלדת וחפש **Windows PowerShell‎** ובחר **הפעל בתור מנהל מערכת**.
   1. בחלון PowerShell שנפתח, הזן `Install-Module AzureAD`.

1. ייבא שלושה מודולים.
   1. בחלון PowerShell, הזן את `Install-Module -Name Az.Accounts` ובצע את הצעדים הבאים.
   1. חזור על הפעולה עבור `Install-Module -Name Az.Resources` ועובר `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>הפעל סקריפטים של PowerShell והשג את מזהה ההרשאה

1. הורד את שני הסקריפטים של PowerShell שאתה צריך להפעיל [ממאגר GitHub](https://github.com/trin-msft/byol) של המנהדס שלנו.
   - `CreateSecurityGroups.ps1`: דרושות הרשאות מנהל מערכת של דייר.
   - `ByolSetup.ps1`: דורש הרשאות בעלים של 'נתוני בלוב אחסון' ברמת חשבון האחסון/הגורם המיכל. הסקריפט הזה ייצור עבורך את ההרשאה. ניתן להסיר את הקצאת התפקיד שלך באופן ידני לאחר הפעלה מוצלחת של הסקריפט.

1. בצע את `CreateSecurityGroups.ps1` ב- Windows PowerShell על ידי מתן מזהה המינוי של Azure המכיל את ה- Azure Data Lake Storage שלך. פתח את הסקריפט של PowerShell בעורך כדי לסקור מידע נוסף ואת הלוגיקה שיושמה.

   סקריפט זה יוצר שתי קבוצות אבטחה במינוי Azure שלך: אחת עבור קבוצת קורא ואחרת עבור קבוצת 'משתתף'. השירות Microsoft Dataverse הוא הבעלים של שתי קבוצות האבטחה הללו.

1. שמור את שני ערכי קבוצת האבטחה שנוצרו על ידי הסקריפט הזה לשימוש בסקריפט `ByolSetup.ps1`.

   > [!NOTE]
   > ניתן להשבית יצירת קבוצת אבטחה בדייר שלך. במקרה כזה, יהיה צורך בהגדרה ידנית ומנהל מערכת Azure AD יצטרך[ להפוך יצירת קבוצת אבטחה לזמינה](/azure/active-directory/enterprise-users/groups-self-service-management).

1. בצע את `ByolSetup.ps1` ב- Windows PowerShell על ידי מתן מזהה המנוי של Azure המכיל את ה- Azure Data Lake Storage שלך, שם חשבון האחסון, שם קבוצת משאבים וערכי מזהי קבוצות האבטחה 'קורא' ו'משתתף'. פתח את הסקריפט של PowerShell בעורך כדי לסקור מידע נוסף ואת הלוגיקה שיושמה.

   סקריפט זה מוסיף את בקרת הגישה מבוססת התפקיד הנדרשת עבור שירות Microsoft Dataverse וכל אפליקציה עסקית מבוססת Dataverse. הסקריפט גם מעדכן את רשימת בקרת הגישה (ACL) בגורם המכיל של `customerinsights` עבור קבוצות האבטחה שנוצרו באמצעות הסקריפט `CreateSecurityGroups.ps1`. לקבוצה 'משתתף' ניתנת הרשאת *rwx* ולקבוצת 'קוראים' תינתן הרשאת *r-x* בלבד.

1. העתק את מחרוזת הפלט שנראית כך: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. הזן את מחרוזת הפלט שהועתקה לשדה **מזהה הרשאות** של שלב הגדרת התצורה של הסביבה עבור Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="אפשרויות הגדרת תצורה להפיכת שיתוף נתונים מ- Azure Data Lake Storage משלך באמצעות Microsoft Dataverse לזמין.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>הסרת חיבור קיים לסביבת Dataverse

כאשר מתחברים לסביבת Dataverse, משמעותה של הודעת השגיאה **ארגון CDS זה כבר מחובר למופע אחר של Customer Insights** היא שסביבת Dataverse כבר נמצאת בשימוש בסביבת Customer Insights. אפשר להסיר את החיבור הקיים כמנהל מערכת גלובלי בסביבת Dataverse. אכלוס השינויים עשוי לקחת כמה שעות.

1. עבור אל [Power Apps](https://make.powerapps.com).
1. בחר את הסביבה מבורר הסביבה.
1. עבור אל **פתרונות**.
1. הסר או מחק את הפתרון בשם **תוסף לכרטיס לקוח של Dynamics 365 Customer Insights ‏(Preview‏‏‏)**.

או

1. פתח את סביבת Dataverse.
1. עבור אל **הגדרות מתקדמות** > **פתרונות**.
1. הסר את ההתקנה של פתרון **CustomerInsightsCustomerCard**.

אם הסרת החיבור נכשלת בגלל יחסי תלות, עליך להסיר גם את יחסי התלות. למידע נוסף, ראה [הסרת יחסי תלות](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>ישויות פלט

ישויות פלט מסוימות מ- Customer Insights זמינות כטבלאות ב- Dataverse. הסעיפים הבאים מתארים את הסכימה הצפויה של טבלאות אלה.

- [CustomerProfile](#customerprofile)
- [ContactProfile](#contactprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [העשרה](#enrichment)
- [חיזוי](#prediction)
- [חברות בפלח](#segment-membership)

### <a name="customerprofile"></a>CustomerProfile

טבלה זו מכילה את פרופיל הלקוח המאוחד מ- Customer Insights. הסכימה עבור פרופיל לקוח מאוחד תלויה בישויות ובתכונות המשמשות בתהליך איחוד הנתונים. סכימת פרופיל לקוח מכילה בדרך כלל קבוצת משנה של תכונות מ[הגדרת Common Data Model של CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile). בתרחיש עסק לעסק, פרופיל הלקוח מכיל תיקי לקוח מאוחדים, והסכימה מכילה בדרך כלל תת-קבוצה של התכונות מה[הגדרת Common Data Model של תיק הלקוח](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/account).

### <a name="contactprofile"></a>ContactProfile

ContactProfile מכיל מידע מאוחד על איש קשר. אנשי קשר הם [אנשים שמופו לתיק לקוח](data-unification-contacts.md) בתרחיש מעסק לעסק.

| עמודה‬                       | Type                | תיאור‬‏‫‬     |
| ---------------------------- | ------------------- | --------------- |
|  BirthDate            | תאריך ושעה       |  תאריך הלידה של איש הקשר               |
|  עיר                 | טקסט |  העיר בכתובת של איש הקשר               |
|  ContactId            | טקסט |  מזהה פרופיל איש הקשר               |
|  ContactProfileId     | מזהה ייחודי   |  GUID עבור איש הקשר               |
|  CountryOrRegion      | טקסט |  המדינה/אזור של כתובת איש הקשר               |
|  מזהה לקוח           | טקסט |  מזהה תיק הלקוח שאליו ממופה איש הקשר               |
|  EntityName           | טקסט |  ישות שממנה מגיעים הנתונים                |
|  FirstName            | טקסט |  השם הפרטי של איש הקשר               |
|  מגדר               | טקסט |  המין איש הקשר               |
|  מזהה                   | טקסט |  GUID דטרמיניסטי מבוסס על `Identifier`               |
|  מזהה           | טקסט |  מזהה פנימי של פרופיל איש הקשר: `ContactProfile|CustomerId|ContactId`               |
|  JobTitle             | טקסט |  תיאור התפקיד של איש הקשר               |
|  LastName             | טקסט |  שם המשפחה של איש הקשר               |
|  PostalCode           | טקסט |  המיקוד בכתובת של איש הקשר               |
|  PrimaryEmail         | טקסט |  כתובת הדואר האלקטרוני של איש הקשר               |
|  PrimaryPhone         | טקסט |  מספר הטלפון של איש הקשר               |
|  מחוז      | טקסט |  המדינה או המחוז של כתובת איש הקשר               |
|  StreetAddress        | טקסט |  הכתובת הפיזית של איש הקשר               |

### <a name="alternatekey"></a>AlternateKey

הטבלה AlternateKey מכילה מפתחות של ישויות שהשתתפו בתהליך האיחוד.

|עמודה‬  |Type  |תיאור‬‏‫‬  |
|---------|---------|---------|
|DataSourceName    |טקסט         | שם מקור הנתונים. לדוגמה: `datasource5`        |
|EntityName        | טקסט        | שם הישות ב- Customer Insights. לדוגמה: `contact1`        |
|AlternateValue    |טקסט         |מזהה חלופי שממופה למזהה הלקוח. דוגמה: `cntid_1078`         |
|KeyRing           | טקסט        | ערך JSON  </br> דוגמה: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|מזהה לקוח         | טקסט        | מזהה פרופיל הלקוח המאוחד.         |
|AlternateKeyId     | מזהה ייחודי        |  GUID דטרמיניסטי AlternateKey מבוסס על `Identifier`      |
|מזהה |   טקסט      |   `DataSourceName|EntityName|AlternateValue`  </br> דוגמה: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

טבלה זו מכילה פעילויות של משתמשים הזמינות ב- Customer Insights.

| עמודה‬            | Type        | תיאור‬‏‫‬                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| מזהה לקוח        | טקסט      | מזהה פרופיל לקוח                                                                      |
| ActivityId        | טקסט      | מזהה פנימי של פעילות הלקוח (מפתח ראשי)                                       |
| SourceEntityName  | טקסט      | שם ישות המקור                                                                |
| SourceActivityId  | טקסט      | מפתח ראשי מישות המקור                                                       |
| ActivityType      | טקסט      | סוג הפעילות הסמנטית או שם הפעילות המותאמת אישית                                        |
| ActivityTimeStamp | תאריך ושעה    | חותמת זמן של פעילות                                                                      |
| שם             | טקסט      | כותרת או שם של הפעילות                                                               |
| תיאור‬‏‫‬       | טקסט      | תיאור פעילות                                                                     |
| כתובת URL               | טקסט      | קישור לכתובת URL חיצונית ספציפית לפעילות                                         |
| SemanticData      | טקסט | כוללת רשימה של זוגות מפתח-ערך עבור שדות מיפוי סמנטיים ספציפית לסוג הפעילות |
| RangeIndex        | טקסט      | חותמת זמן של Unix המשמשת למיון ציר זמן של פעילות ושאילתות טווח יעילות |
| UnifiedActivityId   | מזהה ייחודי | מזהה פנימי של פעילות הלקוח (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

טבלה זו מכילה את נתוני הפלט של מדדים מבוססי תכונות של לקוח.

| עמודה‬             | Type             | תיאור‬‏‫‬                 |
|--------------------|------------------|-----------------------------|
| מזהה לקוח         | טקסט           | מזהה פרופיל לקוח        |
| מדידות           | טקסט      | כולל רשימה של זוגות מפתח-ערך עבור השם והערכים של המדד ללקוח הנתון |
| מזהה | טקסט           | `Customer_Measure|CustomerId` |
| CustomerMeasureId | מזהה ייחודי     | מזהה פרופיל לקוח |

### <a name="enrichment"></a>העשרה

טבלה זו מכילה את הפלט של תהליך ההעשרה.

| עמודה‬               | Type             |  תיאור‬‏‫‬                                          |
|----------------------|------------------|------------------------------------------------------|
| מזהה לקוח           | טקסט           | מזהה פרופיל לקוח                                 |
| EnrichmentProvider   | טקסט           | שם הספק להעשרה                                  |
| EnrichmentType       | טקסט           | סוג ההעשרה                                      |
| ערכים               | טקסט      | רשימת התכונות שנוצרו על-ידי תהליך ההעשרה |
| EnrichmentId | מזהה ייחודי            | GUID דטרמיניסטי שנוצר מתוך `Identifier` |
| מזהה   | טקסט           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>חיזוי

טבלה זו מכילה את הפלט של חיזויי המודל.

| עמודה‬               | Type        | תיאור‬‏‫‬                                          |
|----------------------|-------------|------------------------------------------------------|
| מזהה לקוח           | טקסט      | מזהה פרופיל לקוח                                  |
| ModelProvider        | טקסט      | שם ספק המודל                                      |
| מודל                | טקסט      | שם מודל                                                |
| ערכים               | טקסט | רשימת התכונות שנוצרו על-ידי המודל |
| PredictionId | מזהה ייחודי       | GUID דטרמיניסטי שנוצר מתוך `Identifier` |
| מזהה   | טקסט      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>חברות בפלח

טבלה זו מכילה מידע על חברות בפלח של פרופילי הלקוחות.

| עמודה‬        | Type | תיאור‬‏‫‬                        |
|--------------------|--------------|-----------------------------|
| מזהה לקוח        | טקסט       | מזהה פרופיל לקוח        |
| SegmentProvider      | טקסט       | יישום שמפרסם את הפלחים.      |
| SegmentMembershipType | טקסט       | סוג הלקוח עבור רשומת חברות זו בפלח. תומך בסוגים מרובים, כגון לקוח, איש קשר או תיק לקוח. ברירת מחדל: לקוח  |
| פלחי שוק       | טקסט  | רשימת פלחים ייחודיים שפרופיל הלקוח חבר בהם      |
| מזהה  | טקסט   | המזהה הייחודי של רשומת החברות בפלח. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| SegmentMembershipId | מזהה ייחודי      | GUID דטרמיניסטי שנוצר מתוך `Identifier`          |

[!INCLUDE [footer-include](includes/footer-banner.md)]
