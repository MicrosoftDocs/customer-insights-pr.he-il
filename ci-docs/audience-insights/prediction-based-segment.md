---
title: פלחים המבוססים על פלט חיזוי
description: צור פלחים המבוססים על ישות הפלט של מודל חיזוי.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b0b3357cdf3c049bd92f6c3f690f27433df9117b
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8226664"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>יצירת פלח המבוסס על מודל חיזוי (Preview)

תוצאות החיזויים חלות לפעמים רק על ערכת משנה של הלקוחות שלך. הגדל את ההתאמה האישית של ההמלצות על-ידי יצירת פלחים מתוצאות של מודלי חיזוי. לדוגמה, ייתכן שתרצה לתת המלצות ספציפיות ללקוחות שמעדיפים סוג מסוים של שירות. 

## <a name="prerequisites"></a>דרישות מוקדמות

- לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.

- המלצה על מוצר, נטישת עסקאות, נטישת מנויים, או מודל ערך אורך חיים של לקוח מוגדרים ב- Customer Insights. סקור את הדרישות להגדרת המודלים השונים:

  - [מודל המלצות על מוצרים](predict-product-recommendation.md)
  - [מודל נטישת מנויים](predict-subscription-churn.md)
  - [מודל נטישה של עסקאות](predict-transactional-churn.md)
  - [מודך ערך אורך החיים של הלקוח](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>יצירת פלח לקוחות המבוסס על חיזויים

1. עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.

1. בחר את שלוש הנקודות האנכיות לצד המודל שברצונך לסקור ובחר **הצג**.

1. בדף התוצאות, בחר **צור פלח**. לקבלת מידע נוסף על דף התוצאות, סקור את המאמר אודות המודל.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="צילום מסך של דף תוצאות החיזוי עם הדגשה על פעולת יצירת הפלח.":::

1. צור פלח חדש המבוסס על ישות הפלט של המודל שנבחר. למידע נוסף: [יצירה וניהול של פלחים](segments.md).