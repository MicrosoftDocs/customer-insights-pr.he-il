---
title: ייצוא נתוני Customer Insights אל Adobe Experience Platform
description: למד כיצד להשתמש בפלחי תובנות לגבי קהל בפלטפורמת Adobe Experience.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305525"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="4f098-103">שימוש בפלחי Customer Insights ב- Adobe Experience Platform (preview)‎</span><span class="sxs-lookup"><span data-stu-id="4f098-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="4f098-104">כמשתמש בתובנות לגבי קהלים ב- Dynamics 365 Customer Insights, ייתכן שיצרת פלחים כדי לייעל את הקמפיינים השיווקיים שלך על ידי התמקדות בקהלים הרלוונטיים.</span><span class="sxs-lookup"><span data-stu-id="4f098-104">As a user of audience insights in Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="4f098-105">כדי להשתמש בפלח מ- Audience Insights ב- Adobe Experience Platform וביישומים כמו Adobe Campaign Standard, עליך לבצע מספר שלבים המתוארים במאמר זה.</span><span class="sxs-lookup"><span data-stu-id="4f098-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="תרשים התהליך של השלבים המתוארים במאמר זה.":::

## <a name="prerequisites"></a><span data-ttu-id="4f098-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="4f098-107">Prerequisites</span></span>

-   <span data-ttu-id="4f098-108">רשיון Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="4f098-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="4f098-109">רישיון Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="4f098-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="4f098-110">רישיון Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="4f098-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="4f098-111">חשבון אחסון Blob של Azure</span><span class="sxs-lookup"><span data-stu-id="4f098-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="4f098-112">מבט כולל על קמפיין</span><span class="sxs-lookup"><span data-stu-id="4f098-112">Campaign Overview</span></span>

<span data-ttu-id="4f098-113">כדי להבין טוב יותר כיצד ניתן להשתמש בפלחים מתוך audience insights ב- Adobe Experience Platform, בוא נבחן קמפיין לדוגמה בדוי.</span><span class="sxs-lookup"><span data-stu-id="4f098-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="4f098-114">נניח שהחברה שלך מציעה שירות חודשי מבוסס מנוי ללקוחות שלך בארצות הברית.</span><span class="sxs-lookup"><span data-stu-id="4f098-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="4f098-115">ברצונך לזהות לקוחות שהמנויים שלהם אמורים להתחדש בשמונת הימים הקרובים אך טרם חידשו את המנוי.</span><span class="sxs-lookup"><span data-stu-id="4f098-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="4f098-116">כדי לשמור לקוחות אלה, ברצונך לשלוח להם הצעת קידום מכירות דרך הדואר, באמצעות Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="4f098-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="4f098-117">בדוגמה זו, אנחנו רוצים להפעיל את קמפיין הדואר לקידום מכירות פעם אחת.</span><span class="sxs-lookup"><span data-stu-id="4f098-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="4f098-118">מאמר זה אינו מכסה את מקרה השימוש של הפעלת הקמפיין יותר מפעם אחת.</span><span class="sxs-lookup"><span data-stu-id="4f098-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="4f098-119">זיהוי קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="4f098-119">Identify your target audience</span></span>

<span data-ttu-id="4f098-120">בתרחיש שלנו, אנחנו מניחים שכתובות הדואר של הלקוחות זמינות ב- audience insights ושהעדפות קידום המכירות שלהם נותחו כדי לזהות את החברים בפלח.</span><span class="sxs-lookup"><span data-stu-id="4f098-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="4f098-121">ה [פלח שהגדרת ב- audience insights](segments.md) נקרא **ChurnProneCustomers** ובכוונתך לשלוח ללקוחות אלה את קידום הדואר.</span><span class="sxs-lookup"><span data-stu-id="4f098-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="צילום מסך של דף הפלחים שהפלח ChurnProneCustomers נוצר בו.":::

<span data-ttu-id="4f098-123">דואר ההצעה שברצונך לשלוח יכלול את השם הפרטי, שם המשפחה, ואת תאריך סיום המנוי של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="4f098-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="4f098-124">הוא מעדכן את הלקוחות לגבי ההנחה שהם יקבלו אם יחדשו את המנוי שלהם לפני שיסתיים.</span><span class="sxs-lookup"><span data-stu-id="4f098-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="4f098-125">ייצוא קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="4f098-125">Export your target audience</span></span>

<span data-ttu-id="4f098-126">לאחר שקהל היעד שלנו זוהה, נוכל להגדיר את הייצוא מ- audience insights לחשבון אחסון Blob של Azure.</span><span class="sxs-lookup"><span data-stu-id="4f098-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="4f098-127">קביעת תצורה של חיבור</span><span class="sxs-lookup"><span data-stu-id="4f098-127">Configure a connection</span></span>

1. <span data-ttu-id="4f098-128">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="4f098-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4f098-129">בחר **הוסף חיבור** ובחר **Azure Blob Storage** או בחר **הגדר** בתוך אריח **Azure Blob Storage** כדי להגדיר את החיבור.</span><span class="sxs-lookup"><span data-stu-id="4f098-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile to configure the connection.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="אריח 'קביעת תצורה' עבור אחסון Blob של Azure."::: 

