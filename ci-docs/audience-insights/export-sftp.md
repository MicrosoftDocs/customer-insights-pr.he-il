---
title: ייצוא נתוני Customer Insights אל מארחי SPTF
description: למד כיצד להגדיר את החיבור אל מארח SFTP.
ms.date: 01/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 9ec14fafa8f99e34b95349371298082e166535d0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598386"
---
# <a name="connector-for-sftp-preview"></a>מחבר עבור SFTP‏ (Preview)

השתמש בנתוני הלקוחות שלך ביישומי צד שלישי על-ידי ייצוא שלהם אל מארח Secure File Transfer Protocol‏ (SFTP).

## <a name="prerequisites"></a>דרישות מוקדמות

- זמינות של מארח SFTP ואישורים מתאימים.

## <a name="connect-to-sftp"></a>התחבר ל- SFTP

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. ב- **SFTP**, בחר **הגדר**.

1. תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. ספק **שם משתמש**, **סיסמה**, **שם מארח** ו **תיקיית ייצוא** עבור חשבון SFTP שלך.

1. בחר **אימות** כדי לבדוק את החיבור.

1. לאחר האימות המוצלח, בחר אם ברצונך לייצא את הנתונים שלך כשהם **דחוסים** או **לא דחוסים** ובחר את **מפריד השדה** עבור הקבצים המיוצאים.

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **הבא** כדי להתחיל בהגדרת הייצוא.

## <a name="configure-the-export"></a>קביעת תצורה של הייצוא

1. בחר את הישויות, לדוגמה פלחים, שברצונך לייצא.

   > [!NOTE]
   > כל ישות שנבחרה תכלול עד חמישה קבצי פלט בעת הייצוא. 

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).

## <a name="known-limitations"></a>מגבלות ידועות

- זמן הריצה של ייצוא תלוי בביצועי המערכת שלך. מומלץ שתי ליבות CPU וזיכרון של 1‎ GB כתצורה מינימלית עבור השרת שלך. 
- ייצוא ישויות עם עד 100 מיליון פרופילי לקוחות יכול להימשך 90 דקות בעת שימוש בתצורה המינימלית המומלצת של שתי ליבות CPU וזיכרון של 1‎ GB. 

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים דרך SPTF, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא שיעד הייצוא עומד בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]