---
title: ייצוא נתוני Customer Insights אל Azure Data Lake Storage Gen2
description: למד כיצד לקבוע את תצורת החיבור אל Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596638"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="8db27-103">מחבר עבור Azure Data Lake Storage Gen2‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="8db27-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="8db27-104">אחסן את נתוני Customer Insights ב- Azure Data Lake Storage Gen2 או השתמש בו כדי להעביר את הנתונים שלך ליישומים אחרים.</span><span class="sxs-lookup"><span data-stu-id="8db27-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="8db27-105">קביעת תצורת המחבר עבור Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="8db27-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="8db27-106">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="8db27-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8db27-107">תחת **Azure Data Lake Storage Gen2**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="8db27-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="8db27-108">תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="8db27-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8db27-109">הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור Azure Data Lake Storage Gen2 שלך.</span><span class="sxs-lookup"><span data-stu-id="8db27-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="8db27-110">כדי ללמוד כיצד ליצור חשבון אחסון לשימוש עם Azure Data Lake Storage Gen2, ראה [יצירת חשבון אחסון](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="8db27-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="8db27-111">למידע נוסף על אופן מציאת שם החשבון ומפתח החשבון של חשבון האחסון של Azure Data Lake Gen2, ראה [ניהול של הגדרות חשבון האחסון בפורטל Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="8db27-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="8db27-112">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="8db27-112">Select **Next**.</span></span>

1. <span data-ttu-id="8db27-113">בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.</span><span class="sxs-lookup"><span data-stu-id="8db27-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="8db27-114">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="8db27-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8db27-115">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="8db27-115">Export the data</span></span>

<span data-ttu-id="8db27-116">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="8db27-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="8db27-117">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8db27-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>