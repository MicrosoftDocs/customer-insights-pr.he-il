---
title: התחברות לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות
description: השתמש במנהל שירות של Azure עבור audience insights כדי להתחבר לאגם הנתונים שלך בעת צירופו ל- audience insights.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267723"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="a30df-103">התחברות לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות של Azure עבור audience insights</span><span class="sxs-lookup"><span data-stu-id="a30df-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="a30df-104">כלים אוטומטיים המשתמשים בשירותי Azure צריכים תמיד להיות בעלי הרשאות מוגבלות.</span><span class="sxs-lookup"><span data-stu-id="a30df-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="a30df-105">במקום כניסה ליישומים כמשתמש בעל הרשאות מלאות, Azure מספק מנהלי שירות.</span><span class="sxs-lookup"><span data-stu-id="a30df-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="a30df-106">המשך לקרוא כדי ללמוד כיצד לחבר את audience insights לחשבון Azure Data Lake Storage Gen2 באמצעות מנהל שירות של Azure במקום מפתחות של חשבון אחסון.</span><span class="sxs-lookup"><span data-stu-id="a30df-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="a30df-107">באפשרותך להשתמש במנהל השירות כדי [להוסיף או לערוך תיקיית Common Data Model כמקור נתונים](connect-common-data-model.md) או [ליצור סביבה חדשה או לעדכן סביבה קיימת](manage-environments.md#create-an-environment-in-an-existing-organization) באופן מאובטח.</span><span class="sxs-lookup"><span data-stu-id="a30df-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="a30df-108">חשבון האחסון של Azure Data Lake Gen2 שמתכוון להשתמש במנהל השירות חייב להיות בעל [מרחב שמות הירארכי (HNS) מופעל](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="a30df-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="a30df-109">אתה זקוק להרשאות מנהל עבור המנוי שלך ב- Azure כדי ליצור את מנהל השירות.</span><span class="sxs-lookup"><span data-stu-id="a30df-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="a30df-110">יצירת מנהל שירות של Azure עבור audience insights</span><span class="sxs-lookup"><span data-stu-id="a30df-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="a30df-111">לפני שתיצור מנהל שירות חדש עבור audience insights, בדוק אם הוא קיים כבר בארגון שלך.</span><span class="sxs-lookup"><span data-stu-id="a30df-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="a30df-112">חיפוש מנהל שירות קיים</span><span class="sxs-lookup"><span data-stu-id="a30df-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="a30df-113">עבור אל [פורטל הניהול של Azure](https://portal.azure.com) והיכנס לארגון שלך.</span><span class="sxs-lookup"><span data-stu-id="a30df-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="a30df-114">בחר את **Azure Active Directory** משירותי Azure.</span><span class="sxs-lookup"><span data-stu-id="a30df-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="a30df-115">תחת **ניהול**, בחר **יישומים ארגוניים**.</span><span class="sxs-lookup"><span data-stu-id="a30df-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="a30df-116">חפש את מזהה היישום של הצד הראשון של תובנות הקהל `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` או את השם `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="a30df-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="a30df-117">אם אתה מוצא רשומה תואמת, המשמעות היא שמנהל השירות של audience insights קיים.</span><span class="sxs-lookup"><span data-stu-id="a30df-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="a30df-118">אינך צריך ליצור אותו שוב.</span><span class="sxs-lookup"><span data-stu-id="a30df-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="צילום מסך המציג את מנהל השירות הקיים.":::
   
6. <span data-ttu-id="a30df-120">אם לא מוחזרות תוצאות, צור מנהל שירות חדש.</span><span class="sxs-lookup"><span data-stu-id="a30df-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="a30df-121">יצירת מנהל שירות חדש</span><span class="sxs-lookup"><span data-stu-id="a30df-121">Create a new service principal</span></span>

1. <span data-ttu-id="a30df-122">התקן את הגירסה האחרונה של **Azure Active Directory PowerShell for Graph**.</span><span class="sxs-lookup"><span data-stu-id="a30df-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="a30df-123">לקבלת מידע נוסף, ראה [התקנת Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="a30df-123">For more information, see [Install Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="a30df-124">במחשב שלך, בחר את מקש Windows במקלדת שלך וחפש את **Windows PowerShell** ואת **הפעל כמנהל מערכת**.</span><span class="sxs-lookup"><span data-stu-id="a30df-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="a30df-125">בחלון PowerShell שנפתח, הזן `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="a30df-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="a30df-126">צור את מנהל השירות עבור audience insights עם מודול PowerShell של Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a30df-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="a30df-127">בחלון PowerShell, הזן `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="a30df-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="a30df-128">החלף את "מזהה הדייר שלך" במזהה בפועל של הדייר שלך שבו ברצונך ליצור את מנהל השירות.</span><span class="sxs-lookup"><span data-stu-id="a30df-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="a30df-129">פרמטר שם הסביבה `AzureEnvironmentName` הוא אופציונלי.</span><span class="sxs-lookup"><span data-stu-id="a30df-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="a30df-130">הזן `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="a30df-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="a30df-131">פקודה זו יוצרת את מנהל השירות עבור audience insights בדייר שנבחר.</span><span class="sxs-lookup"><span data-stu-id="a30df-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="a30df-132">הענק הרשאות למנהל השירות כדי לגשת לחשבון האחסון</span><span class="sxs-lookup"><span data-stu-id="a30df-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="a30df-133">עבור לפורטל Azure כדי להעניק הרשאות למנהל השירות עבור חשבון האחסון שבו ברצונך להשתמש ב- audience insights.</span><span class="sxs-lookup"><span data-stu-id="a30df-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="a30df-134">עבור אל [פורטל הניהול של Azure](https://portal.azure.com) והיכנס לארגון שלך.</span><span class="sxs-lookup"><span data-stu-id="a30df-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="a30df-135">פתח את חשבון האחסון שאליו אתה רוצה שתהיה למנהל השירות עבור audience insights גישה.</span><span class="sxs-lookup"><span data-stu-id="a30df-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="a30df-136">בחר **בקרת גישה (IAM)** מתוך חלונית הניווט ובחר **הוסף** > **הוסף הקצאת תפקיד**.</span><span class="sxs-lookup"><span data-stu-id="a30df-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="צילום מסך המציג את פורטל Azure במהלך הוספת הקצאת תפקיד.":::
   
1. <span data-ttu-id="a30df-138">בחלונית **הוסף הקצאת תפקיד**, הגדר את המאפיינים הבאים:</span><span class="sxs-lookup"><span data-stu-id="a30df-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="a30df-139">תפקיד: *תורם נתונים של Blob אחסון*</span><span class="sxs-lookup"><span data-stu-id="a30df-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="a30df-140">הקצה גישה ל: *משתמש, קבוצה או מנהל שירות*</span><span class="sxs-lookup"><span data-stu-id="a30df-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="a30df-141">בחר: *Dynamics 365 AI for Customer Insights* ([מנהל השירות שיצרת](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="a30df-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="a30df-142">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="a30df-142">Select **Save**.</span></span>

<span data-ttu-id="a30df-143">הפצת השינויים עשויה להימשך עד 15 דקות.</span><span class="sxs-lookup"><span data-stu-id="a30df-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="a30df-144">הזן את מזהה משאב Azure או את פרטי מנוי Azure בקובץ המצורף לחשבון האחסון ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="a30df-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="a30df-145">צרף חשבון אחסון ב- Azure Data Lake ל- Audience Insights כדי [לאחסן נתוני פלט](manage-environments.md) או [השתמש בו כמקור נתונים](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="a30df-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="a30df-146">הבחירה באפשרות Azure Data Lake מאפשרת לבחור בין גישה מבוססת-משאב או גישה מבוססת-מנוי.</span><span class="sxs-lookup"><span data-stu-id="a30df-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="a30df-147">בצע את השלבים הבאים כדי לספק את המידע הנדרש על הגישה שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="a30df-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="a30df-148">חיבור לחשבון אחסון מבוסס-משאב</span><span class="sxs-lookup"><span data-stu-id="a30df-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="a30df-149">עבור אל [פורטל הניהול של Azure](https://portal.azure.com), היכנס למנוי שלך ופתח את חשבון האחסון.</span><span class="sxs-lookup"><span data-stu-id="a30df-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="a30df-150">עבור אל **הגדרות** > **מאפיינים** בחלונית הניווט.</span><span class="sxs-lookup"><span data-stu-id="a30df-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="a30df-151">העתק את ערך המזהה של משאב חשבון האחסון.</span><span class="sxs-lookup"><span data-stu-id="a30df-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="העתק את המזהה של משאב חשבון האחסון.":::

1. <span data-ttu-id="a30df-153">ב- Audience Insights, הוסף את מזהה המשאב בשדה המשאב המוצג במסך של חיבור חשבון האחסון.</span><span class="sxs-lookup"><span data-stu-id="a30df-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="הזן את מידע המזהה של משאב חשבון האחסון.":::   
   
1. <span data-ttu-id="a30df-155">המשך בשלבים הנותרים ב- Audience Insights כדי לצרף את חשבון האחסון.</span><span class="sxs-lookup"><span data-stu-id="a30df-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="a30df-156">חיבור לחשבון אחסון מבוסס-מנוי</span><span class="sxs-lookup"><span data-stu-id="a30df-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="a30df-157">עבור אל [פורטל הניהול של Azure](https://portal.azure.com), היכנס למנוי שלך ופתח את חשבון האחסון.</span><span class="sxs-lookup"><span data-stu-id="a30df-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="a30df-158">עבור אל **הגדרות** > **מאפיינים** בחלונית הניווט.</span><span class="sxs-lookup"><span data-stu-id="a30df-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="a30df-159">סקור את **מנוי**, **קבוצת משאבים** ו **שם** של חשבון האחסון כדי לוודא שאתה בוחר את הערכים המתאימים ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="a30df-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="a30df-160">ב- Audience Insights, בחר את הערכים עבור השדות המתאימים בעת צירוף חשבון האחסון.</span><span class="sxs-lookup"><span data-stu-id="a30df-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="a30df-161">המשך בשלבים הנותרים ב- Audience Insights כדי לצרף את חשבון האחסון.</span><span class="sxs-lookup"><span data-stu-id="a30df-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]