---
title: מגבלות שירות ב- Dynamics 365 Customer Insights
description: הכר את המגבלות וההגבלות.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641763"
---
# <a name="service-limits-in-customer-insights"></a>מגבלות שירות ב- Customer Insights

מאמר זה מתאר את המגבלות המובנות בשירות Customer Insights, שנועדו להבטיח את אמינות השירות ויציבותו. כל בקשה לשינויים יכולה להיעשות דרך [פורום הרעיונות](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| אזור  | מגבלות  | הערות |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| פלחים, מדידות וחיזויים | 300  | המספר הכולל של [פלחים](segments.md), [מדידות](measures.md) ו[חיזויים](predictions.md) אינו יכול לעלות על 300 בסך הכל.  |
| קשרים | 20 רמות עומק של קשרים בנתיבי ישות. | בעת יצירת [פלחים](segments.md) או [מדידות](measures.md) באמצעות ממשק הבנייה, נתיבי הישות יכולים לכלול עד 20 דילוגים של קשרים בין ישות ההתחלה לישות היעד.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
