---
title: העשרת פרופילי החברה באמצעות Leadspace ‏(Preview)‏
description: מידע כללי אודות העשרה של צד שלישי באמצעות Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b58532a541ee22a5e34d0af1a3334ccbd53627b2
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081350"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>העשרת פרופילי החברה באמצעות Leadspace ‏(Preview)‏

Leadspace היא חברת מדע נתונים שמספקת פלטפורמת נתוני לקוח מעסק לעסק. הוא מאפשר לסביבות עם פרופילי לקוחות מאוחדים המבוססים על חשבונות להעשיר את הנתונים שלהן. העשר *פרופילי לקוחות* עם תכונות כמו גודל חברה, מיקום או תעשייה. העשר *פרופילי אנשי קשר* עם תכונות כמו כותרת, אישיות או אימות דואר אלקטרוני.

## <a name="prerequisites"></a>דרישות מוקדמות

- רשיון Leadspace פעיל.
- יש לך [פרופילי Unified customer profiles](customer-profiles.md) המבוססים על תיקי לקוח.
- תצורת [החיבור](connections.md) של Leadspace [מוגדרת](#configure-the-connection-for-leadspace) על ידי מנהל מערכת. צור קשר ישירות עם [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) לקבלת פרטים על המוצר שלהם.

## <a name="configure-the-connection-for-leadspace"></a>קביעת תצורת החיבור עבור Leadspace

אתה חייב להיות [מנהל מערכת](permissions.md#admin) ב- Customer Insights ובעל "המפתח התמידי" (המכונה **אסימון Leadspace**).

1. בחר **הוסף חיבור** בעת קביעת תצורת העשרה או עבור אל **מנהל מערכת** > **חיבורים** ובחר **הגדר** באריח Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="דף תצורת החיבור של Leadspace.":::

1. הזן שם לחיבור ואסימון Leadspace תקף.

1. סקור את [פרטיות ותאימות נתונים](#data-privacy-and-compliance) ותן את הסכמתך על-ידי בחירת **אני מסכים**.

1. בחר **אמת** כדי לאמת את התצורה ולאחר מכן בחר **שמור**.

### <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Leadspace, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Leadspace עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי** ב **נתוני חברה** מהאריח של Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="צילום מסך של אריח Leadspace.":::

1. בדוק את הסקירה הכללית ולאחר מכן בחר **הבא**.

1. בחר את החיבור. פנה אל מנהל מערכת אם אחד לא זמין.

1. בחר **הבא**.

1. בחר את **ערכת הנתונים של הלקוח** ובחר בפרופיל או בפלח שברצונך להעשיר בנתוני חברה מ- Leadspace. הישות *לקוח* מעשיר את כל פרופילי הלקוחות שלך בעוד שפלח מעשיר רק פרופילי לקוחות הנכללים באותו פלח.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. הגדר באילו סוגי שדות מהפרופילים המאוחדים שלך יש להשתמש לצורך התאמה: הכתובת הראשית ו/או המשנית. באפשרותך לציין מיפוי שדה עבור שתי הכתובות ולהעשיר את הפרופילים עבור שתי הכתובות בנפרד. למשל, עבור כתובת בית וכתובת עסק. בחר **הבא**.

1. מפה את השדות שלך אל נתוני החברה מ- Leadspace. השדה **שם חברה** הוא נדרש. לקבלת דיוק התאמות גבוה יותר, ניתן להוסיף עד שני שדות אחרים, **אתר אינטרנט של חברה** ו **מיקום חברה**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="חלונית מיפוי שדה של Leadspace.":::

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. בחר בתיבת הסימון אם יש לך *פרופילי אנשי קשר* שברצונך להעשיר. Customer Insights ימפו באופן אוטומטי את השדות הנדרשים.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="העשרת רשומות אנשי קשר של Leadspace.":::

1. בחר **הבא**.

1. ספק **שם** עבור ההעשרה ועבור **שם ישות הפלט**.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

1. בחר **הפעל** כדי להתחיל את תהליך ההעשרה או לסגור כדי לחזור אל דף **העשרה**.

## <a name="view-enrichment-results"></a>הצג תוצאות העשרה

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

לקבלת מידע נוסף, ראה [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>‏‫השלבים הבאים‬

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
