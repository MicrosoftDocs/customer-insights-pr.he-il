---
title: תזמון רענון מערכת
description: תזמן את הזמן שבו יש לרענן את המערכת
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610329"
---
# <a name="schedule-system-refresh"></a>תזמון רענון מערכת

תזמן רענונים אוטומטיים עבור כל [מקורות הנתונים שנקלטו](data-sources.md). רענונים אוטומטיים עוזרים להבטיח שעדכונים ממקורות הנתונים שלך ישתקפו בפרופילי הלקוחות המאוחדים שלך.

> [!NOTE]
> מקורות נתונים של Power Query המנוהלים על ידך מתרעננים לפי לוחות זמנים משלהם. כדי לתזמן רענון של מקורות נתונים אלה של Power Query, הגדר את הגדרות הרענון במקור הנתונים הספציפי בדף **מקורות נתונים**. התאם את התזמון ללוח הזמנים של רענון הנתונים במעלה הזרם כך שהרענונים לא יתרחשו בבת אחת.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Power Platform הגדרות רענון תזרים נתונים.":::

## <a name="set-system-refresh-schedule"></a>הגדרת לוח זמנים לרענון המערכת

1. עבור אל **מנהל מערכת** > **מערכת**, ולאחר מכן בחר בכרטיסיה **לוח זמנים**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="תזמן את כרטיסיית הרענון מדף המערכת.":::

1. מצב ברירת המחדל עבור הרענון המתוזמן הוא **כבוי**. כדי לאפשר רענון מתוזמן, שנה את המתח בחלק העליון של המסך ל **פועל**.

1. בחר בין רענון **שבועי** (ברירת מחדל) לבין **יומי**. אם אתה מתכוון לתזמן רענונים שבועיים, בחר יום אחד או יותר שבו תרצה להפעיל את הרענון.

1. הגדר **אזור זמן** והשתמש בתפריט הנפתח **זמן** להגדרת תזמון הרענון שלך. אם תרצה לתזמן רענונים מרובים ביום אחד, בחר **הוסף עוד זמן**. באפשרותך להוסיף עד ארבעה ריענונים.

1. בחר **שמור** כדי להחיל את השינויים.

[!INCLUDE [footer-include](includes/footer-banner.md)]
