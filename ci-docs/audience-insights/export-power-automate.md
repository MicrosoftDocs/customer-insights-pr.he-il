---
title: מחבר Power Automate | Microsoft Docs
description: צור זרימות ב- Microsoft Power Automate מתוך Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 95e0fcbfb43f2b3e7e2d0e8a1690dc7ff5a44433402b7ef3d437710eb0efff15
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035600"
---
# <a name="power-automate-connector-preview"></a>מחבר Power Automate (תצוגה מקדימה)

הפעל אירועים ספציפיים כך שיתרחשו באופן אוטומטי כאשר הנתונים שלך ישתנו ונהל זרימות מורכבות יותר ישירות ב- [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>גורמים מפעילים של Power Automate

השתמש בגורמים מפעילים כדי ליצור זרמי ענן ולהפוך משימות חוזרות לאוטומטיות, כגון הודעות או פעולות מתקדמות יותר. 

- הפעל כאשר רענון מקור נתונים נכשל. 
- הפעל כאשר רענון מקור נתונים מצליח.
- הפעל כאשר סף כלשהו נחצה במקטע. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- הפעל כאשר סף כלשהו נחצה במדד עסקי. רק מדידות עסקיות ללא ממד נתמכות. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- הפעל כאשר רענון מלא של (מקורות נתונים, פלחים, מדידות, ...) הושלם.
- הפעל לאחר השלמת רענון של תהליך האיחוד (מפה, התאמה, מיזוג).

[הגדר את הגורמים המפעילים ב- Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>פעולות Power Automate

מחבר Power Automate מספק פעולות אחרות לגורמים המפעילים הזמינים. לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>צור זרימת Power Automate

1. ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.

1. באריח **Power Automate**, בחר **הגדר**.

1. מחבר Customer Insights‏ (preview) ב- Power Automate נפתח. **כניסה** אל Power Automate.

1. בחר אחד מהגורמים המפעילים הזמינים והוסף שלבים נוספים לזרימה החדשה שלך. למידע נוסף, ראה [צור זרימת ענן ב- Power Automate](/power-automate/get-started-logic-flow).

דוגמאות לשימוש בזרימות: 
- פרסם הודעה בערוץ Microsoft Teams אם רענון מקור נתונים נכשל. 
- שלח דואר לבעלי הנתונים בעת חציית ערך סף בפלח.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
