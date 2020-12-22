---
title: מחבר Power Automate | Microsoft Docs
description: צור זרימות ב- Microsoft Power Automate מ- Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405864"
---
# <a name="power-automate-connector-preview"></a>מחבר Power Automate (תצוגה מקדימה)

הפעל אירועים ספציפיים כך שיתרחשו באופן אוטומטי כאשר הנתונים שלך ישתנו ונהל זרימות מורכבות יותר ישירות ב- [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>גורמים מפעילים של Power Automate

אתה יכול להשתמש במגוון גורמים מפעילים המאפשרים לך ליצור זרימות לאוטומציה של משימות חוזרות, כגון התראות או פעולות מתקדמות יותר. 

- הפעל כאשר רענון מקור נתונים נכשל. 
- הפעל כאשר רענון מקור נתונים מצליח.
- הפעל כאשר סף כלשהו נחצה במקטע. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- הפעל כאשר סף כלשהו נחצה במדד עסקי. הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.
- הפעל כאשר רענון מלא של (מקורות נתונים, פלחים, מדידות,...) הושלם.
- הפעל לאחר השלמת רענון של תהליך האיחוד (מפה, התאמה, מיזוג).

[הגדר את הגורמים המפעילים ב- Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>פעולות Power Automate
מחבר Power Automate מספק פעולות אחרות לגורמים המפעילים הזמינים. לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>צור זרימת Power Automate ב- Audience Insights

1. ב- audience insights, עבור אל **ניהול** > **מערכת**.

1. בדף **מערכת**, בחר בכרטיסיה **מצב**.

1. במקטע **מקורות נתונים**, בחר **זרימות** ובחר **צור זרימה** מהרשימה הנפתחת.
   > [!div class="mx-imgBorder"]
   > ![מחבר Power Automate מראה פעולה של יצירת זרימה](media/power-automate-connector-create-flow.png "מחבר Power Automate מראה פעולה של יצירת זרימה")

1. ב- Power Automate, בחר אחד מהגורמים המפעילים הזמינים ליצירת הזרימה המועדפת שלך. אם אתה יוצר את הזרימה הראשונה שלך, ראשית יהיה עליך לאמת עם מחבר Power Automate.
