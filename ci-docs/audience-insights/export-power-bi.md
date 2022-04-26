---
title: מחבר Power BI
description: למד איך להשתמש במחבר Dynamics 365 Customer Insights ב- Power BI.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 06c5bed74b82f9ae2a764a2eb363348e0edab531
ms.sourcegitcommit: 4b2ad63aa7a4d4f31b573870bccbc40befe5f8fd
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/07/2022
ms.locfileid: "8552057"
---
# <a name="connector-for-power-bi-preview"></a>Connector עבור Power BI (תצוגה מקדימה)

צור תצוגות חזותיות עבור הנתונים שלך עם Power BI Desktop. צור תובנות נוספות ובנה דוחות בעזרת נתוני הלקוח המאוחד שלך.

## <a name="prerequisites"></a>דרישות מוקדמות

- יש לך פרופילי לקוחות מאוחדים.
- הגירסה האחרונה של [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) מותקנת במחשב שלך. [למד עוד על Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>קביעת תצורת המחבר עבור Power BI

1. ב- Power BI Desktop, בחר **קובץ** > **קבל נתונים**.

1. בחר **הצג יותר** וחפש את **Dynamics 365 Customer Insights**.

1. בחר **התחבר**.

1. **התחבר** עם אותו חשבון ארגוני שבו אתה משתמש עבור Customer Insights ובחר **התחבר**.
   > [!NOTE]
   > החשבון שאתה מציין בשלב זה משמש לאיסוף נתונים מ-Customer Insights ואינו צריך להיות זהה לחשבון איתו נכנסת ל-Power BI. כדי לאפס את החשבון המשמש להבאת נתונים, פתח את Power BI ועבור אל **קובץ** > **אפשרויות** > **הגדרות** > **הגדרות מקור נתונים**. ברשימת מקורות הנתונים בחר **Dynamics 365 Customer Insights התחברות** ובחר **נקה הרשאות**.  

1. בתיבת הדו-שיח **Navigator**. אתה רואה את רשימת הסביבות שיש לך גישה אליהן. הרחב סביבה ופתח כל אחת מהתיקיות (ישויות, מדידות, פלחים, העשרות). לדוגמה, פתח את התיקיה **ישויות** כדי לראות את כל הישויות שאתה יכול לייבא.

   ![נווט במחבר Power BI.](media/power-bi-navigator.png "נווט במחבר Power BI")

1. בחר את תיבות הסימון לצד הישויות שיש לכלול ו **טען**. באפשרותך לבחור ישויות מרובות מכמה סביבות.

1. תראה תיבת דו-שיח שנטענת בזמן שהישויות נטענות. לאחר שכל הישויות שנבחרו נטענו, באפשרותך להשתמש ביכולות של Power BI כדי להציג את הנתונים באופן חזותי.

## <a name="large-data-sets"></a>ערכות נתונים גדולות

מחבר Customer Insights עבור Power BI נועד לעבוד עבור ערכות נתונים המכילות עד מיליון פרופילי לקוחות. ייבוא של ערכות נתונים גדולות יותר עשוי לעבוד, אך זה לוקח זמן רב. בנוסף, התהליך עלול להיקלע לפסק זמן בגלל מגבלות של Power BI. למידע נוסף ראה [Power BI: המלצות לערכות נתונים גדולות](/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>עבוד עם קבוצת משנה של נתונים

שקול לעבוד עם ערכת משנה של הנתונים שלך. לדוגמה, באפשרותך ליצור [פלחים](segments.md) במקום לייצא את כל רשומות הלקוחות אל Power BI.

## <a name="troubleshooting"></a>פתרון בעיות

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>סביבת Customer Insights לא מוצגת ב- Power BI

סביבות שיש להן יותר מ[קשר](relationships.md) אחד מוגדר בין שתי ישויות זהות ב- audience insights לא יהיו זמינות במחבר Power BI.

באפשרותך לזהות ולהסיר את הקשרים הכפולים.

1. ב- audience insights, עבור אל **נתונים** > **קשרים** בסביבה שחסרה לך ב- Power BI.
2. זהה קשרים כפולים:
   - בדוק אם יש יותר מקשר אחד המוגדר בין אותן שתי ישויות.
   - בדוק אם נוצר קשר בין שתי ישויות שנכללות שתיהן בתהליך האיחוד. יש קשר משתמע המוגדר בין כל הישויות הנכללות בתהליך האיחוד.
3. הסר כל קשר כפול שזוהה.

לאחר הסרת הקשרים הכפולים, נסה לקבוע שוב את תצורת מחבר Power BI. הסביבה צריכה להיות זמינה כעת.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>שגיאות בשדות תאריך בעת טעינת ישויות ב- Power BI Desktop

בעת טעינת ישויות המכילות שדות עם תבנית תאריך כמו MM/DD/YYYY, אתה עשוי להיתקל בשגיאות עקב תבניות לא נכונות של אזור. חוסר התאמה זה קורה כאשר קובץ Power BI Desktop מוגדר לאזור שאינו אנגלית (ארצות הברית), מכיוון ששדות תאריכים בתובנות לגבי קהלים נשמרים בתבנית של ארה"ב.

בקובץ Power BI Desktop יש הגדרת אזור אחת, המיושמת בעת אחזור נתונים. כדי לפרש שדות תאריכים אלה כראוי, הגדר את המיקום של קובץ ‎.BPI לאנגלית (ארצות הברית). [למד כיצד ניתן לשנות את האזור של קובץ Power BI Desktop](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
