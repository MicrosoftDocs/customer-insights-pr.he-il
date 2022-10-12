---
title: מדריך לדוגמה של חיזוי המלצות על מוצרים
description: השתמש במדריך לדוגמה זה כדי לנסות את המודל לחיזוי המלצות על מוצרים המוכן לשימוש.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610145"
---
# <a name="product-recommendation-prediction-sample-guide"></a>מדריך לדוגמה של חיזוי המלצות על מוצרים

מדרך זה מדריך אותך לאורך השבלים בדוגמה מקצה לקצה חיזוי המלצות על מוצרים באמצעות הנתונים לדוגמה. אנו ממליצים לנסות את החיזוי הזה [בסביבה חדשה](manage-environments.md).

## <a name="scenario"></a>תרחיש

Contoso היא חברה המייצרת קפה באיכות גבוהה ומכונות קפה. הם מוכרים את המוצרים דרך אתר האינטרנט שלהם Contoso Coffee. המטרה שלה היא להבין על אילו מוצרים עליה להמליץ ללקוחות החוזרים שלה. כשידועים מה לקוחות **עשויים לרכוש בסבירות גבוהה יותר** אפשר לחסוך במאמצי השיווק על-ידי התמקדות בפריטים ספציפיים.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.

## <a name="task-1---ingest-data"></a>משימה 1 - קליטת נתונים

עיין במאמרים [לגבי קליטת נתונים](data-sources.md) ו[התחברות למקור של Power Query ](connect-power-query.md). המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>קליטת נתוני לקוחות מפלטפורמת eCommerce

1. צור מקור נתונים של שאילתת Power Query בשם **eCommerce**, ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce: https://aka.ms/ciadclasscontacts.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **DateOfBirth**: תאריך
   - **CreatedOn**: תאריך/שעה/אזור

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המר את תאריך הלידה לתאריך.":::

1. בשדה **שם** בחלונית השמאלית, שנה את שם מקור נתונים שלך ל- **eCommerceContacts**.

1. **שמור** את מקור הנתונים.

### <a name="ingest-online-purchase-data"></a>קליטת נתוני רכישה מקוונים

1. הוסף ערכת נתונים נוספת לאותו מקור נתונים **eCommerce**. בחר שוב את המחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור נתוני רכישות מקוונות https://aka.ms/ciadclassonline.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **PurchasedOn**: תאריך/שעה
   - **TotalPrice**: מטבע

1. בשדה **שם** בחלונית הצדדית, שנה את שם מקור נתונים שלך משאילתה ל- **eCommercePurchases**.

1. **שמור** את מקור הנתונים.

### <a name="ingest-customer-data-from-loyalty-schema"></a>קליטת נתוני לקוחות מסכמת loyalty

1. צור מקור נתונים בשם **LoyaltyScheme**, ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור לקוחות נאמנים https://aka.ms/ciadclasscustomerloyalty.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **DateOfBirth**: תאריך
   - **RewardsPoints**: מספר שלם
   - **CreatedOn**: תאריך/שעה

1. בשדה **שם** בחלונית השמאלית, שנה את שם מקור נתונים שלך ל- **loyCustomers**.

1. **שמור** את מקור הנתונים.

## <a name="task-2---data-unification"></a>משימה 2 - איחוד נתונים

קרא את המאמר [על איחוד הנתונים](data-unification.md). המידע הבא מניח שאתה מכיר את תהליך איחוד הנתונים באופן כללי.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>משימה 3 - צור פעילות היסטוריית עסקאות

עיין במאמר [על פעילות הלקוחות](activities.md). המידע הבא מניח שאתה מכיר את תהליך יצירת פעילויות באופן כללי.

1. צור פעילות בשם **eCommercePurchases** באמצעות הישות *eCommercePurchases:eCommerce* והמפתח העיקרי שלה, **PurchaseId**.

1. צור קשר בין *eCommercePurchases:eCommerce* ו *eCommerceContacts:eCommerce* עם **ContactID** כמפתח זר לחיבור שתי הישויות.

1. בחר **TotalProce** עבור **EventActivity** ו **PurchasedOn** עבור **חותמת הזמן**.

1. בחר **SalesOrderLine** עבור **סוג הפעילות** ומפה באופן סמנטי את נתוני הפעילות.

1. הפעל את הפעילות.

## <a name="task-4---configure-product-recommendation-prediction"></a>משימה 4 - קביעת התצורה של חיזוי המלצות על מוצרים

לאחר מיקום פרופילי לקוחות מאוחדים ויצירת הפעילות, הפעל את החיזוי של המלצות על מוצרים.

1. עבור אל **בינה** > **חיזויים**.

1. בכרטיסיה **צור**, בחר **שימוש במודל** באריח **מודל המלצות על מוצרים (Preview)**.

1. בחר **תחילת העבודה**.

1. קרא למודל **OOB Product Recommendation Model Prediction** ולישות הפלט **OOBProductRecommendationModelPrediction**.

1. בחר **הבא**.

1. הגדרת העדפות מודל:
   - **מספר המוצרים**: **5** להגדרת מספר המוצרים שברצונך להמליץ ללקוחות שלך.
   - **רכישות חוזרות צפויות**: **כן** כדי לכלול בהמלצה מוצרים שנרכשו בעבר.
   - **חלון מבט לאחור:** **365 ימים** כדי להגדיר עד איזה נקודת זמן בעבר הדגם יבדוק לפני שימליץ שוב על מוצר.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="העדפות מודל עבור מודל ההמלצות על מוצרים.":::

1. בחר **הבא**.

1. בשלב **הוסף הסטוריית רכישה**, בחר **הוסף נתונים**.

1. בחר **SalesOrderLine** ואת הישות eCommercePurchases ובחר **הבא**. הנתונים הנדרשים מתמלאים אוטומטית מהפעילות. בחר **שמור** ולאחר מכן בחר **הבא**.

1. דלג על השלבים **הוסף מידע על המוצר** ועל **מסנני מוצרים** כי אין לנו מידע על המוצר.

1. בשלב **עדכוני נתונים**, בחר **חודשי** עבור לוח הזמנים של המודל.

1. בחר **הבא**.

1. לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**.

## <a name="task-5---review-model-results-and-explanations"></a>משימה 5 - סקירת תוצאות המודל והסברים

הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים. עיין [בהסברים אודות מודל ההמלצה על מוצרים](predict-transactional-churn.md#view-prediction-results)..

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>משימה 6 - יצירת פלח עבור מוצרים שנרכשים בתדירות גבוהה

הפעלת המודל יוצרת ישות חדשה, שמופיעה תחת **נתונים** > **ישויות**. ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.

1. בדף התוצאות, בחר **צור פלח**.

1. צור כלל באמצעות היישות **OOBProductRecommendationModelPrediction** והגדר את הפלח:
   - **שדה**:‏ ProductID
   - **ערך**: בחר את שלושת מזהי המוצר המובילים

1. בחר **שמור** ו **הפעל** את הפלח.

כעת יש לך פלח שמתעדכן באופן דינמי ומזהה את הלקוחות שעשויים להיות מעוניינים לרכוש את חמשת המוצרים המומלצים ביותר. למידע נוסף: [יצירה וניהול של פלחים](segments.md).

> [!TIP]
> אתה יכול גם ליצור פלח עבור מודל חיזוי מהדף **פלחים** על ידי בחירה ב **חדש** ובחירה באפשרות **צור מ** > **בינה**. למידע נוסף, ראה [יצירת פלח חדש באמצעות פלחים מהירים](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
