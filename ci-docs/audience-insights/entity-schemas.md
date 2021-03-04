---
title: סכימות ישות של Customer Insights ב- Common Data Model‏
description: עבוד עם ישויות ב- Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269285"
---
# <a name="entity-schemas-in-common-data-model"></a>סכימות ישויות ב- Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

[Common Data Model](https://docs.microsoft.com/common-data-model/) הוא מפרט הצהרתי, והגדרה של ישויות סטנדרטיות המייצגות מושגים ופעילויות נפוצים ביישומים עסקיים ויישומי פרודוקטיביות. המודל מורחב גם לנתוני תצפית ונתונים אנליטיים. Common Data Model מספק ישויות עסקיות מוגדרות היטב, מודולריות וניתנות להרחבה - כגון 'תיק לקוח', 'יחידה עסקית', 'אירוע', 'איש קשר', 'הפניה', 'הזדמנות' ו'מוצר' - וכן אינטראקציות עם ספקים, עובדים ולקוחות - כגון פעילויות והסכמי רמת שירות. כל אחד יכול לבנות ולהרחיב את ההגדרות של Common Data Model כדי ללכוד רעיונות נוספים הספציפיים לעסק.

זהו מודל נתונים משותף שמאפשר ליישומים ולמשלבי נתונים לשתף פעולה בקלות רבה יותר על-ידי מתן הגדרת נתונים אחידה. Common Data Model כולל מערכת מטה-נתונים עשירים עם ישויות סטנדרטיות, קשרים, הירארכיות, תכונות ועוד. מקורו ביישומי Dynamics 365 והוא בעל קוד פתוח ב- GitHub עם יותר מ- 260 ישויות סטנדרטיות. מערכת גדולה של שותפים פנימיים וחיצוניים תורמת מושגים ספציפיים לתעשייה ל- Common Data Model.

מערכות ופלטפורמות מרובות מיישמות כיום את Common Data Model, כולל זרימות הנתונים של Power BI ו- Azure Data Services. הוא כבר נתמך ב- Common Data Service,‏ Dynamics 365, Power Apps, Power BI, ושירותי נתונים עתידיים של Azure, אשר צוברים ערך ישירות כלפי [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>סכימות ישות של Customer Insights

כדי ליצור תצוגה של 360 מעלות של הלקוח ולהפוך את המודלים של Customer Insights לזמינים ב- Common Data Model עבור יכולת הרחבה, פרסמנו את סכימות הישות הבאות:

| ישות | תיאור |
|---------|---------|
|[CustomerActivity](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | פעילות המתבצעת על-ידי משתמש שיש לה ערך תצפיתי לעסק. |
|[CustomerProfile](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | אדם או ארגון שביצעו או שיש להם פוטנציאל להיות מעורבים בפעילויות עסקיות. |
|[MeasureDefinition](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | הגדרת מחווני KPI המחולקים למחיצות על-ידי אפס ממדים או יותר (למשל, משתמשים פעילים חודשיים, סך כל ההוצאות לפי לקוח, עלות קבלת לקוח ממוצעת) |
|[פלח](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | הגדרת קבוצת חברים עם תכונות משותפות. |
|[SegmentMembership](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | חברים המשתתפים בפלח נתון. |

לקבלת מידע נוסף, עיין בתיעוד לגבי [סכימות ישויות של Customer Insights ב- Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>הצגת ישויות באמצעות Common Data Model Entity Navigator

באפשרותך להציג ישויות ב- [Common Data Model Entity Navigator](https://microsoft.github.io/CDM/). בחר את לחצן **טען מ- GitHub!** ונווט אל **foundationCommon** > **crmCommon** > **פתרונות** > **customerInsights** שם תמצא רשימה של ישויות Customer Insights ואת ההגדרות שלהן.
> [!div class="mx-imgBorder"]
> ![CDM Entity Navigator המציג את הישות CustomerActivity](media/CDM-entity-navigator.png "CDM Entity Navigator המציג את הישות CustomerActivity")


[!INCLUDE[footer-include](../includes/footer-banner.md)]