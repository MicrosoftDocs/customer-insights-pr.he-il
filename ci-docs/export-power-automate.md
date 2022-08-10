---
title: מחבר Power Automate‏‏ (Preview) |‏ Microsoft Docs
description: צור זרימות ב- Microsoft Power Automate מתוך Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196119"
---
# <a name="power-automate-connector-preview"></a>מחבר Power Automate (תצוגה מקדימה)

הפעל אירועים ספציפיים כך שיתרחשו באופן אוטומטי כאשר הנתונים שלך ישתנו ונהל זרימות מורכבות יותר ישירות ב- [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- מקסימום 100 שיחות לכל 60 שניות. השתמש ב[פרמטר ‏‏‎skip$](/connectors/customerinsights/#get-items-from-an-entity) כדי לקרוא לנקודת הקצה של ה- API מספר פעמים.

## <a name="power-automate-triggers"></a>גורמים מפעילים של Power Automate

השתמש בגורמים מפעילים כדי ליצור זרמי ענן ולהפוך משימות חוזרות לאוטומטיות, כגון הודעות או פעולות מתקדמות יותר. השתמש בגורמים מפעילים כאשר:

- רענון מקור נתונים נכשל.
- רענון מקור נתונים בוצע בהצלחה.
- סף נחצה בפלח. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- סף נחצה במדד עסקי. רק מדידות עסקיות ללא ממד נתמכות. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- הושלם רענון מתוזמן מלא. גורם מפעיל זה לא עובד עבור פעולות רענון שהופעלו באופן ידני.
- רענון של תהליך האיחוד הושלם.

[הגדר את הגורמים המפעילים ב- Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>פעולות Power Automate

מחבר Power Automate מספק פעולות אחרות לגורמים המפעילים הזמינים. לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>צור זרימת Power Automate

1. עבור אל **ניהול** > **חיבורים**.

1. באריח **Power Automate**, בחר **הגדר**.

1. מחבר Customer Insights‏ (preview) ב- Power Automate נפתח. **כניסה** אל Power Automate.

1. בחר אחד מהגורמים המפעילים הזמינים והוסף שלבים נוספים לזרימה החדשה שלך. למידע נוסף, ראה [צור זרימת ענן ב- Power Automate](/power-automate/get-started-logic-flow).

דוגמאות לשימוש בזרימות: 
- פרסם הודעה בערוץ Microsoft Teams אם רענון מקור נתונים נכשל. 
- שלח דואר לבעלי הנתונים בעת חציית ערך סף בפלח.

[!INCLUDE [footer-include](includes/footer-banner.md)]
