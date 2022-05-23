---
title: מחבר Power Automate | Microsoft Docs
description: צור זרימות ב- Microsoft Power Automate מתוך Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d22c4c785695b23a257a89f1ffa519fdc18b443e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741180"
---
# <a name="power-automate-connector-preview"></a>מחבר Power Automate (תצוגה מקדימה)

הפעל אירועים ספציפיים כך שיתרחשו באופן אוטומטי כאשר הנתונים שלך ישתנו ונהל זרימות מורכבות יותר ישירות ב- [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>מגבלות ידועות

- אתה יכול לבצע מקסימום 100 שיחות ל-60 שניות. אתה יכול לקרוא לנקודת הקצה של ה- API מספר פעמים על ידי שימוש בפרמטר ‏‏‎skip$. [קבל מידע נוסף על הפרמטר skip‎‏$](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>גורמים מפעילים של Power Automate

השתמש בגורמים מפעילים כדי ליצור זרמי ענן ולהפוך משימות חוזרות לאוטומטיות, כגון הודעות או פעולות מתקדמות יותר.

- הפעל כאשר רענון מקור נתונים נכשל.
- הפעל כאשר רענון מקור נתונים מצליח.
- הפעל כאשר סף כלשהו נחצה במקטע. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- הפעל כאשר סף כלשהו נחצה במדד עסקי. רק מדידות עסקיות ללא ממד נתמכות. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- הפעל כאשר רענון מלא של (מקורות נתונים, פלחים, מדידות, ...) הושלם.
- מופעל כאשר רענון תהליך האיחוד הושלם.

[הגדר את הגורמים המפעילים ב- Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>פעולות Power Automate

מחבר Power Automate מספק פעולות אחרות לגורמים המפעילים הזמינים. לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>צור זרימת Power Automate

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. באריח **Power Automate**, בחר **הגדר**.

1. מחבר Customer Insights‏ (preview) ב- Power Automate נפתח. **כניסה** אל Power Automate.

1. בחר אחד מהגורמים המפעילים הזמינים והוסף שלבים נוספים לזרימה החדשה שלך. למידע נוסף, ראה [צור זרימת ענן ב- Power Automate](/power-automate/get-started-logic-flow).

דוגמאות לשימוש בזרימות: 
- פרסם הודעה בערוץ Microsoft Teams אם רענון מקור נתונים נכשל. 
- שלח דואר לבעלי הנתונים בעת חציית ערך סף בפלח.



[!INCLUDE [footer-include](includes/footer-banner.md)]
