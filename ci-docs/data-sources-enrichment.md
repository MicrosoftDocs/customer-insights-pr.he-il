---
title: העשרת מקור נתונים
description: העשר את מקורות הנתונים לפני ביצוע תהליך איחוד הנתונים.
ms.date: 03/02/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: d1e14d2d4e718d71ccbd2afd259a350ad5c9e69a
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755687"
---
# <a name="enrichment-for-data-sources-preview"></a>העשרה למקורות נתונים (Preview)

השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך לפני איחוד הנתונים. העשרות מקור הנתונים עוזרות לייצר שלמות ואיכות טובה יותר של נתונים, שיכולות לעזור להשיג תוצאות טובות לאחר איחוד הנתונים. לדוגמה, שימוש בפורמט מנורמל וסטנדרטי עבור כתובות מגביר את איכות תוצאות ההתאמה. לרשימה של העשרה נתמכת, ראה [אפשרויות העשרה נתמכות למקורות נתונים](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>העשרת מקור נתונים

חייבים להיות לך הרשאות משתתף או מנהל מערכת כדי ליצור או לערוך העשרה. לקבלת מידע נוסף, ראה [הרשאות](permissions.md).  

1. עבור אל **נתונים** > **איחוד**. בחר את הישות שברצונך להעשיר ובחר בתכונה אחת כמפתח ראשי עבור הישות. למידע נוסף, ראה [בחירת מפתח ראשי](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. עבור אל **נתונים** > **מקורות נתונים**.

1. בחר את שלושת הנקודות האנכיות לצד מקור נתונים שברצונך להעשיר ובחר **העשרה**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="דף העשרת מקורות נתונים.":::

   הכרטיסיה **גילוי** מציגה את [האפשרויות הנתמכות של העשרת מקור נתונים](#supported-data-source-enrichments).

1. בחר **העשר את הנתונים שלי** כדי להגדיר העשרה של מקור נתונים. שם יישות הפלט מאוכלס באופן אוטומטי.

## <a name="supported-data-source-enrichments"></a>העשרות נתמכות למקורות נתונים

סוגי ההעשרות הבאים זמינים כעת עבור מקורות נתונים. סקור את השלבים המפורטים להעשרה כדי ללמוד כיצד להגדיר אותה.

- [כתובות משופרות](enrichment-enhanced-addresses.md)
- [נתוני חברה משופרים](enrichment-enhanced-company-data.md)

## <a name="manage-existing-data-source-enrichments"></a>ניהול העשרות קיימות של מקורות נתונים

עבור אל הכרטיסיה **ההעשרות שלי** כדי לראות את כל ההעשרות שהוגדרו.

בחר את ההעשרה כדי לראות את האפשרויות הזמינות. באפשרותך גם לבחור את שלוש הנקודות (...) בפריט רשימה כדי לראות את האפשרויות. אם הגדרת מספר העשרות, תוכל להשתמש בתיבת החיפוש כדי למצוא אותה במהירות.

אתה יכול להציג, לערוך, להפעיל או למחוק העשרה של מקור נתונים. למידע נוסף, ראה [ניהול העשרות קיימות](enrichment-hub.md).
