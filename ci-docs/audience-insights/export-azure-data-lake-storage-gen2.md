---
title: ייצוא נתוני Customer Insights אל Azure Data Lake Storage Gen2
description: למד כיצד לקבוע את תצורת החיבור אל Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477180"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>מחבר עבור Azure Data Lake Storage Gen2‏ (Preview)

אחסן את נתוני Customer Insights ב- Azure Data Lake Storage Gen2 או השתמש בו כדי להעביר את הנתונים שלך ליישומים אחרים.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>קביעת תצורת המחבר עבור Azure Data Lake Storage Gen2

1. ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.

1. תחת **Azure Data Lake Storage Gen2**, בחר **הגדר**.

1. תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור Azure Data Lake Storage Gen2 שלך.
    - כדי ללמוד כיצד ליצור חשבון אחסון לשימוש עם Azure Data Lake Storage Gen2, ראה [יצירת חשבון אחסון](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account). 
    - למידע נוסף על אופן מציאת שם החשבון ומפתח החשבון של חשבון האחסון של Azure Data Lake Gen2, ראה [ניהול של הגדרות חשבון האחסון בפורטל Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).

1. בחר **הבא**.

1. בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md#export-data-on-demand). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).
