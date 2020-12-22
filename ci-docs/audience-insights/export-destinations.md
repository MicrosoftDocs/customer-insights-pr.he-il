---
title: יעדי ייצוא
description: יצא נתונים ונהל יעדי ייצוא.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643864"
---
# <a name="export-destinations-preview"></a>יעדי ייצוא (גירסת Preview)

הדף **יעדי ייצוא** מציג את כל המיקומים שהגדרת לייצא נתונים אליהם. ניתן להוסיף יעדים חדשים לייצוא. בנוסף, הוא מציג אפשרויות ייצוא הזמינות כעת. קבל סקירה מהירה, תיאור וגלה מה אפשר לעשות עם כל אפשרות להרחבה. ייצא פרופילים, מדדים וקטעים מאוחדים ליישומים נתמכים שרלוונטיים לעסק שלך.

עבור אל **ניהול** > **יעדי ייצוא** כדי למצוא את אפשרויות ההרחבה הבאות:

- [תוסף כרטיסי לקוחות ב- Dynamics 365 Customer](customer-card-add-in.md)
- [מחבר מנהל המודעות של Facebook](export-facebook.md)
- [מחבר Power Automate](export-power-automate.md)
- [מחבר Power Apps](export-power-apps.md)
- [מחבר Power BI](export-power-bi.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [‏‎מחבר ‎LiveRamp‏‏&reg;‏‏](export-liveramp.md)
- [תוכנית Bot עבור Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [Customer Insights API](apis.md)

## <a name="add-a-new-export-destination"></a>הוספת יעד ייצוא חדש

כדי להוסיף יעדי ייצוא, יש לך [הרשאות מנהל מערכת](permissions.md). אם תייצא אל שירותי Microsoft, נניח ששני השירותים הם באותו ארגון.

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. עבור אל הכרטיסיה **יעדי הייצוא שלי**.

1. בחר **הוסף יעד** כדי ליצור יעד ייצוא חדש.

1. בחלונית **הוסף יעד**, בחר את **סוג** של יעד הייצוא ברשימה הנפתחת.

1. ספק את הפרטים הנדרשים ובחר **הבא** כדי ליצור את יעד הייצוא.

באפשרותך גם לבחור **הגדר** באריח בכרטיסיה **גלה**.

## <a name="view-export-destinations"></a>הצג יעדי ייצוא

לאחר יצירת יעדי ייצוא, תמצא אותם בטבלה שבכרטיסיה **יעדי הייצוא שלי**. טבלה זו כוללת שלוש עמודות:

- **שם תצוגה**: השם שהזנת בעת יצירת היעד.
- **סוג**: סוג יעד הייצוא שהגדרת בעת יצירת היעד.
- **נוצר**: התאריך שבו יצרת את היעד.

## <a name="edit-an-export-destination"></a>עריכת יעד ייצוא

1. בחר את שלוש הנקודות האנכיות עבור יעד הייצוא שברצונך לערוך.

   > [!div class="mx-imgBorder"]
   > ![שלוש נקודות אנכיות](media/export-destinations-page-ellipsis.png "שלוש נקודות אנכיות")

1. בחר **ערוך** מהתפריט הנפתח.

1. שנה את הערכים הדורשים עדכון ובחר **שמור**.

## <a name="export-data-on-demand"></a>ייצוא נתונים לפי דרישה

לאחר קביעת התצורה של מחבר ליעד ייצוא, הייצוא יפעל בכל [רענון מתוזמן](system.md#schedule-tab).

כדי לייצא נתונים מבלי לחכות לרענון מתוזמן, עבור אל הכרטיסיה **יעדי הייצוא שלי** ב **ניהול** > **יעדי ייצוא**.

> [!div class="mx-imgBorder"]
> ![שלוש נקודות אנכיות](media/export-destinations-page-ellipsis.png "שלוש נקודות אנכיות")

- בחר **ייצוא** מעל הרשימה כדי להפעיל את הייצוא בכל יעדי הייצוא בו-זמנית.
- בחר את שלוש הנקודות (...) אחרי פריט רשימה ולאחר מכן בחר את האפשרות **ייצוא** כדי להפעיל את הייצוא עבור יעד ייצוא יחיד.

## <a name="remove-an-export-destination"></a>הסר יעד ייצוא

להסרת יעד ייצוא, התחל מהדף **יעדי ייצוא** הראשי.

1. בחר את שלוש הנקודות האנכיות עבור יעד הייצוא שברצונך להסיר.

   > [!div class="mx-imgBorder"]
   > ![שלוש נקודות אנכיות](media/export-destinations-page-ellipsis.png "שלוש נקודות אנכיות")

2. בחר **הסר** מהתפריט הנפתח.

3. אשר את ההסרה על-ידי בחירת **הסר** במסך האישור.
