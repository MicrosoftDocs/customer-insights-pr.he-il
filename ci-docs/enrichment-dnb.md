---
title: העשרת פרופילי החברה באמצעות Dun & Bradstreet
description: מידע כללי על העשרת צד שלישי של Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c738c2657d4cda213342629156ddc8104366bd8a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755401"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>העשרת פרופילי החברה באמצעות Dun & Bradstreet ‏(Preview)‏

חברת Dun & Bradstreet מספקת נתונים מסחריים, ניתוחים ותובנות לעסקים. היא מאפשרת ללקוחות עם פרופילי לקוחות אחידים לחברות להעשיר את הנתונים שלהם. ההעשרה כוללת תכונות כגון מספר DUNS, גודל החברה, המיקום, הענף ועוד.

## <a name="prerequisites"></a>דרישות מוקדמות

כדי להגדיר את התצורת ההעשרה של Dan & Bradstreet, הדרישות המוקדמות הבאות חייבות להתקיים:

- יש לך רישיון פעיל עבור[Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- יש לך [פרופילי לקוחות מאוחדים](customer-profiles.md) עבור חברות.
- תצורת החיבור של [Dun & Bradstreet](connections.md) מוגדר על ידי מנהל מערכת. אתה יכול ליצור את החיבור אם יש לך הרשאות של [מנהל מערכת](permissions.md#admin) והאישורים מ-Dun & Bradstreet Connect.

## <a name="setting-up-your-dun--bradstreet-project"></a>הגדרת פרויקט Dun & Bradstreet

כמשתמש מורשה של Dun & Bradstreet, אתה יכול להגדיר פרויקט ב- [‎Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).


1. התחבר ל- [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). כדי לאחזר אישורים, [שחזר את הסיסמה שלך](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. הורד את [קובץ תבנית ה-CSV שלנו](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) שישמשו למיפוי שדות של Customer Insights לגבי קהלים לשדות Dun & Bradstreet התואמים.

1. העלה את הקובץ בשת **העלאת נתונים** בחוויית יצירת פרויקט Dun & Bradstreet.

1. בחר את הנקודות האופקיות מתחת ל **מקור** הרלוונטי בפרויקט Dun & Bradstreet שנוצר זה עתה כדי לראות את האפשרויות הזמינות.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="צילום מסך של נקודות בפרויקט של Dun & Bradstreet.":::

1. בחר **קבל פרטי S3**. אחסן מידע זה במקום בטוח. תצטרך אותו כדי [להגדיר את החיבור להעשרה](#configure-a-connection-for-dun--bradstreet) ב- Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="צילום מסך של בחירת מידע s3 בפרויקט Dun & Bradstreet.":::

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה**.

1. בחר **העשר את הנתונים שלי** על אריח Dun & Bradstreet ובחר **תחילת העבודה**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="צילום מסך של אריח Dun & Bradstreet.":::

1. בחר [חיבור](connections.md) מהרשימה הנפתחת. צור קשר עם מנהל מערכת אם אין חיבור זמין. אם אתה מנהל מערכת, תוכל ליצור חיבור. בחר **הוסף חיבור** ובחר **Dun & Bradstreet**.

1. בחר **התחבר ל- Dun & Bradstreet** כדי לאשר את החיבור.

1. בחר **הבא** ולאחר מכן בחר את **ערכת נתוני לקוח** שברצונך להעשיר בנתוני חברה מ- Dun & Bradstreet. באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרטי Unified Customer Profile הנכללים בפלח זה.

1. בחר **הבא** והגדר באיזה שדות מהפרופילים המאוחדים שלך יש להשתמש כדי לחפש נתוני חברה תואמים מ- Dun & Bradstreet. השדות נדרשים הם **מספר DUNS** או **שם החברה** ו **מדינה**. השדה מדינה תומך [בקודי מדינה שכוללים שתיים או שלוש אותיות](https://www.iso.org/iso-3166-country-codes.html), שם המדינה באנגלית, שם המדינה בשפת המקומית וקידומת הטלפון. כמה גרסאות נפוצות של מדינה כוללות:

- US:‏ United States of America, ארצות הברית, ארה"ב, אמריקה.
- CA: קנדה.
- GB: ‏United Kingdom, בריטניה, UK, GB, הממלכה המאוחדת של בריטניה וצפון אירלנד, הממלכה המאוחדת של בריטניה.
- AU:‏ Australia, אוסטרליה, חבר העמים של אוסטרליה.
- FR: ‏France,‏ צרפת, הרפובליקה הצרפתית.
- DE: ‏Germany, גרמניה, גרמנית, דויטשלנד, אלמגן, הרפובליקה הפדרלית של גרמניה, הרפובליקה של גרמניה.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="חלונית מיפוי שדות של Dun & Bradstreet.":::

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. ספק שם עבור ההעשרה ובחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

## <a name="configure-a-connection-for-dun--bradstreet"></a>הגדרת חיבור עבור Dun & Bradstreet

עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים. בחר באפשרות **הוסף חיבור** בעת הגדרת ההעשרה או *עבור אל* **מנהל מערכת** > **חיבורים** ובחר **הגדר** באריח של Dun & Bradstreet.

1. בחר **תחילת העבודה**.

1. הזן שם עבור החיבור בתיבה **שם תצוגה**.

1. ספק אישורים תקפים של Dun & Bradstreet ופרטי פרויקט Dun & Bradstreet *אזור, נתיב תקיית ההצבה ושם תיקיית ההצבה*. ניתן [לקבל את המידע הזה](#setting-up-your-dun--bradstreet-project) מפרויקט Dun & Bradstreet.

1. סקור את **פרטיות ותאימות נתונים** ותן את הסכמתך על-ידי בחירת **אני מסכים**.

1. בחר **אימות** כדי לאמת את התצורה.

1. לאחר השלמת האימות, בחר **שמור**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="דף הגדרת חיבור עבור Dun & Bradstreet.":::

## <a name="enrichment-results"></a>תוצאות העשרה

לאחר רענון ההעשרה תוכל לסקור את נתוני החברה שהועשרו לאחרונה מתחת ל[העשרות שלי](enrichment-hub.md). תוכל למצוא את זמן העדכון האחרון ואת מספר הפרופילים המועשרים.

אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.

## <a name="next-steps"></a>השלבים הבאים

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Dun & Bradstreet, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אך אתה אחראי להבטיח ש- Dun & Bradstreet עומד בכל מחויבויות הפרטיות או האבטחה שלקחת על עצמך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.

[!INCLUDE[footer-include](includes/footer-banner.md)]
