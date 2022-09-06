---
title: מגבלות שירות ב- Customer Insights
description: הבן את הגבולות והמגבלות בשירות SaaS של Customer Insights.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 421e1aa41a54a4b8c34ac27fc7c02e510d2bb588
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387157"
---
# <a name="service-limits-in-customer-insights"></a>מגבלות שירות ב- Customer Insights

 ב- Customer Insights יש מגבלות שנועדו להבטיח את האמינות והיציבות של השירות. כל בקשה לשינויים יכולה להיעשות דרך [פורום הרעיונות](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| אזור  | מגבלות  | הערות |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| פלחים, מדידות וחיזויים | 300  | המספר הכולל של [פלחים](segments.md), [מדידות](measures.md) ו[חיזויים](predictions.md) אינו יכול לעלות על 300 בסך הכל.  |
| קשרים | 20 רמות עומק של קשרים בנתיבי ישות. | בעת יצירת [פלחים](segments.md) או [מדידות](measures.md) באמצעות ממשק הבנייה, נתיבי הישות יכולים לכלול עד 20 דילוגים של קשרים בין ישות ההתחלה לישות היעד.  |

## <a name="fair-scheduling-of-jobs"></a>תזמון הוגן של משימות

Customer Insights הוא שירות SaaS המשתמש במשאבי Azure משותפים. ללקוחות נוטים להיות עומסי עבודה בעוצמה משתנה ובלוחות זמנים שונים. כדי להבטיח גישה הוגנת למשאבים שמשמשים כבסיס, אנו מוודאים שתהליכי המערכת מבוצעים בסדר הוגן. דוגמאות לתהליכי מערכת הן משימות הקשורות לאיחוד נתונים, עדכוני פלחים או חישוב מדדים. תזמון הוגן מגן עליך מפני תור למשאבים אם יש עלייה חדה במספר המשימות המבוקשות. יחד עם זאת, Customer Insights לא מבטיחה שכל העבודות שאתה מעמיד בתור יעובדו במקביל.

[!INCLUDE [footer-include](includes/footer-banner.md)]
