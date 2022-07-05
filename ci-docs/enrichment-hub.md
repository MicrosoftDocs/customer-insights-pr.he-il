---
title: סקירה כללית של העשרת נתונים (Preview)
description: השתמש ביכולות של Microsoft ושירותי צד שלישי אחרים כדי להעשיר את נתוני הלקוחות שלך.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 6b6daab480db5e37830ff58b71dcdd3bbdbe46da
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053873"
---
# <a name="data-enrichment-preview-overview"></a>סקירה כללית של העשרת נתונים (Preview)

השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך. העשרות צד שלישי מוגדרות באמצעות [חיבורים](connections.md), אשר מנהל מערכת מגדיר עם אישורים ומספק הסכמה עבור העברות נתונים. מנהלים ומשתתפים יכולים להשתמש בחיבורים כדי לקבוע תצורה של העשרות.  

## <a name="multiple-enrichments-of-the-same-type"></a>העשרות מרובות מאותו סוג

הישות שיש להעשיר מצוינת במהלך קביעת תצורת ההעשרה, אשר מאפשרת לך להעשיר רק ערכת משנה של הפרופילים שלך. לדוגמה, העשרת נתונים רק עבור פלח ספציפי. באפשרותך לקבוע תצורה של מספר העשרות מאותו סוג ולהשתמש מחדש באותו חיבור. לחלק מההעשרות יהיו מגבלות על מספר ההעשרות מאותו הסוג שניתן ליצור. ניתן לראות את המגבלות והשימוש הנוכחי על כל אריח בכרטיסיה **גילוי** בדף **העשָרה**.

## <a name="enrich-data-sources-before-unification"></a>העשר את מקורות הנתונים לפני האיחוד

