---
title: ייצוא נתוני Customer Insights אל מנהל המודעות של Facebook (מכיל סרטון)
description: למד כיצד להגדיר את החיבור ולייצא אל Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f610ab1af83bfd512ec1861e7dc76ebb2eecfcbb
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647310"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>ייצוא רשימת פלחים אל Facebook Ads Manager‏ (Preview)

ייצא קטעים של פרופילי לקוחות מאוחדים אל Facebook Ads Manager ליצירת קמפיינים ב- Facebook ובאינסטגרם.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>דרישות מוקדמות לחיבור

- נדרש [**Facebook חשבון מודעות**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)הכולל [**Facebook חשבון עסקי של**](https://business.facebook.com/).
- עליך להיות מנהל מערכת ב- [**Facebook חשבון מודעות**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>מגבלות ידועות

- עד 10 מיליון פריפילי לקוחות בכל ייצוא - Facebook Ads Manager.
- הייצוא ל- Facebook Ads Manager מוגבל לפלחים.
- צור או עדכן קהלים מותאמים אישית ב- Facebook מהסוג *רשימת לקוחות* בלבד.
- ייצוא פלחים עם מספר כולל של 10 מיליון פרופילי לקוחות עשוי להימשך עד 90 דקות.

## <a name="set-up-connection-to-facebook-ads-manager"></a>הגדרת חיבור אל Facebook Ads Manager

לפני שמשתמשים יוכלו ליצור ייצוא, מנהל מערכת מוכרח להגדיר את החיבור לשירות ולאפשר למשתתפים להשתמש בחיבור.

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Facebook Ads Manager** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. אימות באמצעות Facebook Ads: 

   1. בחר **המשך עם Facebook** כדי להיכנס לחשבון Facebook Ads שלך.

   1. אפשר את הרשאת **ניהול מודעות** לאחר אימות עם Facebook.

   1. בחר את **חשבון המודעות ב-Facebook** שברצונך לעבוד איתו.

   1. בחר **קהל מותאם אישית קיים** מהרשימה הנפתחת או צור **קהל מותאם אישית חדש**. למידע נוסף ראה [**קהלים ב- Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > באפשרותך ליצור או לעדכן קהלים מותאמים אישית ב- Facebook מהסוג *רשימת לקוחות* עם ייצוא זה. במקרים מסוימים יופיעו קהלים מותאמים אישית מסוגים שונים ברשימה הנפתחת. בחירת סוג שונה מ *רשימת לקוחות* תגרום לכשל בייצוא. 

1. סקור את **פרטיות ותאימות נתונים** ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**. 

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע **Facebook Ads Manager**. אם אינך רואה את שם הפלח הזה, אין קשרים זמינים עבורך מסוג זה.

1. בתוך **בחר שדה מזהה מפתח**, בחר **דואר**, **שם וכתובת**, או **טלפון** כדי לשלוח אל Facebook Ads Manager. 

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. מפה את התכונות המתאימות מישות הלקוח המאוחד שלך עבור מזהה המפתח שנבחר.
   > [!TIP]
   > הסיכוי הטוב ביותר להתאמה הוא אם תבחר **דואר** כמזהה מפתח. הוספת מזהים נוספים עשויה לשפר את ההתאמה.

1. בחר **הוסף תכונה** כדי למפות תכונות נוספות לשליחה אל Facebook Ads Manager. תכונות מ- Facebook Ads Manager ממופות לשמות הידידותיים למשתמש הבאים: **FN** = **שם פרטי**, **LN** = **שם משפחה**, **FI** = **ראשי תיבות**, **PHONE** = **טלפון**, **GEN** = **מין**, **DOB** = **תאריך לידה**, **ST** = **מדינה בארה"ב**, **CT** = **עיר**, **ZIP** = **מיקוד**, **COUNTRY** = **מדינה / אזור**

1. בחר את הפלחים שברצונך לייצא.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). 

באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Facebook Ads Manager, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Facebook Adsעומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE [footer-include](includes/footer-banner.md)]
