---
title: תחילת העבודה עם יכולת התובנות לגבי מעורבות
description: סקירה כללית של משאבי העזרה כדי להתחיל לעבוד במהירות.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494595"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>תחילת העבודה עם יכולת התובנות לגבי מעורבות של Dynamics 365 Customer Insights (תצוגה מקדימה ציבורית)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

יכולת התובנות לגבי מעורבות מאפשרת לך לאסוף ולמדוד את התנהגות הלקוחות באתר שלך. היא משתלבת עם יכולת התובנות לגבי קהלים, כך שתוכל לראות ניתוח התנהגותי מקיף בזמן אמת לצד דוחות פרופיל של לקוחות. הקישורים במאמר זה יעזרו לך לקבוע את תצורת הסביבה שלך ולהגדיר אותה במהירות.

## <a name="step-1-review-prerequisites"></a>שלב 1: סקירת הדרישות המוקדמות

ראשית, צריך להיות לך חשבון משתמש פעיל ב- Microsoft Azure Active Directory (AAD). לאחר מכן, יש לקרוא את המאמרים הבאים לפני שתגדיר סביבת עבודה של תובנות לגבי מעורבות.

- סקור וקבל את [תנאי השירות](terms-of-service.md) עם Microsoft.  
- קרא את המאמר [ניהול קובצי Cookie והסכמת משתמש](user-consent-storage.md). לאחר מכן, בדוק אם עליך לעדכן את הודעת הסכמת המשתמש שלך. אם בעבר לא היו לך קבצי Cookie "לא חיוניים", קרוב לוודאי שתצטרך לעדכן את מדיניות האתר שלך.
- סקור את [מילון המונחים](glossary.md) לצורך היכרות מהירה עם מונחים ומושגים עיקריים.

## <a name="step-2-explore-engagement-insights"></a>שלב 2: סייר בתובנות לגבי מעורבות

בפעם הראשונה שאתה מבקר בתובנות לגבי מעורבות, באפשרותך לקבוע תצורה של הגדרות, לסייר בפריטי מדיניות ולסייר ביכולת.

1. היכנס אל [פורטל היכולת של תובנות לגבי מעורבות](https://home.ci.ai.dynamics.com/app/engagement-insights) באמצעות חשבון משתמש Microsoft AAD (בית ספר או עבודה).

1. בחר את האזור שלך וסמן את התיבה אם ברצונך להצטרף לקבלת עדכונים והצעות דוא"ל.

1. סקור את **תנאי השימוש של תובנות לגבי מעורבות (Preview)** ואת **הצהרת הפרטיות** ולאחר מכן בחר **סייר בהדגמה** כדי לקבל הגדרות אלה.

1. חקור את המוצר באמצעות קבוצת נתונים לדוגמה.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>שלב 3: הגדר סביבת עבודה והוסף קוד לאתר שלך

סביבת עבודה היא מקום שבו באפשרותך להציג פעילות משתמש בזמן אמת, ולאחסן ולנהל דוחות. הוסף קוד לאתר שלך כדי להתחיל לאסוף *אירועים*, נתוני הפעילות שמגיעים מהמשתמשים.

1. [צור סביבת עבודה](create-workspace.md) והוסף חברים.

1. [הוסף קוד לאתר שלך](instrument-website.md) או [אפליקציה למכשירים ניידים](developer-resources.md#capture-events-from-mobile-apps) כדי לראות את פעילות המשתמשים המגיעה לסביבת העבודה שלך.

1. הצג [דוח בזמן אמת](view-reports.md) המציג משתמשים פעילים לפי דפדפן, מכשיר, מערכת הפעלה, מיקום ושפה. אתה יכול גם ליצור [דוחות מותאמים אישית](custom-reports.md) כדי ליצור תצוגות חזותיות משלך.
    
## <a name="step-4-export-data-to-other-channels"></a>שלב 4: ייצא נתונים לערוצים אחרים

אתה יכול ליצור *אירועים ממוקדים* (תצוגה וירטואלית) של נתוני ניתוח האינטרנט שלך. לאחר מכן סנן וייצא את הנתונים אל Azure Data Lake Storage. תוכל להטמיע את הנתונים המיוצאים כמקור נתונים. למידע נוסף, ראה [צור קישור בין תובנות קהל לבין תובנות מעורבות](integrate-audience-insights-engagement-insights.md).

1. [צור אירועים ממוקדים](refined-events.md) לייצוא.

1. [ייצא את הנתונים](export-events.md) אל Data Lake Storage.

1. [צור קישור בין תובנות לגבי קהלים ותובנות לגבי מעורבות](integrate-audience-insights-engagement-insights.md) כדי לשתף נתונים בין שתי היכולות.

1. למד כיצד [למחוק ולייצא אירועים המכילים פרטים אישיים](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>שלב 5: הישאר מחובר

אנו מעריכים את השתתפותך הפעילה, ומתחשבים בכל המשוב הרלוונטי לצורך פיתוח מהדורות עתידיות. שתף את המשוב שלך ודווח על בעיות באחד מהערוצים הבאים:
- [קהילה](https://go.microsoft.com/fwlink/?linkid=2141648)
- [ספק משוב](https://go.microsoft.com/fwlink/?linkid=2143222)
- [בקשת תמיכה](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
