---
title: חיזוי נטישה של עסקאות
description: חזה אם קיימת סכנה שלקוח לא ירכוש עוד את המוצרים או השירותים שלך.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f120e9e3cf8d40d913c7fa6a81fbf9facd045e3c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597190"
---
# <a name="transactional-churn-prediction-preview"></a>חיזוי נטישה של עסקאות (Preview)

חיזוי נטישה של עסקאות עוזר לחזות אם לקוח לא ירכוש עוד את המוצרים או השירותים שלך בחלון זמן נתון. באפשרותך ליצור תחזיות נטישה חדשות דרך **בינה** > **תחזיות**. בחר **התחזיות שלי** כדי לראות חיזויים אחרים שיצרת.

> [!TIP]
> נסה את ערכת הלימוד עבור חיזוי נטישה של עסקאות באמצעות נתונים לדוגמה: [מדריך לדוגמה של חיזוי נטישה של עסקאות (Preview)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>דרישות מוקדמות

- לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.
- ידע עסקי כדי להבין מה המשמעות של הנטישה עבור העסק שלך. אנו תומכים בהגדרות נטישה מבוססת-זמן, כלומר שלקוח נחשב למי שנטש לאחר פרק זמן ללא רכישות.
- נתונים על העסקאות/רכישות שלך וההיסטוריה שלהן:
    - מזהי עסקאות להבחנה בין רכישות/עסקאות.
    - מזהי לקוחות כדי להתאים עסקאות ללקוחות שלך.
    - תאריכי אירוע עסקה, המגדירים את התאריכים שבהם התרחשה העסקה.
    - סכמת הנתונים הסמנטית לרכישות/עסקאות דורשת את המידע הבא:
        - **מזהה עסקה:** מזהה ייחודי של רכישה או עסקה.
        - **תאריך עסקה:** תאריך הרכישה או העסקה.
        - **שווי העסקה:** המטבע/סכום הערך המספרי של העסקה/פריט.
        - (אופציונלי) **מזהה מוצר ייחודי:** מזהה המוצר או השירות שנרכש אם הנתונים שלך הם ברמת פריט שורה.
        - (אופציונלי) **אם עסקה זו הייתה החזרה:** שדה true/false המזהה אם העסקה הייתה החזרה או לא. אם **שווי העסקה** שלילי, אנו גם נשתמש במידע זה כדי להסיק החזרה.
- (אופציונלי) נתונים על פעילויות לקוחות:
    - מזהי פעילות כדי להבחין בפעילויות מאותו סוג.
    - מזהי לקוחות כדי למפות פעילויות של הלקוחות.
    - מידע על הפעילויות כולל את השם והתאריך של הפעילות.
    - סכמת הנתונים הסמנטית לפעילות לקוחות כוללת:
        - **מפתח ראשי:** מזהה ייחודי לפעילות. לדוגמה, ביקור באתר או רשומת שימוש המציגים שהלקוח ניסה דוגמית של המוצר שלך.
        - **חותמת זמן:** התאריך והשעה של האירוע שזוהו על ידי המפתח הראשי.
        - **אירוע:** שם האירוע שבו ברצונך להשתמש. לדוגמא, שדה שנקרא "UserAction" בחנות מכולת עשוי להיות שימוש בקופון על-ידי הלקוח.
        - **פרטים:** מידע מפורט על האירוע. לדוגמה, שדה בשם "CouponValue" בחנות מכולת עשוי להיות ערך המטבע של הקופון.

## <a name="create-a-transactional-churn-prediction"></a>יצירת חיזוי נטישה של עסקאות

1. ב- Customer Insights, עבור אל **בינה** > **חיזויים**.

1. בחר את האריח **מודל נטישת לקוחות (Preview)** ובחר **השתמש במודל זה**.
   
1. בחלונית **מודל נטישת לקוחות**, בחר **עסקה** ובחר **תחילת העבודה**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="צילום מסך עם אפשרות העסקה שנבחרה בחלונית מודל נטישת לקוחות.":::

### <a name="name-model"></a>מתן שם למודל

1. תן שם למודל כדי להבדיל אותו ממודלים אחרים.

1. תן שם לישות הפלט שכולל אותיות ומספרים בלבד, ללא רווחים. זה השם שבו ישות המודל תשתמש. 

1. בחר **הבא**.

### <a name="define-customer-churn"></a>הגדרת נטישת לקוחות

1. הגדר חלון של ימים לחיזוי נטישה עבורו בשדה **זהה לקוחות שעלולים לנטוש בטווח הזמן הבא**. לדוגמה, חזה את הסיכון לנטישה עבור הלקוחות שלך במשך 90 הימים הבאים כדי להתאים למאמצי השימור השיווקיים שלך. חיזוי סיכון לנטישה עבור פרק זמן ארוך או קצר יותר עשוי להקשות על הטיפול בגורמים בפרופיל סיכון הנטישה שלך, אבל זה תלוי בדרישות העסקיות הספציפיות. 
   >[!TIP]
   > אתה יכול לבחור **שמור וסגור** בכל עת כדי לשמור את החיזוי כטיוטה. תמצא את הטיוטה של החיזוי בכרטיסיה **התחזיות שלי** כדי להמשיך.

1. הזן את מספר הימים להגדרת נטישה בשדה **לקוח נחשב כלקוח שנטש אם הוא לא ביצע רכישות ב:**. לדוגמא, אם לקוח לא ביצע רכישות ב- 30 הימים האחרונים, הוא עשוי להיחשב כלקוח שנטש עבור העסק שלך. 

1. בחר **הבא** כדי להמשיך

### <a name="add-required-data"></a>הוספת נתונים נדרשים

1. בחר **הוסף נתונים** עבור **היסטוריית רכישות** ובחר בישות המספקת את המידע על היסטוריית העסקאות/הרכישות כמתואר ב[דרישות מוקדמות](#prerequisites).

1. מפה את השדות הסמנטיים לתכונות בישות היסטוריית הרכישות שלך ובחר **הבא**. לתיאורים של השדות, בדוק את [ה‏‫דרישות המוקדמות](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="מפה שדות סמנטיים של היסטוריית הרכישות.":::

1. אם השדות שלהלן אינם מאוכלסים, הגדר את הקשר מישות היסטוריית הרכישות שלך לישות 'לקוח'.
    1. בחר את **ישות היסטוריית הרכישות**.
    1. בחר את **שדה** המזהה את הלקוח בישות היסטוריית הרכישות. עליו להתייחס למזהה הלקוח העיקרי של ישות הלקוח שלך.
    1. בחר את **ישות לקוח** שמתאימה לישות הלקוח העיקרית שלך.
    1. הקלד שם המתאר את הקשר.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="דף היסטוריית הרכישות המציג את היצירה של קשר עם הלקוח.":::
   
1. בחר **הבא**.

1. לחלופין, בחר **הוסף נתונים** עבור **פעילויות לקוח**. בחר את הישות המספקת את פרטי פעילות הלקוח כמתואר בדרישות המוקדמות.

1. מפה את השדות הסמנטיים לתכונות בישות פעילות הלקוח שלך ובחר **הבא**. לתיאורים של השדות, בדוק את [ה‏‫דרישות המוקדמות](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="מפה שדות לקוחות לנתוני עסקאות.":::

1. בחר סוג פעילות שתואם את סוג הפעילות של הלקוח שאתה מגדיר. בחר **צור חדש** ובחר סוג פעילות זמין או צור סוג חדש.

1. יהיה עליך להגדיר את הקשר בין ישות פעילות הלקוח לישות הלקוח.
    1. בחר את השדה המזהה את הלקוח בטבלת פעילות הלקוח. הוא עשוי להיות קשור ישירות למזהה הלקוח הראשי של הישות 'לקוח' שלך.
    1. בחר את ישות לקוח שמתאימה לישות הלקוח העיקרית שלך
    1. הקלד שם המתאר את הקשר.

1. בחר **שמור**.

1. אם יש לך פעילויות אחרות של לקוחות שברצונך לכלול, חזור על השלבים לעיל.

1. בחר **הבא**.

### <a name="set-schedule-and-review-configuration"></a>הגדרת לוח זמנים ובדיקת תצורה

1. הגדר שכיחות כדי לאמן מחדש את המודל שלך. הגדרה זו חשובה כדי לעדכן את דיוק החיזויים כאשר נתונים חדשים מעובדים. מרבית העסקים יכולים לבצע אימון פעם בחודש ולקבל דיוק טוב לחיזוי שלהם.

1. בחר **הבא**.

1. סקור את תצורת החיזוי. באפשרותך לחזור לשלבים הקודמים על-ידי בחירת **ערוך** תחת הערך המוצג. לחלופין, תוכל לבחור שלב תצורה במחוון ההתקדמות.

1. אם כל הערכים מוגדרים כהלכה, בחר **שמור והפעל** כדי להתחיל בתהליך החיזוי. בכרטיסיה **החיזויים שלי**, תוכל לראות את מצב החיזויים שלך. התהליך עשוי להימשך מספר שעות עד להשלמתו, תלוי בכמות הנתונים המשמשים בחיזוי.

## <a name="review-a-prediction-status-and-results"></a>סקור את מצב החיזוי והתוצאות

1. עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.

1. בחר בחיזוי שברצונך לבדוק.
   - **שם חיזוי:** שם החיזוי שסופק בעת יצירתו.
   - **סוג חיזוי:** סוג המודל המשמש עבור החיזוי
   - **ישות פלט:** שם הישות לאחסון פלט החיזוי. אתה יכול למצוא ישות עם שם זה ב- **נתונים** > **ישויות**.
   - **שדה חזוי:** שדה זה מאוכלס רק עבור סוגים מסוימים של תחזיות, ואינו משמש בחיזוי נטישות.
   - **מצב:** מצב הפעלת החיזוי.
        - **הוצב בתור:** חיזוי ממתין להפעלת תהליכים אחרים.
        - **מרענן:** חיזוי פועל כעת כדי ליצור תוצאות שיזרמו לישות הפלט.
        - **נכשל:** הפעלת החיזוי נכשלה. [סקור את יומני הרישום](#troubleshoot-a-failed-prediction) לקבלת פרטים נוספים.
        - **הצליח:** החיזוי הצליח. בחר **הצג** מתחת לשלוש הנקודות האנכיות כדי לבדוק את החיזוי
   - **נערך:** התאריך שבו השתנתה הגדרת החיזוי.
   - **רענון אחרון:** התאריך שבו בוצע רענון של תוצאות החיזוי בישות הפלט.

1. בחר את שלוש הנקודות האנכיות לצד החיזוי שתרצה לבדוק את התוצאות שלו ובחר **הצג**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="פקד תצוגה להצגת תוצאות של חיזוי.":::   

1. ישנם שלושה חלקים עיקריים של נתונים בדף התוצאות:
    1. **ביצועי מודל אימון:** A, B או C הם ציונים אפשריים. ניקוד זה מציין את ביצועי החיזוי ויכול לעזור לך לקבל את ההחלטה להשתמש בתוצאות המאוחסנות בישות הפלט. הניקוד נקבע על פי הכללים הבאים:
         
         - **A** כאשר המודל ניבא במדויק לפחות 50% מכלל התחזיות, וכאשר אחוז התחזיות המדויקות עבור לקוחות שנטשו גדול משיעור הבסיס ב- 10% לפחות.
            
         - **B** כאשר המודל ניבא במדויק לפחות 50% מכלל התחזיות, וכאשר אחוז התחזיות המדויקות עבור לקוחות שנטשו גדול בעד 10% מהבסיס.
            
         - **C** כאשר המודל ניבא במדויק פחות מ- 50% מכלל התחזיות, או כאשר אחוזי התחזיות המדויקות עבור הלקוחות שנטשו קטנים מהבסיס.
               
         - **בסיס** לוקח את קלט חלון הזמן של החיזוי עבור המודל (לדוגמה, שנה אחת) והמודל יוצר חלקים שונים של זמן על-ידי חלוקה שלו ב- 2 עד שהוא מגיע לחודש אחד או פחות. הוא משתמש בחלקים אלה כדי ליצור כלל עסקי עבור לקוחות שלא רכשו במסגרת זמן זו. לקוחות אלה נחשבים ללקוחות שנטשו. הכלל העסקי מבוסס הזמן עם היכולת הגבוהה ביותר לחזות מי עשוי לנטוש נבחר כמודל בסיסי.
            
    1. **הסבירות לנטוש (מספר לקוחות):** קבוצות של לקוחות בהתבסס על הסיכון החזוי שלהם לנטוש. נתונים אלה יכולים לעזור לך מאוחר יותר אם ברצונך ליצור פלח של לקוחות עם סיכון גבוה לנטישה. פלחים כאלה עוזרים להבין היכן כדאי לקצץ בחברות בפלח.
       
    1. **הגורמים המשפיעים ביותר:** ישנם גורמים רבים אשר נלקחים בחשבון בעת יצירת החיזוי. לכל אחד מהגורמים יש חשיבות משלו המחושבת עבור התחזיות המצטברות שמודל יוצר. אתה יכול להשתמש בגורמים אלה כדי לסייע באימות תוצאות החיזוי שלך. לחלופין, תוכל להשתמש במידע זה מאוחר יותר כדי [ליצור פלחים](segments.md), מה שעשוי לעזור להשפיע על סיכויי הנטישה של הלקוחות.

## <a name="troubleshoot-a-failed-prediction"></a>פתור בעיה של חיזוי שנכשל

1. עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.

1. בחר את שלוש הנקודות האנכיות לצד התחזית שברצונך להציג יומני שגיאה עבורה.

1. בחר **יומנים**.

1. סקירת כל השגיאות. יש מספר סוגים של שגיאות שיכולות להתרחש, והם מתארים איזה מצב גרם לשגיאה. לדוגמה, שגיאה כי אין מספיק נתונים כדי לחזות במדויק נפתרת בדרך כלל על ידי טעינת נתונים נוספים ל- Customer Insights.

## <a name="refresh-a-prediction"></a>רענן חיזוי

החיזוי יחודש באופן אוטומטי באותו [תזמון של רענון הנתונים](system.md#schedule-tab) כפי שהוגדר בהגדרות. באפשרותך לרענן אותם גם באופן ידני.

1. עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.

1. בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך לרענן.

1. בחר **רענן**.

## <a name="delete-a-prediction"></a>מחק חיזוי

מחיקת חיזוי גם מסירה את ישות הפלט שלו.

1. עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.

1. בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך למחוק.

1. בחר **מחק**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]