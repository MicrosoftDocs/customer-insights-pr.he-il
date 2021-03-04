---
title: מחבר Power Automate | Microsoft Docs
description: צור זרימות ב- Microsoft Power Automate מ- Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268825"
---
# <a name="power-automate-connector-preview"></a>מחבר Power Automate (תצוגה מקדימה)

הפעל אירועים ספציפיים כך שיתרחשו באופן אוטומטי כאשר הנתונים שלך ישתנו ונהל זרימות מורכבות יותר ישירות ב- [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>גורמים מפעילים של Power Automate

השתמש בגורמים מפעילים כדי ליצור זרמי ענן ולהפוך משימות חוזרות לאוטומטיות, כגון הודעות או פעולות מתקדמות יותר. 

- הפעל כאשר רענון מקור נתונים נכשל. 
- הפעל כאשר רענון מקור נתונים מצליח.
- הפעל כאשר סף כלשהו נחצה במקטע. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- הפעל כאשר סף כלשהו נחצה במדד עסקי. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- הפעל כאשר רענון מלא של (מקורות נתונים, פלחים, מדידות,...) הושלם.
- הפעל לאחר השלמת רענון של תהליך האיחוד (מפה, התאמה, מיזוג).

[הגדר את הגורמים המפעילים ב- Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>פעולות Power Automate
מחבר Power Automate מספק פעולות אחרות לגורמים המפעילים הזמינים. לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>צור זרימת Power Automate

1. ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.

1. באריח **Power Automate**, בחר **הגדר**.

1. מחבר Customer Insights‏ (preview) ב- Power Automate נפתח. **כניסה** אל Power Automate.

1. בחר אחד מהגורמים המפעילים הזמינים והוסף שלבים נוספים לזרימה החדשה שלך. למידע נוסף, ראה [צור זרימת ענן ב- Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

דוגמאות לשימוש בזרימות: 
- פרסם הודעה בערוץ Microsoft Teams אם רענון מקור נתונים נכשל. 
- שלח דואר לבעלי הנתונים בעת חציית ערך סף בפלח.



[!INCLUDE[footer-include](../includes/footer-banner.md)]