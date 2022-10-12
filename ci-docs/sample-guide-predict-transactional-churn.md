---
title: מדריך לדוגמה לחיזוי נטישה של עסקאות
description: השתמש במדריך לדוגמה זה כדי לנסות את המודל לחיזוי נטישה של עסקאות המוכן לשימוש.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609685"
---
# <a name="transactional-churn-prediction-sample-guide"></a>מדריך לדוגמה לחיזוי נטישה של עסקאות

מדריך זה ינחה אותך בדוגמה מקצה לקצה של חיזוי נטישה של עסקאות באמצעות נתונים לדוגמה. אנו ממליצים לנסות את החיזוי הזה [בסביבה חדשה](manage-environments.md).

## <a name="scenario"></a>תרחיש

Contoso היא חברה המייצרת קפה באיכות גבוהה ומכונות קפה. הם מוכרים את המוצרים דרך אתר האינטרנט שלהם Contoso Coffee. מטרת החברה היא לדעת אילו לקוחות, שבדרך כלל רוכשים את המוצרים שלהם על בסיס קבוע, יפסיקו להיות לקוחות פעילים ב- 60 הימים הקרובים. הידיעה מי מהלקוחות **עשוי לנטוש**, יכולה לעזור לה לחסוך מאמצים שיווקיים על-ידי התמקדות בשימור הלקוחות.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- לפחות [הרשאות משתתף](permissions.md).

## <a name="task-1---ingest-data"></a>משימה 1 - קליטת נתונים

עיין במאמרים [לגבי קליטת נתונים](data-sources.md) ו[התחברות למקור של Power Query ](connect-power-query.md). המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>קליטת נתוני לקוחות מפלטפורמת eCommerce

1. צור מקור נתונים בשם **eCommerce**, ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscontacts.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:

   - **DateOfBirth**: תאריך
   - **CreatedOn**: תאריך/שעה/אזור

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המרת תאריך הלידה לתאריך.":::

1. בשדה **שם** בחלונית השמאלית, שנה את שם מקור נתונים שלך ל- **eCommerceContacts**

1. שמור את מקור הנתונים.

### <a name="ingest-online-purchase-data"></a>קליטת נתוני רכישה מקוונים

1. הוסף ערכת נתונים נוספת לאותו מקור נתונים **eCommerce**. בחר שוב את המחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור נתוני רכישות מקוונות https://aka.ms/ciadclassonline.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:

   - **PurchasedOn**: תאריך/שעה
   - **TotalPrice**: מטבע

1. בשדה **שם** בחלונית השמאלית, שנה את שם מקור נתונים שלך ל- **eCommercePurchases**.

1. שמור את מקור הנתונים.

### <a name="ingest-customer-data-from-loyalty-schema"></a>קליטת נתוני לקוחות מסכמת loyalty

1. צור מקור נתונים בשם **LoyaltyScheme**, ובחר במחבר **טקסט/CSV**.

1. הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscustomerloyalty.

1. בעת עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.

1. עדכן את סוג הנתונים עבור העמודות המפורטות להלן:

   - **DateOfBirth**: תאריך
   - **RewardsPoints**: מספר שלם
   - **CreatedOn**: תאריך/שעה

1. בשדה **שם** בחלונית השמאלית, שנה את שם מקור נתונים שלך ל- **loyCustomers**.

1. שמור את מקור הנתונים.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>משימה 4 - הגדר את חיזוי נטישת העסקאות

כשפרופיל לקוח מאוחד במקום ובפעילות, הפעל את חיזוי נטישת העסקאות.

1. עבור אל **בינה** > **חיזויים**.

1. בכרטיסיה **צור**, בחר **שימוש במודל** ב **מודל נטישת לקוחות**.

1. בחר **עסקה** כסוג הנטישה ולאחר מכן **תחילת העבודה**.

1. תן שם למודל **OOB eCommerce Transaction Churn Prediction** ולישות הפלט **OOBeCommerceChurnPrediction**.

1. בחר **הבא**.

1. הגדרת העדפות מודל:

   - **חלון החיזוי**: **60** ימים כדי להגדיר כמה רחוק בעתיד אנו רוצים לחזות את נטישת הלקוחות.

   - **הגדרת הנטישה**: **60** ימים לציון משך הזמן ללא רכישה שלאחריה נחשב הלקוח כלקוח שנטש.

     :::image type="content" source="media/model-levers.PNG" alt-text="בחר ב'חלון החיזוי' וב'הגדרת נטישה' של העדפות המודל.":::

1. בחר **הבא**.

1. בחר **היסטוריית רכישות‬ (נדרש)** ובחר **הוסף נתונים** עבור היסטוריית רכישות.

1. בחר **SalesOrderLine** ואת הישות eCommercePurchases ובחר **הבא**. הנתונים הנדרשים מתמלאים אוטומטית מהפעילות. בחר **שמור** ולאחר מכן בחר **הבא**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="הצטרף לישויות eCommerce.":::

1. דלג על השלב **נתונים נוספים (אופציונלי)**.

1. בשלב **עדכוני נתונים**, בחר **חודשי** עבור לוח הזמנים של המודל.

1. לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**.

## <a name="task-5---review-model-results-and-explanations"></a>משימה 5 - סקירת תוצאות המודל והסברים

הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים. עיין בהסברים על מודל הנטישה. למידע נוסף, ראה [סקירת תוצרות החיזוי](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>משימה 6 - יצירת פלח של לקוחות בסיכון גבוה לנטישה

הפעלת מודל הייצור ישות חדשה, שמופיעה תחת **נתונים** > **ישויות**. ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.

1. בדף התוצאות, בחר **צור פלח**.

1. צור כלל באמצעות היישות  **OOBeCommerceChurnPrediction** והגדר את הפלח:
   - **שדה**: ChurnScore
   - **אופרטור**: גדול מ
   - **ערך**:‏ 0.6

1. בחר **שמור** ו **הפעל** את הפלח.

כעת יש לך פלח שמתעדכן באופן דינמי ומזהה לקוחות בעלי סיכון נטישה גבוה. למידע נוסף: [יצירה וניהול של פלחים](segments.md).

> [!TIP]
> אתה יכול גם ליצור פלח עבור מודל חיזוי מהדף **פלחים** על ידי בחירה ב **חדש** ובחירה באפשרות **צור מ** > **בינה**. למידע נוסף, ראה [יצירת פלח חדש באמצעות פלחים מהירים](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
