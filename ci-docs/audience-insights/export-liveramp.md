---
title: ‏‎מחבר ‎LiveRamp‏‏‏‏
description: למד כיצד לייצא נתונים אל LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667185"
---
# <a name="liverampreg-connector-preview"></a>מחבר LiveRamp&reg; (תצוגה מקדימה)

הפעל את הנתונים שלך ב- LiveRamp כדי להתחבר ליותר מ- 500 פלטפורמות במערכות אקולוגיות דיגיטליות, חברתיות ומערכות אקולוגיות של טלוויזיה. עבוד עם הנתונים שלך ב- LiveRamp כדי להתמקד, להשמיט ולהתאים אישית קמפיינים פרסומיים.

## <a name="prerequisites"></a>דרישות מוקדמות

- כדי להשתמש במחבר זה אתה זקוק למנוי LiveRamp.
- כדי לקבל מנוי, [צור קשר ישירות עם LiveRamp](https://liveramp.com/contact/). [קבל מידע נוסף אודות LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>התחברות אל LiveRamp

1. ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.

1. באריח **LiveRamp**, בחר **הגדר**.

1. תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. ספק **שם משתמש** וכן **סיסמה** עבור חשבון LiveRamp Secure FTP‏ (SFTP) שלך.
אישורים אלה עשויים להיות שונים מאישור LiveRamp Onboarding.

1. בחר **אמת** כדי לבדוק את החיבור ל- LiveRamp.

1. לאחר אימות מוצלח, ספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.

1. בחר **הבא** כדי להגדיר את מחבר LiveRamp.

## <a name="configure-the-connector"></a>קביעת תצורת המחבר

1. בשדה **בחר את מזהה המפתח שלך**, בחר **דואר אלקטרוני**, **שם וכתובת** או **טלפון** כדי לשלוח ל- LiveRamp עבור פענוח זהות.

1. מפה את התכונות המתאימות מישות הלקוח המאוחד שלך עבור מזהה המפתח שנבחר.

1. בחר **הוסף תכונה** כדי למפות תכונות נוספות שיישלחו ל- LiveRamp.

   > [!TIP]
   > שליחת תכונות מזהה מפתח נוספות ל- LiveRamp עשויה להשיג לך שיעור התאמה גבוה יותר.

1. בחר את הפלחים שברצונך לייצא ל- LiveRamp.

1. בחר **שמור**.

> [!div class="mx-imgBorder"]
> ![מחבר LiveRamp עם מיפוי תכונות](media/export-liveramp-segments.png "מחבר LiveRamp עם מיפוי תכונות")

## <a name="export-the-data"></a>ייצוא הנתונים

הייצוא יתחיל בקרוב אם כל הדרישות המוקדמות עבור ייצוא יושלמו. הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).
לאחר השלמת הייצוא בהצלחה, תוכל להיכנס ל- LiveRamp Onboarding כדי להפעיל ולהפיץ את הנתונים שלך.

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Liveramp, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Liveramp עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.