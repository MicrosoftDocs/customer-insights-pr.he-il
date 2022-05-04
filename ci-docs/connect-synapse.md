---
title: קלוט נתונים מתוך Azure Synapse Analytics
description: השתמש במסד נתונים ב- Azure Synapse בתור מקור נתונים ב- Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7c758dccf7ea34dd7b8f80d05eff1ed12030526f
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646867"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>התחבר למקור הנתונים Azure Synapse (תצוגה מקדימה)

Azure Synapse Analytics הוא שירות ניתוח ארגוני המאיץ את הזמן לתובנות בין מחסני נתונים ומערכות Big Data. Azure Synapse Analytics מפגיש את מיטב טכנולוגיות SQL המשמשות במחסני נתונים ארגוניים, טכנולוגיות Spark המשמשות ל-Big Data,‏ Data Explorer לניתוח יומנים וסדרות זמן, Pipelines לשילוב נתונים ו-ETL/ELT, ואינטגרציה עמוקה עם שירותי Azure אחרים כגון Power BI, Cosmos DB, ו- AzureML.

לקבלת מידע נוסף, עיין [ בסקירה הכללית של Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>דרישות מוקדמות

הדרושות המוקדמות הבאות חייבות להתקיים כדי להגדיר את החיבור מ- Dynamics 365 Customer Insights אל Azure Synapse.

> [!IMPORTANT]
> הקפד להגדיר את כל **הקצאות התפקידים** כפי שתואר.  

## <a name="prerequisites-in-customer-insights"></a>דרישות מוקבמות ב- Customer Insights

* יש לך תפקיד **מנהל מערכת** ב- Customer Insights. מידע נוסף בנושא [הרשאות משתמש ב- Customer Insights](permissions.md#assign-roles-and-permissions).

ב- Azure: 

- מנוי פעיל של Azure.

- אם משתמשים בחשבון Gen2 חדש של Azure Data Lake Storage, *מנהל השירות עבור Customer Insights* צריך הרשאות **תורם נתונים של Blob אחסון**. מידע נוסף בנושא [חיבור ל- Azure Data Lake Storage באמצעות מנהל שירות עבור Customer Insights](connect-service-principal.md). Data Lake Storage Gen2 **חייב להפעיל** [מרחב שמות הירארכי](/azure/storage/blobs/data-lake-storage-namespace).

- בקבוצת המשאבים שבה נמצא Azure Synapse workspace, יש להקצות ל *מנהל השירות* ול *משתמש Customer Insights* לפחות הרשאות **קורא**. למידע נוסף, ראה [הקצאת תפקידי Azure באמצעות פורטל Azure](/azure/role-based-access-control/role-assignments-portal).

- ה *משתמש* זקוק להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- ה *זהות המנוהלת של סביבת העבודה של [Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* זקוקה להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage  Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- בסביבת העבודה של Azure Synapse, צריך להקצות ל *מנהל השירות עבור Customer Insights* את התפקיד **מנהל מערכת של Synapse**. למידע נוסף, ראה [כיצד להגדיר בקרת גישה עבור סביבת העבודה שלך ב- Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>התחבר אל מסדי נתונים של Data Lake ב- Azure Synapse Analytics

1. עבור אל **נתונים** > **מקורות נתונים**.

1. בחר **הוסף מקור נתונים**.

1. בחר את שיטת **Azure Synapse Analytics (תצוגה מקדימה)**.

1. הזן **שם** עבור מקור נתונים ובחר **הבא** כדי ליצור את מקור הנתונים. 

1. בחר [חיבור זמין](connections.md) אל Azure Synapse Analytics או צור חדש.

1. בחר **מסד הנתונים של Lake** מסביבת העבודה המחוברת בחיבור Azure Synapse Analytics שנבחר ובחר **הבא**.

1. בחר את הישויות לקליטה ממסד הנתונים המחובר. 

1. לחלופין, בחר את ישויות הנתונים כדי לאפשר יצירת פרופיל נתונים. 

1. בחר **שמור** כדי להחיל את הבחירה שלך ולהתחיל את קליטת הנתונים ממקור הנתונים החדש שלך המקושר לטבלאות מסד הנתונים של Lake ב- Azure Synapse Analytics.
