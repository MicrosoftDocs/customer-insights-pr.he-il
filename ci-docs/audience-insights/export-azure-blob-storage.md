---
title: ייצוא נתוני Customer Insights אל אחסון Blob של Azure
description: למד כיצד להגדיר את החיבור ולייצא אל אחסון Blob.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976135"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="bba70-103">ייצוא רשימת פלחים ונתונים אחרים לאחסון Blob של Azure‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="bba70-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="bba70-104">אחסן את נתוני Customer Insights באחסון Blob או השתמש בו כדי להעביר את הנתונים שלך ליישומים אחרים.</span><span class="sxs-lookup"><span data-stu-id="bba70-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="bba70-105">הגדרת החיבור לאחסון Blob</span><span class="sxs-lookup"><span data-stu-id="bba70-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="bba70-106">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="bba70-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bba70-107">בחר **הוסף חיבור** ובחר **אחסון Blob של Azure** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="bba70-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="bba70-108">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="bba70-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bba70-109">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="bba70-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bba70-110">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="bba70-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bba70-111">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="bba70-111">Choose who can use this connection.</span></span> <span data-ttu-id="bba70-112">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="bba70-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bba70-113">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bba70-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bba70-114">הזן **שם חשבון**, **מפתח חשבון**, ו **גורם מכיל** עבור חשבון אחסון Blob שלך.</span><span class="sxs-lookup"><span data-stu-id="bba70-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="bba70-115">לקבלת מידע נוסף אודות האופן שבו ניתן למצוא שם חשבון ומפתח חשבון של אחסון Blob, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bba70-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="bba70-116">כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="bba70-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="bba70-117">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="bba70-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="bba70-118">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="bba70-118">Configure an export</span></span>

<span data-ttu-id="bba70-119">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="bba70-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bba70-120">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bba70-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bba70-121">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="bba70-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bba70-122">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="bba70-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="bba70-123">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע אחסון Blob של Azure.</span><span class="sxs-lookup"><span data-stu-id="bba70-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="bba70-124">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="bba70-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bba70-125">בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.</span><span class="sxs-lookup"><span data-stu-id="bba70-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="bba70-126">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="bba70-126">Select **Save**.</span></span>

<span data-ttu-id="bba70-127">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="bba70-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bba70-128">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bba70-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="bba70-129">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bba70-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="bba70-130">נתונים מיוצאים מאוחסנים בגורם המכיל של אחסון Blob שהגדרת.</span><span class="sxs-lookup"><span data-stu-id="bba70-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="bba70-131">נתיבי התיקיות הבאים נוצרים באופן אוטומטי בגורם המכיל שלך:</span><span class="sxs-lookup"><span data-stu-id="bba70-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="bba70-132">עבור ישויות מקור וישויות שנוצרו על-ידי המערכת: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="bba70-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="bba70-133">דוגמה: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="bba70-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="bba70-134">ה- model.json עבור הישויות המיוצאות יהיה ברמה %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="bba70-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="bba70-135">דוגמה: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="bba70-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
