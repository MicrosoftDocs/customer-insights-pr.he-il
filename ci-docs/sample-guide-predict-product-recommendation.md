---
title: מדריך לדוגמה של חיזוי המלצות על מוצרים
description: השתמש במדריך לדוגמה זה כדי לנסות את המודל לחיזוי המלצות על מוצרים המוכן לשימוש.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762687"
---
# <a name="product-recommendation-prediction-sample-guide"></a>מדריך לדוגמה של חיזוי המלצות על מוצרים

אנו ננחה אותך ונדגים דוגמה מקצה לקצה של חיזוי המלצות על מוצרים באמצעות הנתונים לדוגמה המפורטים להלן.

## <a name="scenario"></a>תרחיש

Contoso היא חברה המייצרת קפה איכותי ומכונות קפה, שאותם היא מוכרת דרך האתר שלה Contoso Coffee. המטרה שלה היא להבין על אילו מוצרים עליה להמליץ ללקוחות החוזרים שלה. הידיעה מה לקוחות **עשויים לרכוש בסבירות גבוהה יותר** יכולה לעזור לה לחסוך במאמצי השיווק על-ידי התמקדות בפריטים ספציפיים.

## <a name="prerequisites"></a>דרישות מוקדמות

- לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.
- אנו ממליצים ליישם את השלבים הבאים [בסביבה חדשה](manage-environments.md).

## <a name="task-1---ingest-data"></a>משימה 1 - קליטת נתונים

עיין במאמרים [לגבי קליטת נתונים](data-sources.md) ו- [ייבוא מקורות נתונים באמצעות מחברי Power Query ](connect-power-query.md) באופן ספציפי. המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>קליטת נתוני לקוחות מפלטפורמת eCommerce

1. צור מקור נתונים בשם **eCommerce**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce : [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **DateOfBirth**: תאריך
   - **CreatedOn**: תאריך/שעה/אזור

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המר את תאריך הלידה לתאריך.":::

1. בשדה 'שם' בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommerceContacts**

1. **שמור** את מקור הנתונים.

### <a name="ingest-online-purchase-data"></a>קליטת נתוני רכישה מקוונים

1. הוסף ערכת נתונים נוספת לאותו מקור נתונים **eCommerce**. בחר שוב את המחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור נתוני **רכישות מקוונות** [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **PurchasedOn**: תאריך/שעה
   - **TotalPrice**: מטבע

1. בשדה **שם** בחלונית הצדדית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommercePurchases**.

1. **שמור** את מקור הנתונים.

### <a name="ingest-customer-data-from-loyalty-schema"></a>קליטת נתוני לקוחות מסכמת loyalty

1. צור מקור נתונים בשם **LoyaltyScheme**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **DateOfBirth**: תאריך
   - **RewardsPoints**: מספר שלם
   - **CreatedOn**: תאריך/שעה

1. בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **loyCustomers**.

1. **שמור** את מקור הנתונים.

## <a name="task-2---data-unification"></a>משימה 2 - איחוד נתונים

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>משימה 3 - קביעת התצורה של חיזוי המלצות על מוצרים

באמצעות פרופיל לקוח מאוחד אנו יכולים כעת להפעיל את החיזוי של המלצות על מוצרים.

1. עבור אל **בינה** > **חיזוי** ובחר **המלצות על מוצרים**.

1. בחר **תחילת העבודה**.

1. קרא למודל **OOB Product Recommendation Model Prediction** ולישות הפלט **OOBProductRecommendationModelPrediction**.

1. הגדר שלושה תנאים עבור המודל:

   - **מספר המוצרים**: הגדר ערך זה ל- **5**. הגדרה זו מגדירה על כמה מוצרים ברצונך להמליץ ללקוחות שלך.

   - **‏‫רכישות חוזרות צפויות**: בחר **כן** כדי לציין שברצונך לכלול בהמלצה מוצרים שהלקוחות רכשו בעבר.

   - **חלון מבט לאחור:** בחר לפחות **365 יום**. הגדרה זו מגדירה עד איזו נקודת זמן בעבר המודל יבחן את פעילות הלקוח כדי להשתמש בה כקלט בהמלצות שלו.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="העדפות מודל עבור מודל ההמלצות על מוצרים.":::

1. בשלב **הוסף נתונים נדרשים**, בחר **הוסף נתונים**.

1. בחלונית **הוסף נתונים**, בחר את **SalesOrderLine** כישות של היסטוריית הרכישה. בשלב זה, סביר להניח שהוא עדיין לא מוגדר. פתח את הקישור בחלונית כדי ליצור את הפעילות לפי השלבים הבאים:
   1. הזן **שם הפעילות** ובחר *eCommercePurchases:eCommerce* בתור **ישות פעילות**. **המפתח הראשי** הוא *PurchaseId*.
   1. הגדר ותן שם לקשר אל *eCommerceContacts:eCommerce entity* ובחר **ContactId** בתור המפתח הזר.
   1. עבור איחוד פעילות, הגדר **פעילות אירוע** בתור *TotalPrice* וחותמת זמן של *PurchasedOn*. אתה יכול לציין שדות נוספים כפי שמפורט [בפעילות לקוחות](activities.md).
   1. עבור **סוג פעילות**, בחר *SalesOrderLine*. מפה את השדות הבאים עבור שדות הפעילות:
      - מזהה שורת הזמנה: PurchaseId
      - מזהה הזמנה: PurchaseId
      - נתוני הזמנה: PurchasedOn
      - מזהה מוצר: ProductId
      - סכום: TotalPrice
   1. סקור וסיים את הפעילות לפני שתחזור לתצורת המודל.

1. חזרה בשלב **בחר פעילויות**, בחר את הפעילות החדשה שנוצרה במקטע **פעילויות**. בחר **הבא**, מיפוי התכונות כבר מולא. בחר **שמור**.

1. במדריך לדוגמה זה, אנו מדלגים על **הוסף מידע על המוצר** ועל **מסנני מוצרים** כי אין לנו מידע על המוצר.

1. בשלב **עדכוני נתונים**, קבע את לוח הזמנים של המודל.

   המודל צריך לעבור הדרכה שוטפת כדי ללמוד דפוסים חדשים בעת קליטת נתונים חדשים. עבור דוגמה זו, בחר **חודשי**.

1. לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**. זה ייקח כמה דקות להפעיל את המודל בפעם הראשונה.

## <a name="task-4---review-model-results-and-explanations"></a>משימה 4 - סקירת תוצאות המודל והסברים

הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים. כעת תוכל לעיין בהסברים אודות מודל ההמלצות על מוצרים. למידע נוסף, ראה [סקירת מצב החיזוי ותוצאותיו](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>משימה 5 - יצירת פלח עבור מוצרים שנרכשים בתדירות גבוהה

הפעלת מודל הייצור יוצרת ישות חדשה שניתן לראות ב **נתונים** > **ישויות**.

ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.

1. עבור אל **פלחים**. בחר **חדש** ובחר **צור מתוך בינה**.

   ![יצירת פלח עם פלט המודל.](media/segment-intelligence.png)

1. בחר את נקודת הקצה **OOBProductRecommendationModelPrediction** והגדר את הפלח:

   - שדה: מזהה מוצר
   - ערך: בחר את שלושת מזהי המוצר המובילים

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="צור פלח מתוצאות המודל.":::

כעת יש לך פלח שמתעדכן באופן דינמי ומזהה את הלקוחות שעשויים להיות מעוניינים לרכוש את שלושת המוצרים המומלצים ביותר.

למידע נוסף: [יצירה וניהול של פלחים](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
