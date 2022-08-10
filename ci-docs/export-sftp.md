---
title: ייצוא נתונים אל מארחי SFTP ‏(Preview)‏ (מכיל סרטון)
description: למד כיצד להגדיר את החיבור ולייצא אל מיקום SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207230"
---
# <a name="export-data-to-sftp-hosts-preview"></a>ייצוא נתונים אל מארחי SFTP ‏(Preview)

השתמש בנתוני הלקוחות שלך ביישומי צד שלישי על-ידי ייצוא שלהם למיקום Secure File Transfer Protocol‏ (SFTP).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- זמינות של מארח SFTP ואישורים מתאימים.

## <a name="known-limitations"></a>מגבלות ידועות

- יעדי SFTP מאחורי חומות אש אינם נתמכים כרגע.
- זמן הריצה של ייצוא תלוי בביצועי המערכת שלך. מומלץ שתי ליבות CPU וזיכרון של 1‎ GB כתצורה מינימלית עבור השרת שלך.
- עד 100 מיליון פרופילי לקוחות, והפעולה יכולה להימשך 90 דקות בעת שימוש בתצורה המינימלית המומלצת של שתי ליבות CPU וזיכרון של 1‎ GB.
- אם אתה משתמש במפתח SSH לאימות, ודא שאתה [יוצר את המפתח הפרטי שלך](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) כפורמט PEM או SSH.COM. אם אתה משתמש ב- Putty, המר את המפתח הפרטי על ידי ייצוא שלו בתור Open SSH. פורמטי המפתח הפרטי הבאים נתמכים:
  - RSA בפורמט OpenSSL PEM ו- ssh.com
  - DSA בפורמט OpenSSL PEM ו- ssh.com
  - ECDSA 256/384/521 בפורמט OpenSSL PEM
  - ED25519 ו- RSA בפורמט מפתח OpenSSH

## <a name="set-up-connection-to-sftp"></a>הגדרת חיבור ל- SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **SFTP**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. בחר אם ברצונך לבצע אימות באמצעות SSH או באמצעות שם משתמש/סיסמה עבור החיבור שלך וספק את הפרטים הדרושים. אם אתה משתמש במפתח SSH לאימות, ודא שאתה [יוצר את המפתח הפרטי שלך](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) כפורמט PEM או SSH.COM. אם אתה משתמש ב- Putty, המר את המפתח הפרטי על ידי ייצוא שלו בתור Open SSH. פורמטי המפתח הפרטי הבאים נתמכים:
   - RSA בפורמט OpenSSL PEM ו- ssh.com
   - DSA בפורמט OpenSSL PEM ו- ssh.com
   - ECDSA 256/384/521 בפורמט OpenSSL PEM
   - ED25519 ו- RSA בפורמט מפתח OpenSSH

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

> [!TIP]
> ייצוא של ישויות המכילות כמות גדולה של נתונים יכול להוביל למספר קובצי CSV באותה תיקייה עבור כל פעולת ייצוא. פיצול פעולות הייצוא קורה מטעמי ביצועים כדי למזער את הזמן שלוקח לייצוא להסתיים.

[!INCLUDE [footer-include](includes/footer-banner.md)]
