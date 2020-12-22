---
title: העשרת פרופילי לקוחות מאוחדים
description: השתמש ביכולות כדי להעשיר את נתוני הלקוחות שלך.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667095"
---
# <a name="enrichment-for-customer-profiles-preview"></a>העשרה לפרופילי לקוחות (תצוגה מקדימה)

השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="דף מרכז ההעשרה":::

ב- audience insights, עבור אל **נתונים** > **העשרה** כדי לעבוד עם אפשרויות העשרה.    
עליך להיות בעל הרשאות משתתף או מנהל מערכת כדי ליצור או לערוך העשרה. לקבלת מידע נוסף, ראה [הרשאות](permissions.md).

בכרטיסיה **גלה**, תוכל למצוא את ההעשרה הבאה:

- [מותגים](enrichment-microsoft-graph.md) מסופקים על ידי Microsoft Graph
- [תחומי עניין](enrichment-microsoft-graph.md) מסופקים על-ידי Microsoft Graph.
- [נתוני החברה](enrichment-leadspace.md) מסופקים על-ידי Leadspace
- [נתונים דמוגרפיים](enrichment-experian.md) מסופקים על-ידי Experian
- [נתוני מיקום](enrichment-here.md) מסופקים על-ידי HERE Technologies
- [נתונים מותאמים אישית](enrichment-SFTP-custom-import.md) דרך Secure File Transfer Protocol‏ (SFTP)

בכרטיסיה **ההעשרות שלי**, תוכל לראות את ההעשרות שהגדרת ולערוך את המאפיינים שלהן.

## <a name="manage-existing-enrichments"></a>ניהול העשרות קיימות

עבור אל **העשרה שלי** כדי לראות את כל ההעשרה המוגדרת. כל העשרה מיוצגת כשורה הכוללת מידע נוסף על ההעשרה.

בחר העשרה כדי לראות את האפשרויות הזמינות. לחלופין, ניתן לבחור בשלוש נקדות (...) בפריט של רשימה כדי לראות את האפשרויות.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="אפשרויות לניהול ההעשרות ברשימת ההעשרות":::

- **הצג** פרטי העשרה עם המספר של פרופילי לקוחות המועשרים.
- **ערוך** את תצורת ההעשרה.
- **הפעל** את העשרה לעדכון את פרופילי הלקוחות בנתונים העדכניים ביותר.
- **השבת** העשרה קיימת כדי למנוע ממנה רענון אוטומטי עם כל רענון מתוזמן. נתונים מהרענון האחרון המוצלח ימשיכו להיות זמינים. **להפעיל** העשרה לא פעילה להפעלה מחדש של רענון אוטומטי בכל רענון מתוזמן.
- **מחק** העשרה.

באפשרותך להפעיל פעולות העשרה מרובות בבת אחת או לבטלן על ידי בחירתן מתוך רשימה. אפשרויות תצוגה ועריכה אינן זמינות כפעולה בצובר והן פועלות רק עבור העשרה אחת בכל פעם.
