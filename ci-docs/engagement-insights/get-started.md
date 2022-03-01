---
title: תחילת העבודה עם יכולת התובנות לגבי מעורבות
description: סקירה כללית של משאבי העזרה כדי להתחיל לעבוד במהירות.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 12/21/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 5ee1567cea834670a16aaa3253912b7957ce26b3
ms.sourcegitcommit: 86739a3f238162fc96837270b5d184e648fab15c
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/20/2021
ms.locfileid: "7405359"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>תחילת העבודה עם יכולת התובנות לגבי מעורבות של Dynamics 365 Customer Insights (תצוגה מקדימה ציבורית)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

יכולת התובנות לגבי מעורבות מאפשרת לך לאסוף ולמדוד את התנהגות הלקוחות באתר שלך. היא משתלבת עם יכולת התובנות לגבי קהלים, כך שתוכל לראות ניתוח התנהגותי מקיף בזמן אמת לצד דוחות פרופיל של לקוחות. הקישורים במאמר זה יעזרו לך לקבוע את תצורת הסביבה שלך ולהגדיר אותה במהירות.

## <a name="step-1-review-prerequisites"></a>שלב 1: סקירת הדרישות המוקדמות

ראשית, צריך להיות לך חשבון משתמש פעיל ב- Microsoft Azure Active Directory. לאחר מכן, יש לקרוא את המאמרים הבאים לפני שתגדיר סביבת עבודה של תובנות לגבי מעורבות.

- סקור וקבל את [תנאי השירות](terms-of-service.md) עם Microsoft.  
- קרא את המאמר [ניהול קובצי Cookie והסכמת משתמש](user-consent-storage.md). לאחר עיון במאמר זה, יש להעריך אם עליך לעדכן את הודעת הסכמת המשתמש שלך. אם בעבר לא היו לך קבצי Cookie "לא חיוניים", קרוב לוודאי שתצטרך לעדכן את מדיניות האתר שלך.
- סקור את [מילון המונחים](glossary.md) לצורך היכרות מהירה עם מונחים ומושגים עיקריים.

## <a name="step-2-explore-engagement-insights"></a>שלב 2: סייר בתובנות לגבי מעורבות

בביקורך הראשון בתובנות לגבי מעורבות תוכל לקבוע הגדרות, לבדוק פריטי מדיניות ולחקור את המוצר.

1. היכנס אל [פורטל יכולת התובנות לגבי מעורבות](https://pi.dynamics.com) באמצעות חשבון משתמש Microsoft Azure Active Directory שלך. (זה יכול להיות חשבון בית הספר או העבודה שלך).

1. בחר את האזור שלך והשתמש בתיבת הסימון כדי לציין אם ברצונך להצטרף לקבל עדכונים ומבצעים בדואר האלקטרוני.

1. סקור את **תנאי השימוש בתובנות לגבי מעורבות (תצוגה מקדימה)** ואת **הצהרת הפרטיות** ואז בחר **סיור בהדגמה** כדי לאשר אותם.

1. חקור את המוצר באמצעות קבוצת נתונים לדוגמה.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>שלב 3: הגדר סביבת עבודה והוסף קוד לאתר שלך

סביבת העבודה היא המקום שבו תוכל לצפות בפעילות משתמשים בזמן אמת, ולאחסן ולנהל דוחות. הוסף קוד לאתר שלך כדי להתחיל לאסוף *אירועים*, נתוני הפעילות שמגיעים מהמשתמשים.

1. [צור סביבת עבודה](create-workspace.md) והוסף חברים.

1. [הוסף קוד לאתר שלך](instrument-website.md) או [אפליקציה למכשירים ניידים](developer-resources.md#capture-events-from-mobile-apps) כדי לראות את פעילות המשתמשים המגיעה לסביבת העבודה שלך.

1. צפה ב[דוח בזמן אמת](view-reports.md) המציג משתמשים פעילים לפי דפדפן, מכשיר, מערכת הפעלה, מיקום ושפה. אתה יכול גם ליצור [דוחות מותאמים אישית](custom-reports.md) כדי ליצור תצוגות חזותיות משלך.
    
## <a name="step-4-export-data-to-other-channels"></a>שלב 4: ייצא נתונים לערוצים אחרים

אתה יכול ליצור *אירועים ממוקדים* (תצוגה וירטואלית) של נתוני ניתוח האינטרנט שלך. לאחר מכן סנן וייצא את הנתונים אל Azure Data Lake Storage. תוכל להטמיע את הנתונים המיוצאים כמקור נתונים. למידע נוסף, ראה [צור קישור בין תובנות קהל לבין תובנות מעורבות](integrate-audience-insights-engagement-insights.md).

1. [צור אירועים ממוקדים](refined-events.md) לייצוא.

1. [ייצא את הנתונים](export-events.md) אל Data Lake Storage.

1. למד כיצד [למחוק ולייצא אירועים המכילים פרטים אישיים](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>שלב 5: הישאר מחובר

אנחנו מעריכים את השתתפותך הפעילה ומתכננים לקחת בחשבון את כל המשוב הרלוונטי בפיתוח מהדורות עתידיות. שתף את המשוב שלך ודווח על בעיות באחד מהערוצים הבאים:
- [קהילה](https://go.microsoft.com/fwlink/?linkid=2141648)
- [ספק משוב](https://go.microsoft.com/fwlink/?linkid=2143222)
- [בקשת תמיכה](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
