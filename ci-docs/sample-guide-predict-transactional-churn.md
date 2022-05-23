---
title: מדריך לדוגמה לחיזוי נטישה של עסקאות
description: השתמש במדריך לדוגמה זה כדי לנסות את המודל לחיזוי נטישה של עסקאות המוכן לשימוש.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741320"
---
# <a name="transactional-churn-prediction-sample-guide"></a>מדריך לדוגמה לחיזוי נטישה של עסקאות

מדריך זה ינחה אותך וידגים דוגמה מקצה לקצה של חיזוי נטישה של עסקאות ב- Customer Insights באמצעות הנתונים המפורטים להלן. כל הנתונים המופיעים במדריך זה אינם נתונים אמיתיים של לקוחות והם חלק מערכת נתונים של Contoso הנמצאת בסביבת *הדגמה* במנוי Customer Insights שלך.

## <a name="scenario"></a>תרחיש

Contoso היא חברה המייצרת קפה איכותי ומכונות קפה, שאותם היא מוכרת דרך האתר שלה Contoso Coffee. מטרת החברה היא לדעת אילו לקוחות, שבדרך כלל רוכשים את המוצרים שלהם על בסיס קבוע, יפסיקו להיות לקוחות פעילים ב- 60 הימים הקרובים. הידיעה מי מהלקוחות **עשוי לנטוש**, יכולה לעזור לה לחסוך מאמצים שיווקיים על-ידי התמקדות בשימור הלקוחות.

## <a name="prerequisites"></a>דרישות מוקדמות

- לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.
- אנו ממליצים ליישם את השלבים הבאים [בסביבה חדשה](manage-environments.md).

## <a name="task-1---ingest-data"></a>משימה 1 - קליטת נתונים

עיין במאמרים [לגבי קליטת נתונים](data-sources.md) ו- [ייבוא מקורות נתונים באמצעות מחברי Power Query ](connect-power-query.md) באופן ספציפי. המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>קליטת נתוני לקוחות מפלטפורמת eCommerce

1. צור מקור נתונים בשם **eCommerce**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscontacts.

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:

   - **DateOfBirth**: תאריך
   - **CreatedOn**: תאריך/שעה/אזור

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המרת תאריך הלידה לתאריך.":::

1. בשדה **שם** בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommerceContacts**

1. שמור את מקור הנתונים.

### <a name="ingest-online-purchase-data"></a>קליטת נתוני רכישה מקוונים

1. הוסף ערכת נתונים נוספת לאותו מקור נתונים **eCommerce**. בחר שוב את המחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור נתוני **רכישות מקוונות** https://aka.ms/ciadclassonline.

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:

   - **PurchasedOn**: תאריך/שעה
   - **TotalPrice**: מטבע
   
1. בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **eCommercePurchases**.

1. שמור את מקור הנתונים.

### <a name="ingest-customer-data-from-loyalty-schema"></a>קליטת נתוני לקוחות מסכמת loyalty

1. צור מקור נתונים בשם **LoyaltyScheme**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:

   - **DateOfBirth**: תאריך
   - **RewardsPoints**: מספר שלם
   - **CreatedOn**: תאריך/שעה

1. בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **loyCustomers**.

1. שמור את מקור הנתונים.

## <a name="task-2---data-unification"></a>משימה 2 - איחוד נתונים

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>משימה 3 - הגדר את חיזוי נטישת העסקאות

באמצעות פרופיל לקוח מאוחד אנו יכולים כעת להפעיל את החיזוי של נטישת עסקאות. לשלבים מפורטים, ראה את המאמר [חיזוי נטישת עסקאות](predict-transactional-churn.md). 

1. עבור אל **בינה** > **גילוי** ובחר להשתמש ב **מודל נטישת לקוחות**.

1. בחר את האפשרות **עסקאות** ובחר **תחילת העבודה**.

1. תן שם למודל **OOB eCommerce Transaction Churn Prediction** ולישות הפלט **OOBeCommerceChurnPrediction**.

1. הגדר שני תנאים עבור מודל הנטישה:

   * **חלון חיזוי**: **לפחות 60** ימים. הגדרה זו קובעת כמה רחוק בעתיד אנו רוצים לחזות את נטישת הלקוחות.

   * **הגדרת נטישה**: **לפחות 60** ימים. משך הזמן ללא רכישה שלאחריה נחשב הלקוח כלקוח שנטש.

     :::image type="content" source="media/model-levers.PNG" alt-text="בחר את מנופי המודל 'חלון חיזוי' ו'הגדרת נטישה'.":::

1. בחר **היסטוריית רכישות‬ (נדרש)** ובחר **הוסף נתונים** עבור היסטוריית רכישות.

1. הוסף את הישות **eCommercePurchases : eCommerce** ומפה את השדות מ- eCommerce לשדות המתאימים הנדרשים על-ידי המודל.

1. הצטרף לישות **eCommercePurchases: eCommerce** עם **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="הצטרף לישויות eCommerce.":::

1. בחר **הבא** כדי להגדיר את לוח הזמנים של המודל.

   המודל צריך לעבור הדרכה שוטפת כדי ללמוד דפוסים חדשים בעת קליטת נתונים חדשים. עבור דוגמה זו, בחר **חודשי**.

1. לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**.

## <a name="task-4---review-model-results-and-explanations"></a>משימה 4 - סקירת תוצאות המודל והסברים

הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים. כעת תוכל לעיין בהסברים על מודל הנטישה. למידע נוסף, ראה [סקירת מצב החיזוי ותוצאותיו](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>משימה 5 - יצירת פלח של לקוחות בסיכון גבוה לנטישה

הפעלת מודל הייצור יוצרת ישות חדשה שניתן לראות ב **נתונים** > **ישויות**.   

ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.

1.  עבור אל **פלחים**. בחר **חדש** ובחר **צור מתוך** > **בינה**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="יצירת פלח עם פלט המודל.":::

1. בחר את נקודת הקצה **OOBeCommerceChurnPrediction** והגדר את הפלח: 
   - שדה: ChurnScore
   - אופרטור: גדול מ
   - ערך: 0.6

כעת יש לך פלח שמתעדכן באופן דינמי ומזהה לקוחות בעלי סיכון נטישה גבוה.

למידע נוסף: [יצירה וניהול של פלחים](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
