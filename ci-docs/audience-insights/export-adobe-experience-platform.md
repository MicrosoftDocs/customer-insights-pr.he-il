---
title: ייצוא נתוני Customer Insights אל Adobe Experience Platform
description: למד כיצד להשתמש ב- audience insights ב- Adobe Experience Platform.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 884f4d30f354bed29909d57be84dce4c8e46965a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760102"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="b020f-103">שימוש בפלחי Customer Insights ב- Adobe Experience Platform (preview)‎</span><span class="sxs-lookup"><span data-stu-id="b020f-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="b020f-104">כמשתמש של Audience Insights עבור Dynamics 365 Customer Insights, ייתכן שיצרת פלחים כדי להפוך את הקמפיינים השיווקיים שלך ליעילים יותר על-ידי התמקדות בקהלים רלוונטיים.</span><span class="sxs-lookup"><span data-stu-id="b020f-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="b020f-105">כדי להשתמש בפלח מ- Audience Insights ב- Adobe Experience Platform וביישומים כמו Adobe Campaign Standard, עליך לבצע מספר שלבים המתוארים במאמר זה.</span><span class="sxs-lookup"><span data-stu-id="b020f-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="תרשים התהליך של השלבים המתוארים במאמר זה.":::

## <a name="prerequisites"></a><span data-ttu-id="b020f-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="b020f-107">Prerequisites</span></span>

-   <span data-ttu-id="b020f-108">רשיון Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b020f-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="b020f-109">רישיון Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="b020f-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="b020f-110">רישיון Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="b020f-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="b020f-111">חשבון אחסון Blob של Azure</span><span class="sxs-lookup"><span data-stu-id="b020f-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="b020f-112">מבט כולל על קמפיין</span><span class="sxs-lookup"><span data-stu-id="b020f-112">Campaign Overview</span></span>

<span data-ttu-id="b020f-113">כדי להבין טוב יותר כיצד ניתן להשתמש בפלחים מתוך audience insights ב- Adobe Experience Platform, בוא נבחן קמפיין לדוגמה בדוי.</span><span class="sxs-lookup"><span data-stu-id="b020f-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="b020f-114">נניח שהחברה שלך מציעה שירות חודשי מבוסס מנוי ללקוחות שלך בארצות הברית.</span><span class="sxs-lookup"><span data-stu-id="b020f-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="b020f-115">ברצונך לזהות לקוחות שהמנויים שלהם אמורים להתחדש בשמונת הימים הקרובים אך טרם חידשו את המנוי.</span><span class="sxs-lookup"><span data-stu-id="b020f-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="b020f-116">כדי לשמור לקוחות אלה, ברצונך לשלוח להם הצעת קידום מכירות דרך הדואר, באמצעות Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="b020f-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="b020f-117">בדוגמה זו, אנחנו רוצים להפעיל את קמפיין הדואר לקידום מכירות פעם אחת.</span><span class="sxs-lookup"><span data-stu-id="b020f-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="b020f-118">מאמר זה אינו מכסה את מקרה השימוש של הפעלת הקמפיין יותר מפעם אחת.</span><span class="sxs-lookup"><span data-stu-id="b020f-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="b020f-119">זיהוי קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="b020f-119">Identify your target audience</span></span>

<span data-ttu-id="b020f-120">בתרחיש שלנו, אנחנו מניחים שכתובות הדואר של הלקוחות זמינות ב- audience insights ושהעדפות קידום המכירות שלהם נותחו כדי לזהות את החברים בפלח.</span><span class="sxs-lookup"><span data-stu-id="b020f-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="b020f-121">ה [פלח שהגדרת ב- audience insights](segments.md) נקרא **ChurnProneCustomers** ובכוונתך לשלוח ללקוחות אלה את קידום הדואר.</span><span class="sxs-lookup"><span data-stu-id="b020f-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="צילום מסך של דף הפלחים שהפלח ChurnProneCustomers נוצר בו.":::

<span data-ttu-id="b020f-123">דואר ההצעה שברצונך לשלוח יכלול את השם הפרטי, שם המשפחה, ואת תאריך סיום המנוי של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="b020f-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="b020f-124">הוא מעדכן את הלקוחות לגבי ההנחה שהם יקבלו אם יחדשו את המנוי שלהם לפני שיסתיים.</span><span class="sxs-lookup"><span data-stu-id="b020f-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="b020f-125">ייצוא קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="b020f-125">Export your target audience</span></span>

<span data-ttu-id="b020f-126">לאחר שקהל היעד שלנו זוהה, נוכל להגדיר את הייצוא מ- audience insights לחשבון אחסון Blob של Azure.</span><span class="sxs-lookup"><span data-stu-id="b020f-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="b020f-127">קביעת תצורה של חיבור</span><span class="sxs-lookup"><span data-stu-id="b020f-127">Configure a connection</span></span>

1. <span data-ttu-id="b020f-128">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="b020f-128">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b020f-129">בחר **הוסף חיבור** ובחר **אחסון Blob של Azure** או בחר **הגדר** באריח **אחסון Blob של Azure**:</span><span class="sxs-lookup"><span data-stu-id="b020f-129">Select **Add connection** and choose **Azure Blob Storage** or select **Set up** in the **Azure Blob Storage** tile:</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="אריח 'קביעת תצורה' עבור אחסון Blob של Azure."::: <span data-ttu-id="b020f-131">כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="b020f-131">to configure the connection.</span></span>

