---
title: עבודה עם ממשקי API
description: השתמש בממשקי API והכר מגבלות.
ms.date: 12/04/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a03e916676800afdd8692da865a1060952d5c4f
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689131"
---
# <a name="work-with-customer-insights-apis"></a>עבודה עם ממשקי API של Customer Insights

Dynamics 365 Customer Insights מספק ממשקי API לבניית יישומים משלך בהתבסס על הנתונים שלך ב- Customer Insights.

> [!IMPORTANT]
> פרטים על ממשקי API אלה מופיעים ב[הפניה לממשקי API של Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). הם כוללים מידע נוסף על פעולות, פרמטרים ותגובות.

מאמר זה מנחה אותך לגבי גישה לממשקי ה- API של Customer Insights, יצירת רישום יישום של Azure ומסייע לך להתחיל בעבודה עם ספריות הלקוחות הזמינות.

## <a name="get-started-trying-the-customer-insights-apis"></a>התחל לנסות את ממשקי ה- API של Customer Insights

1. [היכנס](https://home.ci.ai.dynamics.com) אל Customer Insights. אם עדיין אין לך מנוי, [הירשם לגירסת ניסיון של Customer Insights](https://aka.ms/tryci).

1. כדי להפעיל ממשקי API בסביבת Customer Insights שלך, עבור אל **ניהול** > **הרשאות**. תזדקק להרשאות מנהל מערכת כדי לעשות זאת.

1. עבור אל הכרטיסיה **ממשקי API** ובחר בלחצן **הפוך לזמין**.    
   הפעלת ממשקי ה- API יוצרת מפתח מנוי ראשי ומשני עבור המופע שלך המשמש בבקשות ה- API. באפשרותך ליצור מחדש את המפתחות על-ידי בחירת **צור מחדש מפתח ראשי** או **צור מחדש מפתח משני** דרך **ניהול** > **הרשאות** > **ממשקי API**.

   :::image type="content" source="media/enable-apis.gif" alt-text="אפשר ממשקי API של Customer Insights":::

1. בחר **סקור את ממשקי ה- API שלנו** כדי לנסות את ממשקי ה- API.

1. בחר פעולת API ובחר **נסה זאת**.

1. בחלונית הצדדית, הגדר את הערך בתפריט הנפתח **הרשאה** ל **משתמע**. לכותרת `Authorization` מתווסף אסימון נושא. מפתח המנוי שלך יאוכלס אוטומטית.
  
1. לחלופין, הוסף את כל פרמטרי השאילתה הדרושים.

1. גלול לתחתית החלונית הצדדית ובחר **שלח**.

תגובת ה- HTTP תופיע תוך זמן קצר למטה.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>יצירת רישום יישום חדש בפורטל Azure

שלבים אלה עוזרים לך להתחיל להשתמש בממשקי ה- API של Customer Insights ביישום Azure באמצעות הרשאות בעלות הקצאה. הקפד להשלים תחילה את [מקטע תחילת העבודה](#get-started-trying-the-customer-insights-apis).

1. היכנס אל [פורטל Azure](https://portal.azure.com) עם החשבון שיכול לגשת לנתוני Customer Insights.

1. משמאל, בחר **רישומי יישום**.

1. בחר **רישום חדש**, ספק שם יישום ובחר את סוג החשבון.
   לבחירתך, הוסף כתובת URL של ניתוב מחדש. http://localhost מספיק לפיתוח יישום במחשב המקומי שלך.

1. ברישום היישום החדש שלך, עבור אל **הרשאות API**.

1. בחר **הוסף הרשאה** ובחר **Customer Insights** בחלונית הצדדית.

1. עבור **סוג הרשאה**, בחר **הרשאות מוקצות** ובחר את ההרשאה **התחזות משתמש**.

1. בחר **הוסף הרשאות**. אם אתה זקוק לגישה ל- API מבלי שמשתמש יתחבר, סקור את המקטע [הרשאות יישום משרת לשרת](#server-to-server-application-permissions).

1. בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.

באפשרותך להשתמש במזהה היישום/לקוח עבור רישום יישום זה עם Microsoft Authentication Library‏ (MSAL) כדי להשיג אסימון נושא לשליחה עם הבקשה שלך ל- API.

לקבלת מידע נוסף אודות MSAL, ראה [מבט כולל על Microsoft Authentication Library‏ (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).

לקבלת מידע נוסף אודות רישום יישום ב- Azure, ראה [חוויית רישום היישום של פורטל Azure החדשה](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).

לקבלת מידע על שימוש בממשקי ה- API בספריות הלקוחות שלנו, ראה [ספריות לקוחות של Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>הרשאות יישום של שרת לשרת

[מקטע רישום יישום](#create-a-new-app-registration-in-the-azure-portal) מפרט כיצד יש לרשום יישום שדורש כניסת משתמש עבור אימות. למד כיצד ליצור רישום יישום שאינו זקוק לאינטראקציית משתמש ויכול לפעול בשרת.

1. ברישום היישום שלך בפורטל Azure, עבור אל **הרשאות API**.

1. בחר **הוסף הרשאה** ובחר **Customer Insights** בחלונית הצדדית.

1. עבור **סוג הרשאה**, בחר **הרשאות יישום** ובחר את ההרשאה **CustomerInsights.Api.All**.

1. בחר **הוסף הרשאות**.

1. כדי להעניק הסכמת מנהל בהרשאת יישום זו, עליך להוסיף מנהל שירות.

   1. התקן את Azure Active Directory מודול ‎(AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`
   1. התחבר לחשבון AD שלך: `Connect-AzureAD -TenantId <your tenant id>`. באפשרותך למצוא את מזהה הדייר שלך ב **מבט כולל** > **Azure Active Directory**.
   1. הפעל את הפקודה הבאה כדי להוסיף מנהל שירות של Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` הפרמטר AppId מתייחס ליישום API של Customer Insights.

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="דוגמה למנהל שירות":::

1. חזור אל **הרשאות API** עבור רישום היישום שלך.

1. בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.

1. לסיום, עלינו להוסיף את שם רישום היישום כמשתמש ב- Customer Insights.    
   פתח את Customer Insights, עבור אל **ניהול** > **הרשאות** ובחר **הוסף משתמש**.

1. חפש את שם רישום היישום שלך, בחר בו מתוך תוצאות החיפוש ובחר **שמור**.

## <a name="customer-insights-client-libraries"></a>ספריות לקוחות של Customer Insights

מקטע זה עוזר לך להתחיל להשתמש בספריות הלקוחות הזמינות לממשקי ה- API של Customer Insights.

### <a name="c-nuget"></a>C# NuGet

למד כיצד להתחיל להשתמש בספריות הלקוחות של C#‎ דרך NuGet‏.org. לקבלת מידע נוסף על חבילת NuGet, ראה [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). נכון לעכשיו, חבילה זו מיועדת למסגרות netstandard2.0 ו- netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>הוסף את ספריית הלקוחות C#‎ לפרוייקט C#‎

1. ב- Visual Studio, פתח את **מנהל החבילות של NuGet** עבור הפרוייקט שלך.

1. חפש את **Microsoft.Dynamics.CustomerInsights.Api**.

1. בחר **התקן** כדי להוסיף את החבילה לפרוייקט.
   לחלופין, הפעל פקודה זו ב **קונסולת מנהל החבילות של NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="הוספת חבילת NuGet לפרוייקט Visual Studio":::

#### <a name="use-the-c-client-library"></a>השתמש בספריית הלקוחות C#‎

1. השתמש ב- [Microsoft Authentication Library‏ (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) כדי לקבל `AccessToken` באמצעות [רישום יישום Azure](#create-a-new-app-registration-in-the-azure-portal) הקיים שלך.

1. לאחר אימות והשגת אסימון בהצלחה, בנה `HttpClient` חדש או השתמש בקיים עם **DefaultRequestHeaders "Authorization"** מוגדר ל- **Bearer <access token>** ו- **Ocp-Apim-Subscription-Key** מוגדר ל [**מפתח מנוי** דרך סביבת Customer Insights שלך](#get-started-trying-the-customer-insights-apis).    
   אפס את הכותרת **הרשאה** במועד המתאים. לדוגמה, כאשר פג תוקף האסימון.

1. העבר `HttpClient` זה אל המבנה של הלקוח `CustomerInsights`.

   :::image type="content" source="media/httpclient-sample.png" alt-text="דוגמה של httpclient":::

1. בצע שיחות עם הלקוח ל"שיטות ההרחבה", למשל, `GetAllInstancesAsync`. אם עדיפה גישה ל- `Microsoft.Rest.HttpOperationResponse` הבסיסי, השתמש ב"שיטות הודעת http", לדוגמה, `GetAllInstancesWithHttpMessagesAsync`.

1. התגובה תהיה ככל הנראה מהסוג `object` משום שפעולת השירות יכולה להחזיר סוגים מרובים (לדוגמה, `IList<InstanceInfo>` ו-`ApiErrorResult`). כדי לבדוק את סוג ההחזרה, באפשרותך להמיר בבטחה את האובייקטים לסוגי התגובה המצוינים ב[דף פרטי API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) עבור פעולה זו.    
   אם יש צורך במידע נוסף על הבקשה, השתמש ב **פעולות שירות של הודעת https** כדי לגשת לאובייקט התגובה הגולמי.
