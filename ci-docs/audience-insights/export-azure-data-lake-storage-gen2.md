---
title: ייצוא נתוני Customer Insights אל Azure Data Lake Storage Gen2
description: למד כיצד לקבוע את תצורת החיבור אל Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477180"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="67e45-103">מחבר עבור Azure Data Lake Storage Gen2‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="67e45-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="67e45-104">אחסן את נתוני Customer Insights ב- Azure Data Lake Storage Gen2 או השתמש בו כדי להעביר את הנתונים שלך ליישומים אחרים.</span><span class="sxs-lookup"><span data-stu-id="67e45-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="67e45-105">קביעת תצורת המחבר עבור Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="67e45-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="67e45-106">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="67e45-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="67e45-107">תחת **Azure Data Lake Storage Gen2**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="67e45-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="67e45-108">תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="67e45-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="67e45-109">הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור Azure Data Lake Storage Gen2 שלך.</span><span class="sxs-lookup"><span data-stu-id="67e45-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="67e45-110">כדי ללמוד כיצד ליצור חשבון אחסון לשימוש עם Azure Data Lake Storage Gen2, ראה [יצירת חשבון אחסון](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="67e45-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="67e45-111">למידע נוסף על אופן מציאת שם החשבון ומפתח החשבון של חשבון האחסון של Azure Data Lake Gen2, ראה [ניהול של הגדרות חשבון האחסון בפורטל Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="67e45-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="67e45-112">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="67e45-112">Select **Next**.</span></span>

1. <span data-ttu-id="67e45-113">בחר את התיבה לצד כל אחת מהישויות שברצונך לייצא אל יעד זה.</span><span class="sxs-lookup"><span data-stu-id="67e45-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="67e45-114">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="67e45-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="67e45-115">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="67e45-115">Export the data</span></span>

<span data-ttu-id="67e45-116">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="67e45-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="67e45-117">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="67e45-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
