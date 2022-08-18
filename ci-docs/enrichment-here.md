---
title: העשרת פרופילי לקוחות באמצעות HERE Technologies ‏(Preview)
description: מידע כללי אודות העשרה של צד שלישי באמצעות HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237859"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>העשרת פרופילי לקוחות באמצעות HERE Technologies ‏(Preview)

HERE Technologies היא חברת פלטפורמת מיקום המספקת נתונים ושירותים הממוקדים במיקום. שירותי העשרת הנתונים של HERE Technologies משפרים את הדיוק של פרטי המיקום של הלקוחות שלך. הוא מספק נורמליזציה של כתובת, חילוץ קווי רוחב ואורך ועוד.

## <a name="prerequisites"></a>דרישות מוקדמות

- מנוי פעיל של HERE Technologies. כדי לקבל מנוי, [הירשם כאן](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) או [צור קשר עם HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) בצורה ישירה. [קבל מידע נוסף אודות העשרת מיקום של HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- תצורת [החיבור](connections.md) של HERE [מוגדרת](#configure-the-connection-for-here-technologies) על ידי מנהל מערכת.

## <a name="configure-the-connection-for-here-technologies"></a>הגדת את תצורת החיבור של HERE Technologies

אתה חייב להיות [מנהל מערכת](permissions.md#admin) ב-Customer Insights ובעל מפתח API פעיל של HERE Technologies.

1. בחר **הוסף חיבור** בעת קביעת תצורת העשרה או עבור אל **מנהל מערכת** > **חיבורים** ובחר **הגדרה** באריח HERE Technologies.

1. הזן שם לחיבור ומפתח תקף של HERE Technologies API.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **אמת** כדי לאמת את התצורה ולאחר מכן בחר **שמור**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="דף תצורת החיבור של HERE Technologies.":::

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי** **מיקום** מהאריח של HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="אריח HERE Technologies.":::

1. בדוק את הסקירה הכללית ולאחר מכן בחר **הבא**.

1. בחר את החיבור. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. בחר **הבא**.

1. בחר את **ערכת הנתונים של הלקוח** ולאחר בחר פרופיל או פלח שברצונך להעשיר בנתונים מ- HERE Technologies. הישות *לקוח* מעשיר את כל פרופילי הלקוחות שלך בעוד שפלח מעשיר רק פרופילי לקוחות הנכללים באותו פלח.

1. הגדר באילו סוגי שדות מהפרופילים המאוחדים שלך יש להשתמש לצורך התאמה: הכתובת הראשית ו/או המשנית. באפשרותך לציין מיפוי שדה עבור שתי הכתובות ולהעשיר את הפרופילים עבור שתי הכתובות בנפרד. למשל, עבור כתובת בית וכתובת עסק. בחר **הבא**.

1. מפה את השדות שלך לנתונים מ- HERE Technologies. השדות **רחוב 1** ו **מיקוד** נדרשים עבור הכתובת הראשית ו/או המשנית שנבחרה. לדיוק התאמה גבוה יותר, הוסף שדות נוספים.

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. ספק **שם** עבור ההעשרה ועבור **שם ישות הפלט**.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

1. בחר **הפעל** כדי להתחיל את תהליך ההעשרה או לסגור כדי לחזור אל דף **העשרה**.

## <a name="view-enrichment-results"></a>הצג תוצאות העשרה

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

הנתון **מספר לקוחות מועשרים לפי שדה** מספק הסבר מפורט על הכיסוי של כל שדה מועשר.

## <a name="next-steps"></a>‏‫השלבים הבאים‬

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