1. <span data-ttu-id="4f098-131">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="4f098-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4f098-132">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="4f098-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4f098-133">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="4f098-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4f098-134">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="4f098-134">Choose who can use this connection.</span></span> <span data-ttu-id="4f098-135">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="4f098-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4f098-136">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4f098-136">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4f098-137">הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור חשבון Blob Storage שלך שאליו ברצונך לייצא את הפלח.</span><span class="sxs-lookup"><span data-stu-id="4f098-137">Enter **Account name**, **Account key**, and **Container** for your Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="צילום מסך של תצורת חשבון האחסון. "::: 
   
    - <span data-ttu-id="4f098-139">לקבלת מידע נוסף אודות האופן שבו ניתן למצוא שם חשבון ומפתח חשבון של Blob Storage, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="4f098-139">To learn more about how to find the Blob Storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="4f098-140">כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="4f098-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="4f098-141">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="4f098-141">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="4f098-142">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="4f098-142">Configure an export</span></span>

<span data-ttu-id="4f098-143">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="4f098-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4f098-144">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4f098-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4f098-145">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="4f098-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4f098-146">כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="4f098-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="4f098-147">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע אחסון Blob של Azure.</span><span class="sxs-lookup"><span data-stu-id="4f098-147">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="4f098-148">אם אינך רואה את שם הפלח הזה, אין קשרים זמינים עבורך מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="4f098-148">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="4f098-149">בחר את הפלח שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="4f098-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="4f098-150">בדוגמה זו, זהו **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="4f098-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="צילום מסך של ממשק המשתמש לבחירת פלח עם הפלח ChurnProneCustomers שנבחר בו.":::

1. <span data-ttu-id="4f098-152">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="4f098-152">Select **Save**.</span></span>

<span data-ttu-id="4f098-153">לאחר שמירת יעד הייצוא, תמצא אותו תחת **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="4f098-153">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="4f098-154">כעת באפשרותך [לייצא את הפלח לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4f098-154">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="4f098-155">הייצוא יפעל גם בכל [רענון מתוזמן](system.md).</span><span class="sxs-lookup"><span data-stu-id="4f098-155">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4f098-156">ודא שמספר הרשומות בפלח המיוצא לא חורג ממגבלה המותרת של רישיון Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="4f098-156">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="4f098-157">הנתונים המיוצאים מאוחסנים בגורם המכיל של Azure Blob Storage שהגדרת לעיל.</span><span class="sxs-lookup"><span data-stu-id="4f098-157">Exported data is stored in the Azure Blob Storage container you configured above.</span></span> <span data-ttu-id="4f098-158">נתיב התיקיה הבא נוצר אוטומטית בגורם המכיל שלך:</span><span class="sxs-lookup"><span data-stu-id="4f098-158">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="4f098-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="4f098-159">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="4f098-160">דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="4f098-160">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="4f098-161">ה- *model.json* עבור הישויות שיוצאו שוכן ברמה *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="4f098-161">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="4f098-162">דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="4f098-162">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="4f098-163">הגדרת Experience Data Model‏ (XDM) ב- Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="4f098-163">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="4f098-164">לפני שניתן יהיה להשתמש בנתונים המיוצאים מ- audience insights בתוך Adobe Experience Platform, עלינו להגדיר את סכימת Experience Data Model וכן [לקבוע את תצורת הנתונים עבור פרופיל הלקוח בזמן אמת](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="4f098-164">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="4f098-165">למד [מהו XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) והבן את [יסודות הרכב הסכימה](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="4f098-165">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="4f098-166">ייבוא נתונים אל Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="4f098-166">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="4f098-167">עכשיו כשהכל מוכן, עלינו לייבא את נתוני קהל המוכנים מ- audience insights אל Adobe Experience Platform כדי ליצור פרופילים.</span><span class="sxs-lookup"><span data-stu-id="4f098-167">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="4f098-168">תחילה, [צור חיבור למקור אחסון Blob של Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="4f098-168">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="4f098-169">לאחר הגדרת חיבור המקור, [קבע תצורה של תזרים נתונים](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) עבור חיבור לאצוות אחסון בענן כדי לייבא את פלט הפלח מ- audience insights אל Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="4f098-169">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="4f098-170">יצירת קהל ב- Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="4f098-170">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="4f098-171">כדי לשלוח את הדואר האלקטרוני עבור קמפיין זה, נשתמש ב- Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="4f098-171">To send the email for this campaign, we'll use Adobe Campaign Standard.</span></span> <span data-ttu-id="4f098-172">לאחר ייבוא הנתונים אל Adobe Experience Platform, עלינו [ליצור קהל](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) ב- Adobe Campaign Standard באמצעות הנתונים ב- Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="4f098-172">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>


<span data-ttu-id="4f098-173">למד כיצד [להשתמש בבונה הפלחים](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) ב- Adobe Campaign Standard כדי להגדיר קהל המבוסס על הנתונים ב- Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="4f098-173">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="4f098-174">יצירה ושליחה של הדואר באמצעות Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="4f098-174">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="4f098-175">צור את תוכן הדואר ולאחר מכן [בדוק ושלח](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) את הדואר שלך.</span><span class="sxs-lookup"><span data-stu-id="4f098-175">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="דואר לדוגמה עם הצעת חידוש של Adobe Campaign Standard.":::
