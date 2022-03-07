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
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350408"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>מגבלות שירות ביכולות Customer Insights

מאמר זה מתאר את המגבלות המובנות בשירות Customer Insights, שנועדו להבטיח את אמינות השירות ויציבותו. כל בקשה לשינויים יכולה להיעשות דרך [פורום הרעיונות](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>תובנות לגבי קהלים

| אזור  | מגבלות  | הערות |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| פלחים, מדידות וחיזויים | 300  | המספר הכולל של [פלחים](audience-insights/segments.md), [מדידות](audience-insights/measures.md) ו[חיזויים](audience-insights/predictions.md) אינו יכול לעלות על 300 בסך הכל.  |
| קשרים | 20 רמות עומק של קשרים בנתיבי ישות. | בעת יצירת [פלחים](audience-insights/segments.md) או [מדידות](audience-insights/measures.md) באמצעות ממשק הבנייה, נתיבי הישות יכולים לכלול עד 20 דילוגים של קשרים בין ישות ההתחלה לישות היעד.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
