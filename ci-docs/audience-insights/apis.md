---
title: עבודה עם ממשקי API
description: השתמש בממשקי API והכר מגבלות.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304743"
---
# <a name="work-with-customer-insights-apis"></a>עבודה עם ממשקי API של Customer Insights

Dynamics 365 Customer Insights מספק ממשקי API לבניית יישומים משלך בהתבסס על הנתונים שלך ב- Customer Insights.

> [!IMPORTANT]
> פרטים על ממשקי API אלה מפורטים ב[הפניית ממשקי API של Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). הם כוללים מידע נוסף על פעולות, פרמטרים ותגובות.

מאמר זה מתאר כיצד לגשת לממשקי API של Customer Insights, ליצור רישום של יישום Azure ולהתחיל בספריות הלקוחות הזמינות.

## <a name="get-started-trying-the-customer-insights-apis"></a>התחל לנסות את ממשקי ה- API של Customer Insights

1. [היכנס](https://home.ci.ai.dynamics.com) אל Customer Insights. אם עדיין אין לך מנוי, [הירשם לגירסת ניסיון של Customer Insights](https://aka.ms/tryci).

1. כדי להפעיל ממשקי API בסביבת Customer Insights שלך, עבור אל **ניהול** > **הרשאות**. תזדקק להרשאות מנהל מערכת כדי לעשות זאת.

1. עבור אל הכרטיסיה **ממשקי API** ובחר בלחצן **הפוך לזמין**.    
 
   הפעלת ממשקי ה- API יוצרת מפתח מנוי ראשי ומשני עבור המופע שלך המשמש בבקשות ה- API. באפשרותך ליצור מחדש את המפתחות על-ידי בחירת **צור מחדש מפתח ראשי** או **צור מחדש מפתח משני** דרך **ניהול** > **הרשאות** > **ממשקי API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="אפשר ממשקי API של Customer Insights":::

1. בחר **סקור את ממשקי ה- API שלנו** כדי [לנסות את ממשקי ה- API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. בחר פעולת API ובחר **נסה זאת**.

1. בחלונית הצד, הגדר את הערך בתפריט הנפתח **הרשאה** ל **משתמע**. הכותרת `Authorization` מתווספת עם אסימון נושא. מפתח המנוי שלך יאוכלס אוטומטית.
  
1. לחלופין, הוסף את כל פרמטרי השאילתה הדרושים.

1. גלול לתחתית החלונית הצדדית ובחר **שלח**.

תגובת ה- HTTP תופיע תוך זמן קצר למטה.

   :::image type="content" source="media/try-apis.gif" alt-text="כיצד לבדוק את ממשקי ה- API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>יצירת רישום יישום חדש בפורטל Azure

שלבים אלה עוזרים לך להתחיל להשתמש בממשקי ה- API של Customer Insights ביישום Azure באמצעות הרשאות מוקצות. הקפד להשלים את [מקטע תחילת העבודה](#get-started-trying-the-customer-insights-apis) תחילה.

1. היכנס אל [פורטל Azure](https://portal.azure.com) עם החשבון שיכול לגשת לנתוני Customer Insights.

1. משמאל, בחר **רישומי יישום**.

1. בחר **רישום חדש**, ספק שם יישום ובחר את סוג החשבון.
 
   לבחירתך, הוסף כתובת URL של ניתוב מחדש. http://localhost מספיק לפיתוח יישום במחשב המקומי שלך.

1. ברישום היישום החדש שלך, עבור אל **הרשאות API**.

   :::image type="content" source="media/app-registration-1.gif" alt-text="כיצד להגדיר הרשאות API ברישום יישומים.":::

1. בחר **הוסף הרשאה** ובחר **Customer Insights** בחלונית הצדדית.

1. עבור **סוג הרשאה**, בחר **הרשאות שהוקצו** ואז בחר את הרשאת **התחזות למשתמש**.

1. בחר **הוסף הרשאות**. אם אתה זקוק לגישה ל- API מבלי שמשתמש יתחבר, סקור את המקטע [הרשאות יישום משרת לשרת](#server-to-server-application-permissions).

1. בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.

באפשרותך להשתמש במזהה היישום/לקוח עבור רישום יישום זה עם Microsoft Authentication Library‏ (MSAL) כדי להשיג אסימון נושא לשליחה עם הבקשה שלך ל- API.

:::image type="content" source="media/grant-admin-consent.gif" alt-text="כיצד להעניק הסכמת מנהל מערכת.":::

לקבלת מידע נוסף אודות MSAL, ראה [מבט כולל על Microsoft Authentication Library‏ (MSAL)](/azure/active-directory/develop/msal-overview).

לקבלת מידע נוסף על רישום יישומים ב- Azure, ראה [רישום בקשה](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

למידע על השימוש בממשקי ה- API בספריות הלקוחות שלנו, ראה [ספריות לקוחות של Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>הרשאות יישום של שרת לשרת

[מקטע רישום יישום](#create-a-new-app-registration-in-the-azure-portal) מפרט כיצד יש לרשום יישום שדורש כניסת משתמש עבור אימות. למד כיצד ליצור רישום יישום שאינו זקוק לאינטראקציית משתמש ויכול לפעול בשרת.

1. ברישום היישום שלך בפורטל Azure, עבור אל **הרשאות API**.

1. בחר **הוסף הרשאה**. 

1. בחר את הכרטיסיה **ממשקי API שהארגון שלי משתמש בהם** ובחר **Dynamics 365 AI for Customer Insights** מתוך הרשימה. 

1. עבור **סוג הרשאה**, בחר **הרשאות של יישומים** ואז בחר את הרשאת **CustomerInsights.Api.All**.

1. בחר **הוסף הרשאות**.

1. חזור אל **הרשאות API** עבור רישום היישום שלך.

1. בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="כיצד להעניק הסכמת מנהל מערכת.":::

1. לסיום, עלינו להוסיף את שם רישום היישום כמשתמש ב- Customer Insights.  
   
   פתח את Customer Insights, עבור אל **ניהול** > **הרשאות** ובחר **הוסף משתמש**.

1. חפש את שם רישום היישום שלך, בחר בו מתוך תוצאות החיפוש ובחר **שמור**.

## <a name="customer-insights-client-libraries"></a>ספריות לקוחות של Customer Insights

מקטע זה עוזר לך להתחיל להשתמש בספריות הלקוחות הזמינות לממשקי ה- API של Customer Insights. ניתן למצוא את כל קוד המקור של הספריה והיישומים לדוגמה [בדף GitHub של Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

למד כיצד להתחיל להשתמש בספריות הלקוחות של C#‎ דרך NuGet‏.org. לקבלת מידע נוסף על חבילת NuGet, ראה [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). נכון לעכשיו, חבילה זו מיועדת למסגרות netstandard2.0 ו- netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>הוסף את ספריית הלקוחות C#‎ לפרוייקט C#‎

1. ב- Visual Studio, פתח את **מנהל החבילות של NuGet** עבור הפרוייקט שלך.

1. חפש את **Microsoft.Dynamics.CustomerInsights.Api**.

1. בחר **התקן** כדי להוסיף את החבילה לפרוייקט.
 
   לחלופין, הפעל פקודה זו ב **קונסולת מנהל החבילות של NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="הוספת חבילת NuGet לפרוייקט Visual Studio":::

#### <a name="use-the-c-client-library"></a>השתמש בספריית הלקוחות C#‎

1. השתמש ב- [Microsoft Authentication Library‏ (MSAL)](/azure/active-directory/develop/msal-overview) כדי לקבל `AccessToken` באמצעות [רישום יישום Azure](#create-a-new-app-registration-in-the-azure-portal) הקיים שלך.

1. לאחר אימות והשגת אסימון בהצלחה, בנה `HttpClient` חדש או השתמש בקיים עם **DefaultRequestHeaders "Authorization"** מוגדר ל- **Bearer <access token>** ו- **Ocp-Apim-Subscription-Key** מוגדר ל [**מפתח מנוי** דרך סביבת Customer Insights שלך](#get-started-trying-the-customer-insights-apis).   
 
   אפס את הכותרת **הרשאה** במועד המתאים. לדוגמה, כאשר פג תוקף האסימון.

1. העבר `HttpClient` זה אל המבנה של הלקוח `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="דוגמה של httpclient":::

1. בצע שיחות עם הלקוח ל"שיטות ההרחבה", למשל `GetAllInstancesAsync`. אם עדיפה גישה ל- `Microsoft.Rest.HttpOperationResponse` הבסיסי, השתמש ב"שיטות הודעת http" - לדוגמה `GetAllInstancesWithHttpMessagesAsync`.

1. התגובה תהיה ככל הנראה מהסוג `object` משום שפעולת השירות יכולה להחזיר סוגים מרובים (לדוגמה, `IList<InstanceInfo>` ו-`ApiErrorResult`). כדי לבדוק את סוג ההחזרה, באפשרותך להמיר בבטחה את האובייקטים לסוגי התגובה המצוינים ב[דף פרטי API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) עבור פעולה זו.    
   
   אם יש צורך במידע נוסף על הבקשה, השתמש ב **פעולות שירות של הודעת https** כדי לגשת לאובייקט התגובה הגולמי.

### <a name="nodejs-package"></a>חבילת NodeJS

השתמש בספריות הלקוח של NodeJS הזמינות דרך NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>חבילת Python

השתמש בספריות הלקוח של Python הזמינות דרך PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
