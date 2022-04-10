---
title: ביקורת של Dynamics 365 Customer Insights עם Azure Monitor
description: למד כיצד לשלוח יומנים אל Microsoft Azure ‫Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 18fc072d129be6b4fc5470b1057f592dc2638216
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523670"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>העברת יומנים ב- Dynamics 365 Customer Insights עם Azure Monitor (תצוגה מקדימה)

Dynamics 365 Customer Insights מספק אינטגרציה ישירה עם Azure Monitor. יומני המשאבים של Azure Monitor מאפשרים לך לנטר ולשלוח יומנים אל [Azure Storage](https://azure.microsoft.com/services/storage/), [תכונת ניתוח יומן רישום של Azure](/azure/azure-monitor/logs/log-analytics-overview), או להזרים אותם אל [מרכזי אירועים של Azure‬](https://azure.microsoft.com/services/event-hubs/).

Customer Insights שולח את יומני האירועים הבאים:

- **אירועי ביקורת**
  - **APIEvent** - מאפשר מעקב אחר שינויים שנעשה באמצעות ממשק המשתמש Dynamics 365 Customer Insights.
- **אירועי תפעול**
  - **WorkflowEvent** - זרימת העבודה מאפשרת להגדיר [מקורות מידע](data-sources.md), [וכן לאחד](data-unification.md), [להעשיר](enrichment-hub.md) ולבסוף [לייצא](export-destinations.md) נתונים למערכות אחרות. כל השלבים הללו יכולים להיעשות בנפרד (למשל, הפעלת ייצוא בודד) או במתואם (למשל ,רענון נתונים ממקורות נתונים אשר מפעילים את תהליך האיחוד אשר ימשוך אליו העשרות נוספות ולאחר הסיום ייצא את הנתונים למערכת אחרת). לקבלת פרטים נוספים, ראה [סכימה של WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - כל קריאות ה- API למופע הלקוחות אל Dynamics 365 Customer Insights. לקבלת פרטים נוספים, ראה [סכימה של APIEvent](#api-event-schema)

## <a name="set-up-the-diagnostic-settings"></a>קביעת הגדרות האבחון

### <a name="prerequisites"></a>דרישות מוקדמות

כדי להגדיר את האבחון ב- Customer Insights, יש לעמוד בתנאים המוקדמים הבאים:

- יש לך [מנוי Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) פעיל.
- יש לך הרשאות [מנהל מערכת](permissions.md#admin) ב- Customer Insights.
- יש לך תפקידי **משתתף** ו **מנהל גישת משתמשים** במשאב היעד ב-Azure. המשאב יכול להיות סביבת עבודה של חשבון של Azure Storage, מרכז אירועים של Azure או תכונת ניתוח יומן רישום של Azure. לקבלת מידע נוסף, ראה [הוספה או הסרה של הקצאות תפקיד Azure באמצעות פורטל Azure](/azure/role-based-access-control/role-assignments-portal).
- עמידה ב[דרישות היעד](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) עבור Azure Storage, מרכזי האירועים של Azure או תכונת ניתוח יומן הרישום של Azure.
- יש לך לפחות תפקיד של **קורא** בקבוצת המשאבים שאליה שייך המשאב.

### <a name="set-up-diagnostics-with-azure-monitor"></a>הגדרת אבחון עם Azure Monitor

1. ב- Customer Insights, בחר **מערכת** > **אבחון** כדי לראות את יעדי האבחון שהוגדרו למופע זה.

1. בחר **הוסף יעד**.

   > [!div class="mx-imgBorder"]
   > ![חיבור אבחון](media/diagnostics-pane.png "חיבור אבחון")

1. ציין שם בשדה **'שם' עבור יעד האבחון**.

1. בחר את ה **דייר** של מנוי Azure עם משאב היעד ובחר **כניסה**.

1. בחר את **סוג המשאב** (חשבון אחסון, מרכז אירועים או ניתוח יומן).

1. בחר את ה **מנוי** עבור משאב היעד.

1. בחר את **קבוצת המשאבים** עבור משאב היעד.

1. בחר את **משאב**.

1. אשר את הצהרת **פרטיות נתונים ותאימות**.

1. בחר **התחבר למערכת** כדי להתחבר למשאב היעד. היומנים מתחילים להופיע ביעד כעבור 15 דקות, אם ה- API נמצא בשימוש ומייצר אירועים.

### <a name="remove-a-destination"></a>הסרת יעד

1. עבור אל **אבחון** > **מערכת**

1. בחר את יעד האבחון ברשימה.

1. בעמודה **פעולות**, בחר את הסמל **מחיקה**.

1. אשר את המחיקה כדי לעצור את העברת היומנים. המשאב במנוי Azure לא יימחק. תוכל לבחור את הקישור בעמודה **פעולות** כדי לפתוח את פורטל Azure עבור המשאב הנבחר ולמחוק אותו שם.

## <a name="log-categories-and-event-schemas"></a>קטגוריות יומנים וסכימות אירועים

בשלב זה [אירועי API](apis.md) ואירועי תזרימי עבודה נתמכים והקטגוריות והסכימות הבאות חלות.
סכימת היומן עוקבת אחר [הסכימה המשותפת של Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>קטגוריות

Customer Insights מספק שתי קטגוריות:

- **אירועי ביקורת**: [אירועי API](#api-event-schema) כדי לעקוב אחר שינויי תצורה בשירות. `POST|PUT|DELETE|PATCH` התפעול נכלל בקטגוריה זו.
- **אירועי תפעול**: [אירועי API](#api-event-schema) אוֹ [אירועי זרימת עבודה](#workflow-event-schema) שנוצרו במהלך השימוש בשירות.  לדוגמה, בקשות `GET` או אירועי ביצוע של זרימת עבודה.

## <a name="configuration-on-the-destination-resource"></a>תצורה במשאב היעד

בהתבסס על בחירתך בסוג המשאב, הצעדים הבאים יחולו באופן אוטומטי:

### <a name="storage-account"></a>חשבון אחסון

מנהל שירות של Customer Insights מקבל את הרשאת **משתתף בחשבון אחסון** עבור המשאב הנבחר ויוצר שני מיכלים תחת מרחב השמות שנבחר:

- `insight-logs-audit` כולל **אירועי ביקורת**
- `insight-logs-operational` כולל **אירועי תפעול**

### <a name="event-hub"></a>מרכז האירועים

מנהל השירות של Customer Insights מקבל את ההרשאה **בעל הנתונים של מרכזי אירועים של Azure** במשאב, והוא ייצור שני מרכזי אירועים תחת מרחב השמות שנבחר:

- `insight-logs-audit` כולל **אירועי ביקורת**
- `insight-logs-operational` כולל **אירועי תפעול**

### <a name="log-analytics"></a>יומני ניתוח

מנהל שירות של Customer Insights מקבל את הרשאת **משתתף בניתוח יומני רישום** עבור המשאב. היומנים יהיו זמינים תחת **יומנים** > **טבלאות** > **ניהול יומנים** בסביבת העבודה הנבחרת של ניתוח היומנים. הרחב את פתרון **ניהול יומנים** ואתר את הטבלאות `CIEventsAudit` ו- `CIEventsOperational`.

- `CIEventsAudit` כולל **אירועי ביקורת**
- `CIEventsOperational` כולל **אירועי תפעול**

תחת החלון **שאילתות**, הרחב את הפתרון **ביקורת** ואתר את השאילתות לדוגמה שהתקבלו בחיפוש אחר `CIEvents`.

## <a name="event-schemas"></a>סכימות אירועים

לאירועי API ולאירועי זרימת עבודה יש מבנה ופרטים משותפים שבהם הם שונים, ראה [סכימת אירוע API](#api-event-schema) או [סכימת אירוע זרימת עבודה](#workflow-event-schema).

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
|                 |

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
