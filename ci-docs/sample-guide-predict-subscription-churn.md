---
title: מדריך לדוגמה לחיזוי של נטישת מנויים
description: השתמש במדריך לדוגמה זה כדי לנסות את מודל החיזוי של נטישת מנויים המוכן לשימוש.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610007"
---
# <a name="subscription-churn-prediction-sample-guide"></a>מדריך לדוגמה לחיזוי של נטישת מנויים

מדריך זה ינחה אותך בדוגמה מקצה לקצה של חיזוי נטישה של מינוים באמצעות נתונים לדוגמה. אנו ממליצים לנסות את החיזוי הזה [בסביבה חדשה](manage-environments.md).

## <a name="scenario"></a>תרחיש

Contoso היא חברה המייצרת קפה באיכות גבוהה ומכונות קפה. הם מוכרים את המוצרים דרך אתר האינטרנט שלהם Contoso Coffee. לאחרונה הקימה החברה עסק של מנויים עבור הלקוחות שלה, המספק להם קפה על בסיס קבוע. מטרתה היא להבין אילו לקוחות הרשומים כמנויים עשויים לבטל את המנוי שלהם בחודשים הקרובים. הידיעה מי מהלקוחות **עשוי לנטוש** יכולה לעזור לה לחסוך מאמצים שיווקיים על-ידי התמקדות בשימור הלקוחות.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.

## <a name="task-1---ingest-data"></a>משימה 1 - קליטת נתונים

עיין במאמרים [לגבי קליטת נתונים](data-sources.md) ו[התחברות למקור של Power Query ](connect-power-query.md). המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>קליטת נתוני לקוחות מפלטפורמת eCommerce

1. צור מקור נתונים של שאילתת Power Query בשם **eCommerce**, ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscontacts.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **DateOfBirth**: תאריך
   - **CreatedOn**: תאריך/שעה/אזור

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המר את תאריך הלידה לתאריך.":::

1. בשדה **שם** בחלונית השמאלית, שנה את שם מקור נתונים שלך ל- **eCommerceContacts**

1. שמור את מקור הנתונים.

### <a name="ingest-customer-data-from-loyalty-schema"></a>קליטת נתוני לקוחות מסכמת loyalty

1. צור מקור נתונים בשם **LoyaltyScheme**, ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור לקוחות במועדון הלקוחות https://aka.ms/ciadclasscustomerloyalty.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **DateOfBirth**: תאריך
   - **RewardsPoints**: מספר שלם
   - **CreatedOn**: תאריך/שעה

1. בשדה **שם** בחלונית השמאלית, שנה את שם מקור נתונים שלך ל- **loyCustomers**.

1. שמור את מקור הנתונים.

### <a name="ingest-subscription-information"></a>קליטת פרטי מנוי

1. צור מקור נתונים בשם **SubscriptionHistory**, ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור מינוים https://aka.ms/ciadchurnsubscriptionhistory.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **SubscriptioID**: מספר שלם
   - **SubscriptionAmount**: מטבע
   - **SubscriptionEndDate**: תאריך/שעה
   - **SubscriptionStartDate**: תאריך/שעה
   - **TransactionDate**: תאריך/שעה
   - **IsRecurring**:‏ True/False
   - **Is_auto_renew**: ‏True/False
   - **RecurringFrequencyInMonths**: מספר שלם

1. בשדה **שם** בחלונית השמאלית, שנה את שם מקור הנתונים  ל **SubscriptionHistory**.

1. שמור את מקור הנתונים.

### <a name="ingest-customer-data-from-website-reviews"></a>קלוט נתוני לקוחות מביקורות של אתרים

1. צור מקור נתונים בשם **אתר אינטרנט**, ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL לביקורת של אתר האינטרנט https://aka.ms/ciadclasswebsite.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:
   - **ReviewRating**: מספר שלם
   - **ReviewDate**: תאריך

1. בשדה **שם** בחלונית השמאלית, שנה את שם מקור הנתונים  ל **webReviews**.

## <a name="task-2---data-unification"></a>משימה 2 - איחוד נתונים

קרא את המאמר [על איחוד הנתונים](data-unification.md). המידע הבא מניח שאתה מכיר את תהליך איחוד הנתונים באופן כללי.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>משימה 3 - צור פעילות היסטוריית עסקאות

עיין במאמר [על פעילות הלקוחות](activities.md). המידע הבא מניח שאתה מכיר את תהליך יצירת פעילויות באופן כללי.

