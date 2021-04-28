---
title: ייצוא נתוני Customer Insights אל Azure Data Lake Storage Gen2
description: למד כיצד לקבוע את תצורת החיבור אל Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760052"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="90a42-103">הגדרת החיבור ל- Azure Data Lake Storage Gen2‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="90a42-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="90a42-104">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="90a42-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="90a42-105">בחר **הוסף חיבור** ובחר **Azure Data Lake Gen 2** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="90a42-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="90a42-106">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="90a42-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="90a42-107">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="90a42-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="90a42-108">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="90a42-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="90a42-109">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="90a42-109">Choose who can use this connection.</span></span> <span data-ttu-id="90a42-110">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="90a42-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="90a42-111">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="90a42-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="90a42-112">הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור Azure Data Lake Storage Gen2 שלך.</span><span class="sxs-lookup"><span data-stu-id="90a42-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="90a42-113">כדי ללמוד כיצד ליצור חשבון אחסון לשימוש עם Azure Data Lake Storage Gen2, ראה [יצירת חשבון אחסון](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="90a42-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="90a42-114">לקבלת מידע נוסף אודות האופן שבו ניתן למצוא שם חשבון ומפתח חשבון של Azure Data Lake Gen 2, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="90a42-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="90a42-115">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="90a42-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="90a42-116">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="90a42-116">Configure an export</span></span>

<span data-ttu-id="90a42-117">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="90a42-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="90a42-118">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="90a42-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="90a42-119">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="90a42-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="90a42-120">כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="90a42-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="90a42-121">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="90a42-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="90a42-122">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="90a42-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="90a42-123">בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.</span><span class="sxs-lookup"><span data-stu-id="90a42-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="90a42-124">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="90a42-124">Select **Save**.</span></span>

<span data-ttu-id="90a42-125">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="90a42-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="90a42-126">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="90a42-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="90a42-127">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="90a42-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="90a42-128">נתונים מיוצאים מאוחסנים בגורם המכיל של אחסון Azure Data Lake Gen 2 שהגדרת.</span><span class="sxs-lookup"><span data-stu-id="90a42-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
