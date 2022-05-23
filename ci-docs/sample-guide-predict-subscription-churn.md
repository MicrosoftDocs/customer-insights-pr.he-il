---
title: מדריך לדוגמה לחיזוי של נטישת מנויים
description: השתמש במדריך לדוגמה זה כדי לנסות את מודל החיזוי של נטישת מנויים המוכן לשימוש.
ms.date: 03/31/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 5a8eeafecacef3d0bb4a798b698cf490423ca98d
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741412"
---
# <a name="subscription-churn-prediction-sample-guide"></a>מדריך לדוגמה לחיזוי של נטישת מנויים

אנו ננחה אותך ונדגים דוגמה מקצה לקצה של חיזוי של נטישת מנויים באמצעות הנתונים לדוגמה המפורטים להלן. 

## <a name="scenario"></a>תרחיש

Contoso היא חברה המייצרת קפה איכותי ומכונות קפה, שאותם היא מוכרת דרך האתר שלה Contoso Coffee. לאחרונה הקימה החברה עסק של מנויים עבור הלקוחות שלה, המספק להם קפה על בסיס קבוע. מטרתה היא להבין אילו לקוחות הרשומים כמנויים עשויים לבטל את המנוי שלהם בחודשים הקרובים. הידיעה מי מהלקוחות **עשוי לנטוש**, יכולה לעזור לה לחסוך מאמצים שיווקיים על-ידי התמקדות בשימור הלקוחות.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המר את תאריך הלידה לתאריך.":::

1. בשדה **שם** בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommerceContacts**

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

### <a name="ingest-subscription-information"></a>קליטת פרטי מנוי

1. צור מקור נתונים בשם **SubscriptionHistory**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadchurnsubscriptionhistory.

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:

   - **SubscriptioID**: מספר שלם
   - **SubscriptionAmount**: מטבע
   - **SubscriptionEndDate**: תאריך/שעה
   - **SubscriptionStartDate**: תאריך/שעה
   - **TransactionDate**: תאריך/שעה
   - **IsRecurring**:‏ True/False
   - **Is_auto_renew**: ‏True/False
   - **RecurringFrequencyInMonths**: מספר שלם

1. בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **SubscriptionHistory**.

1. שמור את מקור הנתונים.

### <a name="ingest-customer-data-from-website-reviews"></a>קלוט נתוני לקוחות מביקורות של אתרים

1. צור מקור נתונים בשם **Website**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasswebsite.

1. בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:

   - **ReviewRating**: מספר שלם
   - **ReviewDate**: תאריך

1. בשדה 'שם' בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **webReviews**.

## <a name="task-2---data-unification"></a>משימה 2 - איחוד נתונים

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-the-subscription-churn-prediction"></a>משימה 3 - הגדר את חיזוי נטישת המנויים

מכיוון שפרופילי הלקוחות המאוחדים קיימים, אנו יכולים כעת להפעיל את חיזוי נטישת המנויים. לשלבים מפורטים, ראה את המאמר [חיזוי נטישת מנויים](predict-subscription-churn.md). 

1. עבור אל **בינה** > **גילוי** ובחר להשתמש ב **מודל נטישת לקוחות**.

1. בחר את האפשרות **מנוי** ובחר **תחילת העבודה**.

1. תן שם למודל **OOB Subscription Churn Prediction** ולישות הפלט **OOBSubscriptionChurnPrediction**.

1. הגדר שני תנאים עבור מודל הנטישה:

   * **ימים מסיום המנוי**: **לפחות 60** ימים. אם לקוח אינו מחדש את המנוי בפרק זמן זה לאחר תום המנוי שלו, הוא נחשב כלקוח שנטש. 

   * **הגדרת נטישה**: **לפחות 93** ימים. משך הזמן שבמהלכו מנבא המודל אילו לקוחות עשויים לנטוש. ככל שתבחן את העתיד הרחוק יותר, כך יהיו התוצאות מדויקות פחות.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="בחר את מנופי המודל 'חלון חיזוי' ו'הגדרת נטישה'.":::

1. בחר **הוסף נתונים נדרשים** ובחר **הוסף נתונים** להיסטוריית המנויים.

1. הוסף את הישות **Subscription: SubscriptionHistory** ומפה את השדות מ- eCommerce לשדות המתאימים הנדרשים על-ידי המודל.

1. הצטרף לישות **Subscription : SubscriptionHistory** עם **eCommerceContacts : eCommerce**, תן שם לקשר **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="הצטרף לישויות eCommerce.":::

1. תחת '‏‫פעילויות של לקוחות‬', הוסף את הישות **webReviews : Website** ומפה את השדות מ- webReviews לשדות המתאימים הנדרשים על-ידי המודל. 
   - מפתח ראשי: ReviewId
   - חותמת זמן: ReviewDate
   - אירוע: ReviewRating

1. הגדר פעילות עבור ביקורות של אתרים.‬ בחר את הפעילות **סקירה** והצטרף לישות **webReviews : Website** עם **eCommerceContacts : eCommerce**.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]