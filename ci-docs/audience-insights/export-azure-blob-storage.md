---
title: ייצוא נתוני Customer Insights אל אחסון Blob של Azure
description: למד כיצד להגדיר את החיבור ולייצא אל אחסון Blob.
ms.date: 06/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e38fc06a948178fcbc62c08a4cf4816e1d030e79
ms.sourcegitcommit: 656b1a6cdff37ba4f808311fd0327ab38e02ed13
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/30/2021
ms.locfileid: "6318300"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>ייצוא רשימת פלחים ונתונים אחרים לאחסון Blob של Azure‏ (Preview)

אחסן את נתוני Customer Insights באחסון Blob או השתמש בו כדי להעביר את הנתונים שלך ליישומים אחרים.

## <a name="set-up-the-connection-to-blob-storage"></a>הגדרת החיבור ל- Blob Storage

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **אחסון Blob של Azure** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן **שם חשבון**, **מפתח חשבון**, ו **גורם מכיל** עבור חשבון Blob Storage שלך.
    - לקבלת מידע נוסף אודות האופן שבו ניתן למצוא שם חשבון ומפתח חשבון של Blob Storage, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).
    - כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. בחר **שמור** כדי להשלים את החיבור. 

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> אם הפעלת את הגדרת המחיקה הרכה עבור חשבון Azure Blob Storage, הייצוא ייכשל. כבה את המחיקה הרכה כדי לייצא נתונים לרכיבי Blob. למידע נוסף, ראה [הפעלת מחיקה רכה של Blob](/azure/storage/blobs/soft-delete-blob-enable.md)

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע אחסון Blob של Azure. אם אינך רואה את שם הפלח הזה, אין קשרים זמינים עבורך מסוג זה.

1. בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).     

באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 

נתונים מיוצאים מאוחסנים בגורם המכיל של Blob Storage שהגדרת. נתיבי התיקיות הבאים נוצרים באופן אוטומטי בגורם המכיל שלך:

- עבור ישויות מקור וישויות שנוצרו על-ידי המערכת:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - דוגמה: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- ה- model.json עבור הישויות המיוצאות יהיה ברמת %ExportDestinationName%.  
  - דוגמה: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
