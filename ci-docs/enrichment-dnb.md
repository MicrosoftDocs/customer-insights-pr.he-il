---
title: העשרת פרופילי החברה באמצעות Dun & Bradstreet ‏(Preview)‏
description: מידע כללי על העשרת צד שלישי של Dun & Bradstreet.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: e89b64774dcb519a071dd3d403473807a50e7f33
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237905"
---
# <a name="enrich-company-profiles-with-dun--bradstreet-preview"></a>העשרת פרופילי החברה באמצעות Dun & Bradstreet ‏(Preview)‏

חברת Dun & Bradstreet מספקת נתונים מסחריים, ניתוחים ותובנות לעסקים. היא מאפשרת ללקוחות עם פרופילי לקוחות אחידים לחברות להעשיר את הנתונים שלהם. ההעשרה כוללת תכונות כגון מספר DUNS, גודל החברה, המיקום, הענף ועוד.

## <a name="prerequisites"></a>דרישות מוקדמות

- רישיון פעיל עבור[Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [פרופילי Unified Customer profile](customer-profiles.md) עבור חברות.
- מוגדר [פרויקט](#set-up-your-dun--bradstreet-project) ‏Dun & Bradstreet.
- [חיבור](connections.md) של Dun & Bradstreet [מוגדר](#configure-a-connection-for-dun--bradstreet) על ידי מנהל מערכת.

## <a name="set-up-your-dun--bradstreet-project"></a>הגדרת פרויקט Dun & Bradstreet

כמשתמש מורשה של Dun & Bradstreet, אתה יכול להגדיר פרויקט ב- [‎Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. התחבר ל- [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). כדי לאחזר אישורים, [שחזר את הסיסמה שלך](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. הורד את [קובץ תבנית ה-CSV שלנו](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) שישמשו למיפוי שדות של Customer Insights לגבי קהלים לשדות Dun & Bradstreet התואמים.

1. העלה את הקובץ בשת **העלאת נתונים** בחוויית יצירת פרויקט Dun & Bradstreet.

1. בחר את הנקודות האופקיות מתחת ל **מקור** הרלוונטי בפרויקט Dun & Bradstreet שנוצר זה עתה כדי לראות את האפשרויות הזמינות.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="צילום מסך של נקודות בפרויקט של Dun & Bradstreet.":::

1. בחר **קבל פרטי S3**. אחסן מידע זה במקום בטוח. תצטרך אותו כדי [להגדיר את החיבור להעשרה](#configure-a-connection-for-dun--bradstreet) ב- Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="צילום מסך של בחירת מידע s3 בפרויקט Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>הגדרת חיבור עבור Dun & Bradstreet

עליך להיות [מנהל מערכת](permissions.md#admin) ב- Customer Insights ובעל אישורים מ- Dun & Bradstreet Connect.

1. בחר באפשרות **הוסף חיבור** בעת הגדרת ההעשרה או עבור אל **מנהל מערכת** > **חיבורים** ובחר **הגדר** באריח של Dun & Bradstreet.

1. הזן שם עבור החיבור.

1. ספק אישורים תקפים של Dun & Bradstreet ופרטי פרויקט Dun & Bradstreet *אזור, נתיב תקיית ההצבה ושם תיקיית ההצבה*. ניתן [לקבל את המידע הזה](#set-up-your-dun--bradstreet-project) מפרויקט Dun & Bradstreet.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **אמת** כדי לאמת את התצורה ולאחר מכן בחר **שמור**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="דף הגדרת חיבור עבור Dun & Bradstreet.":::

## <a name="supported-countries-or-regions"></a>מדינות או אזורים נתמכים

כרגע אנו תומכים באפשרויות המדינה/אזור הבאות: קנדה (אנגלית) או ארצות הברית (אנגלית).

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי** ב **נתוני חברה** עבור האירח Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="צילום מסך של אריח Dun & Bradstreet.":::

1. בדוק את הסקירה הכללית ולאחר מכן בחר **הבא**.

1. בחר את החיבור ואשר. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. בחר **הבא**.

1. בחר את **ערכת הנתונים של הלקוח** ולאחר בחר פרופיל או פלח שברצונך להעשיר בנתוני חברה מ- Dun & Bradstreet. הישות *לקוח* מעשיר את כל פרופילי הלקוחות שלך בעוד שפלח מעשיר רק פרופילי לקוחות הנכללים באותו פלח.

1. קבע באילו סוגי שדות מהפרופילים המאוחדים יש להשתמש כדי לחפש נתוני חברה תואמים מ- Dun & Bradstreet. לפחות אחד מהשדות **שם וכתובת**, **טלפון** או **דואר** נדרש.

1. בחר **הבא**

1. מפה את השדות שלך אל נתוני החברה מ- Dun & Bradstreet. השדות נדרשים הם **מספר DUNS** או **שם החברה** ו **מדינה**.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="חלונית מיפוי שדות של Dun & Bradstreet.":::

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. ספק **שם** עבור ההעשרה ועבור **שם ישות הפלט**.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

1. בחר **הפעל** כדי להתחיל את תהליך ההעשרה או לסגור כדי לחזור אל דף **העשרה**.

## <a name="view-enrichment-results"></a>הצג תוצאות העשרה

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>‏‫השלבים הבאים‬

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
