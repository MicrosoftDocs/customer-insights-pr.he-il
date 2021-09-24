---
title: תחילת העבודה עם תובנות לגבי קהלים ב- Dynamics 365 Customer Insights
description: מבט כולל על תובנות לגבי קהלים עוזר למשאבים להתחיל בעבודה במהירות.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: aaaf1848df175469d8af07754ac153b777781ffb
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466578"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>תחילת העבודה עם יכולת תובנות לגבי קהלים של Dynamics 365 Customer Insights

תובנות לגבי קהלים יכולות לעזור לך לבנות הבנה מעמיקה יותר של הלקוחות שלך. חבר נתונים ממקורות עסקיים, התנהגותיים ותצפיתיים שונים כדי ליצור תצוגת לקוח ב- 360 מעלות. השתמש בתובנות אלה כדי לקדם חוויות ותהליכים המתמקדים בלקוח. אחד והבן את נתוני הלקוחות ורתום אותם לצורך תובנות ופעולות חכמות.

## <a name="step-1-create-an-environment"></a>שלב 1: יצירת סביבה

כדי להתחיל, עליך ליצור תחילה סביבה כדי לעבוד בה. אם הארגון שלך כבר רכש רשיון, ראה [תחילת העבודה עם מנוי בתשלום](get-started-paid.md). כדי להתחיל גירסת ניסיון עבור תובנות לגבי קהלים, ראה [הגדרת סביבת ניסיון](get-started-trial.md). 

## <a name="step-2-explore-audience-insights"></a>שלב 2: סיור בתובנות לגבי קהלים

בפעם הראשונה שאתה נכנס לתובנות לגבי קהלים, באפשרותך לקבוע תצורה של הגדרות ולסייר במוצר.

1. [היכנס לתובנות לגבי קהלהים](https://home.ci.ai.dynamics.com) באמצעות חשבון המשתמש של Microsoft Azure Active Directory (AAD) שלך.

1. [שנה את הסביבה](manage-environments.md#switch-environments) כדי לראות נתוני הדגמה וכן [סייר בתובנות לגבי קהלים](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>שלב 3: קליטה, איחוד והגדרה של קשרי גומלין עבור הנתונים שלך

פרופילים מאוחדים הם הבסיס לקבלת תובנות ולנקיטת פעולה בנתונים. הבא נתונים ממקורות שונים והפעל את תהליך איחוד הנתונים כדי לשלב פרופילים מאוחדים. ציין את קשרים בין הישויות שנקלטו המשתמשות בתכונות העשרה כדי להוסיף מידע לפרופילים. 

1. קלוט נתונים על-ידי יצירת מקורות נתונים מאפשרויות מרובות. בחר בין [מחברי Power Query](connect-power-query.md), [תיקיית Common Data Model](connect-common-data-model.md) או [Microsoft Dataverse](connect-common-data-service-lake.md). 

1. הפעל את [תהליך איחוד הנתונים](data-unification.md) על-ידי מעבר דרך שלבי [מיפוי](map-entities.md), [התאמה](match-entities.md) ו[מיזוג](merge-entities.md).

1. התוודע ל[ישויות שהמערכת יוצרת](entities.md) וצור [קשרים בין הישויות שנקלטו](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>שלב 4: שיפור פרופילים מאוחדים עם חיזויים, פעילויות ומדידות

כאשר פרופילים מאוחדים מוגדרים, באפשרותך לשפר את הנתונים שלך ולהגדיל עוד יותר את המידע שהם מספקים.

1. בחר מתוך ספריה הולכת וגדלה של ספקי העשרה כדי [להעשיר את נתוני הלקוח שלך](enrichment-hub.md).

1. השתמש ב[מודלים מוכנים לשימוש](predictions-overview.md) כדי לחזות סבירות לנטישה או הכנסות צפויות.

1. [קבע תצורה של פעילויות](activities.md) בהתבסס על נתונים שנקלטו והצג באופן חזותי אינטראקציות עם הלקוחות שלך בציר זמן כרונולוגי. 

1. [בנה מדידות](measures.md) כדי למדוד את היעדים העסקיים ואת מחווני ה- KPI שלך.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>שלב 5: יצירת פלחים והפעלת נתונים דרך אפשרויות ייצוא שונות

כעת, כשהנתונים שלך מלאים ומכילים מגוון רחב של מידע אודות הלקוחות שלך, הגיע הזמן לחפש דרכים לנקוט פעולה בנתונים אלה. 

1. [צור פלחים](segments.md) קבוצות משנה של בסיס הלקוחות שלך, כדי להבטיח שהפעולות שלך יהיו רלוונטיות ללקוחות היעד.

1. עיון בקטלוג ההולך וגדל של [אפשרויות ייצוא](export-destinations.md) שבו באפשרותך להשתמש בנתוני לקוחות. לדוגמה, באפשרותך להשתמש בנתונים לניהול מבצעים וליצירת קשר עם שיווק דיגיטלי.

1. סקור אפשרויות שילוב, לדוגמה עם [קשר ישיר לתובנות בנוגע למעורבות](../engagement-insights/integrate-audience-insights-engagement-insights.md) או ליישומי Dynamics 365 אחרים עם [תוספת 'כרטיס לקוח'](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]
