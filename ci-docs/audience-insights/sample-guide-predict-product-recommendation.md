---
title: מדריך לדוגמה של חיזוי המלצות על מוצרים
description: השתמש במדריך לדוגמה זה כדי לנסות את המודל לחיזוי המלצות על מוצרים המוכן לשימוש.
ms.date: 02/10/2021
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ee873d9b7caa5f891cb2d5b8c665dec90ad0e59
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270496"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a>מדריך לדוגמה של חיזוי המלצות על מוצרים (Preview)

אנו ננחה אותך ונדגים דוגמה מקצה לקצה של חיזוי המלצות על מוצרים באמצעות הנתונים לדוגמה המפורטים להלן.

## <a name="scenario"></a>תרחיש

Contoso היא חברה המייצרת קפה איכותי ומכונות קפה, שאותם היא מוכרת דרך האתר שלה Contoso Coffee. המטרה שלה היא להבין על אילו מוצרים עליה להמליץ ללקוחות החוזרים שלה. הידיעה מה לקוחות **עשויים לרכוש בסבירות גבוהה יותר** יכולה לעזור לה לחסוך במאמצי השיווק על-ידי התמקדות בפריטים ספציפיים.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המר את תאריך הלידה לתאריך.":::

5. בשדה 'שם' בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommerceContacts**

6. **שמור** את מקור הנתונים.

### <a name="ingest-online-purchase-data"></a>קליטת נתוני רכישה מקוונים

1. הוסף ערכת נתונים נוספת לאותו מקור נתונים **eCommerce**. בחר שוב את המחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור נתוני **רכישות מקוונות** https://aka.ms/ciadclassonline.

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **PurchasedOn**: תאריך/שעה
   - **TotalPrice**: מטבע

1. בשדה **שם** בחלונית הצדדית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommercePurchases**.

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

2. בחר את הישויות המייצגות את פרופיל הלקוח – **eCommerceContacts** ו- **loyCustomers**.

   ![איחוד מקורות הנתונים ecommerce ו- loyalty.](media/unify-ecommerce-loyalty.png)

3. בחר **ContactId** כמפתח העיקרי עבור **eCommerceContacts** ו- **LoyaltyID** כמפתח העיקרי עבור **loyCustomers**.

   ![איחוד LoyaltyId כמפתח ראשי.](media/unify-loyaltyid.png)

### <a name="match"></a>התאמה

1. עבור אל הכרטיסיה **התאמה** ובחר **הגדר סדר**.

2. ברשימה הנפתחת **ראשי**, בחר **eCommerceContacts : eCommerce** כמקור הראשי וכלול את כל הרשומות.

3. ברשימה הנפתחת **ישות 2**, בחר **loyCustomers : LoyaltyScheme** וכלול את כל הרשומות.

   ![איחוד התאמה של eCommerce ו- Loyalty.](media/unify-match-order.png)

4. בחר **צור כלל חדש**

5. הוסף את התנאי הראשון שלך באמצעות FullName.

   - עבור eCommerceContacts בחר **FullName** ברשימה הנפתחת.
   - עבור loyCustomers בחר **FullName** ברשימה הנפתחת.
   - בחר את הרשימה הנפתחת **נרמל** ובחר **סוג (טלפון, שם, כתובת, ...)**.
   - הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.

6. הזן את השם **FullName, Email** עבור הכלל החדש.

   - הוסף תנאי שני לכתובת הדואר האלקטרוני על-ידי בחירה **הוסף תנאי**
   - לישות eCommerceContacts, בחר **דואר** ברשימה הנפתחת.
   - לישות loyCustomers, בחר **דואר** ברשימה הנפתחת.
   - השאר את השדה 'נרמל' ריק.
   - הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.

   ![איחוד כלל התאמה עבור שם ודואר אלקטרוני.](media/unify-match-rule.png)

7. בחר **שמור** ו **הפעל**.

