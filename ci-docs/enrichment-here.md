---
title: העשרת פרופילי לקוחות באמצעות HERE Technologies ‏(Preview)
description: מידע כללי אודות העשרה של צד שלישי באמצעות HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: d88085b6be156dd1c895e9e5b38cc9d77acbdb95
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9052052"
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

1. סקור את [פרטיות ותאימות נתונים](#data-privacy-and-compliance) ותן את הסכמתך על-ידי בחירת **אני מסכים**.

1. בחר **אמת** כדי לאמת את התצורה ולאחר מכן בחר **שמור**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="דף תצורת החיבור של HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל HERE Technologies, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- HERE Technologies עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי** **מיקום** מהאריח של HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="אריח HERE Technologies.":::

1. בדוק את הסקירה הכללית ולאחר מכן בחר **הבא**.

1. בחר את החיבור. פנה אל מנהל מערכת אם אחד לא זמין.

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
