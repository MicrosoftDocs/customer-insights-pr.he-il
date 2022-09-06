---
title: ייצוא יומני אבחון (Preview)
description: למד כיצד לשלוח יומנים אל Microsoft Azure ‫Monitor.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: c573c46fda895d36d29712e75fe28b261c9b399a
ms.sourcegitcommit: 0b5bfe0145dbd325fa518df4561d6a0a9a352264
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/25/2022
ms.locfileid: "9352802"
---
# <a name="export-diagnostic-logs-preview"></a>ייצוא יומני אבחון (Preview)

העברת יומני Customer Insights באמצעות Azure Monitor. יומני המשאבים של Azure Monitor מאפשרים לך לנטר ולשלוח יומנים אל [Azure Storage](https://azure.microsoft.com/services/storage/), [תכונת ניתוח יומן רישום של Azure](/azure/azure-monitor/logs/log-analytics-overview), או להזרים אותם אל [מרכזי אירועים של Azure‬](https://azure.microsoft.com/services/event-hubs/).

Customer Insights שולח את יומני האירועים הבאים:

- **אירועי ביקורת**
  - **APIEvent** - מאפשר מעקב אחר שינויים באמצעות ממשק המשתמש Dynamics 365 Customer Insights.
- **אירועי תפעול**
  - **WorkflowEvent** - מאפשרת להגדיר [מקורות מידע](data-sources.md), [לאחד](data-unification.md), [להעשיר](enrichment-hub.md) ולבסוף [לייצא](export-destinations.md) נתונים למערכות אחרות. ניתן לבצע את השלבים הללו בנפרד (לדוגמה, להפעיל ייצוא בודד). הם יכולים גם לפעול בתיאום (לדוגמה, רענון נתונים ממקורות נתונים שמפעיל את תהליך האיחוד, שימשוך העשרות וייצא את הנתונים למערכת אחרת). לפרטים נוספים, ראה [סכימה של WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - שולח את כל קריאות ה- API של מופע הלקוחות אל Dynamics 365 Customer Insights. לפרטים נוספים, ראה [סכימה של APIEvent](#api-event-schema)

## <a name="set-up-the-diagnostic-settings"></a>קביעת הגדרות האבחון

### <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- מנוי [Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) פעיל.
- הרשאות [מנהל מערכת](permissions.md#admin) ב- Customer Insights.
- משאב חוקי ב- Azure שעוקב אחר [דרישות היעד](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) עבור Azure Storage, מרכז האירועים של Azure או Azure Log Analytics.
- [תפקיד משתתף ומנהל גישת משתמשים](/azure/role-based-access-control/role-assignments-portal) במשאב היעד ב-Azure. המשאב יכול להיות חשבון של Azure Data Lake Storage, מרכז אירועים של Azure או סביבת עבודה ניתוח יומן רישום של Azure. הרשאה זו נחוצה בזמן קביעת הגדרות האבחון ב- Customer Insights, אך ניתן לשנות אותה לאחר הגדרה מוצלחת.
- לפחות תפקיד של **קורא** בקבוצת המשאבים שאליה שייך המשאב.

### <a name="set-up-diagnostics-with-azure-monitor"></a>הגדרת אבחון עם Azure Monitor

1. ב- Customer Insights, עבור אל **ניהול** > **מערכת** ובחר את הכרטיסיה **אבחון**.

1. בחר **הוסף יעד**.

   :::image type="content" source="media/diagnostics-pane.png" alt-text="חיבור אבחון.":::

1. ציין שם בשדה **'שם' עבור יעד האבחון**.

1. בחר את **סוג המשאב** (חשבון אחסון, מרכז אירועים או Log Analytics).

1. בחר את ה **מינוי**, **קבוצת המשאבים**, ו **המשׁאב** עבור משאב היעד. מידע נוסף: [תצורה במשאב היעד](#configuration-on-the-destination-resource) לקבלת הרשאות ופרטי יומן רישום.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר למערכת** כדי להתחבר למשאב היעד. היומנים מתחילים להופיע ביעד כעבור 15 דקות, אם ה- API נמצא בשימוש ומייצר אירועים.

## <a name="configuration-on-the-destination-resource"></a>תצורה במשאב היעד

בהתבסס על סוג המשאב שבחרת, השינויים הבאים יתרחשו באופן אוטומטי:

### <a name="storage-account"></a>חשבון אחסון

מנהל שירות של Customer Insights מקבל את הרשאת **משתתף בחשבון אחסון** עבור המשאב הנבחר ויוצר שני מיכלים תחת מרחב השמות שנבחר:

- `insight-logs-audit` כולל **אירועי ביקורת**
- `insight-logs-operational` כולל **אירועי תפעול**

### <a name="event-hub"></a>מרכז האירועים

מנהל השירות של Customer Insights מקבל את ההרשאה **בעל הנתונים של מרכזי אירועים של Azure** במשאב, והוא יוצר שני מרכזי אירועים תחת מרחב השמות שנבחר:

- `insight-logs-audit` כולל **אירועי ביקורת**
- `insight-logs-operational` כולל **אירועי תפעול**

### <a name="log-analytics"></a>יומני ניתוח

מנהל שירות של Customer Insights מקבל את הרשאת **משתתף בניתוח יומני רישום** עבור המשאב. היומנים זמינים תחת **יומנים** > **טבלאות** > **ניהול יומנים** בסביבת העבודה הנבחרת של ניתוח היומנים. הרחב את פתרון **ניהול יומנים** ואתר את הטבלאות `CIEventsAudit` ו- `CIEventsOperational`.

- `CIEventsAudit` כולל **אירועי ביקורת**
- `CIEventsOperational` כולל **אירועי תפעול**

תחת החלון **שאילתות**, הרחב את הפתרון **ביקורת** ואתר את השאילתות לדוגמה שהתקבלו בחיפוש אחר `CIEvents`.

## <a name="remove-a-diagnostics-destination"></a>הסרת יעד אבחון

1. עבור אל **מנהל מערכת** > **מערכת**, ובחר בכרטיסיה **אבחון**.

1. בחר את יעד האבחון ברשימה.

   > [!TIP]
   > הסרת היעד עוצרת את העברת היומן, אך אינה מוחקת את המשאב במנוי Azure. כדי למחוק את המשאב ב- Azure, בחר את הקישור בעמודה **פעולות** כדי לפתוח את פורטל Azure עבור המשאב הנבחר ולמחוק אותו שם. אחר כך מחק יעד האבחון.

1. בעמודה **פעולות**, בחר את הסמל **מחיקה**.

1. אשר את המחיקה כדי להסיר את היעד ולעצור את העברת היומנים.

## <a name="log-categories-and-event-schemas"></a>קטגוריות יומנים וסכימות אירועים

בשלב זה [אירועי API](apis.md) ואירועי תזרימי עבודה נתמכים והקטגוריות והסכימות הבאות חלות.
סכימת היומן עוקבת אחר [הסכימה המשותפת של Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>קטגוריות

Customer Insights מספק שתי קטגוריות:

- **אירועי ביקורת**: [אירועי API](#api-event-schema) כדי לעקוב אחר שינויי תצורה בשירות. `POST|PUT|DELETE|PATCH` התפעול נכלל בקטגוריה זו.
- **אירועי תפעול**: [אירועי API](#api-event-schema) אוֹ [אירועי זרימת עבודה](#workflow-event-schema) שנוצרו במהלך השימוש בשירות.  לדוגמה, בקשות `GET` או אירועי ביצוע של זרימת עבודה.

## <a name="event-schemas"></a>סכימות אירועים

לאירועי API ואירועי זרימת עבודה יש מבנה משותף, אך עם כמה הבדלים. לפרטים נוספים, ראה [סכימה ה-API של האירוע](#api-event-schema) או [סכמה של זרימת העבודה של אירוע](#workflow-event-schema).

### <a name="api-event-schema"></a>סכימת אירוע API

| שדה             | DataType  | נדרש/אופציונלי | Description       | דוגמה        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | חותמת זמן | חובה          | חותמת הזמן של האירוע (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | חובה          | מזהה משאב של המופע שפלט את האירוע         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | חובה          | שם הפעולה המיוצגת על ידי אירוע זה.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | חובה          | קטגוריית יומן של האירוע. `Operational` או `Audit`. כל בקשות POST/PUT/PATCH/DELETE של HTTP מתויגות עם `Audit`, וכל השאר עם `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | חובה          | מצב האירוע. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | אופציונלי          | מצב התוצאות של האירוע. אם הפעולה מתאימה לקריאת REST API, זהו קוד המצב של HTTP.        | `200`             |
| `durationMs`      | Long      | אופציונלי          | משך הפעולה באלפיות שנייה.     | `133`     |
| `callerIpAddress` | String    | אופציונלי          | כתובת ה-IP של הקורא, אם הפעולה מתאימה לקריאת API שמגיעה מכתובת IP זמינה לציבור.                                                 | `144.318.99.233`         |
| `identity`        | String    | אופציונלי          | אובייקט JSON המתאר את זהות המשתמש או היישום שעשו את הפעולה.       | ראה המקטע [זהות](#identity-schema).     |  
| `properties`      | String    | אופציונלי          | אובייקט JSON עם מאפיינים נוספים עבור הקטגוריה המסוימת של האירועים.      | ראה המקטע [מאפיינים](#api-properties-schema).    |
| `level`           | String    | חובה          | רמת החומרה של האירוע.    | `Informational`, `Warning`, `Error`, או `Critical`.           |
| `uri`             | String    | אופציונלי          | כתובת URI מוחלטת של הבקשה.    |               |

#### <a name="identity-schema"></a>סכימת זהות

לאובייקט JSON `identity` יש את המבנה הבא

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| שדה                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | תפקיד שהוקצה למשתמש או ליישום. לקבלת מידע נוסף, ראה [הרשאות משתמש](permissions.md).                                     |
| `Authorization.RequiredRoles` | תפקידים נדרשים לביצוע הפעולה. התפקיד `Admin` רשאי לעשות את כל הפעולות.                                                    |
| `Claims`                      | תביעות של המשתמש או אסימון JSON web token‏ (JWT) של היישום. מאפייני התביעה משתנים בהתאם לארגון ולתצורת Azure Active Directory. |

#### <a name="api-properties-schema"></a>סכימת מאפייני API

ל[אירועי API](apis.md) יש את המאפיינים הבאים.

| שדה                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | תמיד `ApiEvent`, לסימון אירוע היומן כאירוע API.                                                                 |
| `properties.userAgent`       | סוכן הדפדפן שולח את הבקשה או את `unknown`.                                                                        |
| `properties.method`          | שיטת ה- HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | נתיב יחסי של הבקשה.                                                                                          |
| `properties.origin`          | כתובת URI המציינת מאיפה הגיעה בקשת הבאה או `unknown`.                                                                  |
| `properties.operationStatus` | `Success` לקוד מצב HTTP קטן מ- 400 <br> `ClientError` לקוד מצב HTTP קטן מ- 500 <br> `Error` לקוד מצב HTTP גדול או שווה ל- 500 |
| `properties.tenantId`        | מזהה ארגון                                                                                                        |
| `properties.tenantName`      | שם הארגון.                                                                                              |
| `properties.callerObjectId`  | Azure Active Directory ObjectId של הקורא.                                                                         |
| `properties.instanceId`      | Customer Insights `instanceId`                                                                                         |

### <a name="workflow-event-schema"></a>סכימת אירוע זרימת עבודה

זרימת העבודה מכילה מספר שלבים. [קליטת מקורות הנתונים](data-sources.md), [איחוד](data-unification.md), [העשרה](enrichment-hub.md) ו[ייצוא](export-destinations.md) של הנתונים. כל השלבים הללו יכולים לפעול בנפרד או במתואם עם התהליכים הבאים.

#### <a name="operation-types"></a>סוגי פעולה

| OperationType     | הוסף קבוצה                                     |
| ----------------- | ----------------------------------------- |
| קליטה         | [מקורות נתונים](data-sources.md)           |
| DataPreparation   | [מקורות נתונים](data-sources.md)           |
| מיפוי               | [איחוד נתונים](data-unification.md)   |
| התאמה             | [איחוד נתונים](data-unification.md)   |
| מזג             | [איחוד נתונים](data-unification.md)   |
| ProfileStore      | [פרופילי לקוחות](customer-profiles.md) |
| חיפוש            | [פרופילי לקוחות](customer-profiles.md) |
| פעילות          | [פעילויות](activities.md)                  |
| AttributeMeasures | [פלחים ואמצעים](segments.md)      |
| EnityMeasures    | [פלחים ואמצעים](segments.md)      |
| מדידות          | [פלחים ואמצעים](segments.md)      |
| פילוח      | [פלחים ואמצעים](segments.md)      |
| העשרה        | [העשרה](enrichment-hub.md)                                          |
| בינה      | [חיזויים](predictions-overview.md)                                          |
| AiBuilder         | [חיזויים](predictions-overview.md)                                          |
| תובנות          | [חיזויים](predictions-overview.md)                                          |
| Export            | [פעולות ייצוא](export-destinations.md)                                          |
| ModelManagement   | [חיזויים](custom-models.md)                                           |
| קשר גומלין      | [איחוד נתונים](relationships.md)                                           |

#### <a name="field-description"></a>תיאור שדה

| שדה           | DataType  | נדרש/אופציונלי | Description                                                                                                                                                   | דוגמה                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | חותמת זמן | חובה          | חותמת הזמן של האירוע (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | חובה          | מזהה משאב של המופע שפלט את האירוע.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | חובה          | שם הפעולה המיוצגת על ידי אירוע זה. `{OperationType}.[WorkFlow|Task][Started|Completed]`. ראה [סוגי פעולות](#operation-types) להשוואה. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | חובה          | קטגוריית יומן של האירוע. תמיד `Operational` עבור אירועי זרימת עבודה                                                                                           | `Operational`                                                                                                                                                            |
| `resultType`    | String    | חובה          | מצב האירוע. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Long      | אופציונלי          | משך הפעולה באלפיות שנייה.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | אופציונלי          | אובייקט JSON עם מאפיינים נוספים עבור הקטגוריה המסוימת של האירועים.                                                                                        | ראה מקטע משנה [מאפייני זרימת עבודה](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | חובה          | רמת החומרה של האירוע.                                                                                                                                  | `Informational`, ‏`Warning` או `Error`                                                                                                                                   |

#### <a name="workflow-properties-schema"></a>סכימת זרימת עבודה

לאירועי זרימת עבודה יש את המאפיינים הבאים.

| שדה              | Workflow | משימה | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | כן      | כן  | תמיד `WorkflowEvent`, לסימון אירוע היומן כאירוע זרימת עבודה.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | כן      | כן  | מזהה הפעלת זרימת העבודה. לכל אירועי של זרימת עבודה ומשימה במסגרת ביצוע זרימת העבודה יש אותו `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | כן      | כן  | מזהה הפעולה, ראה [סוגי פעולה](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | כן      | כן   | זרימת עבודה בלבד. מספר המשימות שזרימת העבודה מפעילה.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | כן      | Yes   | אופציונלי. אירועי זרימת עבודה בלבד. Azure Active Directory[ObjectId של המשתמש](/azure/marketplace/find-tenant-object-id#find-user-object-id) שהפעיל את זרימת העבודה, ראה גם `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | כן      | Yes   | רענון של `full` או `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | כן      | Yes   | `OnDemand` או `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | כן      | Yes   | `Running` או `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | כן      | כן  | חותמת זמן UTC: `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | כן      | כן  | חותמת זמן UTC: `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | כן      | כן  | חותמת זמן UTC: `yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | כן      | כן  | Customer Insights `instanceId`                                                                                                                                                                                                                              |  
| `properties.identifier`                      | Yes       | כן  | - עבור OperationType = `Export`, המזהה הוא GUID של תצורת הייצוא. <br> - עבור OperationType = `Enrichment`, זהו ה- GUID של ההעשרה <br> - עבור OperationType `Measures` ו- `Segmentation`, המזהה הוא שם הישות. |
| `properties.friendlyName`                    | Yes       | כן  | שם ידידותי למשתמש של הייצוא או של הישות המעובדת.                                                                                                                                                                                           |
| `properties.error`                           | Yes       | כן  | אופציונלי. הודעת שגיאה עם יותר פרטים.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | Yes       | כן  | אופציונלי. עבור OperationType `Export` בלבד. מזהה את סוג הייצוא. לקבלת מידע נוסף, ראה [סקירת יעדי ייצוא](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | Yes       | כן  | אופציונלי. עבור OperationType `Export` בלבד. כולל רשימה של ישויות מוגדרות בייצוא.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | Yes       | כן  | אופציונלי. עבור OperationType `Export` בלבד. הודעה מפורטת עבור הייצוא.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | Yes       | כן  | אופציונלי. עבור OperationType `Segmentation` בלבד. מציין את סך הכל מספרי החברים שיש לפלח.                                                                                                                                                    |

[!INCLUDE [footer-include](includes/footer-banner.md)]
