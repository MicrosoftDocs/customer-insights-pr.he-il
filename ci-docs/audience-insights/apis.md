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
ms.openlocfilehash: 966db1a22e7dece1bcd89733880bce059151157f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267525"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="b4a37-103">עבודה עם ממשקי API של Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b4a37-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="b4a37-104">Dynamics 365 Customer Insights מספק ממשקי API לבניית יישומים משלך בהתבסס על הנתונים שלך ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4a37-104">Dynamics 365 Customer Insights provides APIs to build your own applications based you data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4a37-105">פרטים על ממשקי API אלה מופיעים ב[הפניה לממשקי API של Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="b4a37-105">Details of these APIs, are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="b4a37-106">הם כוללים מידע נוסף על פעולות, פרמטרים ותגובות.</span><span class="sxs-lookup"><span data-stu-id="b4a37-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="b4a37-107">מאמר זה מנחה אותך לגבי גישה לממשקי ה- API של Customer Insights, יצירת רישום יישום של Azure ומסייע לך להתחיל בעבודה עם ספריות הלקוחות הזמינות.</span><span class="sxs-lookup"><span data-stu-id="b4a37-107">This article guides you to access to the Customer Insights APIs, create an Azure App Registration, and help you get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="b4a37-108">התחל לנסות את ממשקי ה- API של Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b4a37-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="b4a37-109">[היכנס](https://home.ci.ai.dynamics.com) אל Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4a37-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="b4a37-110">אם עדיין אין לך מנוי, [הירשם לגירסת ניסיון של Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="b4a37-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="b4a37-111">כדי להפעיל ממשקי API בסביבת Customer Insights שלך, עבור אל **ניהול** > **הרשאות**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="b4a37-112">תזדקק להרשאות מנהל מערכת כדי לעשות זאת.</span><span class="sxs-lookup"><span data-stu-id="b4a37-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="b4a37-113">עבור אל הכרטיסיה **ממשקי API** ובחר בלחצן **הפוך לזמין**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
   <span data-ttu-id="b4a37-114">הפעלת ממשקי ה- API יוצרת מפתח מנוי ראשי ומשני עבור המופע שלך המשמש בבקשות ה- API.</span><span class="sxs-lookup"><span data-stu-id="b4a37-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="b4a37-115">באפשרותך ליצור מחדש את המפתחות על-ידי בחירת **צור מחדש מפתח ראשי** או **צור מחדש מפתח משני** דרך **ניהול** > **הרשאות** > **ממשקי API**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="אפשר ממשקי API של Customer Insights":::

1. <span data-ttu-id="b4a37-117">בחר **סקור את ממשקי ה- API שלנו** כדי לנסות את ממשקי ה- API.</span><span class="sxs-lookup"><span data-stu-id="b4a37-117">Select **Explore our APIs** to try out the APIs.</span></span>

1. <span data-ttu-id="b4a37-118">בחר פעולת API ובחר **נסה זאת**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="b4a37-119">בחלונית הצדדית, הגדר את הערך בתפריט הנפתח **הרשאה** ל **משתמע**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-119">In the side pane, set the value in the **Authorization** drop-down menu to **implicit**.</span></span> <span data-ttu-id="b4a37-120">לכותרת `Authorization` מתווסף אסימון נושא.</span><span class="sxs-lookup"><span data-stu-id="b4a37-120">The `Authorization` header gets with a bearer token added.</span></span> <span data-ttu-id="b4a37-121">מפתח המנוי שלך יאוכלס אוטומטית.</span><span class="sxs-lookup"><span data-stu-id="b4a37-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="b4a37-122">לחלופין, הוסף את כל פרמטרי השאילתה הדרושים.</span><span class="sxs-lookup"><span data-stu-id="b4a37-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="b4a37-123">גלול לתחתית החלונית הצדדית ובחר **שלח**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="b4a37-124">תגובת ה- HTTP תופיע תוך זמן קצר למטה.</span><span class="sxs-lookup"><span data-stu-id="b4a37-124">The HTTP response will soon appear below.</span></span>

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="b4a37-125">יצירת רישום יישום חדש בפורטל Azure</span><span class="sxs-lookup"><span data-stu-id="b4a37-125">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="b4a37-126">שלבים אלה עוזרים לך להתחיל להשתמש בממשקי ה- API של Customer Insights ביישום Azure באמצעות הרשאות בעלות הקצאה.</span><span class="sxs-lookup"><span data-stu-id="b4a37-126">These steps help you get started in using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="b4a37-127">הקפד להשלים תחילה את [מקטע תחילת העבודה](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="b4a37-127">Make sure to have completed [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="b4a37-128">היכנס אל [פורטל Azure](https://portal.azure.com) עם החשבון שיכול לגשת לנתוני Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4a37-128">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="b4a37-129">משמאל, בחר **רישומי יישום**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-129">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="b4a37-130">בחר **רישום חדש**, ספק שם יישום ובחר את סוג החשבון.</span><span class="sxs-lookup"><span data-stu-id="b4a37-130">Select **New registration** provide an application name and choose the account type.</span></span>
   <span data-ttu-id="b4a37-131">לבחירתך, הוסף כתובת URL של ניתוב מחדש.</span><span class="sxs-lookup"><span data-stu-id="b4a37-131">Optionally, add a redirect URL.</span></span> <span data-ttu-id="b4a37-132">http://localhost מספיק לפיתוח יישום במחשב המקומי שלך.</span><span class="sxs-lookup"><span data-stu-id="b4a37-132">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="b4a37-133">ברישום היישום החדש שלך, עבור אל **הרשאות API**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-133">On your new App registration, go to **API permissions**.</span></span>

1. <span data-ttu-id="b4a37-134">בחר **הוסף הרשאה** ובחר **Customer Insights** בחלונית הצדדית.</span><span class="sxs-lookup"><span data-stu-id="b4a37-134">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="b4a37-135">עבור **סוג הרשאה**, בחר **הרשאות מוקצות** ובחר את ההרשאה **התחזות משתמש**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-135">For **Permission type**, select **Delegated permissions** and select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="b4a37-136">בחר **הוסף הרשאות**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-136">Select **Add permissions**.</span></span> <span data-ttu-id="b4a37-137">אם אתה זקוק לגישה ל- API מבלי שמשתמש יתחבר, סקור את המקטע [הרשאות יישום משרת לשרת](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="b4a37-137">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="b4a37-138">בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.</span><span class="sxs-lookup"><span data-stu-id="b4a37-138">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="b4a37-139">באפשרותך להשתמש במזהה היישום/לקוח עבור רישום יישום זה עם Microsoft Authentication Library‏ (MSAL) כדי להשיג אסימון נושא לשליחה עם הבקשה שלך ל- API.</span><span class="sxs-lookup"><span data-stu-id="b4a37-139">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

<span data-ttu-id="b4a37-140">לקבלת מידע נוסף אודות MSAL, ראה [מבט כולל על Microsoft Authentication Library‏ (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="b4a37-140">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="b4a37-141">לקבלת מידע נוסף אודות רישום יישום ב- Azure, ראה [חוויית רישום היישום של פורטל Azure החדשה](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span><span class="sxs-lookup"><span data-stu-id="b4a37-141">For more information about app registration in Azure, see [The new Azure portal app registration experience](https://docs.microsoft.com/azure/active-directory/develop/app-registration-portal-training-guide).</span></span>

<span data-ttu-id="b4a37-142">לקבלת מידע על שימוש בממשקי ה- API בספריות הלקוחות שלנו, ראה [ספריות לקוחות של Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="b4a37-142">For information on using the APIs our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="b4a37-143">הרשאות יישום של שרת לשרת</span><span class="sxs-lookup"><span data-stu-id="b4a37-143">Server-to-server application permissions</span></span>

<span data-ttu-id="b4a37-144">[מקטע רישום יישום](#create-a-new-app-registration-in-the-azure-portal) מפרט כיצד יש לרשום יישום שדורש כניסת משתמש עבור אימות.</span><span class="sxs-lookup"><span data-stu-id="b4a37-144">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="b4a37-145">למד כיצד ליצור רישום יישום שאינו זקוק לאינטראקציית משתמש ויכול לפעול בשרת.</span><span class="sxs-lookup"><span data-stu-id="b4a37-145">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="b4a37-146">ברישום היישום שלך בפורטל Azure, עבור אל **הרשאות API**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-146">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="b4a37-147">בחר **הוסף הרשאה** ובחר **Customer Insights** בחלונית הצדדית.</span><span class="sxs-lookup"><span data-stu-id="b4a37-147">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="b4a37-148">עבור **סוג הרשאה**, בחר **הרשאות יישום** ובחר את ההרשאה **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-148">For **Permission type**, select **Application permissions** and select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="b4a37-149">בחר **הוסף הרשאות**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-149">Select **Add permissions**.</span></span>

1. <span data-ttu-id="b4a37-150">כדי להעניק הסכמת מנהל בהרשאת יישום זו, עליך להוסיף מנהל שירות.</span><span class="sxs-lookup"><span data-stu-id="b4a37-150">To give admin consent on this Application permission, you need to add a Service Principal.</span></span>

   1. <span data-ttu-id="b4a37-151">התקן את Azure Active Directory מודול ‎(AD) PowerShell: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span><span class="sxs-lookup"><span data-stu-id="b4a37-151">Install the Azure Active Directory (AD) PowerShell module: `Install-Module -Name AzureAD -AllowClobber -Scope AllUsers`</span></span>
   1. <span data-ttu-id="b4a37-152">התחבר לחשבון AD שלך: `Connect-AzureAD -TenantId <your tenant id>`.</span><span class="sxs-lookup"><span data-stu-id="b4a37-152">Connect to your AD account: `Connect-AzureAD -TenantId <your tenant id>`.</span></span> <span data-ttu-id="b4a37-153">באפשרותך למצוא את מזהה הדייר שלך ב **מבט כולל** > **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-153">You can find your tenant ID on **Overview** > **Azure Active Directory**.</span></span>
   1. <span data-ttu-id="b4a37-154">הפעל את הפקודה הבאה כדי להוסיף מנהל שירות של Azure AD: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` הפרמטר AppId מתייחס ליישום API של Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4a37-154">Run the following command to add an Azure AD Service Principal: `New-AzureADServicePrincipal -AppId "38c77d00-5fcb-4cce-9d93-af4738258e3c" -DisplayName "Microsoft Dynamics 365 Customer Insights"` The AppId parameter pertains to the Customer Insights API app.</span></span>

   :::image type="content" source="media/azureAD-service-principal.png" alt-text="דוגמה למנהל שירות":::

1. <span data-ttu-id="b4a37-156">חזור אל **הרשאות API** עבור רישום היישום שלך.</span><span class="sxs-lookup"><span data-stu-id="b4a37-156">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="b4a37-157">בחר **הענק הסכמת מנהל עבור...** כדי להשלים את רישום היישום.</span><span class="sxs-lookup"><span data-stu-id="b4a37-157">Select **Grant admin consent for...** to complete the app registration.</span></span>

1. <span data-ttu-id="b4a37-158">לסיום, עלינו להוסיף את שם רישום היישום כמשתמש ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4a37-158">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>    
   <span data-ttu-id="b4a37-159">פתח את Customer Insights, עבור אל **ניהול** > **הרשאות** ובחר **הוסף משתמש**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-159">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="b4a37-160">חפש את שם רישום היישום שלך, בחר בו מתוך תוצאות החיפוש ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-160">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="b4a37-161">ספריות לקוחות של Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b4a37-161">Customer Insights client libraries</span></span>

<span data-ttu-id="b4a37-162">מקטע זה עוזר לך להתחיל להשתמש בספריות הלקוחות הזמינות לממשקי ה- API של Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4a37-162">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span>

### <a name="c-nuget"></a><span data-ttu-id="b4a37-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="b4a37-163">C# NuGet</span></span>

<span data-ttu-id="b4a37-164">למד כיצד להתחיל להשתמש בספריות הלקוחות של C#‎ דרך NuGet‏.org. לקבלת מידע נוסף על חבילת NuGet, ראה [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="b4a37-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="b4a37-165">נכון לעכשיו, חבילה זו מיועדת למסגרות netstandard2.0 ו- netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="b4a37-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="b4a37-166">הוסף את ספריית הלקוחות C#‎ לפרוייקט C#‎</span><span class="sxs-lookup"><span data-stu-id="b4a37-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="b4a37-167">ב- Visual Studio, פתח את **מנהל החבילות של NuGet** עבור הפרוייקט שלך.</span><span class="sxs-lookup"><span data-stu-id="b4a37-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="b4a37-168">חפש את **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="b4a37-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="b4a37-169">בחר **התקן** כדי להוסיף את החבילה לפרוייקט.</span><span class="sxs-lookup"><span data-stu-id="b4a37-169">Select **Install** to add the package to the project.</span></span>
   <span data-ttu-id="b4a37-170">לחלופין, הפעל פקודה זו ב **קונסולת מנהל החבילות של NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="b4a37-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="הוספת חבילת NuGet לפרוייקט Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="b4a37-172">השתמש בספריית הלקוחות C#‎</span><span class="sxs-lookup"><span data-stu-id="b4a37-172">Use the C# client library</span></span>

1. <span data-ttu-id="b4a37-173">השתמש ב- [Microsoft Authentication Library‏ (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) כדי לקבל `AccessToken` באמצעות [רישום יישום Azure](#create-a-new-app-registration-in-the-azure-portal) הקיים שלך.</span><span class="sxs-lookup"><span data-stu-id="b4a37-173">Use the [Microsoft Authentication Library (MSAL)](https://docs.microsoft.com/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="b4a37-174">לאחר אימות והשגת אסימון בהצלחה, בנה `HttpClient` חדש או השתמש בקיים עם **DefaultRequestHeaders "Authorization"** מוגדר ל- **Bearer <access token>** ו- **Ocp-Apim-Subscription-Key** מוגדר ל [**מפתח מנוי** דרך סביבת Customer Insights שלך](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="b4a37-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>    
   <span data-ttu-id="b4a37-175">אפס את הכותרת **הרשאה** במועד המתאים.</span><span class="sxs-lookup"><span data-stu-id="b4a37-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="b4a37-176">לדוגמה, כאשר פג תוקף האסימון.</span><span class="sxs-lookup"><span data-stu-id="b4a37-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="b4a37-177">העבר `HttpClient` זה אל המבנה של הלקוח `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="b4a37-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="דוגמה של httpclient":::

1. <span data-ttu-id="b4a37-179">בצע שיחות עם הלקוח ל"שיטות ההרחבה", למשל, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="b4a37-179">Make calls with the client to the "extension methods", for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="b4a37-180">אם עדיפה גישה ל- `Microsoft.Rest.HttpOperationResponse` הבסיסי, השתמש ב"שיטות הודעת http", לדוגמה, `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="b4a37-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods", for example `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="b4a37-181">התגובה תהיה ככל הנראה מהסוג `object` משום שפעולת השירות יכולה להחזיר סוגים מרובים (לדוגמה, `IList<InstanceInfo>` ו-`ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="b4a37-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="b4a37-182">כדי לבדוק את סוג ההחזרה, באפשרותך להמיר בבטחה את האובייקטים לסוגי התגובה המצוינים ב[דף פרטי API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) עבור פעולה זו.</span><span class="sxs-lookup"><span data-stu-id="b4a37-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   <span data-ttu-id="b4a37-183">אם יש צורך במידע נוסף על הבקשה, השתמש ב **פעולות שירות של הודעת https** כדי לגשת לאובייקט התגובה הגולמי.</span><span class="sxs-lookup"><span data-stu-id="b4a37-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]