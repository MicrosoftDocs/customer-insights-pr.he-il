---
title: ייצוא נתוני Customer Insights אל Azure Synapse Analytics
description: למד כיצד להגדיר את החיבור ולייצא אל Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7ee57aa9e86ebf9bd1989d88750642f0b01bd4bf
ms.sourcegitcommit: f18635c29bb25d9e424a3f5825dc2696278450cf
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/30/2021
ms.locfileid: "6327365"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>ייצא נתונים אל Azure Synapse Analytics (גירסת Preview)

Azure Synapse הוא שירות ניתוח שמזרז את הזמן להשגת תובנה בין מחסני נתונים ומערכות Big Data. אתה יכול לעבד את נתוני Customer Insights ולהשתמש בהם ב- [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>דרישות מוקדמות

יש לעמוד בדרישות המוקדמות הבאות כדי להגדיר את החיבור מ- Customer Insights אל Azure Synapse.

> [!NOTE]
> הקפד להגדיר את כל **הקצאות התפקידים** כפי שתואר.  

## <a name="prerequisites-in-customer-insights"></a>דרישות מוקבמות ב- Customer Insights

* אתה בעל תפקיד **מנהל מערכת** בתובנות לגבי קהלים‬. למידע נוסף על [הגדרת הרשאות משתמש בתובנות לגבי קהלים‬](permissions.md#assign-roles-and-permissions)

ב- Azure: 

- מנוי פעיל של Azure.

- אם אתה משתמש בחשבון חדש של Azure Data Lake Storage Gen2, *מנהל שירות של תובנות לגבי קהלים‬* זקוק להרשאות מסוג **תורם נתונים של Blob אחסון**. למידע נוסף על [התחברות לחשבון Azure Data Lake Storage ‏Gen2 עם מנהל שירות Azure עבור תובנות לגבי קהלים](connect-service-principal.md). Data Lake Storage Gen2 **חייב להפעיל** [מרחב שמות הירארכי](/azure/storage/blobs/data-lake-storage-namespace).

- בקבוצת המשאבים שבו ממוקמת סביבת העבודה של Azure Synapse, יש להקצות לתפקידים *מנהל שירות* ו *משתמש עבור תובנות לגבי קהלים* הרשאות מסוג **קורא** לפחות. למידע נוסף, ראה [הקצאת תפקידי Azure באמצעות פורטל Azure](/azure/role-based-access-control/role-assignments-portal).

- ה *משתמש* זקוק להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- ה *זהות המנוהלת של סביבת העבודה של [Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* זקוקה להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage  Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse. למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- בסביבת העבודה של Azure Synapse, *מנהל השירות של תובנות לגבי קהלים* זקוק להקצאת תפקיד של **מנהל Synapse**. למידע נוסף, ראה [כיצד להגדיר בקרת גישה עבור סביבת העבודה שלך ב- Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>הגדרת החיבור וייצוא אל Azure Synapse

### <a name="configure-a-connection"></a>קביעת תצורה של חיבור

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Azure Synapse ‏Analytics** או בחר **הגדר** באריח **Azure Synapse Analytics** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה שם תצוגה. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר או חפש את המנוי שבו תרצה להשתמש בנתוני Customer Insights. ברגע שנבחר מנוי, ניתן גם לבחור באפשרויות **סביבת עבודה**,**חשבון אחסון** ו **גורם מכיל**.

1. בחר **שמור** כדי לשמור את החיבור.

### <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע **Azure Synapse Analytics**. אם אינך רואה שם מקטע זה, אין [חיבורים](connections.md) מסוג זה הזמינים עבורך.

1. ספק **שם תצוגה** ניתן לזיהוי עבור הייצוא שלך ו **שם מסד נתונים**.

1. בחר אילו ישויות ברצונך לייצא אל Azure Synapse Analytics.
   > [!NOTE]
   > אין תמיכה במקורות נתונים המבוססים על  [תיקיית Common Data Model](connect-common-data-model.md).

2. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).

### <a name="update-an-export"></a>עדכון ייצוא

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **ערוך** בייצוא שברצונך לעדכן.

   - **הוסף** או **הסר** ישויות מתוך הבחירה. אם מתבצעת הסרה של ישויות מהבחירה, הן לא נמחקות ממסד הנתונים של Synapse Analytics. עם זאת, פעולות רענון של נתונים עתידיים לא יעדכנו את הישויות שהוסרו באותו מסד נתונים.

   - **שינוי של שם מסד הנתונים** יוצר מסד נתונים חדש של Synapse Analytics. מסד הנתונים בעל השם שהוגדר בעבר לא יקבל עדכונים כלשהם בפעולות רענון עתידיות.
