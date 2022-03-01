---
title: ייצוא נתוני Customer Insights אל אחסון Blob של Azure
description: למד כיצד להגדיר את החיבור לאחסון Blob של Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667140"
---
# <a name="connector-for-azure-blob-storage-preview"></a>מחבר לאחסון Blob של Azure (תצוגה מקדימה)

אחסן את נתוני Customer Insights שלך באחסון Blob של Azure או השתמש בו כדי להעביר את הנתונים שלך אל יישומים אחרים.

## <a name="configure-the-connector-for-azure-blob-storage"></a>קביעת התצורה של המחבר לאחסון Blob של Azure

1. ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.

1. תחת **אחסון Blob של Azure**, בחר **הגדר**.

1. הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור חשבון אחסון Blob של Azure.
    - כדי לקבל מידע נוסף אודות אופן מציאת שם החשבון ומפתח החשבון של אחסון Blob של Azure, ראה [ניהול הגדרות חשבון אחסון בפורטל Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).
    - כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. בחר **הבא**.

1. בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.

1. בחר **שמור**.

נתונים מיוצאים מאוחסנים בגורם המכיל של אחסון Blob של Azure שהגדרת. נתיבי התיקיות הבאים נוצרים באופן אוטומטי בגורם המכיל שלך:

- עבור ישויות מקור וישויות שנוצרו על-ידי המערכת: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - דוגמה: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- ה-model.json עבור הישויות המיוצאות יימצא ברמת % ExportDestinationName%
  - דוגמה: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](/export-destinations.md#export-data-on-demand). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).
