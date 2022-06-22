---
title: ייצוא נתוני Customer Insights אל Azure Data Lake Storage Gen2
description: למד כיצד לקבוע את תצורת החיבור אל Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 22eee11666752459a1750d728c4e254ab0c59e58
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947231"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>ייצוא רשימת פלחים ונתונים אחרים אל Azure Data Lake Storage Gen2 ‏(Preview)

אחסן את נתוני Customer Insights בחשבון Data Lake Storage Gen2 או השתמש בו כדי להעביר את הנתונים שלך ליישומים אחרים.

## <a name="known-limitations"></a>מגבלות ידועות

1. עבור Azure Data Lake Storage Gen2, באפשרותך יכול לבחור בין [‬‏‫רמת ביצועים סטנדרטית לרמת ביצועים Premium](/azure/storage/blobs/create-data-lake-storage-account) בעת יצירת חשבון אחסון לאגם הנתונים שלך. אם תבחר ברמת הביצועים Premium, בחר blobs של בלוקי Premium כסוג החשבון.

## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>הגדרת החיבור ל- Azure Data Lake Storage Gen2

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Azure Data Lake Gen 2** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור Azure Data Lake Storage Gen2 שלך.
    - כדי ללמוד כיצד ליצור חשבון אחסון לשימוש עם Azure Data Lake Storage Gen2, ראה [יצירת חשבון אחסון](/azure/storage/blobs/create-data-lake-storage-account). 
    - לקבלת מידע נוסף אודות האופן שבו ניתן למצוא שם חשבון ומפתח חשבון של Azure Data Lake Gen 2, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע **Azure Data Lake**. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).
באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).

נתונים מיוצאים מאוחסנים בגורם המכיל של אחסון Azure Data Lake Gen 2 שהגדרת.

> [!TIP]
> ייצוא של ישויות המכילות כמות גדולה של נתונים יכול להוביל למספר קובצי CSV באותה תיקייה עבור כל פעולת ייצוא. פיצול פעולות הייצוא קורה מטעמי ביצועים כדי למזער את הזמן שלוקח לייצוא להסתיים.

[!INCLUDE [footer-include](includes/footer-banner.md)]
