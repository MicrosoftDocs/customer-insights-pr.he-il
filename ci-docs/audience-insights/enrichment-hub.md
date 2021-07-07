---
title: העשרת פרופילי לקוחות מאוחדים
description: השתמש ביכולות כדי להעשיר את נתוני הלקוחות שלך.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305249"
---
# <a name="enrichment-for-customer-profiles-preview"></a>העשרה לפרופילי לקוחות (תצוגה מקדימה)

השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="דף מרכז ההעשרה":::

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

בחר העשרה כדי לראות את האפשרויות הזמינות. באפשרותך גם לבחור את שלוש הנקודות (...) בפריט רשימה כדי לראות את האפשרויות.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="אפשרויות לניהול ההעשרות ברשימת ההעשרות":::

- **הצג** פרטי העשרה עם המספר של פרופילי לקוחות המועשרים.
- **ערוך** את תצורת ההעשרה.
- **הפעל** את העשרה לעדכון את פרופילי הלקוחות בנתונים העדכניים ביותר.
- **השבת** העשרה קיימת כדי למנוע ממנה רענון אוטומטי עם כל רענון מתוזמן. נתונים מהרענון האחרון המוצלח ימשיכו להיות זמינים. **להפעיל** העשרה לא פעילה להפעלה מחדש של רענון אוטומטי בכל רענון מתוזמן.
- **מחק** העשרה.

באפשרותך להפעיל פעולות העשרה מרובות בבת אחת או לבטלן על ידי בחירתן מתוך רשימה. אפשרויות תצוגה ועריכה אינן זמינות כפעולה בצובר והן פועלות רק עבור העשרה אחת בכל פעם.

## <a name="enrichments-and-connections"></a>העשרות וחיבורים

העשרות צד שלישי מוגדרות באמצעות [חיבורים](connections.md), אשר מנהל מערכת מגדיר עם אישורים ומספק הסכמה עבור העברות נתונים. החיבור יכול לשמש את מנהלי המערכת והמשתתפים לקביעת תצורה של העשרות.  

## <a name="multiple-enrichments-of-the-same-type"></a>העשרות מרובות מאותו סוג

הישות שיש להעשיר מצוינת במהלך קביעת תצורת ההעשרה, אשר מאפשרת לך להעשיר רק ערכת משנה של הפרופילים שלך. לדוגמה, העשרת נתונים רק עבור פלח ספציפי. באפשרותך לקבוע תצורה של מספר העשרות מאותו סוג ולהשתמש מחדש באותו חיבור. לחלק מההעשרות יהיו מגבלות על מספר ההעשרות מאותו הסוג שניתן ליצור. ניתן לראות את המגבלות והשימוש הנוכחי בדף **העשרה**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
