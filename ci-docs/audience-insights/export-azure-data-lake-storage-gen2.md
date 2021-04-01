---
title: ייצוא נתוני Customer Insights אל Azure Data Lake Storage Gen2
description: למד כיצד לקבוע את תצורת החיבור אל Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596638"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>מחבר עבור Azure Data Lake Storage Gen2‏ (Preview)

אחסן את נתוני Customer Insights ב- Azure Data Lake Storage Gen2 או השתמש בו כדי להעביר את הנתונים שלך ליישומים אחרים.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>קביעת תצורת המחבר עבור Azure Data Lake Storage Gen2

1. ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.

1. תחת **Azure Data Lake Storage Gen2**, בחר **הגדר**.

1. תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור Azure Data Lake Storage Gen2 שלך.
    - כדי ללמוד כיצד ליצור חשבון אחסון לשימוש עם Azure Data Lake Storage Gen2, ראה [יצירת חשבון אחסון](/azure/storage/blobs/create-data-lake-storage-account). 
    - למידע נוסף על אופן מציאת שם החשבון ומפתח החשבון של חשבון האחסון של Azure Data Lake Gen2, ראה [ניהול של הגדרות חשבון האחסון בפורטל Azure](/azure/storage/common/storage-account-manage).

1. בחר **הבא**.

1. בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md#export-data-on-demand). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).