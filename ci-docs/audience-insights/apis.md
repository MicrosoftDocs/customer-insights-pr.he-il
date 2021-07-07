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
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="20bff-103">עבודה עם ממשקי API של Customer Insights</span><span class="sxs-lookup"><span data-stu-id="20bff-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="20bff-104">Dynamics 365 Customer Insights מספק ממשקי API לבניית יישומים משלך בהתבסס על הנתונים שלך ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="20bff-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="20bff-105">פרטים על ממשקי API אלה מפורטים ב[הפניית ממשקי API של Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="20bff-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="20bff-106">הם כוללים מידע נוסף על פעולות, פרמטרים ותגובות.</span><span class="sxs-lookup"><span data-stu-id="20bff-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="20bff-107">מאמר זה מתאר כיצד לגשת לממשקי API של Customer Insights, ליצור רישום של יישום Azure ולהתחיל בספריות הלקוחות הזמינות.</span><span class="sxs-lookup"><span data-stu-id="20bff-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="20bff-108">התחל לנסות את ממשקי ה- API של Customer Insights</span><span class="sxs-lookup"><span data-stu-id="20bff-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="20bff-109">[היכנס](https://home.ci.ai.dynamics.com) אל Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="20bff-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="20bff-110">אם עדיין אין לך מנוי, [הירשם לגירסת ניסיון של Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="20bff-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="20bff-111">כדי להפעיל ממשקי API בסביבת Customer Insights שלך, עבור אל **ניהול** > **הרשאות**.</span><span class="sxs-lookup"><span data-stu-id="20bff-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="20bff-112">תזדקק להרשאות מנהל מערכת כדי לעשות זאת.</span><span class="sxs-lookup"><span data-stu-id="20bff-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="20bff-113">עבור אל הכרטיסיה **ממשקי API** ובחר בלחצן **הפוך לזמין**.</span><span class="sxs-lookup"><span data-stu-id="20bff-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="20bff-114">הפעלת ממשקי ה- API יוצרת מפתח מנוי ראשי ומשני עבור המופע שלך המשמש בבקשות ה- API.</span><span class="sxs-lookup"><span data-stu-id="20bff-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="20bff-115">באפשרותך ליצור מחדש את המפתחות על-ידי בחירת **צור מחדש מפתח ראשי** או **צור מחדש מפתח משני** דרך **ניהול** > **הרשאות** > **ממשקי API**.</span><span class="sxs-lookup"><span data-stu-id="20bff-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="אפשר ממשקי API של Customer Insights":::

1. <span data-ttu-id="20bff-117">בחר **סקור את ממשקי ה- API שלנו** כדי [לנסות את ממשקי ה- API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="20bff-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="20bff-118">בחר פעולת API ובחר **נסה זאת**.</span><span class="sxs-lookup"><span data-stu-id="20bff-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="20bff-119">בחלונית הצד, הגדר את הערך בתפריט הנפתח **הרשאה** ל **משתמע**.</span><span class="sxs-lookup"><span data-stu-id="20bff-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="20bff-120">הכותרת `Authorization` מתווספת עם אסימון נושא.</span><span class="sxs-lookup"><span data-stu-id="20bff-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="20bff-121">מפתח המנוי שלך יאוכלס אוטומטית.</span><span class="sxs-lookup"><span data-stu-id="20bff-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="20bff-122">לחלופין, הוסף את כל פרמטרי השאילתה הדרושים.</span><span class="sxs-lookup"><span data-stu-id="20bff-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="20bff-123">גלול לתחתית החלונית הצדדית ובחר **שלח**.</span><span class="sxs-lookup"><span data-stu-id="20bff-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="20bff-124">תגובת ה- HTTP תופיע תוך זמן קצר למטה.</span><span class="sxs-lookup"><span data-stu-id="20bff-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="כיצד לבדוק את ממשקי ה- API.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="20bff-126">יצירת רישום יישום חדש בפורטל Azure</span><span class="sxs-lookup"><span data-stu-id="20bff-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="20bff-127">שלבים אלה עוזרים לך להתחיל להשתמש בממשקי ה- API של Customer Insights ביישום Azure באמצעות הרשאות מוקצות.</span><span class="sxs-lookup"><span data-stu-id="20bff-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="20bff-128">הקפד להשלים את [מקטע תחילת העבודה](#get-started-trying-the-customer-insights-apis) תחילה.</span><span class="sxs-lookup"><span data-stu-id="20bff-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="20bff-129">היכנס אל [פורטל Azure](https://portal.azure.com) עם החשבון שיכול לגשת לנתוני Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="20bff-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="20bff-130">משמאל, בחר **רישומי יישום**.</span><span class="sxs-lookup"><span data-stu-id="20bff-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="20bff-131">בחר **רישום חדש**, ספק שם יישום ובחר את סוג החשבון.</span><span class="sxs-lookup"><span data-stu-id="20bff-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="20bff-132">לבחירתך, הוסף כתובת URL של ניתוב מחדש.</span><span class="sxs-lookup"><span data-stu-id="20bff-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="20bff-133">http://localhost מספיק לפיתוח יישום במחשב המקומי שלך.</span><span class="sxs-lookup"><span data-stu-id="20bff-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="20bff-134">ברישום היישום החדש שלך, עבור אל **הרשאות API**.</span><span class="sxs-lookup"><span data-stu-id="20bff-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="כיצד להגדיר הרשאות API ברישום יישומים.":::

1. <span data-ttu-id="20bff-136">בחר **הוסף הרשאה** ובחר **Customer Insights** בחלונית הצדדית.</span><span class="sxs-lookup"><span data-stu-id="20bff-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="20bff-137">עבור **סוג הרשאה**, בחר **הרשאות שהוקצו** ואז בחר את הרשאת **התחזות למשתמש**.</span><span class="sxs-lookup"><span data-stu-id="20bff-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="20bff-138">בחר **הוסף הרשאות**.</span><span class="sxs-lookup"><span data-stu-id="20bff-138">Select **Add permissions**.</span></span> <span data-ttu-id="20bff-139">אם אתה זקוק לגישה ל- API מבלי שמשתמש יתחבר, סקור את המקטע [הרשאות יישום משרת לשרת](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="20bff-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="20bff-140">בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.</span><span class="sxs-lookup"><span data-stu-id="20bff-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="20bff-141">באפשרותך להשתמש במזהה היישום/לקוח עבור רישום יישום זה עם Microsoft Authentication Library‏ (MSAL) כדי להשיג אסימון נושא לשליחה עם הבקשה שלך ל- API.</span><span class="sxs-lookup"><span data-stu-id="20bff-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="כיצד להעניק הסכמת מנהל מערכת.":::

<span data-ttu-id="20bff-143">לקבלת מידע נוסף אודות MSAL, ראה [מבט כולל על Microsoft Authentication Library‏ (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="20bff-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="20bff-144">לקבלת מידע נוסף על רישום יישומים ב- Azure, ראה [רישום בקשה](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="20bff-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="20bff-145">למידע על השימוש בממשקי ה- API בספריות הלקוחות שלנו, ראה [ספריות לקוחות של Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="20bff-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="20bff-146">הרשאות יישום של שרת לשרת</span><span class="sxs-lookup"><span data-stu-id="20bff-146">Server-to-server application permissions</span></span>

<span data-ttu-id="20bff-147">[מקטע רישום יישום](#create-a-new-app-registration-in-the-azure-portal) מפרט כיצד יש לרשום יישום שדורש כניסת משתמש עבור אימות.</span><span class="sxs-lookup"><span data-stu-id="20bff-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="20bff-148">למד כיצד ליצור רישום יישום שאינו זקוק לאינטראקציית משתמש ויכול לפעול בשרת.</span><span class="sxs-lookup"><span data-stu-id="20bff-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="20bff-149">ברישום היישום שלך בפורטל Azure, עבור אל **הרשאות API**.</span><span class="sxs-lookup"><span data-stu-id="20bff-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="20bff-150">בחר **הוסף הרשאה**.</span><span class="sxs-lookup"><span data-stu-id="20bff-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="20bff-151">בחר את הכרטיסיה **ממשקי API שהארגון שלי משתמש בהם** ובחר **Dynamics 365 AI for Customer Insights** מתוך הרשימה.</span><span class="sxs-lookup"><span data-stu-id="20bff-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="20bff-152">עבור **סוג הרשאה**, בחר **הרשאות של יישומים** ואז בחר את הרשאת **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="20bff-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="20bff-153">בחר **הוסף הרשאות**.</span><span class="sxs-lookup"><span data-stu-id="20bff-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="20bff-154">חזור אל **הרשאות API** עבור רישום היישום שלך.</span><span class="sxs-lookup"><span data-stu-id="20bff-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="20bff-155">בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.</span><span class="sxs-lookup"><span data-stu-id="20bff-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="כיצד להעניק הסכמת מנהל מערכת.":::

1. <span data-ttu-id="20bff-157">לסיום, עלינו להוסיף את שם רישום היישום כמשתמש ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="20bff-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="20bff-158">פתח את Customer Insights, עבור אל **ניהול** > **הרשאות** ובחר **הוסף משתמש**.</span><span class="sxs-lookup"><span data-stu-id="20bff-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="20bff-159">חפש את שם רישום היישום שלך, בחר בו מתוך תוצאות החיפוש ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="20bff-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="20bff-160">ספריות לקוחות של Customer Insights</span><span class="sxs-lookup"><span data-stu-id="20bff-160">Customer Insights client libraries</span></span>

<span data-ttu-id="20bff-161">מקטע זה עוזר לך להתחיל להשתמש בספריות הלקוחות הזמינות לממשקי ה- API של Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="20bff-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="20bff-162">ניתן למצוא את כל קוד המקור של הספריה והיישומים לדוגמה [בדף GitHub של Customer Insights](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="20bff-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="20bff-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="20bff-163">C# NuGet</span></span>

<span data-ttu-id="20bff-164">למד כיצד להתחיל להשתמש בספריות הלקוחות של C#‎ דרך NuGet‏.org. לקבלת מידע נוסף על חבילת NuGet, ראה [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="20bff-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="20bff-165">נכון לעכשיו, חבילה זו מיועדת למסגרות netstandard2.0 ו- netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="20bff-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="20bff-166">הוסף את ספריית הלקוחות C#‎ לפרוייקט C#‎</span><span class="sxs-lookup"><span data-stu-id="20bff-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="20bff-167">ב- Visual Studio, פתח את **מנהל החבילות של NuGet** עבור הפרוייקט שלך.</span><span class="sxs-lookup"><span data-stu-id="20bff-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="20bff-168">חפש את **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="20bff-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="20bff-169">בחר **התקן** כדי להוסיף את החבילה לפרוייקט.</span><span class="sxs-lookup"><span data-stu-id="20bff-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="20bff-170">לחלופין, הפעל פקודה זו ב **קונסולת מנהל החבילות של NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="20bff-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="הוספת חבילת NuGet לפרוייקט Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="20bff-172">השתמש בספריית הלקוחות C#‎</span><span class="sxs-lookup"><span data-stu-id="20bff-172">Use the C# client library</span></span>

1. <span data-ttu-id="20bff-173">השתמש ב- [Microsoft Authentication Library‏ (MSAL)](/azure/active-directory/develop/msal-overview) כדי לקבל `AccessToken` באמצעות [רישום יישום Azure](#create-a-new-app-registration-in-the-azure-portal) הקיים שלך.</span><span class="sxs-lookup"><span data-stu-id="20bff-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="20bff-174">לאחר אימות והשגת אסימון בהצלחה, בנה `HttpClient` חדש או השתמש בקיים עם **DefaultRequestHeaders "Authorization"** מוגדר ל- **Bearer <access token>** ו- **Ocp-Apim-Subscription-Key** מוגדר ל [**מפתח מנוי** דרך סביבת Customer Insights שלך](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="20bff-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="20bff-175">אפס את הכותרת **הרשאה** במועד המתאים.</span><span class="sxs-lookup"><span data-stu-id="20bff-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="20bff-176">לדוגמה, כאשר פג תוקף האסימון.</span><span class="sxs-lookup"><span data-stu-id="20bff-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="20bff-177">העבר `HttpClient` זה אל המבנה של הלקוח `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="20bff-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="דוגמה של httpclient":::

1. <span data-ttu-id="20bff-179">בצע שיחות עם הלקוח ל"שיטות ההרחבה", למשל `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="20bff-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="20bff-180">אם עדיפה גישה ל- `Microsoft.Rest.HttpOperationResponse` הבסיסי, השתמש ב"שיטות הודעת http" - לדוגמה `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="20bff-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="20bff-181">התגובה תהיה ככל הנראה מהסוג `object` משום שפעולת השירות יכולה להחזיר סוגים מרובים (לדוגמה, `IList<InstanceInfo>` ו-`ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="20bff-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="20bff-182">כדי לבדוק את סוג ההחזרה, באפשרותך להמיר בבטחה את האובייקטים לסוגי התגובה המצוינים ב[דף פרטי API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) עבור פעולה זו.</span><span class="sxs-lookup"><span data-stu-id="20bff-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="20bff-183">אם יש צורך במידע נוסף על הבקשה, השתמש ב **פעולות שירות של הודעת https** כדי לגשת לאובייקט התגובה הגולמי.</span><span class="sxs-lookup"><span data-stu-id="20bff-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="20bff-184">חבילת NodeJS</span><span class="sxs-lookup"><span data-stu-id="20bff-184">NodeJS package</span></span>

<span data-ttu-id="20bff-185">השתמש בספריות הלקוח של NodeJS הזמינות דרך NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="20bff-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="20bff-186">חבילת Python</span><span class="sxs-lookup"><span data-stu-id="20bff-186">Python package</span></span>

<span data-ttu-id="20bff-187">השתמש בספריות הלקוח של Python הזמינות דרך PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="20bff-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
