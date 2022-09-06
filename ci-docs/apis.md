---
title: עבודה עם ממשקי API של Customer Insights
description: השתמש בממשקי API והכר מגבלות.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387341"
---
# <a name="work-with-customer-insights-apis"></a>עבודה עם ממשקי API של Customer Insights

Dynamics 365 Customer Insights מספק ממשקי API לבניית יישומים משלך בהתבסס על הנתונים שלך ב- Customer Insights.

> [!IMPORTANT]
> פרטים על ממשקי API אלה מפורטים ב[הפניית ממשקי API של Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). הם כוללים מידע נוסף על פעולות, פרמטרים ותגובות.

נסה לעבוד עם ממשקי ה-API של Customer Insights, ליצור רישום אפליקציות של Azure ולהתחיל בעבודה עם ספריות לקוחות.

## <a name="get-started-trying-the-customer-insights-apis"></a>התחל לנסות את ממשקי ה- API של Customer Insights

הפעל את ממשקי ה- API של Customer Insights ונסה אותם. מנהל Customer Insights חייב לאפשר גישת API ל- Customer Insights. לאחר הפעלת הגישה, כל משתמש יכול להשתמש ב- API עם מפתח המנוי.

1. [היכנס](https://home.ci.ai.dynamics.com) אל Customer Insights. אם עדיין אין לך מנוי, [הירשם לגירסת ניסיון של Customer Insights](https://aka.ms/tryci).

1. עבור אל **מנהל מערכת** > **אבטחה**, ולאחר מכן בחר בכרטיסיה **API**.

1. אם לא הוגדרה גישת API לסביבה, בחר **הפוך לזמין**.

   הפעלת ממשקי ה- API יוצרת מפתח מנוי ראשי ומשני עבור המופע שלך המשמש בבקשות ה- API. כדי ליצור מחדש את המפתחות, בחר באפשות **יצירה מחדש של המפתח הראשי** או **יצירה מחדש של המפתח המשני** בכרטיסיה **API**.

1. בחר  [**סקור את ממשקי ה- API**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) כדי לנסות אותם.

1. חפש ובחר פעולת API ובחר **נסה זאת**.

   :::image type="content" source="media/try-api.png" alt-text="כיצד לבדוק את ממשקי ה- API.":::

1. בחלונית הצד, הגדר את הערך בתפריט הנפתח **הרשאה** ל **משתמע**. הכותרת `Authorization` מתווספת עם אסימון נושא. מפתח המנוי שלך מאוכלס אוטומטית.
  
1. לחלופין, הוסף את כל פרמטרי השאילתה הדרושים.

1. גלול לתחתית החלונית הצדדית ובחר **שלח**.

   תגובת ה-HTTP מוצגת בתחתית החלונית.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>יצירת רישום יישום חדש בפורטל Azure

צור [רישום אפליקציה](/graph/auth-register-app-v2) כדי להתחיל להשתמש בממשקי ה- API של Customer Insights ביישום Azure באמצעות הרשאות בעלות הקצאה.

1. השלם את [סעיף תחילת העבודה](#get-started-trying-the-customer-insights-apis).

1. היכנס אל [פורטל Azure](https://portal.azure.com) עם החשבון שיכול לגשת לנתוני Customer Insights.

1. חפש ולאחר מכן בחר **רישומי אפליקציה**.

1. בחר **רישום חדש**, ספק שם יישום ובחר את סוג החשבון.

   לבחירתך, הוסף כתובת URL של ניתוב מחדש. http://localhost מספיק לפיתוח יישום במחשב המקומי שלך.

1. בחר **הירשם**.

1. ברישום היישום החדש שלך, עבור אל **הרשאות API**.

1. בחר **הוסף הרשאה** ובחר **Dynamics 365 AI for Customer Insights** בחלונית הצד.

1. עבור **סוג הרשאה**, בחר **הרשאות שהוקצו** ואז בחר את הרשאת **התחזות למשתמש**.

1. בחר **הוסף הרשאות**.

1. בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.

1. כדי לגשת ל- API מבלי שמשתמש יתחבר, עבור אל [הרשאות יישום משרת לשרת](#server-to-server-application-permissions).

באפשרותך להשתמש במזהה היישום/לקוח עבור רישום יישום זה עם [Microsoft Authentication Library‏ (MSAL)](/azure/active-directory/develop/msal-overview) כדי להשיג אסימון נושא לשליחה עם הבקשה שלך ל- API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

למידע על השימוש בממשקי ה- API בספריות הלקוחות שלנו, ראה [ספריות לקוחות של Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>הרשאות יישום של שרת לשרת

צור רישום אפליקציה שאינה זקוקה לאינטראקציה של המשתמש וניתן להפעיל אותה על שרת.

1. ברישום היישום שלך בפורטל Azure, עבור אל **הרשאות API**.

1. בחר **הוסף הרשאה**.

1. בחר את הכרטיסיה **ממשקי API שהארגון שלי משתמש בהם** ובחר **Dynamics 365 AI for Customer Insights** מתוך הרשימה.

1. עבור **סוג הרשאה**, בחר **הרשאות של יישומים** ואז בחר את הרשאת **CustomerInsights.Api.All**.

1. בחר **הוסף הרשאות**.

1. חזור אל **הרשאות API** עבור רישום היישום שלך.

1. בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. הוסף את שם רישום היישום כמשתמש ב- Customer Insights.

   1. פתח את Customer Insights, עבור אל **מנהל מערכת** > **אבטחה** ובחר **הוסף משתמשים**.

   1. חפש את שם רישום היישום שלך, בחר בו מתוך תוצאות החיפוש ובחר **שמור**.

## <a name="sample-queries"></a>שאילתות לדוגמה

לרשימה קצרה של שאילתות לדוגמה של OData לעבודה עם ממשקי ה-API, ראה [דוגמאות לשאילתות OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>ספריות לקוחות של Customer Insights

התחל להשתמש בספריות הלקוחות הזמינות לממשקי ה- API של Customer Insights. ניתן למצוא את כל קוד המקור של הספריה והיישומים לדוגמה [בדף GitHub של Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

השתמש בספריות לקוח של C# מ-NuGet‏.org. נכון לעכשיו, חבילה זו מיועדת למסגרות netstandard2.0 ו- netcoreapp2.0. למידע נוסף על חבילת NuGet, ראה[Microsoft.Dynamics.CustomerInsights.Api ](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>הוסף את ספריית הלקוחות C#‎ לפרוייקט C#‎

1. ב- Visual Studio, פתח את **מנהל החבילות של NuGet** עבור הפרוייקט שלך.

1. חפש את **Microsoft.Dynamics.CustomerInsights.Api**.

1. בחר **התקן** כדי להוסיף את החבילה לפרוייקט.

   לחלופין, הפעל פקודה זו ב **קונסולת מנהל החבילות של NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>השתמש בספריית הלקוחות C#‎

1. השתמש ב- [Microsoft Authentication Library‏ (MSAL)](/azure/active-directory/develop/msal-overview) כדי לקבל `AccessToken` באמצעות [רישום יישום Azure](#create-a-new-app-registration-in-the-azure-portal) הקיים שלך.

1. לאחר רכישה ואימות מוצלחים של אסימון, בנה `HttpClient` חדש או השתמש בקיים, עם **DefaultRequestHeaders "אימות"** שמוגדר ל- **"אסימון גישה" של נושא** ו- **Ocp-Apim-Subscription-Key** שמוגדרת ל [**מפתח מנוי** מסביבת Customer Insights שלך](#get-started-trying-the-customer-insights-apis).   

   אפס את הכותרת **הרשאה** במועד המתאים. לדוגמה, כאשר פג תוקף האסימון.

1. העבר `HttpClient` זה אל המבנה של הלקוח `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. בצע שיחות עם הלקוח ל"שיטות ההרחבה", למשל, `GetAllInstancesAsync`. אם עדיפה לך גישה אל `Microsoft.Rest.HttpOperationResponse` הבסיסי, השתמש ב"שיטות הודעת http", לדוגמה `GetAllInstancesWithHttpMessagesAsync`.

1. התגובה תהיה ככל הנראה מסוג `object`, כי פעולת השירות יכולה להחזיר סוגים מרובים (לדוגמה, `IList<InstanceInfo>` ו-`ApiErrorResult`). כדי לבדוק את סוג ההחזרה, השתמש באובייקטים בסוגי התגובה שצוינו [בדף פרטי API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) לאותה פעולה.

   אם יש צורך במידע נוסף על הבקשה, השתמש ב **פעולות שירות של הודעת https** כדי לגשת לאובייקט התגובה הגולמי.

### <a name="nodejs-package"></a>חבילת NodeJS

השתמש בספריות הלקוח של NodeJS הזמינות דרך NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>חבילת Python

השתמש בספריות הלקוח של Python הזמינות דרך PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
