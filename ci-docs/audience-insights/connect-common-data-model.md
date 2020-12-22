---
title: חיבור נתונים של Common Data Model לחשבון Azure Data Lake
description: עבוד עם נתונים של Common Data Model באמצעות Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643459"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a><span data-ttu-id="f438c-103">חיבור לתיקיה של Common Data Model באמצעות חשבון Azure Data Lake</span><span class="sxs-lookup"><span data-stu-id="f438c-103">Connect to a Common Data Model folder using an Azure Data Lake account</span></span>

<span data-ttu-id="f438c-104">מאמר זה מספק מידע בנוגע לאופן הקליטה של נתונים מתיקיית Common Data Model באמצעות חשבון Azure Data Lake Storage Gen2 שלך.</span><span class="sxs-lookup"><span data-stu-id="f438c-104">This article provides information on how to ingest data from a Common Data Model folder using your Azure Data Lake Storage Gen2 account.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="f438c-105">שיקולים חשובים:</span><span class="sxs-lookup"><span data-stu-id="f438c-105">Important considerations</span></span>

- <span data-ttu-id="f438c-106">נתונים ב- Azure Data Lake שלך צריכים לציית לתקן Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="f438c-106">Data in your Azure Data Lake needs to follow the Common Data Model standard.</span></span> <span data-ttu-id="f438c-107">אין תמיכה בתבניות אחרות כרגע.</span><span class="sxs-lookup"><span data-stu-id="f438c-107">Other formats aren't supported at the moment.</span></span>

- <span data-ttu-id="f438c-108">קליטת נתונים תומכת בחשבונות אחסון של Azure Data Lake *Gen2* באופן בלעדי.</span><span class="sxs-lookup"><span data-stu-id="f438c-108">Data ingestion supports Azure Data Lake *Gen2* storage accounts exclusively.</span></span> <span data-ttu-id="f438c-109">אין באפשרותך להשתמש בחשבונות אחסון של Azure Data Lake Gen1 לקליטת נתונים.</span><span class="sxs-lookup"><span data-stu-id="f438c-109">You can't use Azure Data Lake Gen1 storage accounts to ingest data.</span></span>

- <span data-ttu-id="f438c-110">כדי לאמת עם מנהל שירות של Azure, ודא שהוא מוגדר בדייר שלך.</span><span class="sxs-lookup"><span data-stu-id="f438c-110">To authenticate with an Azure service principal, make sure it's configured in your tenant.</span></span> <span data-ttu-id="f438c-111">לקבלת מידע נוסף, ראה [חיבור audience insights לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות של Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="f438c-111">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span>

- <span data-ttu-id="f438c-112">Azure Data Lake שברצונך לחבר ולקלוט נתונים ממנו צריך להיות באותו אזור Azure כשל סביבת Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f438c-112">The Azure Data Lake you want to connect and ingest data from have to be in the same Azure region as the Dynamics 365 Customer Insights environment.</span></span> <span data-ttu-id="f438c-113">אין תמיכה בחיבורים לתיקיית Common Data Model מ- Data Lake באזור Azure אחר.</span><span class="sxs-lookup"><span data-stu-id="f438c-113">Connections to a Common Data Model folder from a data lake in a different Azure region is not supported.</span></span> <span data-ttu-id="f438c-114">כדי להכיר את אזור Azure של הסביבה, עבור אל **ניהול** > **מערכת** > **אודות** ב- audience insights.</span><span class="sxs-lookup"><span data-stu-id="f438c-114">To know the Azure region of the environment, go to **Admin** > **System** > **About** in audience insights.</span></span>

- <span data-ttu-id="f438c-115">נתונים המאוחסנים בשירותים מקוונים עשויים להיות מאוחסנים במיקום אחר מאשר במיקום שבו נתונים מעובדים או מאוחסנים ב- Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f438c-115">Data stored in online services, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="f438c-116"> על-ידי ייבוא נתונים או חיבור לנתונים שמאוחסנים בשירותים מקוונים, אתה מסכים שנתונים יועברו אל Dynamics 365 Customer Insights ויאוחסנו בו.  [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="f438c-116"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-model-folder"></a><span data-ttu-id="f438c-117">התחבר לתיקיה של Common Data Model</span><span class="sxs-lookup"><span data-stu-id="f438c-117">Connect to a Common Data Model folder</span></span>

1. <span data-ttu-id="f438c-118">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="f438c-118">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="f438c-119">בחר **הוסף מקור נתונים**.</span><span class="sxs-lookup"><span data-stu-id="f438c-119">Select **Add data source**.</span></span>

1. <span data-ttu-id="f438c-120">בחר **התחבר לתיקיית Common Data Model**, הזן **שם** עבור מקור הנתונים ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f438c-120">Select **Connect to a Common Data Model folder**, enter a **Name** for the data source, and select **Next**.</span></span>

