---
title: ייצוא נתוני Customer Insights ל- InMobi
description: למד כיצד להגדיר את תצורת החיבור ולייצא ל- InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195889"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>ייצוא נתוני Customer Insights ל- InMobi ‏(Preview)

ייצא רשימות פלחים או נתונים אחרים ממופע Customer Insights שלך אל [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון InMobi](https://www.inmobi.com/) ואישורי מנהל מערכת.
- שם [חשבון Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ומפתח חשבון. כדי לחפש את השם ואת המפתח, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).
- [גורם מכיל של Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) שאליו יש לייצא את נתוני InMobi.
- InMobi תיצור חיבור ישיר ל-Blob האחסון שלך, ותגדיר ייבוא אוטומטי של הנתונים שלך ל-InMobi. צור קשר עם נציג InMobi שלך כדי להתחיל בתהליך.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עבור Azure Blob Storage, בחר בין [רמת ביצועים סטנדרטית לרמת ביצועים Premium](/azure/storage/blobs/storage-blob-performance-tiers). אם תבחר ברמת הביצועים Premium, בחר [blobs של בלוקי Premium כסוג החשבון](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>הגדרת חיבור ל- Azure Blob Storage

[הגדר חיבור אל Azure Blob Storage](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[קביעת תצורה של ייצוא](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
