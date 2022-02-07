---
title: שימוש במקורות נתונים לקליטת נתונים
description: למד כיצד לייבא נתונים ממקורות שונים.
ms.date: 12/06/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
---

# <a name="data-sources-overview"></a>מבט כולל על מקורות נתונים



יכולת תובנות הקהל ב- Dynamics 365 Customer Insights מתחברת לנתונים מערכת מקורות רחבה. לעיתים קרובות מתייחסים לחיבור למקור נתונים כאל תהליך של *עיבוד נתונים*. לאחר עיבוד הנתונים, ניתן [לאחד](data-unification.md) ולנקוט פעולה.

## <a name="add-a-data-source"></a>הוספה של מקור נתונים

עיין במאמרים המפורטים בנושא כיצד להוסיף מקור נתונים, בהתאם לאפשרות שתבחר.

תוכל להוסיף את מקורות הנתונים הבאים:

- [Power Query מחברים](connect-power-query.md)
- [Common Data Model](connect-common-data-model.md)
- [Microsoft Dataverse אגם](connect-dataverse-managed-lake.md)

> [!NOTE]
> אם אתה משתמש בגרסת הניסיון, מקטע שיטות הייבוא כולל אפשרות של **ספריית נתונים של Customer Insights**. בחר באפשרות זו כדי לבחור ערכת נתונים לדוגמה הזמינה עבור תעשיות שונות. לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights ניסיון](../trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>הוספת נתונים ממקורות נתונים מקומיים

קליטת נתונים ממקורות נתונים מקומיים בתובנות לגבי קהלים נתמכת בהתבסס על זרימות הנתונים של Microsoft Power Platform. תוכל להפוך תזרימי נתונים לזמינים ב- Customer Insights על ידי [מתן Microsoft Dataverse כתובת URL של הסביבה](create-environment.md) בעת הגדרת הסביבה.

מקורות נתונים שנוצרים לאחר שיוך Dataverse סביבה עם Customer Insights משתמשים [Power Platform בתזרימי נתונים](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) כברירת מחדל. זרימות נתונים תומכות בקישוריות מקומית באמצעות שער הנתונים. תוכל להסיר וליצור מחדש מקורות נתונים שהתקיימו לפני שיוך Dataverse סביבה [באמצעות שערי נתונים מקומיים](/data-integration/gateway/service-gateway-app).

שערי נתונים מסביבת Power BI או Power Apps קיימת יהיו גלויים ותוכל להשתמש בהם מחדש ב- Customer Insights. דף מקורות הנתונים מציג קישורים למעבר אל סביבת Microsoft Power Platform שבה תוכל להציג ולהגדיר את שערי הנתונים המקומיים.

## <a name="review-ingested-data"></a>סקירה של נתונים מעובדים

תראה את השם של כל מקור נתונים שעובד, את המצב שלו ואת הפעם האחרונה שבו הנתונים מאותו מקור רועננו. ניתן למיין את רשימת מקורות הנתונים לפי כל עמודה.

> [!div class="mx-imgBorder"]
> ![מקור נתונים נוסף.](media/configure-data-datasource-added.png "מקור נתונים נוסף")

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

טעינת נתונים עשויה להימשך זמן מה. לאחר רענון מוצלח, ניתן לסקור את הנתונים שעובדו בדף **ישויות**. לקבלת מידע נוסף, ראה [ישויות](entities.md).

## <a name="refresh-a-data-source"></a>רענון מקור נתונים

ניתן לרענן את מקורות הנתונים בלוח זמנים אוטומטי או לרענן אותם באופן ידני לפי דרישה. 

עבור אל **ניהול** > **מערכת** > [**לוח זמנים**](system.md#schedule-tab) כדי לקבוע תצורה של רענונים מתוזמנים של כל מקורות הנתונים שקלטת.

כדי לרענן מקור נתונים לפי דרישה, בצע את השלבים הבאים:

1. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.

2. בחר את שלוש הנקודות האנכיות לצד מקור נתונים שברצונך לרענן ובחר **רענון** מהרשימה הנפתחת.

3. מקור הנתונים מופעל כעת עבור רענון ידני. רענון מקור נתונים יעדכן הן את סכימת הישות והן את הנתונים עבור כל הישויות שצוינו במקור הנתונים.

4. בחר **הפסק רענון** אם ברצונך לבטל רענון קיים ומקור הנתונים יחזור למצב הרענון האחרון שלו.

## <a name="delete-a-data-source"></a>מחק מקור נתונים

1. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.

2. בחר את שלוש הנקודות האנכיות לצד מקור נתונים שברצונך להסיר ובחר **מחיקה** מהתפריט הנפתח.

3. אשר את המחיקה.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
