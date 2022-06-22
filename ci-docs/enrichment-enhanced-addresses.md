---
title: העשרה לשיפור כתובות (מכיל סרטון)
description: העשר ונרמל מידע על כתובות שמופיעות בפרופילי לקוחות באמצעות מודלים של Microsoft.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: f6279b9bb721d99d66f73e8dc839a92f1ad90140
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953812"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>העשרה של פרופילי לקוחות עם כתובות משופרות

כתובות בנתונים שלך יכולות להיות לא מובנות, לא שלמות או שגויות. השתמש במודלים של Microsoft כדי לנרמל ולהעשיר את הכתובות שלך ב[תבנית Common Data Model](/common-data-model/schema/core/applicationcommon/address) ליתר דיוק ולהשגת תובנות טובות יותר.

אתה יכול גם [להעשיר כתובות במקורות נתונים](data-sources-enrichment.md) כדי לשפר את דיוק ההתאמה בתהליך איחוד הנתונים. 

## <a name="how-we-enhance-addresses"></a>כיצד אנו משפרים כתובות

המודל שלנו מבצע תהליך דו-שלבי לשיפור כתובת. תחילה, הוא מנתח את הכתובת לזיהוי הרכיבים שלה ומציב אותם בתבנית מובנית. לאחר מכן אנו משתמשים ב- AI כדי לתקן, להשלים ולתקנן את הערכים בכתובת.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>דוגמה

פרטי הכתובת עשויים להיות בפורמט שאינו רגיל ולהכיל שגיאות כתיב. המודל יכול לפתור את הבעיות הללו וליצור כתובות עקביות בפרופילי לקוחות מאוחדים.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>הגבלות

כתובות משופרות פועלות רק עם הערכים שכבר קיימים בנתוני הכתובות שעובדו. המודל אינו:

1. מאמת אם הכתובת היא כתובת חוקית.
2. מאמת אם אחד הערכים, כגון ערכי מיקוד או שמות של רחובות, הנו חוקי.
3. משנה ערכים שהוא אינו מזהה.

המודל משתמש בטכניקות מבוססות למידת מכונה כדי לשפר כתובות. כמו בכל מודל מבוסס למידת מכונה, דיוק של 100 אחוז אינו מובטח.

## <a name="supported-countries-or-regions"></a>מדינות או אזורים נתמכים

אנו תומכים כיום בכתובות מועשרות במדינות או באזורים הבאים:

- אוסטרליה
- קנדה
- צרפת
- גרמניה
- איטליה
- יפן
- בריטניה
- ארצות הברית

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי‬** באריח **‏‫כתובות משופרות**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="צילום מסך של האריח 'כתובות משופרות'.":::

1. בדוק את הסקירה הכללית ולאחר מכן בחר **הבא**.

1. בחר את **ערכת הנתונים של הלקוח** ולאחר בחר בפרופיל או בפלח שברצונך להעשיר. הישות *לקוח* מעשיר את כל פרופילי הלקוחות שלך בעוד שפלח מעשיר רק פרופילי לקוחות הנכללים באותו פלח.

1. בחר את התבנית של הכתובות בערכת הנתונים שלך. בחר **כתובת בעלת תכונה יחידה** אם הכתובות בנתונים שלך משתמשות בשדה יחיד. בחר **כתובת בעלת תכונות מרובות** אם הכתובות בנתונים שלך משתמשות ביותר משדה נתונים אחד.

1. בחר **הבא** ומפה את שדות הכתובות מיישות הלקוח המאוחד שלך.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="דף מיפוי שדה של כתובת משופרת.":::

   > [!NOTE]
   > מדינה / אזור נדרשים הן בכתובת בעלת תכונה יחידה והן בכתובת מרובת תכונות. לא תתבצע העשרה של כתובות שאינן מכילות ערכים חוקיים או נתמכים של מדינה/אזור.

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. ספק **שם** עבור ההעשרה ועבור **ישות הפלט**.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

## <a name="enrichment-results"></a>תוצאות העשרה

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

הנתון **מספר לקוחות מועשרים לפי שדה** מספק הסבר מפורט על הכיסוי של כל שדה מועשר.

### <a name="overview-card"></a>כרטיס סקירה כללית

כרטיס **מבט כולל על שינויי לקוחות** מציג פרטים על כיסוי ההעשרה:

- **כתובות שעובדו ושונו**: מספר פרופילי הלקוחות עם כתובות שהועשרו בהצלחה.
- **כתובות שעובדו ולא השתנו**: מספר פרופילי הלקוחות עם כתובות שזוהו אך לא השתנו. זה קורה בדרך כלל כאשר נתוני הקלט תקפים ולא ניתן לשפר אותם על ידי ההעשרה.
- **כתובות שלא עובדו ולא השתנו**: מספר הפרופילים עם כתובות שלא זוהו. בדרך כלל עבור נתוני קלט שאינם חוקיים או שאינם נתמכים על ידי העשרה.

## <a name="next-steps"></a>השלבים הבאים

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
