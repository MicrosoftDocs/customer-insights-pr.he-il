---
title: העשרת פרופילי הלקוחות בנתוני זהות מ- LiveRamp‏ (Preview)
description: העשרת פרופילי לקוחות עם נתוני LiveRamp
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196349"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>העשרת פרופילי הלקוחות בנתוני זהות מ- LiveRamp‏ (Preview)

LiveRamp מספק פתרון זהות לא מקוון דטרמיניסטי ואיחוד נתוני לקוחות. ניתן למפות מזהים אישיים בנתוני הלקוחות שלך לגרף הזהות של AbiliTec ולקבל מזהים של AbiliTec. לאחר מכן תוכל להשתמש במזהים אלה לאיחוד טוב יותר של נתוני הלקוחות שלך.

## <a name="supported-countriesregions"></a>מדינות/אזורים נתמכים

כרגע אנו תומכים בהעשרת פרופילי לקוחות בנתוני LiveRamp בארצות הברית בלבד.

## <a name="prerequisites"></a>דרישות מוקדמות

- מנוי LiveRamp פעיל. כדי לקבל מנוי, צור קשר עם צוות חשבון LiveRamp שלך או go [dynamics@liveramp.com](mailto:dynamics@liveramp.com) למידע נוסף.

- מנוי AbiliTec פעיל עם מזהה וסוד לקוח לגישה ל- API. לקבלת מידע נוסף, ראה ‏‫[מרכז המפתחים של ה-API של AlibiTec](https://developers.liveramp.com/abilitec-api/).

- תצורת [החיבור](connections.md) של LiveRamp [מוגדרת](#configure-the-connection-for-liveramp) על ידי מנהל מערכת.

## <a name="configure-the-connection-for-liveramp"></a>הגדרת את החיבור עבור LiveRamp

עליך להיות [מנהל מערכת](permissions.md#admin) ב- Customer Insights ולהיות בעל מזהה לקוח LiveRamp פעיל וסוד.

1. בחר באפשרות **הוסף חיבור** בעת הגדרת ההעשרה או עבור אל **מנהל מערכת** > **חיבורים** ובחר **הגדר** באריח של LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="חלונית קביעת התצורה להגדרת החיבור לשירות LiveRamp AbiliTec. ":::

1. הזן שם לחיבור ומזהה לקוח LiveRamp וסוד תקינים.

1. סקור את [פרטיות ותאימות נתונים](#data-privacy-and-compliance) ותן את הסכמתך על-ידי בחירת **אני מסכים**.

1. בחר **אמת** כדי לאמת את התצורה ולאחר מכן בחר **שמור**.

### <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Liveramp, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אך אתה אחראי להבטיח ש- LiveRamp עומד בכל מחויבויות הפרטיות או האבטחה שלקחת על עצמך. למידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי** ב **זהות** באריח LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="האריח זהות בדף 'מבט כולל על העשרה'. ":::

1. בדוק את הסקירה הכללית ולאחר מכן בחר **הבא**.

1. בחר את החיבור. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. בחר **הבא**.

1. בחר את **ערכת הנתונים של הלקוח** ובחר פרופיל או פלח שברצונך להעשיר בנתוני זהות מ- LiveRamp. הישות *לקוח* מעשיר את כל פרופילי הלקוחות שלך בעוד שפלח מעשיר רק פרופילי לקוחות הנכללים באותו פלח.

1. קבע באילו סוגי שדות מהפרופילים המאוחדים יש להשתמש כדי לחפש נתוני זהות תואמים מ- LiveRamp. לפחות אחד מהשדות **שם וכתובת**, **טלפון** או **דואר אלקטרוני** נדרש. לדיוק התאמה גבוה יותר, הוסף שדות נוספים. בחר **הבא**.

1. מפה את השדות שלך אל נתוני זהוי מ- LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="אפשרויות מיפוי נתונים להעשרת LiveRamp.":::

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. ספק **שם** עבור ההעשרה ועבור **שם ישות הפלט**.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

1. בחר **הפעל** כדי להתחיל את תהליך ההעשרה או לסגור כדי לחזור אל דף **העשרה**.

## <a name="view-enrichment-results"></a>הצג תוצאות העשרה

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

הנתון **מספר לקוחות מועשרים לפי שדה** מספק הסבר מפורט על הכיסוי של כל שדה מועשר.

## <a name="next-steps"></a>‏‫השלבים הבאים‬

בנה על נתוני הלקוחות המועשרים שלך. השתמש במזהי AbiliTec כדי לאחד את פרופילי הלקוחות לתצוגה מבוססת אדם.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
