---
title: ייצוא פלחים אל LiveRamp‏ (Preview)
description: למד כיצד להגדיר את החיבור ואת הייצוא אל LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196717"
---
# <a name="export-segments-to-liverampreg-preview"></a>ייצוא פלחים אל LiveRamp&reg;‏ (Preview)

הפעל את הנתונים שלך ב- LiveRamp כדי להתחבר ליותר מ- 500 פלטפורמות בעולם הדיגיטלי, החברתי ובעולם הטלוויזיות. עבוד עם הנתונים שלך ב- LiveRamp כדי להתמקד, להשמיט ולהתאים אישית קמפיינים פרסומיים.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- מינוי ל- LiveRamp כדי להשתמש במחבר זה. כדי לקבל מנוי, [צור קשר ישירות עם LiveRamp](https://liveramp.com/contact/). [קבל מידע נוסף אודות LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>‏‫מגבלות ידועות‬

- הייצוא של LiveRamp משתמש בייצוא SFTP. יעדי SFTP מאחורי חומות אש אינם נתמכים כרגע.
- אם אתה משתמש במפתח SSH לאימות, ודא שאתה [יוצר את המפתח הפרטי שלך](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) כפורמט PEM או SSH.COM. אם אתה משתמש ב- Putty, המר את המפתח הפרטי על ידי ייצוא שלו בתור Open SSH. פורמטי המפתח הפרטי הבאים נתמכים:
  - RSA בפורמט OpenSSL PEM ו- ssh.com
  - DSA בפורמט OpenSSL PEM ו- ssh.com
  - ECDSA 256/384/521 בפורמט OpenSSL PEM
  - ED25519 ו- RSA בפורמט מפתח OpenSSH
- זמן הריצה של ייצוא תלוי בביצועי המערכת שלך. מומלץ שתי ליבות CPU וזיכרון של 1‎ GB כתצורה מינימלית עבור השרת שלך.
- ייצוא ישויות עם עד 100 מיליון פרופילי לקוחות יכול להימשך 90 דקות בעת שימוש בתצורה המינימלית המומלצת של שתי ליבות CPU וזיכרון של 1‎ GB.
- מספר הפרופילים (או הנתונים) בפועל שאתה יכול לייצא אל LiveRamp תלוי במינוי שלך ל- LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>הגדרת חיבור אל LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **LiveRamp‎**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר אם ברצונך לבצע אימות באמצעות SSH או באמצעות שם משתמש/סיסמה עבור החיבור שלך וספק את הפרטים הדרושים.

1. בחר **אמת** כדי לבדוק את החיבור ל- LiveRamp.

1. לאחר אימות מוצלח, סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

## <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע LiveRamp. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. בשדה **חבר נתונים**, בחר **דואר אלקטרוני**, **שם וכתובת** או **טלפון** כדי לשלוח ל- LiveRamp עבור פענוח זהות.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="מחבר LiveRamp עם מיפוי תכונות.":::

1. מפה את התכונות המתאימות מישות *לקוח* עבור מזהה המפתח שנבחר.

1. בחר **הוסף תכונה** כדי למפות תכונות נוספות לשליחה אל LiveRamp.

   > [!TIP]
   > שליחת תכונות מזהה מפתח נוספות ל- LiveRamp עשויה להשיג לך שיעור התאמה גבוה יותר.

1. בחר את הפלחים שברצונך לייצא.

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
