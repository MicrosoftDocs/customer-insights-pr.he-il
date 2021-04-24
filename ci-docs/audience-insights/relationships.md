---
title: קשרים בין ישויות ונתיבי ישויות
description: צור ונהל קשרים בין ישויות ממקורות נתונים מרובים.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595213"
---
# <a name="relationships-between-entities"></a>קשרים בין ישויות

קשרי גומלין עוזרים לך לחבר ישויות וליצור גרף מהנתונים כאשר לישויות יש מזהה משותף (מפתח זר) שאפשר להפנות מגורם אחד למשנהו. ישויות מחוברות מאפשרות לך להגדיר פלחים ומדידות על בסיס מקורות נתונים מרובים.

קיימים שני סוגים של קשרי גומלין. קשרי מערכת שאינם ניתנים לעריכה, אשר נוצרים באופן אוטומטי, וקשרים מותאמים אישית שנוצרים ומוגדרים על ידי משתמשים.

במהלך תהליכי ההתאמה והמיזוג, מערכת קשרים נוצרת מאחורי הקלעים על בסיס התאמה חכמה. קשרים אלה עוזרים לקשר בין רשומות פרופיל הלקוח לבין רשומות של ישויות מתאימות אחרות. התרשים הבא ממחיש את היצירה של שלוש מערכות קשרים כאשר ישות הלקוח מתאימה לישויות נוספות כדי ליצור את הישות הסופית של פרופיל הלקוח.

> [!div class="mx-imgBorder"]
> ![‏‏יצירת קשר](media/relationships-entities-merge.png "‏‏יצירת קשר")

- **קשר מסוג *CustomerToContact*** נוצר בין ישות הלקוח לבין ישות איש קשר. ישות הלקוח מקבלת את שדה המפתח **Contact_contactId** כדי להתייחס לשדה מפתח ישות איש קשר **contactId**.
- **קשר מסוג *CustomerToAccount*** נוצר בין ישות הלקוח לבין ישות תיק הלקוח. ישות הלקוח מקבלת את שדה המפתח **Account_accountId** כדי להתייחס לשדה מפתח ישות תיק הלקוח **accountId**.
- **קשר מסוג *CustomerToWebAccount*** נוצר בין ישות הלקוח לבין הישות WebAccount. ישות הלקוח מקבלת את שדה המפתח **WebAccount_webaccountId** כדי להתייחס לשדה מפתח ישות תיק הלקוח **webaccountId**.

## <a name="create-a-relationship"></a>יצירת קשר

הגדר קשרים מותאם אישית בדף **קשרים**. כל קשר מורכב מישות מקור (הישות שמחזיקה במפתח הזר) ומישות יעד (הישות שאליה מצביע המפתח הזר של ישות המקור).

1. ב- Audience Insights, עבור אל **נתונים** > **קשרים**.

2. בחר **קשר חדש**.

3. בחלונית **הוסף קשר**, ספק את הפרטים הבאים:

   > [!div class="mx-imgBorder"]
   > ![הזן פרטי קשר](media/relationships-add.png "הזן פרטי קשר")

   - **שם הקשר** : שם שמשקף את מטרת הקשר (לדוגמה, **AccountWebLogs**).
   - **תיאור**: תיאור של הקשר.
   - **ישות המקור** : בחר את הישות שמשמשת כמקור בקשר (לדוגמה, WebLog).
   - **מספר מונה** : בחר את הקרדינליות, המספר המונה של רשומות ישויות המקור. לדוגמה, "רבים" פירושו שרשומות Weblog מרובות קשורות לחשבון WebAccount אחד.
   - **שדה מפתח מקור** : שדה זה מייצג את שדה המפתח הזר בישות המקור. לדוגמה, ל- WebLog יש את שדה המפתח הזר **accountId‎**.
   - **ישות היעד** : בחר את הישות שמשמשת כיעד בקשר (לדוגמה, WebAccount).
   - **מספר מונה של היעד** : בחר את הקרדינליות, המספר המונה של רשומות ישויות היעד. לדוגמה, "אחד" פירושו שרשומות Weblog מרובות קשורות לחשבון WebAccount אחד.
   - **שדה מפתח יעד**: שדה זה מייצג את שדה המפתח של ישות היעד. לדוגמה, ל- WebAccount יש את שדה המפתח **accountId‎**.

> [!NOTE]
> רק קשרים מסוג רבים-לאחד ואחד-אחד נתמכים. ניתן ליצור קשרים מסוג רבים-לרבים באמצעות שני קשרים של רבים-לאחד וישות קישור (ישות המשמשת לחיבור ישות המקור לישות היעד).

## <a name="delete-a-relationship"></a>‏‏מחק קשר

1. ב- Audience Insights, עבור אל **נתונים** > **קשרים**.

2. בחר תיבות סימון עבור הקשר שברצונך למחוק.

3. בחר **מחק** בחלק העליון של הטבלה **קשרים**.

4. אשר את המחיקה.

## <a name="next-step"></a>השלב הבא

קשרי מערכת וקשרים מותאמים אישית משמשים ליצירת פלחים המבוססים על מקורות נתונים מרובים שכבר אינם נפרדים. לקבלת מידע נוסף, ראה [פלחים](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]