אתה יכול להעשיר את נתוני הלקוחות שלך לפני איחוד הנתונים כדי לעזור להגביר את האיכות של התאמת נתונים. למידע נוסף, ראה [העשרת מקורות נתונים](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>יצירת העשרה

עליך להיות בעל [הרשאות](permissions.md) מנהל מערכת כדי ליצור או לערוך העשרות.

עבור אל **נתונים** > **העשרה**. בכרטיסיה **גלוי**, תמצא את כל אפשרויות ההעשרה הנתמכות.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="דף מרכז ההעשרה.":::

# <a name="individual-consumers-b-to-c"></a>[צרכנים בודדים (B-to-C)](#tab/b2c)

- [זהות AbiliTec](enrichment-liveramp.md) מסופק על ידי LiveRamp AbiliTec
- [מותגים](enrichment-microsoft.md) שסופקו על-ידי Microsoft
- [נתונים דמוגרפיים](enrichment-experian.md) המסופקים על-ידי Experian
- [כתובות משופרות](enrichment-enhanced-addresses.md) מסופקות על-ידי Microsoft
- [תחומי עניין](enrichment-microsoft.md) שסופקו על-ידי Microsoft
- [נתוני מיקום](enrichment-azure-maps.md) המסופקים על ידי Microsoft Azure Maps
- [נתוני מיקום](enrichment-here.md) מסופקים על-ידי HERE Technologies
- [נתוני SFTP מותאמים אישית](enrichment-SFTP-custom-import.md) דרך פרוטוקול העברת קבצים מאובטחת (SFTP)

# <a name="business-accounts-b-to-b"></a>[תיקי לקוחות עסקיים (B-to-B)](#tab/b2b)

- [נתוני מעורבות בחשבון](enrichment-office.md) מסופקים על ידי Microsoft
- [נתוני חברה](enrichment-dnb.md) מבית Dun & Bradstreet
- [נתוני החברה](enrichment-leadspace.md) מסופקים על-ידי Leadspace
- [כתובות משופרות](enrichment-enhanced-addresses.md) מסופקות על-ידי Microsoft
- [נתוני חברה משופרים](enrichment-enhanced-company-data.md) מסופקים על-ידי Microsoft.
- [נתוני מיקום](enrichment-azure-maps.md) המסופקים על ידי Microsoft Azure Maps
- [נתוני מיקום](enrichment-here.md) מסופקים על-ידי HERE Technologies
- [נתוני SFTP מותאמים אישית](enrichment-SFTP-custom-import.md) דרך פרוטוקול העברת קבצים מאובטחת (SFTP)

---

## <a name="manage-existing-enrichments"></a>ניהול העשרות קיימות

עבור אל **נתונים** > **העשרה**. הכרטיסיה **ההעשרות שלי**, הצג את ההעשרות המוגדרות, את המצב שלהן, את מספר הלקוחות המועשרים ואת הפעם האחרונה שבה רועננו הנתונים. אתה יכול למיין את רשימת ההעשרות לפי כל עמודה או להשתמש בתיבת החיפוש כדי למצוא את ההעשרה שברצונך לנהל.

בחר את ההעשרה כדי להציג פעולות זמינות.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="אפשרויות לניהול ההעשרות ברשימת ההעשרות.":::

- **הצג** פרטי העשרה עם המספר של פרופילי לקוחות המועשרים.
- **ערוך** את תצורת ההעשרה.
- [**הפעל**](#run-or-refresh-enrichments) את העשרה לעדכון את פרופילי הלקוחות בנתונים העדכניים ביותר. הפעל מספר העשרות בבת אחת על ידי בחירתם ברשימה.
- **הפעלה** או **ביטול הפעלה** של העשרה. העשרות לא פעילות לא יתרעננו במהלך [רענון מתוזמן](system.md#schedule-tab).
- **מחק** את ההעשרה.

אתה יכול גם ליצור [פלחים](segments.md) או [מדדים](measures.md) מהעשרה.

## <a name="run-or-refresh-enrichments"></a>הפעל או רענן העשרות

לאחר ההפעלה, ניתן לרענן את ההעשרה לפי לוח זמנים אוטומטי או לרענן באופן ידני לפי דרישה.

1. כדי לרענן באופן ידני העשרה אחת או יותר, בחר אותם ובחר **הפעל**. כדי [לתזמן רענון אוטומטי](system.md#schedule-tab), עבור אל **מנהל מערכת** > **מערכת** > **לוח זמנים**. זמן העיבוד תלוי בגודל נתוני הלקוח שלך.

1. באופן אופציונלי, [ניתן לראות את התקדמות תהליך ההעשרה](#see-the-progress-of-the-enrichment-process).

1. לאחר השלמת תהליך ההעשרה, עבור אל **ההעשרות שלי** לסקור את נתוני פרופילי הלקוחות שהועשרו לאחרונה, את זמן העדכון האחרון ואת מספר הפרופילים המועשרים.

1. בחר את ההעשרה כדי לראות את [תוצאות ההעשרה](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>ראה את התקדמות תהליך ההעשרה

באפשרותך למצוא פרטים על עיבוד העשרה, כולל המצב שלה ובעיות אפשריות בעת ביצוע הרענון שלה או לאחר שהרענון הושלם. הבן אילו תהליכים מעורבים כדי לרענן העשרה ואת משך הזמן שנדרש להפעלת התהליכים. מצב ההעשרה נתמך עבור Experian,‏ Leadspace‏, HERE Technologies‏, SFTP Import ו- Azure Maps.

1. עבור אל **נתונים** > **העשרה**.
1. בכרטיסיה **ההעשרה שלי**, בחר את סטטוס ההעשרה כדי לפתוח חלונית צדדית.
1. בחלונית **פרטי התקדמות**, הרחב את המקטע **העשרות**.
1. תחת ההעשרה שברצונך לראות את ההתקדמות שלה, בחר **הצג פרטים**.
1. בחלונית **פרטי משימה**, בחר **הצג פרטים** כדי לראות את התהליכים המעורבים בעדכון ההעשרה והמצב שלהם.

## <a name="view-enrichment-results"></a>הצג תוצאות העשרה

לאחר השלמת הפעלת העשרה, תוכל לעיין בתוצאות ההעשרה.

1. עבור אל **נתונים** > **העשרה**.
1. בכרטיסייה **ההעשרות שלי**, בחר את ההעשרה שברצונך להציג.

כל ההעשרות מציגות מידע בסיסי כגון מספר הפרופילים המועשרים ומספר הפרופילים המועשרים לאורך זמן. האריח **תצוגה מקדימה של לקוחות מועשרים** מציג דוגמה של ישות ההעשרה שנוצרה. כדי לראות תצוגה מפורטת, בחר **ראה עוד** ובחר בכרטיסיה **נתונים**.

:::image type="content" source="media/enrichments-results.png" alt-text="דף תוצאות של פעולות העשרה.":::

אם זמין, הנתון **מספר לקוחות מועשרים לפי תחום** מספק הסבר מפורט על הכיסוי של כל שדה מועשר.

חלק מפעולות ההעשרה מציגים גם מידע ספציפי לסוג ההעשרה. לקבלת מידע נוסף, עיין בתיעוד הקשור.

[!INCLUDE [footer-include](includes/footer-banner.md)]
