---
title: ייצוא פלחים אל LinkedIn Ads ‏(Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304704"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>ייצוא פלחים אל LinkedIn Ads ‏(Preview)

ייצא פלחים של פרופילי לקוחות מאוחדים אל LinkedIn Ads כדי ליצור קהלים תואמים. השתמש בקהלים תואמים ל- Company Targeting ול- Contact Targeting.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) ואישורי מנהל מערכת תואמים.
- [מזהה תיק לקוח של LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- הפלחים המיוצאים צריכים לפחות שדה ספציפי אחד בהתאם לבחירתך ב[פילוח לפי אנשי קשר](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) או [פילוח לפי חברה](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) ב- LinkedIn. השדות האפשריים מפורטים בשלב **התאמת נתונים**  בעת [הגדרת הייצוא](#configure-an-export).

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד 100,000 פרופילי לקוחות לכל ייצוא אל LinkedIn Ads. השלמת הפעולה עשויה להימשך עד 10 דקות.
- פלחים בלבד. פלח חייב להכיל לפחות 300 פרופילים ייחודיים.

## <a name="set-up-connection-to-linkedin-ads"></a>הגדרת חיבור אל LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **LinkedIn Ads**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק את מזהה החשבון של LinkedIn Campaign Manager.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **בצע אימות באמצעות LinkedIn** וספק את אישורי מנהל המערכת שלך עבור LinkedIn Campaign Manager.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע LinkedIn Ads. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. בחר אם ברצונך לייצא נתונים לשימוש ב- [Contact Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) או ב- [Company Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) ב- LinkedIn.

1. למיקוד אנשי קשר, במקטע **התאמת נתונים**, בחר שדה אחד לפחות שמייצג כתובת דואר אלקטרוני של לקוח, Apple Ad ID,‏ Google Ad ID, מזהה משתמש של Google או שם פרטי ושם משפחה. אם תבחר מיקוד לחברה, בחר לפחות שדה אחד שמייצג שם חברה, תחום דואר אלקטרוני, כתובת URL של דף LinkedIn, סמל מניה או אתר אינטרנט.

1. לחלופין, הוסף שדות נוספים להגדרת הייצוא. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא. הקהלים התואמים ב- LinkedIn Campaign Manager ייווצרו באופן אוטומטי עם שם הפלחים שבחרת לייצא. לכל מקטע ייווצר קהל תואם נפרד.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
