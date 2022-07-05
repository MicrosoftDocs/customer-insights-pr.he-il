---
title: ייצוא נתונים ל-Salesforce Marketing Cloud ‏(Preview)
description: למד כיצד להגדיר את החיבור ולייצא ל- Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081460"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>ייצוא נתונים ל-Salesforce Marketing Cloud ‏(Preview)

השתמש בנתוני הלקוחות שלך ב- Salesforce Marketing Cloud על-ידי ייצוא שלהם באמצעות מיקום Secure File Transfer Protocol‏ (STFP).

## <a name="prerequisites-for-connection"></a>דרישות מוקדמות לחיבור

- זמינות של מארח SFTP ואישורי מנהל מערכת תואמים. [כיצד להגדיר מיקומי SFTP עבור Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>הגדרת החיבור ל- Salesforce Marketing Cloud

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ולאחר מכן בחר **Salesforce Marketing Cloud** כדי להגדיר את החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק **שם משתמש**, **סיסמה**, **שם מארח** ו **תיקיית ייצוא** עבור חשבון SFTP שלך.

1. בחר **אימות** כדי לבדוק את החיבור.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע SFTP. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. בחר אם ברצונך לייצא את הנתונים שלך **דחוסים ב- Gzip** או **לא דחוסים** ואת **מפריד השדה** עבור הקבצים המיוצאים.

1. בחר את הישויות, לדוגמה פלחים, שברצונך לייצא.

   > [!NOTE]
   > כל ישות שנבחרה תחולק לעד חמישה קבצי פלט בעת הייצוא. 

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>ייבוא נתוני Customer Insights ממיקום SFTP ל- Salesforce Marketing Cloud

1. צור [הרחבות נתונים ב- Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) כדי לייבא את קובץ הנתונים של Customer Insights ממיקום SFTP.

2. [ייבא את הנתונים ממיקום SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) לתוך הרחבת הנתונים ב- Salesforce Marketing Cloud. 

3. הגדר את האוטומציה לייבוא הנתונים אל הרחבות הנתונים. למידע נוסף על [אוטומציות file drop ואוטומציות מתוזמנות](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   הגדר [אוטומציה של file drop](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) או [אוטומציה מתוזמנת](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

הנה דוגמה ל[אוטומציה באמצעות SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים דרך SPTF, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא שיעד הייצוא עומד בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.

[!INCLUDE [footer-include](includes/footer-banner.md)]
