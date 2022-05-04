---
title: תחילת העבודה עם Dynamics 365 Customer Insights
description: סקירה כללית של Customer Insights עוזרת למשאבים להתחיל בעבודה במהירות.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: audience-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 6d23552687530fddf42418b924571dddc0209e69
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8646744"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>תחילת העבודה עם Dynamics 365 Customer Insights

Customer Insights יכול לעזור לך לבנות הבנה מעמיקה יותר של הלקוחות שלך. חבר נתונים ממקורות עסקיים, התנהגותיים ותצפיתיים שונים כדי ליצור תצוגת לקוח ב- 360 מעלות. השתמש בתובנות אלה כדי לקדם חוויות ותהליכים המתמקדים בלקוח. אחד והבן את נתוני הלקוחות ורתום אותם לצורך תובנות ופעולות חכמות.

## <a name="step-1-create-an-environment"></a>שלב 1: יצירת סביבה

כדי להתחיל, עליך ליצור תחילה סביבה כדי לעבוד בה. אם הארגון שלך כבר רכש רשיון, ראה [יצירת סביבה](create-environment.md). כדי להתחיל ניסיון של Customer Insights, ראה [הגדרת סביבת ניסיון](trial-signup.md). 

## <a name="step-2-explore-customer-insights"></a>שלב 2: גלה את Customer Insights

בפעם הראשונה שאתה נכנס ל- Customer Insights, אתה יכול לקבוע הגדרות ולגלות את המוצר.

1. [היכנס ל- Customer Insights](https://home.ci.ai.dynamics.com) באמצעות חשבון המשתמש (AAD) Azure Active Directory ‏Microsoft שלך.

1. [שנה את הסביבה](manage-environments.md#switch-environments) כדי לראות נתוני הדגמה ו[לגלות את Customer Insights](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>שלב 3: קליטה, איחוד והגדרה של קשרי גומלין עבור הנתונים שלך

פרופילים מאוחדים הם הבסיס לקבלת תובנות ולנקיטת פעולה בנתונים. הבא נתונים ממקורות שונים והפעל את תהליך איחוד הנתונים כדי לשלב פרופילים מאוחדים. ציין את קשרים בין הישויות שנקלטו המשתמשות בתכונות העשרה כדי להוסיף מידע לפרופילים. 

1. קלוט נתונים על-ידי יצירת מקורות נתונים מאפשרויות מרובות. בחר בין [Power Query מחברים](connect-power-query.md), [תיקיית Common Data Model](connect-common-data-model.md), או [Microsoft Dataverse](connect-dataverse-managed-lake.md). 

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

1. סקור את אפשרויות האינטגרציה, למשל ליישומי Dynamics 365 אחרים באמצעות [התוספת 'כרטיס לקוח'](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]