---
title: העשרת פרופילי הלקוחות בנתוני מיקום מ- Azure Maps‏ (Preview)
description: מידע כללי על העשרת צד ראשון של Azure Maps.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238043"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>העשרת פרופילי הלקוחות בנתוני מיקום מ- Azure Maps‏ (Preview)

Azure Maps מספקת נתונים ושירותים ממוקדי מיקום כדי לספק חוויות המבוססות על נתונים גיאו-מרחביים עם בינת מיקום מובנית. שירותי העשרת הנתונים של Azure Maps מספקים את הדיוק של מידע המיקום על הלקוחות שלך. הם מספקים יכולות כגון נרמול כתובות וחילוץ קו אורך וקו רוחב אל Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>דרישות מוקדמות

- מנוי Azure Maps פעיל. לקבלת מינוי, [הירשם או קבל ניסיון ללא תשלום](https://azure.microsoft.com/services/azure-maps/).

- תצורת [החיבור](connections.md) של Azure Maps[ מוגדרת](#configure-the-connection-for-azure-maps) על ידי מנהל מערכת.

## <a name="configure-the-connection-for-azure-maps"></a>קבע את תצורת החיבור עבור Azure Maps

אתה חייב להיות [מנהל מערכת](permissions.md#admin) ב-Customer Insights ובעל מפתח API פעיל של Azure Maps.

1. בחר **הוסף חיבור** בעת קביעת תצורה של העשרה, או עבור אל **ניהול** > **חיבורים** ובחר **הגדר** באריח Azure Maps.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="דף קביעת תצורה של חיבור Azure Maps.":::

1. הזן שם לחיבור ומפתח תקף של ה- ‏API של Azure Maps.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **אמת** כדי לאמת את התצורה ולאחר מכן בחר **שמור**.

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי** ב **מיקום** מהאריח של Microsoft Azure Maps.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="אריח Azure Maps.":::

1. בדוק את הסקירה הכללית ולאחר מכן בחר **הבא**.

1. בחר את החיבור. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. בחר **הבא**.

1. בחר את **ערכת הנתונים של הלקוח** ולאחר בחר פרופיל או פלח שברצונך להעשיר בנתונים מ- Microsoft. הישות *לקוח* מעשיר את כל פרופילי הלקוחות שלך בעוד שפלח מעשיר רק פרופילי לקוחות הנכללים באותו פלח.

1. הגדר באילו סוגי שדות מהפרופילים המאוחדים שלך יש להשתמש לצורך התאמה: הכתובת הראשית ו/או המשנית. באפשרותך לציין מיפוי שדה עבור שתי הכתובות ולהעשיר את הפרופילים עבור שתי הכתובות בנפרד. למשל, עבור כתובת בית וכתובת עסק. בחר **הבא**.

1. מפה את השדות שלך אל נתוני מיקום מ- Azure Maps. השדות **רחוב 1** ו **מיקוד** נדרשים עבור הכתובת הראשית ו/או המשנית שנבחרה. לדיוק התאמה גבוה יותר, הוסף שדות נוספים.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="מיפוי תכונות של Azure Maps.":::

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. סקור את **ההגדרות המתקדמות** המציעות גמישות מרבית לטיפול במקרי שימוש מתקדמים. עם זאת, בדרך כלל אין צורך לשנות את ערכי ברירת המחדל הבאים.

   - **סוג כתובות**: התאמת הכתובת הטובה ביותר חוזרת גם אם היא לא שלמה. כדי לקבל כתובות שלמות בלבד&mdash;לדוגמה, כתובות הכוללות את מספר הבית&mdash;נקה את כל תיבות הסימון למעט **כתובות נקודה**.
   - **שפה**: כתובות חוזרות בשפה המבוססת על אזור הכתובות. כדי להחיל שפת כתובת מתוקננת, בחר את השפה מהתפריט הנפתח. לדוגמה, בחירה ב **אנגלית** מחזירה **Copenhagen, Denmark** במקום **København, Danmark**.
   - **מספר מקסימלי של תוצאות**: מספר תוצאות לכל כתובת.

1. בחר **הבא**.

1. ספק **שם** עבור ההעשרה ועבור **שם ישות הפלט**.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

1. בחר **הפעל** כדי להתחיל את תהליך ההעשרה או לסגור כדי לחזור אל דף **העשרה**.

## <a name="view-enrichment-results"></a>הצג תוצאות העשרה

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

הנתון **מספר לקוחות מועשרים לפי שדה** מספק הסבר מפורט על הכיסוי של כל שדה מועשר.

## <a name="next-steps"></a>‏‫השלבים הבאים‬

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
