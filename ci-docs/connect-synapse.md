---
title: התחבר למקור הנתונים Azure Synapse (תצוגה מקדימה)
description: השתמש במסד נתונים ב- Azure Synapse בתור מקור נתונים ב- Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 675fd03c44a7a7a492b111895d79c2e77f93a5b5
ms.sourcegitcommit: 4ba74816ebfa46412c64c40a61e1f31c4ccc40f2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9738157"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>התחבר למקור הנתונים Azure Synapse Analytics (תצוגה מקדימה)

Azure Synapse Analytics הוא שירות ניתוח ארגוני המאיץ את הזמן לתובנות בין מחסני נתונים ומערכות Big Data. Azure Synapse Analytics מפגיש את מיטב טכנולוגיות SQL המשמשות במחסני נתונים ארגוניים, טכנולוגיות Spark המשמשות ל-Big Data,‏ Data Explorer לניתוח יומנים וסדרות זמן, Pipelines לשילוב נתונים ו-ETL/ELT, ואינטגרציה עמוקה עם שירותי Azure אחרים כגון Power BI, Cosmos DB, ו- AzureML.

לקבלת מידע נוסף, עיין [ בסקירה הכללית של Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

> [!NOTE]
> סביבות Synapse Workspaces שבהן [חומת אש מופעלת](/azure/synapse-analytics/security/synapse-workspace-ip-firewall) אינן ניתמכות כרגע.
> [!IMPORTANT]
> הקפד להגדיר את כל **הקצאות התפקידים** כפי שתואר.  

**ב- Customer Insights**:

* יש לך תפקיד **מנהל מערכת** ב- Customer Insights. מידע נוסף בנושא [הרשאות משתמש ב- Customer Insights](permissions.md#add-users).

**ב- Azure**:

- מנוי פעיל של Azure.

- אם משתמשים בחשבון Azure Data Lake Storage Gen2, *מנהל השירות עבור Customer Insights* מסוג "Dynamics 365 AI for Customer Insights" צריך הרשאות **תורם נתונים של Blob אחסון**. מידע נוסף בנושא [חיבור ל- Azure Data Lake Storage באמצעות מנהל שירות עבור Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **חייב להפעיל** [מרחב שמות הירארכי](/azure/storage/blobs/data-lake-storage-namespace).

- בקבוצת המשאבים שבה נמצא Azure Synapse workspace, יש להקצות ל *מנהל השירות* מסוג "Dynamics 365 AI for Customer Insights" ול *משתמש Customer Insights* לפחות הרשאות **קורא**. למידע נוסף, ראה [הקצאת תפקידי Azure באמצעות פורטל Azure](/azure/role-based-access-control/role-assignments-portal).

- ה *משתמש* זקוק להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- ה *זהות המנוהלת של סביבת העבודה של [Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* זקוקה להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage  Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- ב- Azure Synapse Workspace, צריך להקצות ל *מנהל השירות עבור Customer Insights* מסוג "Dynamics 365 AI for Customer Insights" את התפקיד **מנהל מערכת של Synapse**. ה **משתמש** צריך תפקיד של לפחות **משתתף ב- Synapse** שהוקצה עבור סביבת העבודה. למידע נוסף, ראה [כיצד להגדיר בקרת גישה עבור סביבת העבודה שלך ב- Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- אם סביבת Customer Insights שלך מאחסנת נתונים [ב- Azure Data Lake Storage משלך](own-data-lake-storage.md), המשתמש שהגדיר את החיבור ל- Azure Synapse Analytics צריך לפחות את התפקיד המובנה **קורא** בחשבון Data Lake Storage. למידע נוסף, ראה [הקצאת תפקידי Azure באמצעות פורטל Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>התחבר אל מסד הנתונים של Data Lake ב- Azure Synapse Analytics

1. עבור אל **נתונים** > **מקורות נתונים**.

1. בחר **הוסף מקור נתונים**.

1. בחר את שיטת **Azure Synapse Analytics (תצוגה מקדימה)**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="תיבת דו-שיח לחיבור לנתוני Synapse Analytics":::
  
1. הזן **שם** עבור מקור הנתונים ו **תיאור** אופציונלי.

1. בחר [חיבור זמין](connections.md) אל Azure Synapse Analytics או [צור חדש](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. בחר **מסד הנתונים** מסביבת העבודה המחוברת בחיבור Azure Synapse Analytics שנבחר ובחר **הבא**. נכון לעכשיו, אנו תומכים רק בסוג מסד הנתונים *מסד נתונים מסוג אגם*.

1. בחר את הישויות לעיבוד ממסד הנתונים המחובר ובחר **הבא**.

1. לחלופין, בחר את ישויות הנתונים כדי לאפשר יצירת פרופיל נתונים.

1. בחר **שמור** כדי להחיל את הבחירה שלך ולהתחיל את קליטת הנתונים ממקור הנתונים החדש שלך המקושר לטבלאות מסד הנתונים של Lake ב- Azure Synapse Analytics. הדף **מקורות נתונים** נפתח ומציג את מקור נתונים החדש במצב **ריענון**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

טעינת נתונים עשויה להימשך זמן מה. לאחר רענון מוצלח, ניתן לסקור את הנתונים שעובדו בדף [**ישויות**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
