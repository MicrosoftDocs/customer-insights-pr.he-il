---
title: ייצוא פלחים ל- Klaviyo ‏(Preview)
description: למד כיצד להגדיר את החיבור ולייצא ל-Klaviyo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e45ca5827afa29d97a746bd1a474c2346cc32d2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196763"
---
# <a name="export-segments-to-klaviyo-preview"></a>ייצוא פלחים ל- Klaviyo ‏(Preview)

ייצא פלחים של פרופילי לקוחות מאוחדים ל-Klaviyo והשתמש בהם לצורך פעילויות שיווק.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Klaviyo](https://www.klaviyo.com/) ואישורי מנהל מערכת תואמים.
- [מפתח API של Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys).
- [מזהה רשימה של Klaviyo](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד מיליון פרופילי לקוחות לכל ייצוא אל Klaviyo. השלמת פעולה זו עשויה להימשך עד 20 דקות. מספר פרופילי הלקוחות שתוכל לייצא אל Klaviyo תלוי בחוזה שלך עם Klaviyo.
- פלחים בלבד.

## <a name="set-up-connection-to-klaviyo"></a>הגדרת חיבור ל-Klaviyo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Klaviyo**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק את מפתח API של Klaviyo שלך כדי להמשיך בכניסה.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **אימות באמצעות Klaviyo** וספק את אישורי מנהל המערכת עבור Klaviyo.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מהמקטע Klaviyo. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את **מזהה רשימת Klaviyo** שלך.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
