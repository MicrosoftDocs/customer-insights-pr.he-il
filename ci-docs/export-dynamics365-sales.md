---
title: ייצוא פלחים ל- Dynamics 365 Sales ‏(Preview)
description: למד כיצד להגדיר את החיבור ולייצא אל Dynamics 365 Sales.
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
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195982"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>ייצוא פלחים ל- Dynamics 365 Sales ‏(Preview)

השתמש בנתוני הלקוחות שלך כדי ליצור רשימות שיווק, להמשיך לטפל בזרימות עבודה ולשלוח מבצעים באמצעות Dynamics 365 Sales.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

רשומות אנשי קשר מוכרחות להיות קיימות ב- Dynamics 365 Sales לפני שתוכל לייצא פלח מ- Customer Insights אל Sales. קרא עוד על אופן הטמעת אנשי קשר מ- [Dynamics 365 Sales באמצעות Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > ייצוא פלחים מ- Customer Insights ל- Sales לא ייצור רשומות אנשי קשר חדשות במופעי Sales. יש להטמיע את רשומות אנשי הקשר מ- Sales ב- Customer Insights ולהשתמש בהם כמקור נתונים. יש גם לכלול אותן בישות 'לקוח' המאוחדת כדי למפות מזהי לקוחות למזהי אנשי קשר לפני ייצוא הפלחים.

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

מספר פעולות הייצוא אל Dynamics 365 Sales מוגבל ל- 100,000 לכל פלח והשלמת הפעולה יכולה להימשך עד 3 שעות.

## <a name="set-up-connection-to-sales"></a>הגדרת חיבור ל- Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Dynamics 365 Sales**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן את כתובת ה- URL של Sales של הארגון שלך בשדה **כתובת שרת**.

1. במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Sales.

1. מפה שדה של מזהה לקוח למזהה איש הקשר של Dynamics 365.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Dynamics 365 Sales. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. בחר את שדה מזהה איש הקשר בישות הלקוח שתואמת למזהה איש קשר של Dynamics 365.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **שמור**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
