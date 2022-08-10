---
title: ייצוא פלחים אל RollWorks‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e13aeca4ee5309f85e7de2986cd1a2ba5d2992fb
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195613"
---
# <a name="export-segments-to-rollworks-preview"></a>ייצוא פלחים אל RollWorks‏ (Preview)

יצא פלחים של פרופילי לקוחות מאוחדים אל RollWorks והשתמש בהם עבור פרסום.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון RollWorks](https://www.rollworks.com/) ואישורי מנהל מערכת מתאימים.
- [מזהה מפרסם של RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד 250,000 פרופילי לקוחות לכל ייצוא אל RollWorks. השלמת הפעולה עשויה להימשך עד 10 דקות. מספר פרופילי הלקוחות שתוכל לייצא אל RollWorks תלוי בחוזה שלך עם RollWorks.
- פלחים בלבד.

## <a name="set-up-connection-to-rollworks"></a>הגדרת חיבור אל RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **RollWorks‎**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה.  כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **בצע אימות מול RollWorks** וספק את אישורי מנהל המערכת שלך עבור RollWorks.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע RollWorks. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את **מזהה המפרסם של RollWorks** שלך.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
