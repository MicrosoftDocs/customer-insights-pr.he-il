---
title: ייצוא נתוני Customer Insights אל Facebook Ads Manager
description: למד כיצד להגדיר את החיבור אל Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3e2b52fe743563e4bf61d870cbf1718e6c752a67
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596683"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>מחבר ל- Facebook Ads Manager‏ (preview)

ייצא קטעים של פרופילי לקוחות מאוחדים אל Facebook Ads Manager ליצירת קמפיינים ב- Facebook ובאינסטגרם.

## <a name="prerequisites"></a>דרישות מוקדמות

- אתה צריך שיהיה לך [חשבון מודעות של **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) שכולל [חשבון עסקי של **Facebook**](https://business.facebook.com/).
- אתה צריך להיות מנהל מערכת ב [חשבון מודעות של **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>התחבר אל Facebook Ads Manager

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. ב- **Facebook Ads Manager**, בחר **הגדר**.

1. תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. בחר **המשך עם Facebook** כדי להיכנס לחשבון המודעות שלך ב- Facebook.

1. אפשר את הרשאת **ניהול מודעות** לאחר אימות עם Facebook.

1. בחר את **חשבון המודעות ב-Facebook** שברצונך לעבוד איתו.

1. בחר **קהל מותאם אישית קיים** מהרשימה הנפתחת או צור **קהל מותאם אישית חדש**. למידע נוסף ראה [**קהלים ב- Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **הבא** להגדרת התצורה של הייצוא.

## <a name="configure-the-connector"></a>קביעת תצורת המחבר

1. בתוך **בחר שדה מזהה מפתח**, בחר **דואר**, **שם וכתובת**, או **טלפון** כדי לשלוח אל Facebook Ads Manager.

1. מפה את התכונות המתאימות מישות הלקוח המאוחד שלך עבור מזהה המפתח שנבחר.
   > [TIP] הסיכוי הטוב ביותר להתאמה הוא אם תבחר **דואר** כמזהה מפתח. הוספת מזהים נוספים עשויה לשפר את ההתאמה.

1. בחר **הוסף תכונה** כדי למפות תכונות נוספות שיש לשלוח אל Facebook Ads Manager. תכונות מ- Facebook Ads Manager ממופות לשמות המשתמש הבאים: **FN** = **שם פרטי**, **LN** = **שם משפחה**, **FI** = **ראשי תיבות**, **PHONE** = **טלפון**, **GEN** = **מין**, **DOB** = **תאריך לידה**, **ST** = **מדינה בארה"ב**, **CT** = **עיר**, **ZIP** = **מיקוד**, **COUNTRY** = **מדינה / אזור**

1. בחר את הפלחים שברצונך לייצא.

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).

## <a name="known-limitations"></a>מגבלות ידועות

- עד 10 מיליון פרופילי לקוחות לכל ייצוא אל Facebook Ads Manager 
- הייצוא ל- Facebook Ads Manager מוגבל לפלחים
- ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 90 דקות

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Facebook Ads Manager, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Facebook Adsעומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]