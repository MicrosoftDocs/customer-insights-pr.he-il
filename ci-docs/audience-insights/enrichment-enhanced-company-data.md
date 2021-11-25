---
title: שיפור של נתוני חברה
description: העשרה ונרמול של נתוני חברה עם מודלים של Microsoft.
ms.date: 11/05/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9bfb96d47de4ec98325e644c60752fc7cab2706c
ms.sourcegitcommit: 6efcba688d1db1a5d6343c229f292a26c48fc007
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/05/2021
ms.locfileid: "7770171"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>העשרה של פרופילי חברה עם נתוני חברה משופרים

השתמש במודלים של Microsoft ובנתוני חברה מרוכזים כדי לתקן, להשלים ולתקנן את פרופילי החברה. נשתמש [בתבנית Common Data Model](/common-data-model/schema/core/applicationcommon/account) עבור תובנות ודיוק טובים יותר.

## <a name="how-we-enhance-company-data"></a>כיצד אנחנו משפרים נתוני חברה

המודל שלנו עובר תהליך דו-שלבי לשיפור של פרופיל חברה. תחילה הוא מנרמל את שם החברה. לדוגמה, *Microsft Corp* יתוקן ויתוקנן ל- *Microsoft Corporation*. הוא ינסה למצוא התאמה בנתוני החברה המרוכזים של Microsoft. אם נמצאה התאמה, נעשיר את פרופיל החברה במידע מנתוני החברה המרוכזים, כולל שם החברה.


### <a name="example"></a>דוגמה

ייתכן שפרטי החברה שלך אינם בתבנית סטנדרטית ומכילים שגיאות כתיב. המודל מנסה לתקן את הבעיות הללו וליצור מידע עקבי.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>מגבלות

לנתונים המשופרים יש מספר מגבלות. הפריטים ברשימה למטה אינם נתמכים על-ידי המודל.

1.  אישור זהות החברה. אנחנו לא מאמתים אם הקלט הוא ארגון קיים או שחברה משתמשת בפלט כשמה הסטנדרטי.
2.  כיסוי מקיף של חברות ברחבי העולם. לנתוני החברה המרוכזים של Microsoft יש כיסוי עולמי, אך רוב הכיסוי מוצע באוסטרליה, קנדה, בריטניה וארצות הברית.
3.  הבטחת דיוק או טריות של הנתונים. מכיוון שמידע עסקי משתנה לעתים קרובות, לא נוכל להבטיח שנתוני החברה המשופרים המתקבלים יהיו תמיד מדויקים או עדכניים.

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה**.

1. בחר **העשירו את הנתונים שלי** באריח **נתוני חברה משופרים**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="אריח העשרה במרכז ההעשרה לנתוני חברה.":::

1. בחר **ערכת הנתונים של הלקוח** ובחר את הישות המכילה את הכתובות שברצונך להעשיר. ניתן לבחור בישות *לקוח* להעשרת כתובות בכל פרופילי הלקוחות או לבחור ישות פלח שוק להעשרת כתובות רק בפרופילי לקוחות הכלולים בפלח זה.

1. בחר את סוג השדות מפרופילי החברה שלך שישמש לצורך התאמה עם נתוני החברה המרוכזים של Microsoft. בחירה זו תשפיע על שדות המיפוי שאליהם יש לך גישה בשלב הבא.

1.  מפה את שדות החברה מישות הלקוח המאוחדת שלך. ככל שתמפה יותר שדות ומזהי מפתח, כך תגדל הסבירות לשיעור התאמה גבוה.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="שלב מיפוי נתונים בעת הגדרת העשרה של חברה.":::

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. ספק שם עבור ההעשרה ועבור ישות הפלט.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

## <a name="enrichment-results"></a>תוצאות העשרה

כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות. ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab). זמן העיבוד תלוי בגודל נתוני הלקוח שלך.

לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**. בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.

אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.

## <a name="next-steps"></a>השלבים הבאים

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
