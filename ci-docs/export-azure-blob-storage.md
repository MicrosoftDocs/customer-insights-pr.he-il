---
title: ייצוא נתונים ל- Blob אחסון של Azure ‏(Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל אחסון Blob.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22593ed05f403a40fe494e30f807b57658594f01
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195705"
---
# <a name="export-data-to-an-azure-blob-storage-preview"></a>ייצוא נתונים ל- Blob אחסון של Azure ‏(Preview)

אחסן את נתוני Customer Insights באחסון Blob או השתמש בו כדי להעביר את הנתונים שלך ליישומים אחרים.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- שם [חשבון Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ומפתח חשבון. כדי לחפש את השם ואת המפתח, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).
- [גורם מכיל של Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עבור Azure Blob Storage, בחר בין [רמת ביצועים סטנדרטית לרמת ביצועים Premium](/azure/storage/blobs/storage-blob-performance-tiers). אם תבחר ברמת הביצועים Premium, בחר [blobs של בלוקי Premium כסוג החשבון](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-blob-storage"></a>הגדרת חיבור ל- Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Azure Blob Storage**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן **שם חשבון**, **מפתח חשבון**, ו **גורם מכיל** עבור חשבון Blob Storage שלך.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

כדי לקבוע את תצורת הייצוא הזה, נדרשת לך [הרשאה](export-destinations.md#set-up-a-new-export) עבור סוג חיבור זה.

> [!IMPORTANT]
> אם הפעלת את [הגדרת המחיקה הזמנית](/azure/storage/blobs/soft-delete-blob-enable) עבור חשבון Azure Blob Storage, הייצוא ייכשל. כבה את המחיקה הרכה כדי לייצא נתונים לרכיבי Blob.

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע אחסון Blob של Azure. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את שם התיקייה עבור אחסון ה-Bob.

1. בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

נתונים מיוצאים מאוחסנים בגורם המכיל של Blob Storage שהגדרת. נתיבי התיקיות הבאים נוצרים באופן אוטומטי בגורם המכיל שלך:

- עבור ישויות מקור וישויות שנוצרו על-ידי המערכת:   
  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*  

  דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv
  
  > [!TIP]
  > ייצוא של ישויות המכילות כמות גדולה של נתונים יכול להוביל למספר קובצי CSV באותה תיקייה עבור כל פעולת ייצוא. פיצול פעולות הייצוא קורה מטעמי ביצועים כדי למזער את הזמן שלוקח לייצוא להסתיים.

- ה- model.json עבור הישויות שיוצאו נמצא ברמה *%ExportDestinationName%*.  
  
  דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json

[!INCLUDE [footer-include](includes/footer-banner.md)]
