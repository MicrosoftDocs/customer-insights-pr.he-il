---
title: סקירה כללית על תרחישי חיזוי נתמכים
description: תרחישי חיזוי ואפשרויות המכוסות על-ידי היישום Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095713"
---
# <a name="predictions-overview"></a>מבט כולל על חיזויים

Dynamics 365 Customer Insights מגיע עם מגוון אפשרויות שמנצלות את AI ולמידת מכונה לחיזוי נתונים. 

## <a name="out-of-box-models"></a>מודלים מוכנים לשימוש

הדרך הקלה ביותר להתחיל עם חיזוי נתונים היא באמצעות מודלים מוגדרים מראש, שלעתים קרובות נקראים 'מודלים מוכנים לשימוש'. כדי ליצור תובנות במהירות, נדרשים רק נתונים ומבנים מסוימים. נכון לעכשיו, המודלים הבאים זמינים: 
- [‏‫‏‫ערך אורך החיים של הלקוח‬](predict-customer-lifetime-value.md): חוזה את ההכנסות הפוטנציאליות של לקוח לאורך כל האינטראקציה עם עסק. 
- [המלצת מוצר](predict-product-recommendation.md): מציע קבוצה של המלצות תחזיתיות למוצרים בהתבסס על התנהגות רכישה ולקוחות עם דפוסי רכישה דומים.
- [נטישת מנויים](predict-subscription-churn.md): חוזה אם קיימת סכנה שלקוח לא ישתמש עוד במוצרי המנוי או בשירותי המנוי של החברה שלך.
- [נטישה של עסקאות‬‏‫](predict-transactional-churn.md): חוזה אם לקוח לא ירכוש עוד את המוצרים או השירותים שלך במסגרת זמן מסוימת.

## <a name="azure-machine-learning-integration"></a>שילוב למידת מכונה של Azure

אם ארגון כבר משתמש בתרחישי למידת מכונה המבוססים על חוויות למידת מכונה של Azure, תכונת המודלים המותאמים אישית ב- Customer Insights עוזרת לחבר את הנקודות. צור זרימות עבודה שיעזרו לך לבחור את הנתונים שמהם ברצונך לייצר תובנות ולמפות את התוצאות לפרופילי הלקוחות המאוחדים שלך. למידע נוסף ראה [דגמי למידת מכונה מותאמים אישית](custom-models.md).

## <a name="ai-builder-prediction"></a>חיזוי של AI Builder

לפעמים ערכות נתונים אינן שלמות וחסרים בהן ערכים מסוימים. Customer Insights יכול לסייע בחיזוי ערכים חסרים עבור ישות הלקוח והפלחים. למידע נוסף, ראה [השלמת נתונים חלקיים בעזרת חיזויים](predictions.md).
