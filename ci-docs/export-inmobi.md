---
title: ייצוא נתוני Customer Insights ל- InMobi
description: למד כיצד להגדיר את תצורת החיבור ולייצא ל- InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056543"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>ייצוא רשימת פלחים ונתונים אחרים אל InMobi ‏(Preview)

ייצא רשימות פלחים או נתונים אחרים ממופע Customer Insights שלך אל [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

1. יש לך [חשבון InMobi](https://www.inmobi.com/) ואישורי מנהל מערכת.
1. יש לך שם של חשבון אחסון Blob של Azure ואת מפתח החשבון המתאים. למידע נוסף, ראה [נהל את הגדרות חשבון האחסון בפורטל Azure](/azure/storage/common/storage-account-manage). יש גורם מכיל בחשבון האחסון שאליו ניתן לייצא נתוני inMobi. לקבלת מידע נוסף, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. InMobi תיצור חיבור ישיר ל-Blob האחסון שלך, ותגדיר ייבוא אוטומטי של הנתונים שלך ל-InMobi. צור קשר עם נציג InMobi שלך כדי להתחיל בתהליך.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

1. עבור Blob אחסון של Azure, תוכל לבחור בין [רמת ביצועים סטנדרטית לרמת ביצועים Premium](/azure/storage/blobs/storage-blob-performance-tiers). אם תבחר ברמת הביצועים Premium, בחר [blobs של בלוקי Premium כסוג החשבון](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>הגדר את החיבור לאחסון Blob של Azure והגדר ייצוא

1. עקוב אחר ההוראות כדי [להגדיר חיבור לאחסון Blob של Azure שלך](export-azure-blob-storage.md).
2. עקוב אחר ההוראות כדי [להגדיר ייצוא](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
