---
title: ייצוא נתוני Customer Insights אל Dynamics 365 Marketing
description: למד כיצד להגדיר את החיבור ולייצא אל Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759638"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>שימוש בפלחים ב- Dynamics 365 Marketing‏ (Preview)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

השתמש ב[פלחים](segments.md) כדי ליצור קמפיינים וליצור קשר עם קבוצות ספציפיות של לקוחות באמצעות Dynamics 365 Marketing. למידע נוסף ראה [השתמש בקטעים מ- Dynamics 365 Customer Insights עם Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>דרישה מוקדמת לחיבור

- רשומות אנשי קשר מוכרחות להיות קיימות ב- Dynamics 365 Marketing לפני שתוכל לייצא פלח מ- Customer Insights אל Marketing. המשך לקרוא על אופן הקליטה של אנשי קשר ב- [Dynamics 365 Marketing באמצעות Common Data Services](connect-power-query.md).

  > [!NOTE]
  > ייצוא פלחים מ- audience insights אל Marketing לא ייצור רשומות אנשי קשר חדשות במופעי Marketing. יש לקלוט את רשומות אנשי הקשר מ- Marketing ב- audience insights ולהשתמש בהן כמקור נתונים. יש גם לכלול אותן בישות 'לקוח' המאוחדת כדי למפות מזהי לקוחות למזהי אנשי קשר לפני ייצוא הפלחים.

## <a name="set-up-connection-to-marketing"></a>הגדרת חיבור אל Marketing

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Dynamics 365 Marketing** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את כתובת ה- URL של Marketing של הארגון שלך בשדה **כתובת שרת**.

1. במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Marketing.

1. מפה שדה של מזהה לקוח למזהה איש הקשר של Dynamics 365.

1. בחר **שמור** כדי להשלים את החיבור. 

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Dynamics 365 Marketing. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. בחר קטע אחד או יותר.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
