---
title: העשרת פרופילי לקוחות מאוחדים
description: השתמש ביכולות כדי להעשיר את נתוני הלקוחות שלך.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d12c0a9dd65d31f9ae8a9cafeafab2767d57893e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555262"
---
# <a name="enrichment-for-customer-profiles-preview"></a>העשרה לפרופילי לקוחות (תצוגה מקדימה)

השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="דף מרכז ההעשרה.":::

ב- audience insights, עבור אל **נתונים** > **העשרה** כדי לעבוד עם אפשרויות העשרה.  

עליך להיות בעל הרשאות משתתף או מנהל מערכת כדי ליצור או לערוך העשרה. לקבלת מידע נוסף, ראה [הרשאות](permissions.md).

בכרטיסיה **גלה**, תוכל למצוא את ההעשרה הבאה:

- [מותגים](enrichment-microsoft.md) שסופקו על-ידי Microsoft
- [תחומי עניין](enrichment-microsoft.md) שסופקו על-ידי Microsoft
- [כתובות משופרות](enrichment-enhanced-addresses.md) מסופקות על-ידי Microsoft
- [נתוני החברה](enrichment-leadspace.md) מסופקים על-ידי Leadspace
- [נתונים דמוגרפיים](enrichment-experian.md) המסופקים על-ידי Experian
- [נתוני מיקום](enrichment-here.md) מסופקים על-ידי HERE Technologies
- [נתונים מותאמים אישית](enrichment-SFTP-custom-import.md) דרך Secure File Transfer Protocol‏ (SFTP)

בכרטיסיה **ההעשרות שלי**, תוכל לראות את ההעשרות שהגדרת ולערוך את המאפיינים שלהן.

## <a name="manage-existing-enrichments"></a>ניהול העשרות קיימות

עבור אל הכרטיסיה **ההעשרות שלי** כדי לראות את כל ההעשרות שהוגדרו. כל העשרה מיוצגת כשורה הכוללת מידע נוסף על ההעשרה.

בחר את ההעשרה כדי לראות את האפשרויות הזמינות. באפשרותך גם לבחור את שלוש הנקודות (...) בפריט רשימה כדי לראות את האפשרויות. אם הגדרת מספר העשרות, תוכל להשתמש בתיבת החיפוש כדי למצוא אותה במהירות.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="אפשרויות לניהול ההעשרות ברשימת ההעשרות.":::

- **הצג** פרטי העשרה עם המספר של פרופילי לקוחות המועשרים.
- **ערוך** את תצורת ההעשרה.
- **הפעל** את העשרה לעדכון את פרופילי הלקוחות בנתונים העדכניים ביותר.
- **השבת** העשרה קיימת כדי למנוע ממנה רענון אוטומטי עם כל רענון מתוזמן. נתונים מהרענון האחרון המוצלח ימשיכו להיות זמינים. **להפעיל** העשרה לא פעילה להפעלה מחדש של רענון אוטומטי בכל רענון מתוזמן.
- **מחק** את ההעשרה.

הפעל או השבת העשרות מרובות בבת אחת על-ידי בחירתן ברשימה. אפשרויות ההצגה והעריכה אינן זמינות כפעולה בצובר. הן פועלות רק להעשרה אחת בכל פעם.

## <a name="enrichments-and-connections"></a>העשרות וחיבורים

העשרות צד שלישי מוגדרות באמצעות [חיבורים](connections.md), אשר מנהל מערכת מגדיר עם אישורים ומספק הסכמה עבור העברות נתונים. החיבור יכול לשמש את מנהלי המערכת והמשתתפים לקביעת תצורה של העשרות.  

## <a name="multiple-enrichments-of-the-same-type"></a>העשרות מרובות מאותו סוג

הישות שיש להעשיר מצוינת במהלך קביעת תצורת ההעשרה, אשר מאפשרת לך להעשיר רק ערכת משנה של הפרופילים שלך. לדוגמה, העשרת נתונים רק עבור פלח ספציפי. באפשרותך לקבוע תצורה של מספר העשרות מאותו סוג ולהשתמש מחדש באותו חיבור. לחלק מההעשרות יהיו מגבלות על מספר ההעשרות מאותו הסוג שניתן ליצור. ניתן לראות את המגבלות והשימוש הנוכחי בדף **העשרה**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
