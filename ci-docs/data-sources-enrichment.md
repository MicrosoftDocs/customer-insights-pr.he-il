---
title: העשרת מקור נתונים
description: העשר את מקורות הנתונים לפני ביצוע תהליך איחוד הנתונים.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: b34b83d7a73dbdf21984f626174524188f0f1dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011474"
---
# <a name="enrichment-for-data-sources-preview"></a>העשרה למקורות נתונים (Preview)

השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך לפני איחוד הנתונים. העשרות מקור הנתונים עוזרות לייצר שלמות ואיכות טובה יותר של נתונים, שיכולות לעזור להשיג תוצאות טובות לאחר איחוד הנתונים. לדוגמה, שימוש בפורמט מנורמל וסטנדרטי עבור כתובות מגביר את איכות תוצאות ההתאמה. לרשימה של העשרה נתמכת, ראה [אפשרויות העשרה נתמכות למקורות נתונים](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>העשרת מקור נתונים

חייבים להיות לך הרשאות משתתף או מנהל מערכת כדי ליצור או לערוך העשרה. לקבלת מידע נוסף, ראה [הרשאות](permissions.md).  

1. עבור אל **נתונים** > **איחוד**. בחר את הישות שברצונך להעשיר ובחר בתכונה אחת כמפתח ראשי עבור הישות. למידע נוסף, ראה [בחירת מפתח ראשי](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. עבור אל **נתונים** > **מקורות נתונים**.

1. בחר את שלוש הנקודות האנכיות (&vellip;) לצד מקור נתונים שברצונך להעשיר ובחר **העשרה**.

   :::image type="content" source="media/data_sources_enrich.png" alt-text="דף מקורות נתונים שבו 'להעשיר' מודגש":::

   הכרטיסיה **גילוי** מציגה את [האפשרויות הנתמכות של העשרת מקור נתונים](#supported-data-source-enrichments).

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="דף העשרת מקורות נתונים.":::

1. בחר **העשר את הנתונים שלי** כדי להגדיר העשרה של מקור נתונים. שם יישות הפלט מאוכלס באופן אוטומטי.

## <a name="supported-data-source-enrichments"></a>העשרות נתמכות למקורות נתונים

סוגי ההעשרות הבאים זמינים כעת עבור מקורות נתונים. סקור את השלבים המפורטים להעשרה כדי ללמוד כיצד להגדיר אותה.

- [כתובות משופרות](enrichment-enhanced-addresses.md)
- [נתוני חברה משופרים](enrichment-enhanced-company-data.md)
- [נתוני זהות מ- LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>ניהול העשרות קיימות של מקורות נתונים

עבור אל הכרטיסיה **ההעשרות שלי** כדי לראות את כל ההעשרות שהוגדרו.

בחר את ההעשרה כדי לראות את האפשרויות הזמינות. אתה יכול גם לבחור את שלוש הנקודות האנכיות (&vellip;) על פריט רשימה כדי לראות את האפשרויות. אם הגדרת מספר העשרות, תוכל להשתמש בתיבת החיפוש כדי למצוא אותה במהירות.

אתה יכול להציג, לערוך, להפעיל או למחוק העשרה של מקור נתונים. למידע נוסף, ראה [ניהול העשרות קיימות](enrichment-hub.md).
