---
title: מחבר Power BI (תצוגה מקדימה)
description: למד איך להשתמש במחבר Dynamics 365 Customer Insights ב- Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196671"
---
# <a name="power-bi-connector-preview"></a>מחבר Power BI (תצוגה מקדימה)

צור הדמיות עבור הנתונים שלך באמצעות Microsoft Power BI Desktop. צור תובנות נוספות ובנה דוחות בעזרת נתוני הלקוח המאוחד שלך.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- פרופילי לקוח מאוחדים.
- הגירסה האחרונה של [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) מותקנת במחשב שלך. [למד עוד על Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>קביעת תצורת המחבר עבור Power BI

1. ב- Power BI Desktop, בחר **קובץ** > **קבל נתונים**.

1. בחר **הצג יותר** וחפש את **Dynamics 365 Customer Insights**.

1. בחר **התחבר**.

1. **התחבר** עם אותו חשבון ארגוני שבו אתה משתמש עבור Customer Insights ובחר **התחבר**.
   > [!NOTE]
   > החשבון שאתה מציין בשלב זה משמש לאיסוף נתונים מ-Customer Insights ואינו צריך להיות זהה לחשבון איתו נכנסת ל-Power BI. כדי לאפס את החשבון המשמש להבאת נתונים, פתח את Power BI ועבור אל **קובץ** > **אפשרויות** > **הגדרות** > **הגדרות מקור נתונים**. ברשימת מקורות הנתונים בחר **Dynamics 365 Customer Insights התחברות** ובחר **נקה הרשאות**.  

1. בתיבת הדו-שיח **נווט**, הצג את הרשימה של כל הסביבות שאליהן יש לך גישה. הרחב סביבה ופתח כל אחת מהתיקיות (ישויות, מדידות, פלחים, העשרות). לדוגמה, פתח את התיקיה **ישויות** כדי לראות את כל הישויות שאתה יכול לייבא.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="נווט במחבר Power BI.":::

1. בחר את תיבות הסימון לצד הישויות שיש לכלול ו **טען**. באפשרותך לבחור ישויות מרובות מכמה סביבות.

   תיבת דו-שיח לטעינה מוצגת בזמן שהישויות נטענות. לאחר שכל הישויות שנבחרו נטענו, השתמש ביכולות של Power BI כדי להציג את הנתונים באופן חזותי.

## <a name="large-data-sets"></a>ערכות נתונים גדולות

מחבר Customer Insights עבור Power BI נועד לעבוד עבור ערכות נתונים המכילות עד מיליון פרופילי לקוחות. ייבוא ערכות נתונים גדולות יותר עשוי לעבוד, אך הוא אורך זמן רב ועלול להגיע לזמן הקצוב עקב מגבלות Power BI. למידע נוסף ראה [Power BI: המלצות לערכות נתונים גדולות](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>עבוד עם קבוצת משנה של נתונים

שקול לעבוד עם ערכת משנה של הנתונים שלך. לדוגמה, צור [פלחים](segments.md) במקום לייצא את כל רשומות הלקוחות אל Power BI.

## <a name="troubleshooting"></a>פתרון בעיות

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>סביבת Customer Insights לא מוצגת ב- Power BI

סביבות שיש בהן יותר [מקשר](relationships.md) אחד המוגדר בין שתי ישויות זהות ב- Customer Insights לא יהיו זמיניות במחבר של Power BI.

זהה והסר את הקשרים הכפולים.

1. עבור אל **נתונים** > **קשרים** בסביבה שחסרה לך ב- Power BI.
1. זהה קשרים כפולים:
   - בדוק אם יש יותר מקשר אחד המוגדר בין אותן שתי ישויות.
   - בדוק אם נוצר קשר בין שתי ישויות שנכללות שתיהן בתהליך האיחוד. יש קשר משתמע המוגדר בין כל הישויות הנכללות בתהליך האיחוד.
1. הסר כל קשר כפול שזוהה.

לאחר הסרת הקשרים הכפולים, נסה לקבוע שוב את תצורת מחבר Power BI.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>שגיאות בשדות תאריך בעת טעינת ישויות ב- Power BI Desktop

בעת טעינת ישויות המכילות שדות עם תבנית תאריך כמו MM/DD/YYYY, אתה עשוי להיתקל בשגיאות עקב תבניות לא נכונות של אזור. חוסר ההתאמה זו מתרחשת כאשר קובץ Power BI Desktop מוגדר למיקום אחר שהוא לא אנגלית (ארצות הברית), מכיוון ששדות תאריך ב- Customer Insights נשמרים בפורמט ארה"ב.

בקובץ Power BI Desktop יש הגדרת אזור אחת, המיושמת בעת אחזור נתונים. כדי לתקן את שגיאות התאריך, [הגדר את האזור של קובץ ה- ‎.BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) לאנגלית (ארצות הברית).

[!INCLUDE [footer-include](includes/footer-banner.md)]
