---
title: מדריך לדוגמה לחיזוי של נטישת מנויים
description: השתמש במדריך לדוגמה זה כדי לנסות את מודל החיזוי של נטישת מנויים המוכן לשימוש.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: e2360c707bcbdfa64482f06f0a0cd0783a377b4fd79620ffd3cc1c9c6cad9ed3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7029584"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>מדריך לדוגמה לחיזוי של נטישת מנויים (מהדורת Preview)

אנו ננחה אותך ונדגים דוגמה מקצה לקצה של חיזוי של נטישת מנויים באמצעות הנתונים לדוגמה המפורטים להלן. 

## <a name="scenario"></a>תרחיש

Contoso היא חברה שמייצרת קפה ומכונות קפה באיכות גבוהה, ומוכרת אותם באמצעות אתר האינטרנט Contoso Coffee. לאחרונה הקימה החברה עסק של מנויים עבור הלקוחות שלה, המספק להם קפה על בסיס קבוע. מטרתה היא להבין אילו לקוחות הרשומים כמנויים עשויים לבטל את המנוי שלהם בחודשים הקרובים. הידיעה מי מהלקוחות **עשוי לנטוש**, יכולה לעזור לה לחסוך מאמצים שיווקיים על-ידי התמקדות בשימור הלקוחות.

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


## <a name="task-3---configure-the-subscription-churn-prediction"></a>משימה 3 - הגדר את חיזוי נטישת המנויים

מכיוון שפרופילי הלקוחות המאוחדים קיימים, אנו יכולים כעת להפעיל את חיזוי נטישת המנויים. לקבלת השלבים המפורטים, עיין במאמר [חיזוי נטישה של מנויים (מהדורת Preview)](predict-subscription-churn.md). 

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


[!INCLUDE[footer-include](../includes/footer-banner.md)]