1. צור פעילות בשם **SubscriptionHistory** באמצעות הישות *מינוי* והמפתח העיקרי שלה, **CustomerId**.

1. צור קשר בין *SubscriptionHistory:Subscription* ו *eCommerceContacts:eCommerce* עם **ContactID** כמפתח זר לחיבור שתי הישויות.

1. בחר **SubscriptionType** עבור **EventActivity** ו **SubscriptionEndDate** עבור **חותמת הזמן**.

1. בחר **מינוי** עבור **סוג הפעילות** ומפה באופן סמנטי את נתוני הפעילות.

1. הפעל את הפעילות.

1. הוסף פעילות נוספת ומפה את שמות השדות שלה לשדות המתאימים:
   - ישות פעילות לקוחות: ביקורות: אתר אינטרנט
   - מפתח ראשי: Website.Reviews.ReviewId
   - חותמת זמן: Website.Reviews.ReviewDate
   - אירוע (שם פעילות): Website.Reviews.ActivityTypeDisplay
   - פרטים (סכום או ערך): Website.Reviews.ReviewRating

1. הפעל את הפעילות.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>משימה 4 - הגדר את חיזוי נטישת המנויים

מכיוון שפרופילי הלקוחות המאוחדים קיימים והפעילות נוצרה, הפעל את חיזוי נטישת המנויים. לשלבים מפורטים, ראה [חיזוי נטישת מנויים](predict-subscription-churn.md).

1. עבור אל **בינה** > **חיזויים**.

1. בכרטיסיה **צור**, בחר **שימוש במודל** באריח **מודל נטישת לקוחות**.

1. בחר **מינוי** עבור סוג הנטישה ולאחר מכן **תחילת העבודה**.

1. תן שם למודל **OOB Subscription Churn Prediction** ולישות הפלט **OOBSubscriptionChurnPrediction**.

1. הגדרת העדפות מודל:
   - **ימים מאז שהסתיים המנוי**: **60** ימים כדי לציין שלקוח נחשב כנוטש אם הוא לא יחדש את המנוי בתקופה זו לאחר סיום המנוי.
   - **ימים בעתיד שיש לבדוק כדי לחזות נטישה**: **93** ימים, שהוא משך הזמן שבו המודל חוזה אילו לקוחות עלולים לנטוש. ככל שתבחן את העתיד הרחוק יותר, כך יהיו התוצאות מדויקות פחות.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="בחר את העדפות המודל והגדרת הנטישה.":::

1. בחר **הבא**.

1. בשלב **נתונים נדרשים**, בחר **הוסף נתונים** כדי לספק את נתוני היסטוריית המינוי.

1. בחר **מינוּי** ואת הישות SubscriptionHistory ובחר **הבא**. הנתונים הנדרשים מתמלאים אוטומטית מהפעילות. בחר **Save**.

1. תחת 'פעילויות לקוח' בחר **הוסף נתונים**.

1. עבור דוגמה זו, הוסף את פעילות ביקורת באינטרנט.

1. בחר **הבא**.

1. בשלב **עדכוני נתונים**, בחר **חודשי** עבור לוח הזמנים של המודל.

1. לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**.

## <a name="task-5---review-model-results-and-explanations"></a>משימה 5 - סקירת תוצאות המודל והסברים

הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים. כעיין בהסברים על מודל נטישת המינוים. למידע נוסף, ראה [סקירת תוצרות החיזוי](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>משימה 6 - יצירת פלח של לקוחות בסיכון גבוה לנטישה

הפעלת המודל יוצרת ישות חדשה, שמופיעה תחת **נתונים** > **ישויות**. ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.

1. בדף התוצאות, בחר **צור פלח**.

1. צור כלל באמצעות היישות **OOBSubscriptionChurnPrediction** והגדר את הפלח:
   - **שדה**: ChurnScore
   - **אופרטור**: גדול מ
   - **ערך**:‏ 0.6

1. בחר **שמור** ו **הפעל** את הפלח.

כעת יש לך פלח שמתעדכן באופן דינאמי, המזהה לקוחות בסיכון גבוה לנטישה עבור עסק זה של מנויים. למידע נוסף: [יצירה וניהול של פלחים](segments.md).

> [!TIP]
> אתה יכול גם ליצור פלח עבור מודל חיזוי מהדף **פלחים** על ידי בחירה ב **חדש** ובחירה באפשרות **צור מ** > **בינה**. למידע נוסף, ראה [יצירת פלח חדש באמצעות פלחים מהירים](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
