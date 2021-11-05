---
title: העשרת פרופילי לקוחות מאוחדים
description: השתמש ביכולות כדי להעשיר את נתוני הלקוחות שלך.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: bc0128c222c032e8cfe35e6f3baa0ea722bce7cb
ms.sourcegitcommit: 31985755c7c973fb1eb540c52fd1451731d2bed2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/22/2021
ms.locfileid: "7673000"
---
# <a name="enrichment-for-customer-profiles-preview"></a>העשרה לפרופילי לקוחות (תצוגה מקדימה)

השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="דף מרכז ההעשרה.":::

ב- audience insights, עבור אל **נתונים** > **העשרה** כדי לעבוד עם אפשרויות העשרה.  

עליך להיות בעל הרשאות משתתף או מנהל מערכת כדי ליצור או לערוך העשרה. לקבלת מידע נוסף, ראה [הרשאות](permissions.md).

בכרטיסיה **גלה**, תמצא את כל אפשרויות ההעשרה הנתמכות.

# <a name="individual-consumers-b-to-c"></a>[צרכנים בודדים (B-to-C)](#tab/b2c)

- [מותגים](enrichment-microsoft.md) שסופקו על-ידי Microsoft
- [תחומי עניין](enrichment-microsoft.md) שסופקו על-ידי Microsoft
- [כתובות משופרות](enrichment-enhanced-addresses.md) מסופקות על-ידי Microsoft 
- [נתונים דמוגרפיים](enrichment-experian.md) המסופקים על-ידי Experian
- [נתונים מותאמים אישית](enrichment-SFTP-custom-import.md) דרך Secure File Transfer Protocol‏ (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) מסופק על-ידי Microsoft

# <a name="business-accounts-b-to-b"></a>[תיקי לקוחות עסקיים (B-to-B)](#tab/b2b)

- [נתוני החברה](enrichment-leadspace.md) מסופקים על-ידי Leadspace
- [כתובות משופרות](enrichment-enhanced-addresses.md) מסופקות על-ידי Microsoft 
- [נתוני מיקום](enrichment-here.md) מסופקים על-ידי HERE Technologies 
- [נתונים מותאמים אישית](enrichment-SFTP-custom-import.md) דרך Secure File Transfer Protocol‏ (SFTP) 
- [Azure Maps](enrichment-azure-maps.md) מסופק על-ידי Microsoft

---

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

העשרות צד שלישי מוגדרות באמצעות [חיבורים](connections.md), אשר מנהל מערכת מגדיר עם אישורים ומספק הסכמה עבור העברות נתונים. מנהלים ומשתתפים יכולים להשתמש בחיבורים כדי לקבוע תצורה של העשרות.  

## <a name="multiple-enrichments-of-the-same-type"></a>העשרות מרובות מאותו סוג

הישות שיש להעשיר מצוינת במהלך קביעת תצורת ההעשרה, אשר מאפשרת לך להעשיר רק ערכת משנה של הפרופילים שלך. לדוגמה, העשרת נתונים רק עבור פלח ספציפי. באפשרותך לקבוע תצורה של מספר העשרות מאותו סוג ולהשתמש מחדש באותו חיבור. לחלק מההעשרות יהיו מגבלות על מספר ההעשרות מאותו הסוג שניתן ליצור. ניתן לראות את המגבלות והשימוש הנוכחי בדף **העשרה**.

## <a name="see-the-progress-of-the-enrichment-process"></a>ראה את התקדמות תהליך ההעשרה

באפשרותך למצוא פרטים על עיבוד העשרה, כולל המצב שלה ובעיות אפשריות בעת ביצוע הרענון שלה או לאחר שהרענון הושלם. הבן אילו תהליכים מעורבים כדי לרענן העשרה ואת משך הזמן שנדרש להפעלת התהליכים. מצב ההעשרה נתמך עבור Experian,‏ Leadspace‏, HERE Technologies‏, SFTP Import ו- Azure Maps.

כדי לראות את מצב ההעשרה

1. עבור אל **נתונים** > **העשרה**. 
1. בכרטיסיה **ההעשרות שלי**, בחר את מצב ההעשרה כדי לפתוח חלונית צדדית. 
1. בחלונית **פרטי התקדמות**, הרחב את המקטע **העשרות**. 
1. תחת ההעשרה שברצונך לראות את ההתקדמות שלה, בחר **הצג פרטים**. 
1. בחלונית **פרטי משימה**, בחר **הצג פרטים** כדי לראות את התהליכים המעורבים בעדכון ההעשרה והמצב שלהם. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
