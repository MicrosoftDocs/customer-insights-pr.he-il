---
title: ייצא פלחים אל מנהל המודעות של Facebook ‏(Preview‏) (מכיל סרטון)
description: למד כיצד להגדיר את החיבור ולייצא אל Facebook Ads Manager.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01be1a075db0da05dc5536aea8a33093f9a2ea13
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195015"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>ייצא פלחים אל מנהל המודעות של Facebook ‏(Preview‏)

ייצא קטעים של פרופילי לקוחות מאוחדים אל Facebook Ads Manager ליצירת קמפיינים ב- Facebook ובאינסטגרם.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- [חשבון Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) שכולל [חשבון עסקי של Facebook](https://business.facebook.com/).
- הרשאות מנהל מערכת ב[חשבון Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- עד 10 מיליון פרופילי לקוחות לכל ייצוא אל Facebook Ads. פעולה זו עשויה להימשך עד 90 דקות.
- פלחים בלבד.
- סוג *רשימת לקוחות* של Facebook ב[קהלים מותאמים אישית](https://www.facebook.com/business/help/744354708981227?id=2469097953376494) בלבד.
  > [!NOTE]
  > במקרים מסוימים, ייתכן שתראה קהלים מותאמים אישית מסוגים שונים ברשימה הנפתחת. אם תבחר סוג שונה מ *רשימת לקוחות*, הייצוא ייכשל.

## <a name="set-up-connection-to-facebook-ads-manager"></a>הגדרת חיבור אל Facebook Ads Manager

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Facebook Ads Manager**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. אימות באמצעות Facebook Ads:

   1. בחר **המשך עם Facebook** כדי להיכנס לחשבון Facebook Ads שלך.

   1. אפשר את הרשאת **ניהול מודעות** לאחר אימות עם Facebook.

   1. בחר את **חשבון המודעות ב-Facebook** שברצונך לעבוד איתו.

   1. בחר **קהל מותאם אישית קיים** מהרשימה הנפתחת או צור **קהל מותאם אישית חדש**.

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע Facebook Ads Manager. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. בשדה **חבר נתונים**, בחר **דואר אלקטרוני**, **שם וכתובת**, או **טלפון** כדי לשלוח אל Facebook Ads Manager.

1. מפה את התכונות המתאימות מישות הלקוח המאוחד שלך עבור מזהה המפתח שנבחר.
   > [!TIP]
   > הסיכוי הטוב ביותר להתאמה הוא אם תבחר **דואר** כמזהה מפתח. הוספת מזהים נוספים עשויה לשפר את ההתאמה.

1. בחר **הוסף תכונה** כדי למפות תכונות נוספות לשליחה אל Facebook Ads Manager. תכונות מ- Facebook Ads Manager ממופות לשמות הידידותיים למשתמש הבאים: **FN** = **שם פרטי**, **LN** = **שם משפחה**, **FI** = **ראשי תיבות**, **PHONE** = **טלפון**, **GEN** = **מין**, **DOB** = **תאריך לידה**, **ST** = **מדינה בארה"ב**, **CT** = **עיר**, **ZIP** = **מיקוד**, **COUNTRY** = **מדינה / אזור**

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
