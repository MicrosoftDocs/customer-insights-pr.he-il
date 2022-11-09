---
title: ייצוא פלחים אל AdRoll‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 81adad4caf2d4c6f792bf920b29fc7c67eef42b0
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724679"
---
# <a name="export-segments-to-adroll-preview"></a>ייצוא פלחים אל AdRoll‏ (Preview)

יצא פלחים של פרופילי לקוח מאוחדים אל AdRoll והשתמש בהם עבור פרסום.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון AdRoll](https://www.adroll.com/) ואישורי מנהל מערכת מתאימים.
- [מזהה מפרסם של AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [פלחים מוגדרים](segments.md) ב- Customer Insights.
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- קישור פרטי בשילוב עם Bring your own storage ‏(BYOS) אינו נתמך.
- עד 250,000 פרופילי לקוחות לכל ייצוא אל AdRoll. פעולה זו עשויה להימשך עד 10 דקות. מספר פרופילי הלקוחות שתוכל לייצא אל AdRoll תלוי בחוזה שלך עם AdRoll.
- פלחים בלבד. פלח חייב להכיל לפחות 100 פרופילי לקוחות.

## <a name="set-up-connection-to-adroll"></a>הגדרת חיבור אל AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **AdRoll**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **בצע אימות באמצעות AdRoll** וספק את אישורי מנהל המערכת שלך עבור AdRoll.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע AdRoll. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את **מזהה מפרסם AdRoll** שלך.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
