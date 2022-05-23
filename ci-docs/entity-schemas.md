---
title: סכימות ישות של Customer Insights ב- Common Data Model‏
description: עבוד עם ישויות ב- Common Data Model.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 33a0562854e97b9ac5218e060f965996305627fd
ms.sourcegitcommit: d45c00a5f6cb106714366af81e8070e7f53654b3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/15/2022
ms.locfileid: "8757433"
---
# <a name="entity-schemas-in-common-data-model"></a>סכימות ישויות ב- Common Data Model



[Common Data Model](/common-data-model/) הוא מפרט הצהרתי, והגדרה של ישויות סטנדרטיות המייצגות מושגים ופעילויות נפוצים ביישומים עסקיים ויישומי פרודוקטיביות. המודל מורחב גם לנתוני תצפית ונתונים אנליטיים. Common Data Model מספק ישויות עסקיות מוגדרות היטב, מודולריות וניתנות להרחבה - כגון 'תיק לקוח', 'יחידה עסקית', 'אירוע', 'איש קשר', 'הפניה', 'הזדמנות' ו'מוצר' - וכן אינטראקציות עם ספקים, עובדים ולקוחות - כגון פעילויות והסכמי רמת שירות. כל אחד יכול לבנות ולהרחיב את ההגדרות של Common Data Model כדי ללכוד רעיונות נוספים הספציפיים לעסק.

זהו מודל נתונים משותף שמאפשר ליישומים ולמשלבי נתונים לשתף פעולה בקלות רבה יותר על-ידי מתן הגדרת נתונים אחידה. Common Data Model כולל מערכת מטה-נתונים עשירים עם ישויות סטנדרטיות, קשרים, הירארכיות, תכונות ועוד. מקורו ביישומי Dynamics 365 והוא בעל קוד פתוח ב- GitHub עם יותר מ- 260 ישויות סטנדרטיות. מערכת גדולה של שותפים פנימיים וחיצוניים תורמת מושגים ספציפיים לתעשייה ל- Common Data Model.

מערכות ופלטפורמות מרובות מיישמות את Common Data Model כיום, כולל זרימות נתונים של Power BI ו- Azure Data Services. הוא כבר נתמך ב- Microsoft Dataverse, Dynamics 365, Power Apps, Power BI ובשירותי הנתונים העתידיים של Azure, וצובר ערך ישירות לקראת ה- [Open Data Initiative](https://dynamics.microsoft.com/en-us/open-data-initiative/).

## <a name="customer-insights-entity-schemas"></a>סכימות ישות של Customer Insights

כדי ליצור תצוגה של 360 מעלות של הלקוח ולהפוך את המודלים של Customer Insights לזמינים ב- Common Data Model עבור יכולת הרחבה, פרסמנו את סכימות הישות הבאות:

| ישות | תיאור |
|---------|---------|
|[CustomerActivity](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | פעילות המתבצעת על-ידי משתמש שיש לה ערך תצפיתי לעסק. |
|[CustomerProfile](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | אדם או ארגון שביצעו או שיש להם פוטנציאל להיות מעורבים בפעילויות עסקיות. |
|[MeasureDefinition](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | הגדרת מחווני KPI המחולקים למחיצות על-ידי אפס ממדים או יותר (למשל, משתמשים פעילים חודשיים, סך כל ההוצאות לפי לקוח, עלות קבלת לקוח ממוצעת) |
|[פלח](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | הגדרת קבוצת חברים עם תכונות משותפות. |
|[SegmentMembership](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | חברים המשתתפים בפלח נתון. |

לקבלת מידע נוסף, עיין בתיעוד לגבי [סכימות ישויות של Customer Insights ב- Common Data Model](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>הצגת ישויות באמצעות Common Data Model Entity Navigator

באפשרותך להציג ישויות ב- [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/). בחר ישות מהקטע Application Insights כדי לקבל את רשימת ישויות Customer Insights והגדרותיהם.
> [!div class="mx-imgBorder"]
> ![CDM Entity Navigator המציג את הישות CustomerActivity.](media/CDM-entity-navigator.png "CDM Entity Navigator המציג את הישות CustomerActivity")


[!INCLUDE [footer-include](includes/footer-banner.md)]
