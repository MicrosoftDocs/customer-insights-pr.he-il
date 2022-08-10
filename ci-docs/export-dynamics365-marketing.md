---
title: ייצוא פלחים ל- Dynamics 365 Marketing‏ (Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Dynamics 365 Marketing.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 123b565421a7d096e7341a8f600f91e59aefe8d0
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196625"
---
# <a name="export-segments-to-dynamics-365-marketing-preview"></a>ייצוא פלחים ל- Dynamics 365 Marketing‏ (Preview)

השתמש ב[פלחים](segments.md) כדי ליצור קמפיינים וליצור קשר עם קבוצות ספציפיות של לקוחות באמצעות [Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

אם אתה משתמש ביכולות החדשות של Dynamics 365 Marketing להפקת מסע הלקוח בזמן אמת ב-Dataverse org, אין צורך ליצור ייצוא רגיל ל-Dynamics 365 Marketing. אנשי קשר ופלחים מ- Customer Insights זמינים ישירות ב- Dynamics 365 Marketing לאחר חיבור Marketing ו- Customer Insights. לפני שאתה מוחק פריטי יצוא קיימים, עיין בתיעוד על [כיצד לחבר Customer Insights ותאיום מסע לקוח ב- Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite"></a>דרישה מוקדמת

רשומות אנשי קשר מוכרחות להיות קיימות ב- Dynamics 365 Marketing לפני שתוכל לייצא פלח מ- Customer Insights אל Marketing. המשך לקרוא על אופן הקליטה של אנשי קשר ב- [Dynamics 365 Marketing באמצעות Microsoft Dataverse](connect-dataverse-managed-lake.md).

> [!NOTE]
> ייצוא פלחים מ-Customer Insights ל- Marketing לא ייצור רשומות אנשי קשר חדשות במופעי Marketing. יש להטמיע את רשומות אנשי הקשר מ- Marketing ב- Customer Insights ולהשתמש בהם כמקור נתונים. יש גם לכלול אותן בישות 'לקוח' המאוחדת כדי למפות מזהי לקוחות למזהי אנשי קשר לפני ייצוא הפלחים.

## <a name="set-up-connection-to-marketing"></a>הגדרת חיבור אל Marketing

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Dynamics 365 Marketing**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את כתובת ה- URL של Marketing של הארגון שלך בשדה **כתובת שרת**.

1. במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Marketing.

1. מיפוי שדה מזהה איש קשר בישות הלקוח למזהה איש קשר של Dynamics 365.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Dynamics 365 Marketing. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. בחר את שדה מזהה איש הקשר בישות הלקוח שתואמת למזהה איש קשר של Dynamics 365.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
