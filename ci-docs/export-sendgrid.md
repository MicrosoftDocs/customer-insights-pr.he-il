---
title: ייצוא פלחים ל- SendGrid‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196993"
---
# <a name="export-segments-to-sendgrid-preview"></a>ייצוא פלחים ל- SendGrid‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים לרשימות אנשי הקשר של SendGrid והשתמש בהם עבור קמפיינים ושיווק בדוא"ל ב- SendGrid.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון SendGrid](https://sendgrid.com/) ואישורי מנהל מערכת תואמים.
- [רשימות אנשי קשר קיימות ב- SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) והמזהים התואמים.
- [מפתח API של SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד 100,000 פרופילי לקוחות בסך הכול אל SendGrid. השלמת הפעולה עשויה להימשך עד כמה שעות. מספר פרופילי הלקוחות שתוכל לייצא אל SendGrid תלוי בחוזה שלך עם SendGrid.
- פלחים בלבד.

## <a name="set-up-connection-to-sendgrid"></a>הגדרת חיבור אל SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **SendGrid‎**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **מפתח ה- API של SendGrid** שלך.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע SendGrid. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את **מזהה רשימת SendGrid**.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. לחלופין, בחר שדות כגון **שם פרטי**, **שם משפחה**, **מדינה/אזור**, **מחוז**, **עיר** ו **מיקוד**.

1. בחר את הפלחים שברצונך לייצא שמצייתים למגבלות הידועות.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
