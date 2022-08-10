---
title: ייצוא נתונים אל Azure Synapse Analytics ‏(Preview)
description: למד כיצד להגדיר את תצורת החיבור אל Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196395"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>ייצוא נתונים אל Azure Synapse Analytics ‏(Preview)

Azure Synapse הוא שירות ניתוח שמזרז את הזמן להשגת תובנה בין מחסני נתונים ומערכות Big Data. אתה יכול לעבד את נתוני Customer Insights ולהשתמש בהם ב- [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

> [!NOTE]
> הקפד להגדיר את כל **הקצאות התפקידים** כפי שתואר.

- ב- Customer Insights, חשבון המשתמש שלך ב- Azure Active Directory ‏(AD) חייב לכלול [תפקיד מנהל מערכת](permissions.md#assign-roles-and-permissions).

ב- Azure:

- מנוי פעיל של Azure.

- אם משתמשים בחשבון חדש של Azure Data Lake Storage Gen2, [מנהל השירות עבור Customer Insights](connect-service-principal.md) כולל הרשאות **תורם נתונים של Blob אחסון**. Data Lake Storage Gen2 **חייב להפעיל** [מרחב שמות הירארכי](/azure/storage/blobs/data-lake-storage-namespace).

- בקבוצת המשאבים שבה נמצא Azure Synapse Workspace, יש להקצות ל *מנהל השירות* ולמשתמש *Azure AD, שיש להם הרשאות מנהל מערכת ב- Customer Insights*, לפחות [הרשאות](/azure/role-based-access-control/role-assignments-portal) **קורא**.

- משתמש *Azure AD עם הרשאות מנהל מערכת ב- Customer Insights* כולל הרשאות **תורם נתונים של Blob אחסון** בחשבון Gen2 של Azure Data Lake Storage שבו הנתונים ממוקמים ומקושרים ל- Azure Synapse Workspace. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- ה *זהות המנוהלת של  [ workspaceAzure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* כולל הרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage  Gen2 שבו הנתונים ממוקמים ומקושרים אל workspace Azure Synapse. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- ב- Azure Synapse Workspace, ל *מנהל השירות עבור Customer Insights* [מוקצה התפקיד](/azure/synapse-analytics/security/how-to-set-up-access-control) **מנהל מערכת של Synapse**.

## <a name="set-up-connection-to-azure-synapse"></a>הגדרת חיבור ל- Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Azure Synapse Analytics**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר או חפש את המנוי שבו תרצה להשתמש בנתוני Customer Insights. ברגע שנבחר מנוי, ניתן גם לבחור באפשרויות **סביבת עבודה**,**חשבון אחסון** ו **גורם מכיל**.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)] כדי להגדיר את הייצוא עם חיבור משותף, צריך לפחות הרשאות **משתתף** ב- Customer Insights.

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע Azure Synapse Analytics. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. ספק **שם תצוגה** ניתן לזיהוי עבור הייצוא שלך ו **שם מסד נתונים**. הייצוא ייצור [אגם מסד נתונים חדש של Azure Synapse](/azure/synapse-analytics/database-designer/concepts-lake-database) במרחב העבודה המוגדר בחיבור.

1. בחר אלו ישויות ברצונך לייצא אל Azure Synapse Analytics.
   > [!NOTE]
   > אין תמיכה במקורות נתונים המבוססים על  [תיקיית Common Data Model](connect-common-data-model.md).

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

כדי לבצע שאילתה על נתונים שיוצאו ל- Synapse Analytics, צריך גישה של **קורא נתונים של Blob אחסון** לאחסון היעד בסביבת העבודה של פעולות הייצוא.

## <a name="update-an-export"></a>עדכון ייצוא

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **ערוך** בייצוא שברצונך לעדכן.

   - **הוסף** או **הסר** ישויות מתוך הבחירה. אם מתבצעת הסרה של ישויות מהבחירה, הן לא נמחקות ממסד הנתונים של Synapse Analytics. עם זאת, פעולות רענון של נתונים עתידיים לא יעדכנו את הישויות שהוסרו באותו מסד נתונים.

   - **שינוי של שם מסד הנתונים** יוצר מסד נתונים חדש של Synapse Analytics. מסד הנתונים בעל השם שהוגדר בעבר לא יקבל עדכונים כלשהם בפעולות רענון עתידיות.

[!INCLUDE [footer-include](includes/footer-banner.md)]
