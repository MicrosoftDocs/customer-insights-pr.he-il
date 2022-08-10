---
title: ייצוא ל- Azure Data Lake Storage של Gen2‏ (Preview)
description: למד כיצד לקבוע את תצורת החיבור אל Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196441"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>ייצוא ל- Azure Data Lake Storage של Gen2‏ (Preview)

אחסן את נתוני Customer Insights בחשבון Data Lake Storage Gen2 או השתמש בו כדי להעביר את הנתונים שלך ליישומים אחרים.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון אחסון לשימוש עם Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). כדי לחפש את שם החשבון ואת המפתח, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).
- [גורם מכיל של Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עבור Azure Data Lake Storage Gen2, בחר בין [רמת ביצועים סטנדרטית לרמת ביצועים Premium](/azure/storage/blobs/create-data-lake-storage-account). אם תבחר ברמת הביצועים Premium, בחר [blobs של בלוקי Premium כסוג החשבון](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>הגדרת חיבור ל- Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Azure Data Lake Gen 2**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור Azure Data Lake Storage Gen2 שלך.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע Azure Data Lake. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את שם התיקייה עבור האחסון של Azure Data Lake Storage Gen2.

1. בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

נתונים מיוצאים מאוחסנים בגורם המכיל של אחסון Azure Data Lake Gen 2 שהגדרת.

> [!TIP]
> ייצוא של ישויות המכילות כמות גדולה של נתונים יכול להוביל למספר קובצי CSV באותה תיקייה עבור כל פעולת ייצוא. פיצול פעולות הייצוא קורה מטעמי ביצועים כדי למזער את הזמן שלוקח לייצוא להסתיים.

[!INCLUDE [footer-include](includes/footer-banner.md)]