1. <span data-ttu-id="b020f-132">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="b020f-132">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b020f-133">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="b020f-133">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b020f-134">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="b020f-134">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b020f-135">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="b020f-135">Choose who can use this connection.</span></span> <span data-ttu-id="b020f-136">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="b020f-136">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b020f-137">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b020f-137">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b020f-138">הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור חשבון אחסון Blob שלך שאליו ברצונך לייצא את הפלח.</span><span class="sxs-lookup"><span data-stu-id="b020f-138">Enter **Account name**, **Account key**, and **Container** for your Blob storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="צילום מסך של תצורת חשבון האחסון. "::: 
   
    - <span data-ttu-id="b020f-140">לקבלת מידע נוסף אודות האופן שבו ניתן למצוא שם חשבון ומפתח חשבון של אחסון Blob, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="b020f-140">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="b020f-141">כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="b020f-141">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="b020f-142">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="b020f-142">Select **Save** to complete the connection.</span></span> 

### <a name="configure-an-export"></a><span data-ttu-id="b020f-143">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="b020f-143">Configure an export</span></span>

<span data-ttu-id="b020f-144">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="b020f-144">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b020f-145">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b020f-145">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b020f-146">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="b020f-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b020f-147">כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="b020f-147">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="b020f-148">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע אחסון Blob של Azure.</span><span class="sxs-lookup"><span data-stu-id="b020f-148">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="b020f-149">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="b020f-149">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b020f-150">בחר את הפלח שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="b020f-150">Choose the segment that you want to export.</span></span> <span data-ttu-id="b020f-151">בדוגמה זו, זהו **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b020f-151">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="צילום מסך של ממשק המשתמש לבחירת פלח עם הפלח ChurnProneCustomers שנבחר בו.":::

1. <span data-ttu-id="b020f-153">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="b020f-153">Select **Save**.</span></span>

<span data-ttu-id="b020f-154">לאחר שמירת יעד הייצוא, תמצא אותו תחת **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="b020f-154">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="b020f-155">כעת באפשרותך [לייצא את הפלח לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b020f-155">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="b020f-156">הייצוא יפעל גם בכל [רענון מתוזמן](system.md).</span><span class="sxs-lookup"><span data-stu-id="b020f-156">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b020f-157">ודא שמספר הרשומות בפלח המיוצא לא חורג ממגבלה המותרת של רישיון Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="b020f-157">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="b020f-158">הנתונים המיוצאים מאוחסנים בגורם המכיל של אחסון Blob של Azure שהגדרת לעיל.</span><span class="sxs-lookup"><span data-stu-id="b020f-158">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="b020f-159">נתיב התיקיה הבא נוצר אוטומטית בגורם המכיל שלך:</span><span class="sxs-lookup"><span data-stu-id="b020f-159">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="b020f-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="b020f-160">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="b020f-161">דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="b020f-161">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="b020f-162">ה- *model.json* עבור הישויות שיוצאו שוכן ברמה *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="b020f-162">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="b020f-163">דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="b020f-163">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="b020f-164">הגדרת Experience Data Model‏ (XDM) ב- Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="b020f-164">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="b020f-165">לפני שניתן יהיה להשתמש בנתונים המיוצאים מ- audience insights בתוך Adobe Experience Platform, עלינו להגדיר את סכימת Experience Data Model וכן [לקבוע את תצורת הנתונים עבור פרופיל הלקוח בזמן אמת](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="b020f-165">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="b020f-166">למד [מהו XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) והבן את [יסודות הרכב הסכימה](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="b020f-166">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="b020f-167">ייבוא נתונים אל Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="b020f-167">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="b020f-168">עכשיו כשהכל מוכן, עלינו לייבא את נתוני קהל המוכנים מ- audience insights אל Adobe Experience Platform כדי ליצור פרופילים.</span><span class="sxs-lookup"><span data-stu-id="b020f-168">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="b020f-169">תחילה, [צור חיבור למקור אחסון Blob של Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="b020f-169">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="b020f-170">לאחר הגדרת חיבור המקור, [קבע תצורה של תזרים נתונים](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) עבור חיבור לאצוות אחסון בענן כדי לייבא את פלט הפלח מ- audience insights אל Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="b020f-170">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="b020f-171">יצירת קהל ב- Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="b020f-171">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="b020f-172">כדי לשלוח את הדואר עבור קמפיין זה, נשתמש ב- Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="b020f-172">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="b020f-173">לאחר ייבוא הנתונים אל Adobe Experience Platform, עלינו [ליצור קהל](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) ב- Adobe Campaign Standard באמצעות הנתונים ב- Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="b020f-173">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="b020f-174">למד כיצד [להשתמש בבונה הפלחים](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) ב- Adobe Campaign Standard כדי להגדיר קהל המבוסס על הנתונים ב- Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="b020f-174">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="b020f-175">יצירה ושליחה של הדואר באמצעות Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="b020f-175">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="b020f-176">צור את תוכן הדואר ולאחר מכן [בדוק ושלח](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) את הדואר שלך.</span><span class="sxs-lookup"><span data-stu-id="b020f-176">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="דואר לדוגמה עם הצעת חידוש של Adobe Campaign Standard.":::
