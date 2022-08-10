---
title: התחבר אל מקור נתונים של Power Query (מכיל סרטון)
description: עיבוד באמצעות מחבר Power Query (מכיל סרטון).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207046"
---
# <a name="connect-to-a-power-query-data-source"></a>התחבר למקור נתונים של Power Query

Power Query מציע קשת רחבה של מחברים לקליטת נתונים. רוב המחברים הללו נתמכים על ידי Dynamics 365 Customer Insights.

הוספת מקורות נתונים המבוססים על מחברי Power Query בדרך כלל פועלת לפי השלבים המפורטים במקטע הזה. עם זאת, בהתאם למחבר שבו אתה משתמש, נדרש מידע שונה. לקבלת מידע נוסף, ראה את התיעוד על מחברים יחידים בהפניה אל מחבר [Power Query ](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>צור מקור נתונים חדש

1. עבור אל **נתונים** > **מקורות נתונים**.

1. בחר **הוסף מקור נתונים**.

1. בחר **Microsoft Power Query**.

1. ספק **שֵם** ו **תיאור** אופציונלי עבור מקור נתונים, ובחר **הבא**.

1. בחר אחד [מהמחברים הזמינים](#available-power-query-data-sources). בדוגמה זו, אנו בוחרים את המחבר **Text/CSV**.

1. הזן את הפרטים הנדרשים ב- **הגדרות חיבור** עבור המחבר שנבחר ובחר **הבא** כדי לראות תצוגה מקדימה של הנתונים.

1. בחר **המרת נתונים**.

1. תיבת הדו-שיח של **Power Query – עריכת שאילתות** מאפשרת לך לבדוק ולכוונן את הנתונים. הישויות שהמערכות זיהו במקור הנתונים שבחרת מופיעות בחלונית הימנית.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="תיבת דו-שיח של עריכת שאילתות":::

1. באפשרותך גם לשנות את הנתונים שלך. בחר ישות לעריכה או להמרה. השתמש באפשרויות המופיעות בחלון של Power Query כדי לבצע טרנספורמציות. כל טרנספורמציה מופיעה ב **שלבים שיישומו**. Power Query מספק אפשרויות רבות ל[טרנספורמציות בנויות מראש](/power-query/power-query-what-is-power-query#transformations).

   אנו ממליצים להשתמש בטרנפורמציות הבאות:

   - אם אתה קולט נתונים מקובץ CSV, השורה הראשונה מכילה לעיתים קרובות כותרות. עבור אל **שינוי** ובחר **השתמש בשורה הראשונה ככותרות**.
   - ודא שסוג הנתונים מוגדר כראוי. לדוגמה, בשדה התאריך בחר בסוג התאריך.

1. כדי להוסיף ישויות למקור הנתונים שלך בתיבת הדו-שיח **עריכת שאילתות** , עבור אל **בית** ובחר **קבל נתונים**. חזור על שלבים 5-10 עד שתוסיף את כל הישויות עבור מקור נתונים זה. אם ברשותך מסד נתונים הכולל ערכות נתונים מרובות, כל ערכת נתונים היא ישות בפני עצמה.

1. בחר **Save**. הדף **מקורות נתונים** נפתח ומציג את מקור נתונים החדש במצב **ריענון**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

טעינת נתונים עשויה להימשך זמן מה. לאחר רענון מוצלח, ניתן לסקור את הנתונים שעובדו בדף [**ישויות**](entities.md).

> [!CAUTION]
> מקור נתונים המבוסס על Power Query יוצר [תזרים נתונים ב- Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). אל תשנה את השם של זרימת נתונים במרכז הניהול של Power Platform שנמצא בשימוש ב- Customer Insights. שינוי שם של זרימת נתונים גורם לבעיות בהפניות בין מקור הנתונים של Customer Insights לבין זרימת הנתונים של Dataverse.

### <a name="available-power-query-data-sources"></a>מקורות נתונים זמינים של  Power Query

עיין בהפניה למחבר [Power Query ](/power-query/connectors/) כדי למצוא רשימת מחברים לשימוש במהלך ייבוא נתונים ל- Customer Insights.

מחברים עם סימן ביקורת בעמודה **Customer Insights (זרימות נתונים)** זמינים ליצירת מקורות נתונים חדשים המבוססים על Power Query. עיין בתיעוד של מחבר ספציפי כדי ללמוד עוד על הדרישות המוקדמות הדרושות, [מגבלות של שאילתות](/power-query/power-query-online-limits) ופרטים נוספים.

## <a name="add-data-from-on-premises-data-sources"></a>הוספת נתונים ממקורות נתונים מקומיים

עיבוד נתונים ממקורות נתונים מקומיים נתמכת על סמך זרימות הנתונים של Microsoft Power Platform ‏(PPDFs‎‏). תוכל להפוך תזרימי נתונים לזמינים ב- Customer Insights על ידי [מתן  כתובת URL של סביבת Microsoft Dataverse](create-environment.md) בעת הגדרת הסביבה.

מקורות נתונים שנוצרים לאחר שיוך Dataverse סביבה עם Customer Insights משתמשים [Power Platform בתזרימי נתונים](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) כברירת מחדל. זרימות נתונים תומכות בקישוריות מקומית באמצעות שער הנתונים. תוכל להסיר וליצור מחדש מקורות נתונים שהתקיימו לפני שיוך Dataverse סביבה [באמצעות שערי נתונים מקומיים](/data-integration/gateway/service-gateway-app).

שערי נתונים מסביבה קיימת של Power BI או של Power Apps יהיו גלויים ותוכל להשתמש בהם מחדש ב- Customer Insights. דף מקורות הנתונים מציג קישורים למעבר אל סביבת Microsoft Power Platform שבה תוכל להציג ולהגדיר את שערי הנתונים המקומיים.

> [!IMPORTANT]
> ודא שהשערים שלך מעודכנים לגרסה האחרונה. אפשר להתקין עדכון ולהגדיר מחדש שער ישירות מהנחיה המוצגת על מסך השער ישירות או [להוריד את הגרסה העדכנית ביותר](https://powerapps.microsoft.com/downloads/). אם אינך משתמש בגרסת השער העדכנית ביותר, רענון זרימת הנתונים נכשל עם הודעות שגיאה כמו **מילת המפתח אינה נתמכת: מאפייני תצורה. שם פרמטר: מילת מפתח**.
>
> שגיאות בשערי נתונים מקומיים ב- Customer Insights נגרמות לרוב מבעיות בתצורה. לקבלת מידע נוסף על פתרון בעיות בשערי נתונים, ראה [פתרון בעיות בשער הנתונים המקומי](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>עריכת מקורות נתונים של Power Query

> [!NOTE]
> ייתכן שאין אפשרות לבצע שינויים במקורות נתונים הנמצאים כעת בשימוש באחד מתהליכי היישום (פילוח או איחוד נתונים לדוגמה).
>
> בדף **הגדרות**, באפשרותך לעקוב אחר ההתקדמות של כל אחד מהתהליכים הפעילים. כאשר תהליך הושלם, באפשרותך לחזור לדף **מקורות הנתונים** ולבצע את השינויים.

1. עבור אל **נתונים** > **מקורות נתונים**.

1. לצד מקור הנתונים שברצונך לעדכן, בחר את **עריכה**.

1. בצע את השינויים והטרנספורמציות בדו-השיח של **Power Query – עריכת שאילתות** לפי המתואר במקטע [צור מקור נתונים חדש](#create-a-new-data-source).

1. בחר **שמור** כדי להחיל את השינויים ולחזור לדף **מקורות נתונים**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
