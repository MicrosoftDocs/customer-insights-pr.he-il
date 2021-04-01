---
title: התחבר לישויות באגם המנוהל של Common Data Service
description: ייבא נתונים מאגם נתונים מנוהל של Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596960"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="ab622-103">התחבר לנתונים בתוך אגם נתונים מנוהל של Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ab622-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ab622-104">מאמר זה מספק מידע על האופן שבו לקוחות קיימים של Dynamics 365 יכולים להתחבר במהירות ליישויות האנליטיות שלהם באגם מנוהל של Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ab622-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="ab622-105">אתה חייב להיות מנהל מערכת בארגון Common Data Service כדי להמשיך ולראות את רשימת הישויות הזמינות באגם המנוהל.</span><span class="sxs-lookup"><span data-stu-id="ab622-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="ab622-106">שיקולים חשובים:</span><span class="sxs-lookup"><span data-stu-id="ab622-106">Important considerations</span></span>

<span data-ttu-id="ab622-107">נתונים המאוחסנים בשירותים מקוונים כגון Azure Data Lake Storage עשויים להיות מאוחסנים במקום אחר שאינו מקום העיבוד או האחסון של הנתונים ב- Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ab622-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="ab622-108"> על-ידי ייבוא נתונים או חיבור לנתונים שמאוחסנים בשירותים מקוונים, אתה מסכים שנתונים יועברו אל Dynamics 365 Customer Insights ויאוחסנו בו.  [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="ab622-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="ab622-109">התחבר אל אגם נתונים מנוהל של Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ab622-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="ab622-110">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="ab622-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ab622-111">בחר **הוסף מקור נתונים**.</span><span class="sxs-lookup"><span data-stu-id="ab622-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="ab622-112">בחר **התחבר אל Common Data Service** ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="ab622-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="ab622-113">הזן **שם** עבור מקור הנתונים ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="ab622-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="ab622-114">קווים מנחים של שם:</span><span class="sxs-lookup"><span data-stu-id="ab622-114">Name guidelines:</span></span> 
   - <span data-ttu-id="ab622-115">התחל עם אות.</span><span class="sxs-lookup"><span data-stu-id="ab622-115">Start with a letter.</span></span>
   - <span data-ttu-id="ab622-116">השתמש באותיות ומספרים בלבד.</span><span class="sxs-lookup"><span data-stu-id="ab622-116">Use letters and numbers only.</span></span> <span data-ttu-id="ab622-117">אסור להזין תווים מיוחדים ורווחים.</span><span class="sxs-lookup"><span data-stu-id="ab622-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="ab622-118">השתמש בין 3 ל- 64 תווים.</span><span class="sxs-lookup"><span data-stu-id="ab622-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="ab622-119">ספק **כתובת שרת** של ארגון Common Data Service שלך ובחר **התחבר**.</span><span class="sxs-lookup"><span data-stu-id="ab622-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab622-120">![תיבת דו-שיח להזנת כתובת שרת Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="ab622-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="ab622-121">בחר את הישויות שברצונך לקלוט מהרשימה הזמינה.</span><span class="sxs-lookup"><span data-stu-id="ab622-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="ab622-122">אם ישויות מסוימות כבר נבחרו, הן עשויות לשמש ביישומי Dynamics 365 אחרים (כגון Dynamics 365 Sales Insights או Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="ab622-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="ab622-123">אין באפשרותך לשנות את הבחירה.</span><span class="sxs-lookup"><span data-stu-id="ab622-123">You can't change the selection.</span></span> <span data-ttu-id="ab622-124">ישויות אלה יהיו זמינות לאחר יצירת מקור נתונים.</span><span class="sxs-lookup"><span data-stu-id="ab622-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ab622-125">![תיבת דו-שיח המציגה רשימת ישויות בארגון Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="ab622-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="ab622-126">שמור את הבחירה שלך כדי להתחיל לסנכרן את הישויות שנבחרו עם אגם מנוהל של Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ab622-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="ab622-127">תמצא את החיבור החדש שנוסף בדף **מקורות מידע**.</span><span class="sxs-lookup"><span data-stu-id="ab622-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="ab622-128">הוא יופיע בתור לרענון ויראה שהישויות נספרות כ- 0 עד לסנכרון של כל הישויות.</span><span class="sxs-lookup"><span data-stu-id="ab622-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="ab622-129">רק מקור נתונים אחד של סביבה יכול להשתמש בו-זמנית באותו אגם מנוהל של Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ab622-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="ab622-130">ערוך מקור נתונים של אגם מנוהל של Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ab622-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="ab622-131">אתה עורך רק את בחירת הישויות לאחר יצירת מקור נתונים.</span><span class="sxs-lookup"><span data-stu-id="ab622-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="ab622-132">לדוגמא, אם נוספו ישויות נוספות ל- Common Data Service ואתה רוצה לייבא גם אותם.</span><span class="sxs-lookup"><span data-stu-id="ab622-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="ab622-133">כדי להתחבר ל- Common Data Service אחר, [צור מקור נתונים חדש](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="ab622-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="ab622-134">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="ab622-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="ab622-135">לצד מקור הנתונים שברצונך לעדכן, בחר את שלוש הנקודות.</span><span class="sxs-lookup"><span data-stu-id="ab622-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="ab622-136">בחר באפשרות **ערוך** מתוך הרשימה.</span><span class="sxs-lookup"><span data-stu-id="ab622-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="ab622-137">בחר ישויות נוספות מרשימת הישויות הזמינה ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="ab622-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]