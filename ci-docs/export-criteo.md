---
title: ייצוא פלחים ל- Criteo (תצוגה מקדימה)
description: למד כיצד להגדיר את תצורת החיבור ולייצא ל- Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760027"
---
# <a name="export-segments-to-criteo-preview"></a>ייצוא פלחים ל- Criteo (תצוגה מקדימה)

יצא פלחים של פריטי unified customer profile כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Criteo.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Criteo Dynamics Retargeting](https://www.criteo.com/login/) ואישורי מנהל מערכת תואמים.
- [פלחים מוגדרים](segments.md).
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד מיליון פרופילי לקוחות לכל ייצוא אל Campaign Monitor. השלמת פעולה זו עשויה להימשך עד 30 דקות. מספר פרופילי הלקוחות שתוכל לייצא אל Criteo תלוי בחוזה שלך עם Criteo.
- פלחים בלבד.

## <a name="set-up-connection-to-criteo"></a>הגדרת חיבור ל- Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Criteo**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **אימות באמצעות Criteo** וספק את שם המשתמש והאישורים שלך כמנהל המערכת עבור Criteo.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור עבור ייצוא**, בחר חיבור מתוך מקטע Criteo. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
