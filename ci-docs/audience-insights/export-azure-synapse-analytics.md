---
title: ייצוא נתוני Customer Insights אל Azure Synapse Analytics
description: למד כיצד להגדיר את החיבור ולייצא אל Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977378"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="90ca0-103">ייצא נתונים אל Azure Synapse Analytics (גירסת Preview)</span><span class="sxs-lookup"><span data-stu-id="90ca0-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="90ca0-104">Azure Synapse הוא שירות ניתוח שמזרז את הזמן להשגת תובנה בין מחסני נתונים ומערכות Big Data.</span><span class="sxs-lookup"><span data-stu-id="90ca0-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="90ca0-105">אתה יכול לעבד את נתוני Customer Insights ולהשתמש בהם ב- [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="90ca0-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="90ca0-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="90ca0-106">Prerequisites</span></span>

<span data-ttu-id="90ca0-107">יש לעמוד בדרישות המוקדמות הבאות כדי להגדיר את החיבור מ- Customer Insights אל Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="90ca0-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="90ca0-108">הקפד להגדיר את כל **הקצאות התפקידים** כפי שתואר.</span><span class="sxs-lookup"><span data-stu-id="90ca0-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="90ca0-109">דרישות מוקבמות ב- Customer Insights</span><span class="sxs-lookup"><span data-stu-id="90ca0-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="90ca0-110">אתה בעל תפקיד **מנהל מערכת** בתובנות לגבי קהלים‬.</span><span class="sxs-lookup"><span data-stu-id="90ca0-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="90ca0-111">למידע נוסף על [הגדרת הרשאות משתמש בתובנות לגבי קהלים‬](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="90ca0-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="90ca0-112">ב- Azure:</span><span class="sxs-lookup"><span data-stu-id="90ca0-112">In Azure:</span></span> 

- <span data-ttu-id="90ca0-113">מנוי פעיל של Azure.</span><span class="sxs-lookup"><span data-stu-id="90ca0-113">An active Azure subscription.</span></span>

- <span data-ttu-id="90ca0-114">אם אתה משתמש בחשבון חדש של Azure Data Lake Storage Gen2, *מנהל שירות של תובנות לגבי קהלים‬* זקוק להרשאות מסוג **תורם נתונים של Blob אחסון**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="90ca0-115">למידע נוסף על [התחברות לחשבון Azure Data Lake Storage ‏Gen2 עם מנהל שירות Azure עבור תובנות לגבי קהלים](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="90ca0-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="90ca0-116">Data Lake Storage Gen2 **חייב להפעיל** [מרחב שמות הירארכי](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="90ca0-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="90ca0-117">בקבוצת המשאבים שבו ממוקמת סביבת העבודה של Azure Synapse, יש להקצות לתפקידים *מנהל שירות* ו *משתמש עבור תובנות לגבי קהלים* הרשאות מסוג **קורא** לפחות.</span><span class="sxs-lookup"><span data-stu-id="90ca0-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="90ca0-118">למידע נוסף, ראה [הקצאת תפקידי Azure באמצעות פורטל Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="90ca0-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="90ca0-119">ה *משתמש* זקוק להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="90ca0-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="90ca0-120">למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="90ca0-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="90ca0-121">ה *זהות המנוהלת של סביבת העבודה של [Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* זקוקה להרשאות מסוג **תורם נתונים של Blob אחסון** בחשבון Azure Data Lake Storage  Gen2 שבו הנתונים ממוקמים ומקושרים אל סביבת העבודה Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="90ca0-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="90ca0-122">למידע נוסף על [השימוש בפורטל Azure כדי להקצות תפקיד Azure לצורך גישה לנתוני Blob ולנתוני תור](/azure/storage/common/storage-auth-aad-rbac-portal) ועל [הרשאות תורם נתונים של Blob אחסון](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="90ca0-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="90ca0-123">בסביבת העבודה של Azure Synapse, *מנהל השירות של תובנות לגבי קהלים* זקוק להקצאת תפקיד של **מנהל Synapse**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="90ca0-124">למידע נוסף, ראה [כיצד להגדיר בקרת גישה עבור סביבת העבודה שלך ב- Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="90ca0-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="90ca0-125">הגדרת החיבור וייצוא אל Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="90ca0-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="90ca0-126">קביעת תצורה של חיבור</span><span class="sxs-lookup"><span data-stu-id="90ca0-126">Configure a connection</span></span>

1. <span data-ttu-id="90ca0-127">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="90ca0-128">בחר **הוסף חיבור** ובחר **Azure Synapse ‏Analytics** או בחר **הגדר** באריח **Azure Synapse Analytics** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="90ca0-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="90ca0-129">תן לחיבור שלך שם הניתן לזיהוי בשדה שם תצוגה.</span><span class="sxs-lookup"><span data-stu-id="90ca0-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="90ca0-130">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="90ca0-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="90ca0-131">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="90ca0-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="90ca0-132">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="90ca0-132">Choose who can use this connection.</span></span> <span data-ttu-id="90ca0-133">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="90ca0-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="90ca0-134">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="90ca0-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="90ca0-135">בחר או חפש את המנוי שבו תרצה להשתמש בנתוני Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="90ca0-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="90ca0-136">ברגע שנבחר מנוי, ניתן גם לבחור באפשרויות **סביבת עבודה**,**חשבון אחסון** ו **גורם מכיל**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="90ca0-137">בחר **שמור** כדי לשמור את החיבור.</span><span class="sxs-lookup"><span data-stu-id="90ca0-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="90ca0-138">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="90ca0-138">Configure an export</span></span>

<span data-ttu-id="90ca0-139">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="90ca0-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="90ca0-140">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="90ca0-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="90ca0-141">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="90ca0-142">כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="90ca0-143">בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="90ca0-144">אם אינך רואה שם מקטע זה, אין [חיבורים](connections.md) מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="90ca0-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="90ca0-145">ספק **שם תצוגה** ניתן לזיהוי עבור הייצוא שלך ו **שם מסד נתונים**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="90ca0-146">בחר אילו ישויות ברצונך לייצא אל Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="90ca0-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="90ca0-147">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-147">Select **Save**.</span></span>

<span data-ttu-id="90ca0-148">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="90ca0-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="90ca0-149">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="90ca0-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="90ca0-150">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="90ca0-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="90ca0-151">עדכון ייצוא</span><span class="sxs-lookup"><span data-stu-id="90ca0-151">Update an export</span></span>

1. <span data-ttu-id="90ca0-152">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="90ca0-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="90ca0-153">בחר **ערוך** בייצוא שברצונך לעדכן.</span><span class="sxs-lookup"><span data-stu-id="90ca0-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="90ca0-154">**הוסף** או **הסר** ישויות מתוך הבחירה.</span><span class="sxs-lookup"><span data-stu-id="90ca0-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="90ca0-155">אם מתבצעת הסרה של ישויות מהבחירה, הן לא נמחקות ממסד הנתונים של Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="90ca0-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="90ca0-156">עם זאת, פעולות רענון של נתונים עתידיים לא יעדכנו את הישויות שהוסרו באותו מסד נתונים.</span><span class="sxs-lookup"><span data-stu-id="90ca0-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="90ca0-157">**שינוי של שם מסד הנתונים** יוצר מסד נתונים חדש של Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="90ca0-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="90ca0-158">מסד הנתונים בעל השם שהוגדר בעבר לא יקבל עדכונים כלשהם בפעולות רענון עתידיות.</span><span class="sxs-lookup"><span data-stu-id="90ca0-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
