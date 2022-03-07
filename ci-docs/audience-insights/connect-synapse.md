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
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356023"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>התחבר למקור הנתונים Azure Synapse (תצוגה מקדימה)

Azure Synapse Analytics הוא שירות ניתוח ארגוני המאיץ את הזמן לתובנות בין מחסני נתונים ומערכות Big Data. Azure Synapse Analytics מפגיש את מיטב טכנולוגיות SQL המשמשות במחסני נתונים ארגוניים, טכנולוגיות Spark המשמשות ל-Big Data,‏ Data Explorer לניתוח יומנים וסדרות זמן, Pipelines לשילוב נתונים ו-ETL/ELT, ואינטגרציה עמוקה עם שירותי Azure אחרים כגון Power BI, Cosmos DB, ו- AzureML.

לקבלת מידע נוסף, עיין [ בסקירה הכללית של Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>דרישות מוקדמות

יש לעמוד בדרישות המוקדמות הבאות כדי להגדיר את החיבור מ- Customer Insights אל Azure Synapse.

> [!IMPORTANT]
> הקפד להגדיר את כל **הקצאות התפקידים** כפי שתואר.  

## <a name="prerequisites-in-customer-insights"></a>דרישות מוקבמות ב- Customer Insights

* יש לך תפקיד **מנהל מערכת** ב- Customer Insights. קבל מידע נוסף אודות [הרשאות משתמש בתובנות קהל](permissions.md#assign-roles-and-permissions).

ב- Azure: 

- מנוי פעיל של Azure.

- אם אתה משתמש בחשבון חדש של Azure Data Lake Storage Gen2, *מנהל שירות של תובנות לגבי קהלים‬* זקוק להרשאות מסוג **תורם נתונים של Blob אחסון**. למידע נוסף על [חיבור ל- Azure Data Lake Storage עם מנהל שירות לתובנות לגבי קהל](connect-service-principal.md). Data Lake Storage Gen2 **חייב להפעיל** [מרחב שמות הירארכי](/azure/storage/blobs/data-lake-storage-namespace).

- בקבוצת המשאבים שבו ממוקמת סביבת העבודה של Azure Synapse, יש להקצות לתפקידים *מנהל שירות* ו *משתמש עבור תובנות לגבי קהלים* הרשאות מסוג **קורא** לפחות. למידע נוסף, ראה [הקצאת תפקידי Azure באמצעות פורטל Azure](/azure/role-based-access-control/role-assignments-portal).

- ה *משתמש* זקוק להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- ה *זהות המנוהלת של סביבת העבודה של [Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* זקוקה להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage  Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- בסביבת העבודה של Azure Synapse, *מנהל השירות של תובנות לגבי קהלים* זקוק להקצאת תפקיד של **מנהל Synapse**. למידע נוסף, ראה [כיצד להגדיר בקרת גישה עבור סביבת העבודה שלך ב- Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

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
