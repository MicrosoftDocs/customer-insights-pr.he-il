---
title: מגבלות שירות ב- Dynamics 365 Customer Insights
description: הכר את המגבלות וההגבלות.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eba7871faf304d5945191b5b9bc215243b4f8a05
ms.sourcegitcommit: 5704002484cdf85ebbcf4e7e4fd12470fd8e259f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/08/2021
ms.locfileid: "7483671"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>מגבלות שירות ביכולות Customer Insights

מאמר זה מתאר את המגבלות המובנות בשירות Customer Insights, שנועדו להבטיח את אמינות השירות ויציבותו. כל בקשה לשינויים יכולה להיעשות דרך [פורום הרעיונות](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>תובנות לגבי קהלים

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>מגבלות שירות ביכולת Audience Insights של Dynamics 365 Customer Insights

| אזור  | מגבלות  | הערות |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| פלחים ומידות | 100 פלחים או מדדים. | המספר הכולל של [הפלחים](audience-insights/segments.md) ו[המדדים](audience-insights/measures.md) הפעילים יחד אינו יכול לעלות על 100.  |
| קשרים | 20 רמות עומק של קשרים בנתיבי ישות. | בעת יצירת [פלחים](audience-insights/segments.md) או [מדידות](audience-insights/measures.md) באמצעות ממשק הבנייה, נתיבי הישות יכולים לכלול עד 20 דילוגים של קשרים בין ישות ההתחלה לישות היעד.  |


## <a name="engagement-insights"></a>תובנות לגבי מעורבות

### <a name="workspace-and-event-quotas"></a>סביבת עבודה ומיכסות אירועים

תובנות לגבי מעורבות הוא יישום בעל מדרגיות גבוהה שיכול לתמוך במיליוני אירועים בשנייה. במהלך תצוגה מקדימה ציבורית, לאירועים יש סף נפח. יש גם מגבלה למספר סביבות העבודה בארגון.

### <a name="engagement-insights-limits"></a>מגבלות של תובנות לגבי מעורבות

- הנפח המרבי של אירועים לכל סביבת עבודה = 100 אירועים לשנייה

- מספר מרבי של סביבות עבודה בארגון = 100

כאשר אירועים חורגים מהסף, הדבר יכול להוביל לאובדן של נתונים בדוחות המבוססים על אירועים אלה. באפשרותך [לפנות לתמיכה](https://go.microsoft.com/fwlink/?linkid=2145734) כדי לבקש הגדלת נפח לפני שתחרוג מהמגבלות. נעבוד יחד איתך כדי לקבוע מהו הצורך שלך בהגדלת נפח ונתמוך בבקשתך.


[!INCLUDE[footer-include](includes/footer-banner.md)]