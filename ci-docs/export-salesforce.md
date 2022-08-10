---
title: ייצוא נתונים ל-Salesforce Marketing Cloud ‏(Preview)
description: למד כיצד להגדיר את החיבור ולייצא ל- Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197039"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>ייצוא נתונים ל-Salesforce Marketing Cloud ‏(Preview)

השתמש בנתוני הלקוחות שלך ב- Salesforce Marketing Cloud על-ידי ייצוא שלהם באמצעות מיקום Secure File Transfer Protocol‏ (STFP).

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [מארח SFTP עבור Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) ואישורי מנהל מערכת תואמים.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>הגדרת חיבור ל- Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Salesforce Marketing Cloud**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק **שם משתמש**, **סיסמה**, **שם מארח** ו **תיקיית ייצוא** עבור חשבון SFTP שלך.

1. בחר **אימות** כדי לבדוק את החיבור.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע SFTP. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. בחר אם ברצונך לייצא את הנתונים שלך **דחוסים ב- Gzip** או **לא דחוסים** ואת **מפריד השדה** עבור הקבצים המיוצאים.

1. בחר את הישויות, לדוגמה פלחים, שברצונך לייצא.

   > [!NOTE]
   > כל ישות שנבחרה תחולק לחמישה קבצי פלט לכל היותר בעת הייצוא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>ייבוא נתוני Customer Insights ממיקום SFTP ל- Salesforce Marketing Cloud

1. צור [הרחבות נתונים ב- Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) כדי לייבא את קובץ הנתונים של Customer Insights ממיקום SFTP.

2. [ייבא את הנתונים ממיקום SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) לתוך הרחבת הנתונים ב- Salesforce Marketing Cloud.

3. הגדר את האוטומציה לייבוא הנתונים אל הרחבות הנתונים. למידע נוסף על [אוטומציות file drop ואוטומציות מתוזמנות](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   הגדר [אוטומציה של file drop](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) או [אוטומציה מתוזמנת](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

הנה דוגמה ל[אוטומציה באמצעות SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