1. <span data-ttu-id="f438c-121">באפשרותך לבחור בין שימוש באפשרות מבוססת-משאב לאפשרות מבוססת-מנוי עבור אימות.</span><span class="sxs-lookup"><span data-stu-id="f438c-121">You can choose between using a resource-based option and a subscription-based option for authentication.</span></span> <span data-ttu-id="f438c-122">לקבלת מידע נוסף, ראה [חיבור audience insights לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות של Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="f438c-122">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="f438c-123">הזן את פרטי **הגורם המכיל** ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f438c-123">Enter the **Container** information and select **Next**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f438c-124">![תיבת דו-שיח להזנת פרטי חיבור עבור Azure Data Lake](media/enter-new-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="f438c-124">![Dialog box to enter connection details for Azure Data Lake](media/enter-new-storage-details.png)</span></span>

1. <span data-ttu-id="f438c-125">בתיבת הדו-שיח **בחירת תיקיית Common Data Model**, בחר את קובץ model.json לייבוא נתונים ממנו, ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f438c-125">In the **Select a Common Data Model folder** dialog, select the model.json file to import data from, and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f438c-126">כל קובץ model.json המשויך למקור נתונים אחר בסביבה לא יופיע ברשימה.</span><span class="sxs-lookup"><span data-stu-id="f438c-126">Any model.json file associated with another data source in the environment won't show in the list.</span></span>

1. <span data-ttu-id="f438c-127">תקבל רשימה של ישויות זמינות בקובץ model.json שנבחר.</span><span class="sxs-lookup"><span data-stu-id="f438c-127">You'll get a list of available entities in the selected model.json file.</span></span> <span data-ttu-id="f438c-128">ניתן לסקור ולבחור מרשימת הישויות ולבחור **שמור**.</span><span class="sxs-lookup"><span data-stu-id="f438c-128">You can review and select from the list of available entities and select **Save**.</span></span> <span data-ttu-id="f438c-129">כל הישויות שנבחרו ייקלטו ממקור הנתונים החדש.</span><span class="sxs-lookup"><span data-stu-id="f438c-129">All of the selected entities will be ingested from the new data source.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f438c-130">![תיבת דו-שיח המציגה רשימת ישויות מתוך קובץ model.json](media/review-entities.png)</span><span class="sxs-lookup"><span data-stu-id="f438c-130">![Dialog box showing a list of entities from a model.json file](media/review-entities.png)</span></span>

8. <span data-ttu-id="f438c-131">ציין באילו ישויות נתונים ברצונך להפוך יצירת פרופיל נתונים לזמינה ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="f438c-131">Indicate which data entities you want to enable data profiling and select **Save**.</span></span> <span data-ttu-id="f438c-132">יצירת פרופילים של נתונים הופכת ניתוח ויכולות אחרות לזמינים.</span><span class="sxs-lookup"><span data-stu-id="f438c-132">Data profiling enables analytics and other capabilities.</span></span> <span data-ttu-id="f438c-133">באפשרותך לבחור את הישות השלמה, שבוחרת את כל התכונות מהישות, או לבחור בתכונות מסוימות לבחירתך.</span><span class="sxs-lookup"><span data-stu-id="f438c-133">You can select the whole entity, which selects all attributes from the entity, or select certain attributes of your choice.</span></span> <span data-ttu-id="f438c-134">כברירת מחדל, אף ישות לא תופעל עבור יצירת פרופיל נתונים.</span><span class="sxs-lookup"><span data-stu-id="f438c-134">By default, no entity is enabled for data profiling.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f438c-135">![תיבת דו-שיח המציגה פרופיל נתונים](media/dataprofiling-entities.png)</span><span class="sxs-lookup"><span data-stu-id="f438c-135">![Dialog box showing a data profiling](media/dataprofiling-entities.png)</span></span>

9. <span data-ttu-id="f438c-136">לאחר שמירת הבחירות שלך, הדף **מקורות מידע** נפתח.</span><span class="sxs-lookup"><span data-stu-id="f438c-136">After saving your selections, the **Data sources** page opens.</span></span> <span data-ttu-id="f438c-137">כעת אתה אמור לראות את החיבור לתיקייה Common Data Model כמקור נתונים.</span><span class="sxs-lookup"><span data-stu-id="f438c-137">You should now see the Common Data Model folder connection as a data source.</span></span>

> [!NOTE]
> <span data-ttu-id="f438c-138">קובץ model.json יכול להשתייך למקור נתונים אחד באותה סביבה.</span><span class="sxs-lookup"><span data-stu-id="f438c-138">A model.json file can only associate with one data source in the same environment.</span></span> <span data-ttu-id="f438c-139">עם זאת, ניתן להשתמש באותו קובץ model.json עבור מקורות נתונים בסביבות מרובות.</span><span class="sxs-lookup"><span data-stu-id="f438c-139">However, the same model.json file can be used for data sources in multiple environments.</span></span>

## <a name="edit-a-common-data-model-folder-data-source"></a><span data-ttu-id="f438c-140">עריכת מקור נתונים של תיקיית Common Data Model</span><span class="sxs-lookup"><span data-stu-id="f438c-140">Edit a Common Data Model folder data source</span></span>

<span data-ttu-id="f438c-141">באפשרותך לעדכן את מפתח הגישה עבור חשבון האחסון המכיל את תיקיית Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="f438c-141">You can update the access key for the storage account containing the Common Data Model folder.</span></span> <span data-ttu-id="f438c-142">אתה יכול גם לשנות את קובץ model.json.</span><span class="sxs-lookup"><span data-stu-id="f438c-142">You may also change the model.json file.</span></span> <span data-ttu-id="f438c-143">כדי להתחבר לגורם מכיל שונה מתוך חשבון האחסון שלך, או לשנות את שם החשבון, [צור חיבור למקור נתונים חדש](#connect-to-a-common-data-model-folder).</span><span class="sxs-lookup"><span data-stu-id="f438c-143">To connect to a different container from your storage account, or change the account name, [create a new data source connection](#connect-to-a-common-data-model-folder).</span></span>

1. <span data-ttu-id="f438c-144">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="f438c-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="f438c-145">לצד מקור הנתונים שברצונך לעדכן, בחר את שלוש הנקודות.</span><span class="sxs-lookup"><span data-stu-id="f438c-145">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="f438c-146">בחר באפשרות **ערוך** מתוך הרשימה.</span><span class="sxs-lookup"><span data-stu-id="f438c-146">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="f438c-147">לבחירתך, תוכל לעדכן את **מפתח גישה** ולבחור **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f438c-147">Optionally, update the **Access key** and select **Next**.</span></span>

   ![תיבת דו-שיח לעריכה ולעדכון של מפתח גישה עבור מקור נתונים קיים](media/edit-access-key.png)

5. <span data-ttu-id="f438c-149">לחלופין, באפשרותך לעדכן מחיבור מפתח חשבון לחיבור מבוסס-משאב או מבוסס-מנוי.</span><span class="sxs-lookup"><span data-stu-id="f438c-149">Optionally, you can update from an account key connection to a resource-based or a subscription-based connection.</span></span> <span data-ttu-id="f438c-150">לקבלת מידע נוסף, ראה [חיבור audience insights לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות של Azure](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="f438c-150">For more information, see [Connect audience insights to an Azure Data Lake Storage Gen2 account with an Azure service principal](connect-service-principal.md).</span></span> <span data-ttu-id="f438c-151">אין באפשרותך לשנות מידע **גורם מכיל** בעת עדכון החיבור.</span><span class="sxs-lookup"><span data-stu-id="f438c-151">You can't change **Container** information when updating the connection.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f438c-152">![תיבת דו-שיח להזנת פרטי חיבור עבור Azure Data Lake](media/enter-existing-storage-details.png)</span><span class="sxs-lookup"><span data-stu-id="f438c-152">![Dialog box to enter connection details for Azure Data Lake](media/enter-existing-storage-details.png)</span></span>

6. <span data-ttu-id="f438c-153">אם תרצה בכך, בחר קובץ model.json אחר עם מערכת ישויות שונה מהגורם המכיל.</span><span class="sxs-lookup"><span data-stu-id="f438c-153">Optionally, choose a different model.json file with a different set of entities from the container.</span></span>

7. <span data-ttu-id="f438c-154">לבחירתך, תוכל לבחור ישויות נוספות לקליטה.</span><span class="sxs-lookup"><span data-stu-id="f438c-154">Optionally, you can select additional entities to ingest.</span></span> <span data-ttu-id="f438c-155">תוכל גם להסיר כל ישות שכבר נבחרה, אם אין תלות.</span><span class="sxs-lookup"><span data-stu-id="f438c-155">You can also remove any already selected entities if there are no dependencies.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="f438c-156">אם קיימים יחסי תלות בקובץ model.json הקיים ובמערכת הישויות, תראה הודעת שגיאה ולא תוכל לבחור קובץ model.json אחר.</span><span class="sxs-lookup"><span data-stu-id="f438c-156">If there are dependencies on the existing model.json file and the set of entities, you'll see an error message and can't select a different model.json file.</span></span> <span data-ttu-id="f438c-157">הסר יחסי תלות אלה לפני שינוי קובץ model.json או צור מקור נתונים חדש עם קובץ model.json שבו ברצונך להשתמש כדי להימנע מהסרת יחסי התלות.</span><span class="sxs-lookup"><span data-stu-id="f438c-157">Remove those dependencies before changing the model.json file or create a new data source with the model.json file that you want to use to avoid removing the dependencies.</span></span>

8. <span data-ttu-id="f438c-158">לבחירתך תוכל לבחור תכונות או ישויות נוספות כדי להפוך פרופיל נתונים לזמין או כדי להפוך תכונות וישויות שנבחרו כבר ללא זמינות.</span><span class="sxs-lookup"><span data-stu-id="f438c-158">Optionally, you can select additional attributes or entities to enable data profiling on or disable already selected ones.</span></span>   
