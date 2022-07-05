---
title: ייצוא פלחים ל- Dynamics 365 Marketing‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: fed4ae1b017cca2b6060c4dda155859cd77e0daf
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054617"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>ייצוא פלחים ל- Dynamics 365 Marketing‏ (Preview)

השתמש ב[פלחים](segments.md) כדי ליצור קמפיינים וליצור קשר עם קבוצות ספציפיות של לקוחות באמצעות Dynamics 365 Marketing. למידע נוסף ראה [השתמש בקטעים מ-Dynamics 365 Customer Insights עם Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

אם אתה משתמש ביכולות החדשות של Dynamics 365 Marketing להפקת מסע הלקוח בזמן אמת ב-Dataverse org, אין צורך ליצור ייצוא רגיל ל-Dynamics 365 Marketing. אנשי קשר ופלחים מ- Customer Insights זמינים ישירות ב- Dynamics 365 Marketing לאחר חיבור Marketing ו- Customer Insights. לפני שאתה מוחק פריטי יצוא קיימים, עיין בתיעוד על [כיצד לחבר Customer Insights ותאיום מסע לקוח ב- Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>דרישה מוקדמת לחיבור

- רשומות אנשי קשר מוכרחות להיות קיימות ב- Dynamics 365 Marketing לפני שתוכל לייצא פלח מ- Customer Insights אל Marketing. המשך לקרוא על אופן הקליטה של אנשי קשר ב- [Dynamics 365 Marketing באמצעות Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > ייצוא פלחים מ-Customer Insights ל- Marketing לא ייצור רשומות אנשי קשר חדשות במופעי Marketing. יש להטמיע את רשומות אנשי הקשר מ- Marketing ב- Customer Insights ולהשתמש בהם כמקור נתונים. יש גם לכלול אותן בישות 'לקוח' המאוחדת כדי למפות מזהי לקוחות למזהי אנשי קשר לפני ייצוא הפלחים.

## <a name="set-up-connection-to-marketing"></a>הגדרת חיבור אל Marketing

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Dynamics 365 Marketing** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את כתובת ה- URL של Marketing של הארגון שלך בשדה **כתובת שרת**.

1. במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Marketing.

1. מיפוי שדה מזהה איש קשר בישות הלקוח למזהה איש קשר של Dynamics 365.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
