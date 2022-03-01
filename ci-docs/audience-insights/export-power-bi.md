---
title: מחבר Power BI
description: למד איך להשתמש במחבר Dynamics 365 Customer Insights ב- Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405869"
---
# <a name="connector-for-power-bi-preview"></a>Connector עבור Power BI (תצוגה מקדימה)

צור תצוגות חזותיות עבור הנתונים שלך עם Power BI Desktop. צור תובנות נוספות ובנה דוחות בעזרת נתוני הלקוח המאוחד שלך.

## <a name="prerequisites"></a>דרישות מוקדמות

- יש לך פרופילי לקוחות מאוחדים.
- הגרסה האחרונה של [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) מותקנת במחשב שלך. [למד עוד על Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>קביעת תצורת המחבר עבור Power BI

1. ב- Power BI Desktop, בחר **קובץ** > **קבל נתונים**.

1. בחר **הצג יותר** וחפש את **Dynamics 365 Customer Insights**.

1. בחר את התוצאה ובחר **התחבר**.

1. **התחבר** עם אותו חשבון ארגוני שבו אתה משתמש עבור Customer Insights ובחר **התחבר**.
   > [!NOTE]
   > החשבון שאתה מציין בשלב זה משמש לאיסוף נתונים מ-Customer Insights ואינו צריך להיות זהה לחשבון איתו נכנסת ל-Power BI. כדי לאפס את החשבון המשמש להבאת נתונים, פתח את Power BI ועבור אל **קובץ** > **אפשרויות** > **הגדרות** > **הגדרות מקור נתונים**. ברשימת מקורות הנתונים בחר **Dynamics 365 Customer Insights התחברות** ובחר **נקה הרשאות**.  

1. בתיבת הדו-שיח **Navigator**. אתה רואה את רשימת הסביבות שיש לך גישה אליהן. הרחב סביבה ופתח כל אחת מהתיקיות (ישויות, מדידות, פלחים, העשרות). לדוגמה, פתח את התיקיה **ישויות** כדי לראות את כל הישויות שאתה יכול לייבא.

   ![נווט במחבר Power BI](media/power-bi-navigator.png "נווט במחבר Power BI")

1. בחר את תיבות הסימון לצד הישויות שיש לכלול ו **טען**. באפשרותך לבחור ישויות מרובות מכמה סביבות.

1. תראה תיבת דו-שיח שנטענת בזמן שהישויות נטענות. לאחר שכל הישויות שנבחרו נטענו, באפשרותך להשתמש ביכולות של Power BI כדי להציג את הנתונים באופן חזותי.

## <a name="large-data-sets"></a>ערכות נתונים גדולות

מחבר Customer Insights עבור Power BI נועד לעבוד עבור ערכות נתונים המכילות עד מיליון פרופילי לקוחות. ייבוא של ערכות נתונים גדולות יותר עשוי לעבוד, אך זה לוקח זמן רב. בנוסף, התהליך עלול להיקלע לפסק זמן בגלל מגבלות של Power BI. למידע נוסף ראה [Power BI: המלצות לערכות נתונים גדולות](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>עבוד עם קבוצת משנה של נתונים

שקול לעבוד עם ערכת משנה של הנתונים שלך. לדוגמה, באפשרותך ליצור [פלחים](segments.md) במקום לייצא את כל רשומות הלקוחות אל Power BI.
