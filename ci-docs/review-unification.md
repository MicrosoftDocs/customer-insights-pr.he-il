---
title: בדוק את איחוד הנתונים
description: סקור את שלבי איחוד הנתונים, צור פרופילי לקוחות מאוחדים וסקור את התוצאות
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 0f7b2e9af65796c4d304dbd9893a21617e847620
ms.sourcegitcommit: 760fbac397c738407c7dea59297d54cae19b6f57
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8844087"
---
# <a name="review-data-unification"></a>בדוק את איחוד הנתונים

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

שלב אחרון זה בתהליך האיחוד מציג סיכום של השלבים בתהליך ומספק הזדמנות לבצע שינויים לפני שתיצור את הפרופיל המאוחד.

:::image type="content" source="media/m3_review.png" alt-text="צילום מסך של סקירה ויצירת פרופילי לקוחות.":::

## <a name="review-the-data-unification-steps"></a>סקור את שלבי איחוד הנתונים

1. בחר **ערוך** בכל אחד משלבי איחוד הנתונים כדי לבדוק ולבצע שינויים כלשהם.

1. אם אתה מרוצה מהבחירות שלך, בחר **צור פרופילי לקוחות**. הדף **איחוד** מוצג בזמן יצירת פרופיל לקוח מאוחד. כל האריחים מלבד **שדות מקור** מציגים **בתור** או מצב **מרענן**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="צילום מסך של דף Unify עם אריחים המציגים 'בתור' או 'מרענן'.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

לאלגוריתם האיחוד לוקח קצת זמן להשלים ולא ניתן לשנות את התצורה עד שהיא תושלם. כאשר תהליך האיחוד מסתיים, ישות פרופיל לקוח מאוחד, שנקראת *לקוח*, מופיעה בדף **ישויות** במקטע **פרופילים**. הפעלת האיחוד המוצלחת הראשונה יוצרת את הישות המאוחדת *לקוח*. כל ההפעלות הבאות מרחיבות את הישות הזו.

## <a name="review-the-results-of-data-unification"></a>סקור את תוצאות איחוד הנתונים

לאחר האיחוד, הדף **נתונים** > **איחוד‎** מציג את המספר של פרופיל לקוח מאוחד. התוצאות של כל שלב בתהליך האיחוד מוצגות בכל אריח. לדוגמה, **שדות מקור** מציג את מספר התכונות הממופות (שדות) והאפשרות **רשומות כפולות** מציגה את מספר הרשומות הכפולות שנמצאו.

:::image type="content" source="media/m3_unified.png" alt-text="צילום מסך של הדף Data איחוד לאחר איחוד הנתונים.":::

> [!TIP]
> האריח **תנאים תואמים** מוצג רק אם נבחרו ישויות מרובות.

אנו ממליצים לבדוק את התוצאות, במיוחד את האיכות של [חוקי ההתאמה](data-unification-update.md#manage-match-rules) ולהתאים אותם במידת הצורך.

במקרה הצורך, [בצע שינויים בהגדרות האיחוד](data-unification-update.md) והפעל מחדש את הפרופיל המאוחד.

## <a name="next-step"></a>השלב הבא

הגדר [פעילויות](activities.md), [העשרה](enrichment-hub.md), [קשרים](relationships.md), או [מדדים](measures.md) כדי לקבל יותר תובנות לגבי הלקוחות שלך.

[!INCLUDE[footer-include](includes/footer-banner.md)]
