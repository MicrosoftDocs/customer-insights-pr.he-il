---
title: מדריך לדוגמה לחיזוי נטישה של עסקאות
description: השתמש במדריך לדוגמה זה כדי לנסות את המודל לחיזוי נטישה של עסקאות המוכן לשימוש.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306121"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a>מדריך לדוגמה לחיזוי נטישה של עסקאות (מהדורת Preview)

מדריך זה ינחה אותך וידגים דוגמה מקצה לקצה של חיזוי נטישה של עסקאות ב- Customer Insights באמצעות הנתונים המפורטים להלן. כל הנתונים הנמצאים בשימוש במדריך זה אינם נתוני לקוחות אמיתיים והם חלק מערכת הנתונים של Contoso שנמצא בסביבה *לדוגמה* במנוי Customer Insights שלך.

## <a name="scenario"></a>תרחיש

Contoso היא חברה שמייצרת קפה ומכונות קפה באיכות גבוהה, ומוכרת אותם באמצעות אתר האינטרנט Contoso Coffee. מטרת החברה היא לדעת אילו לקוחות, שבדרך כלל רוכשים את המוצרים שלהם על בסיס קבוע, יפסיקו להיות לקוחות פעילים ב- 60 הימים הקרובים. הידיעה מי מהלקוחות **עשוי לנטוש**, יכולה לעזור לה לחסוך מאמצים שיווקיים על-ידי התמקדות בשימור הלקוחות.

## <a name="prerequisites"></a>דרישות מוקדמות

- לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.
- אנו ממליצים ליישם את השלבים הבאים [בסביבה חדשה](manage-environments.md).

## <a name="task-1---ingest-data"></a>משימה 1 - קליטת נתונים

עיין בעיקר במאמרים [אודות קליטת נתונים](data-sources.md) ו[ייבוא מקורות נתונים באמצעות מחברים של Power Query](connect-power-query.md). המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>קליטת נתוני לקוחות מפלטפורמת eCommerce

1. צור מקור נתונים בשם **eCommerce**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscontacts.

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:

   - **DateOfBirth**: תאריך
   - **CreatedOn**: תאריך/שעה/אזור

   [!div class="mx-imgBorder"]
   ![המרת תאריך הלידה לתאריך](media/ecommerce-dob-date.PNG "המרת תאריך הלידה לתאריך")

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

לאחר קליטת הנתונים אנו מתחילים כעת בתהליך **מיפוי, התאמה, מיזוג** כדי ליצור פרופיל לקוח מאוחד. לקבלת מידע נוסף, ראה [איחוד נתונים](data-unification.md).

### <a name="map"></a>מיפוי

1. לאחר קליטת הנתונים, מפה את אנשי הקשר מנתוני eCommerce ו- Loyalty לסוגי נתונים נפוצים. עבור אל **נתונים** > **איחוד** > **מיפוי**.

1. בחר את הישויות המייצגות את פרופיל הלקוח – **eCommerceContacts** ו- **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="איחוד מקורות הנתונים ecommerce ו- loyalty.":::

1. בחר **ContactId** כמפתח העיקרי עבור **eCommerceContacts** ו- **LoyaltyID** כמפתח העיקרי עבור **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="איחוד LoyaltyId כמפתח ראשי.":::

### <a name="match"></a>התאמה

1. עבור אל הכרטיסיה **התאמה** ובחר **הגדר סדר**.

1. בתפריט הנפתח **ראשי**, בחר **eCommerceContacts : ‏eCommerceContacts** כמקור העיקרי וכלול את כל הרשומות.

1. ברשימה הנפתחת **ישות 2**, בחר **LoyaltyScheme : ‏loyCustomers** וכלול את כל הרשומות.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="איחוד התאמה של eCommerce ו- Loyalty.":::

1. בחר **צור כלל חדש**

1. הוסף את התנאי הראשון שלך באמצעות FullName.

   * עבור eCommerceContacts בחר **FullName** בתפריט הנפתח.
   * עבור loyCustomers בחר **FullName** בתפריט הנפתח.
   * בחר את הרשימה הנפתחת **נרמל** ובחר **סוג (טלפון, שם, כתובת, ...)**.
   * הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.

1. הזן את השם **FullName, Email** עבור הכלל החדש.

   * הוסף תנאי שני לכתובת הדואר האלקטרוני על-ידי בחירה **הוסף תנאי**
   * עבור הישות eCommerceContacts, בחר **דואר אלקטרוני** בתפריט הנפתח.
   * עבור הישות loyCustomers, בחר **דואר אלקטרוני** בתפריט הנפתח. 
   * השאר את השדה 'נרמל' ריק. 
   * הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="איחוד כלל התאמה עבור שם ודואר אלקטרוני.":::

7. בחר **שמור** ו **הפעל**.

### <a name="merge"></a>מזג

1. עבור לכרטיסיה **מיזוג**.

1. ב- **ContactId** עבור הישות **loyCustomers**, שנה את שם התצוגה ל- **ContactIdLOYALTY** כדי להבחין בינה לבין מספרי זהות אחרים שנקלטו.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="שינוי שם ל- contactid מ- loyalty id.":::

1. בחר **שמור** ו **הפעל** כדי להתחיל בתהליך המיזוג.



## <a name="task-3---configure-transaction-churn-prediction"></a>משימה 3 - הגדר את חיזוי נטישת העסקאות

מכיוון שפרופילי הלקוחות המאוחדים קיימים, אנו יכולים כעת להפעיל את חיזוי נטישת המנויים. לקבלת השלבים המפורטים, עיין במאמר [חיזוי נטישה של מנויים (מהדורת Preview)](predict-subscription-churn.md). 

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

הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים. כעת תוכל לעיין בהסברים אודות מודל נטישת המנויים. למידע נוסף, ראה [סקירת מצב החיזוי ותוצאותיו](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>משימה 5 - יצירת פלח של לקוחות בסיכון גבוה לנטישה

הפעלת מודל הייצור יוצרת ישות חדשה שניתן לראות ב **נתונים** > **ישויות**.   

ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.

1.  עבור אל **פלחים**. בחר **חדש** ובחר **צור מתוך** > **בינה**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="יצירת פלח עם פלט המודל.":::

1. בחר את נקודת הקצה **OOBSubscriptionChurnPrediction** והגדר את הפלח: 
   - שדה: ChurnScore
   - אופרטור: גדול מ
   - ערך: 0.6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="הגדרת פלח של נטישת מנויים‬.":::

כעת יש לך פלח שמתעדכן באופן דינאמי, המזהה לקוחות בסיכון גבוה לנטישה עבור עסק זה של מנויים.

למידע נוסף: [יצירה וניהול של פלחים](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]