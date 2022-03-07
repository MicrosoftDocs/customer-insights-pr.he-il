---
title: ‏‎מחבר ‎LiveRamp‏‏‏‏
description: למד כיצד להגדיר את החיבור ואת הייצוא אל LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: b377a3500c5d91962e59d46fbc259db5cc8fa7d0
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555446"
---
# <a name="export-segments-to-liverampreg-preview"></a>ייצוא פלחים אל LiveRamp&reg;‏ (Preview)

הפעל את הנתונים שלך ב- LiveRamp כדי להתחבר ליותר מ- 500 פלטפורמות בעולם הדיגיטלי, החברתי ובעולם הטלוויזיות. עבוד עם הנתונים שלך ב- LiveRamp כדי להתמקד, להשמיט ולהתאים אישית קמפיינים פרסומיים.

## <a name="prerequisites-for-a-connection"></a>דרישות מוקדמות לחיבור

- כדי להשתמש במחבר זה אתה זקוק למנוי LiveRamp.
- כדי לקבל מנוי, [צור קשר ישירות עם LiveRamp](https://liveramp.com/contact/). [קבל מידע נוסף אודות LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>הגדרת חיבור אל LiveRamp

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **LiveRamp** כדי לקבוע את תצורת החיבור.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. ספק **שם משתמש** וכן **סיסמה** עבור חשבון LiveRamp Secure FTP‏ (SFTP) שלך.
אישורים אלה עשויים להיות שונים מאישור LiveRamp Onboarding.

1. בחר **אמת** כדי לבדוק את החיבור ל- LiveRamp.

1. לאחר אימות מוצלח, ספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף יעד**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע LiveRamp. אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.

1. בשדה **בחר את מזהה המפתח שלך**, בחר **דואר אלקטרוני**, **שם וכתובת** או **טלפון** כדי לשלוח ל- LiveRamp עבור פענוח זהות.
   > [!div class="mx-imgBorder"]
   > ![מחבר LiveRamp עם מיפוי תכונות.](media/export-liveramp-segments.png "מחבר LiveRamp עם מיפוי תכונות")

1. מפה את התכונות המתאימות מישות הלקוח המאוחד שלך עבור מזהה המפתח שנבחר.

1. בחר **הוסף תכונה** כדי למפות תכונות נוספות לשליחה אל LiveRamp.

   > [!TIP]
   > שליחת תכונות מזהה מפתח נוספות ל- LiveRamp עשויה להשיג לך שיעור התאמה גבוה יותר.

1. בחר את הפלחים שברצונך לייצא ל- LiveRamp.

1. בחר **שמור**.

שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.

הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab). באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Liveramp, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Liveramp עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
