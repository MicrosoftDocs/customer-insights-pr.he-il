---
title: ייצוא פלחים ל- Sendinblue‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא ל- Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724895"
---
# <a name="export-segments-to-sendinblue-preview"></a>ייצוא פלחים ל- Sendinblue‏ (Preview)

ייצא פלחים של פרופילי לקוחות מאוחדים כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Sendinblue.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Sendinblue](https://www.sendinblue.com/) ואישורי מנהל מערכת תואמים.
- [מפתח API של Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- רשימות קיימות ב- Sendinblue והמזהים התואמים.
- [פלחים מוגדרים](segments.md).
- פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- קישור פרטי בשילוב עם Bring your own storage ‏(BYOS) אינו נתמך.
- עד מיליון פרופילי לקוחות לכל ייצוא אל Sendinblue. השלמת פעולה זו עשויה להימשך עד 90 דקות. מספר פרופילי הלקוחות שתוכל לייצא אל Sendinblue תלוי בחוזה שלך עם Sendinblue.
- פלחים בלבד.

## <a name="set-up-connection-to-sendinblue"></a>הגדרת חיבור ל- Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Sendinblue‎**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת אפשריים. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את **מפתח ה- API של SendinBlue**.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **התחבר** כדי לאתחל את החיבור.

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מהמקטע Sendinblue. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. הזן את **מזהה רשימת Sendinblue** שלך.

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר בשדה שמייצג כתובת דואר אלקטרוני של לקוח.

1. לחלופין, יצא **שם פרטי**, **שם משפחה** ו **טלפון** ליצירת הודעות דואר אלקטרוני מותאמות אישית יותר. בחר **הוסף תכונה** כדי למפות שדות אלה.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