### <a name="merge"></a>מזג

1. עבור לכרטיסיה **מיזוג**.

1. ב- **ContactId** עבור הישות **loyCustomers**, שנה את שם התצוגה ל- **ContactIdLOYALTY** כדי להבחין בינה לבין מספרי זהות אחרים שנקלטו.

   ![שינוי שם ל- contactid מ- loyalty id.](media/unify-merge-contactid.png)

1. בחר **שמור** ו **הפעל** כדי להתחיל בתהליך המיזוג.

## <a name="task-3---configure-product-recommendation-prediction"></a>משימה 3 - קביעת התצורה של חיזוי המלצות על מוצרים

מכיוון שפרופילי הלקוחות המאוחדים קיימים, אנו יכולים כעת להפעיל את חיזוי נטישת המנויים.

1. עבור אל **בינה** > **חיזוי** ובחר **המלצות על מוצרים**.

1. בחר **תחילת העבודה**.

1. קרא למודל **OOB Product Recommendation Model Prediction** ולישות הפלט **OOBProductRecommendationModelPrediction**.

1. הגדר שלושה תנאים עבור המודל:

   - **מספר המוצרים**: הגדר ערך זה ל- **5**. הגדרה זו מגדירה על כמה מוצרים ברצונך להמליץ ללקוחות שלך.

   - **האם להציע מוצרים שהלקוחות רכשו לאחרונה?**: בחר **כן** כדי לציין שברצונך לכלול מוצרים בהמלצות שהלקוחות שלך רכשו בעבר.

   - **חלון מבט לאחור:** בחר לפחות **365 יום**. הגדרה זו מגדירה עד איזו נקודת זמן בעבר המודל יבחן את פעילות הלקוח כדי להשתמש בה כקלט בהמלצות שלו.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="העדפות מודל עבור מודל ההמלצות על מוצרים.":::

1. בחר **נתונים נדרשים** ובחר **הוסף נתונים** עבור היסטוריית רכישות.

1. הוסף את הישות **eCommercePurchases : eCommerce** ומפה את השדות מ- eCommerce לשדות המתאימים הנדרשים על-ידי המודל.

1. הצטרף לישות **eCommercePurchases: eCommerce** עם **eCommerceContacts : eCommerce**.

   ![הצטרף לישויות eCommerce.](media/model-purchase-join.png)

1. בחר **הבא** כדי להגדיר את לוח הזמנים של המודל.

   המודל צריך לעבור הדרכה שוטפת כדי ללמוד דפוסים חדשים בעת קליטת נתונים חדשים. עבור דוגמה זו, בחר **חודשי**.

1. לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**.


## <a name="task-4---review-model-results-and-explanations"></a>משימה 4 - סקירת תוצאות המודל והסברים

הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים. כעת תוכל לעיין בהסברים אודות מודל ההמלצות על מוצרים. למידע נוסף, ראה [סקירת מצב החיזוי ותוצאותיו](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>משימה 5 - יצירת פלח עבור מוצרים שנרכשים בתדירות גבוהה

הפעלת מודל הייצור יוצרת ישות חדשה שניתן לראות ב **נתונים** > **ישויות**.

ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.

1. עבור אל **פלחים**. בחר **חדש** ובחר **צור מתוך** > **בינה**.

   ![יצירת פלח עם פלט המודל.](media/segment-intelligence.png)

1. בחר את נקודת הקצה **OOBProductRecommendationModelPrediction** והגדר את הפלח:

   - שדה: מזהה מוצר
   - אופרטור: Value
   - ערך: בחר את שלושת מזהי המוצר המובילים

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="צור פלח מתוצאות המודל.":::

כעת יש לך פלח שעודכן באופן דינמי אשר מזהה את הלקוחות בעלי המוכנות הגדולה יותר לרכוש את שלושת המוצרים המומלצים ביותר 

למידע נוסף: [יצירה וניהול של פלחים](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]