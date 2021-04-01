---
title: יעדי ייצוא
description: יצא נתונים ונהל יעדי ייצוא.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596086"
---
# <a name="export-destinations-preview-overview"></a>מבט כולל על יעדי ייצוא (Preview)

הדף **יעדי ייצוא** מציג את כל המיקומים שהגדרת לייצא נתונים אליהם. ניתן להוסיף יעדים חדשים לייצוא. בנוסף, הוא מציג אפשרויות ייצוא הזמינות כעת. קבל סקירה מהירה, תיאור וגלה מה אפשר לעשות עם כל אפשרות להרחבה. ייצא פרופילים, מדדים וקטעים מאוחדים ליישומים נתמכים שרלוונטיים לעסק שלך.

עבור אל **ניהול** > **יעדי ייצוא** כדי למצוא את אפשרויות ההרחבה הבאות:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience Platform](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Azure Blob Storage](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [תוכנית Bot עבור Microsoft Teams](export-teams-bot.md)
- [Customer Insights API](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (תוספת כרטיס לקוח)](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [מרכז המכירות של Dynamics 365 (תוספת כרטיס לקוח)](customer-card-add-in.md)
- [Facebook Ads Manager](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]