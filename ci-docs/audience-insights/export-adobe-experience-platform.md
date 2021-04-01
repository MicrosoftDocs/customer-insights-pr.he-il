---
title: ייצוא נתוני Customer Insights אל Adobe Experience Platform
description: למד כיצד להשתמש ב- audience insights ב- Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596270"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="71a9e-103">שימוש בפלחי Customer Insights ב- Adobe Experience Platform (preview)‎</span><span class="sxs-lookup"><span data-stu-id="71a9e-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="71a9e-104">כמשתמש של Audience Insights עבור Dynamics 365 Customer Insights, ייתכן שיצרת פלחים כדי להפוך את הקמפיינים השיווקיים שלך ליעילים יותר על-ידי התמקדות בקהלים רלוונטיים.</span><span class="sxs-lookup"><span data-stu-id="71a9e-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="71a9e-105">כדי להשתמש בפלח מ- Audience Insights ב- Adobe Experience Platform וביישומים כמו Adobe Campaign Standard, עליך לבצע מספר שלבים המתוארים במאמר זה.</span><span class="sxs-lookup"><span data-stu-id="71a9e-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="תרשים התהליך של השלבים המתוארים במאמר זה.":::

## <a name="prerequisites"></a><span data-ttu-id="71a9e-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="71a9e-107">Prerequisites</span></span>

-   <span data-ttu-id="71a9e-108">רשיון Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="71a9e-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="71a9e-109">רישיון Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="71a9e-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="71a9e-110">רישיון Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="71a9e-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="71a9e-111">חשבון אחסון Blob של Azure</span><span class="sxs-lookup"><span data-stu-id="71a9e-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="71a9e-112">מבט כולל על קמפיין</span><span class="sxs-lookup"><span data-stu-id="71a9e-112">Campaign Overview</span></span>

<span data-ttu-id="71a9e-113">כדי להבין טוב יותר כיצד ניתן להשתמש בפלחים מתוך audience insights ב- Adobe Experience Platform, בוא נבחן קמפיין לדוגמה בדוי.</span><span class="sxs-lookup"><span data-stu-id="71a9e-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="71a9e-114">נניח שהחברה שלך מציעה שירות חודשי מבוסס מנוי ללקוחות שלך בארצות הברית.</span><span class="sxs-lookup"><span data-stu-id="71a9e-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="71a9e-115">ברצונך לזהות לקוחות שהמנויים שלהם אמורים להתחדש בשמונת הימים הקרובים אך טרם חידשו את המנוי.</span><span class="sxs-lookup"><span data-stu-id="71a9e-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="71a9e-116">כדי לשמור לקוחות אלה, ברצונך לשלוח להם הצעת קידום מכירות דרך הדואר, באמצעות Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="71a9e-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="71a9e-117">בדוגמה זו, אנחנו רוצים להפעיל את קמפיין הדואר לקידום מכירות פעם אחת.</span><span class="sxs-lookup"><span data-stu-id="71a9e-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="71a9e-118">מאמר זה אינו מכסה את מקרה השימוש של הפעלת הקמפיין יותר מפעם אחת.</span><span class="sxs-lookup"><span data-stu-id="71a9e-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="71a9e-119">זיהוי קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="71a9e-119">Identify your target audience</span></span>

<span data-ttu-id="71a9e-120">בתרחיש שלנו, אנחנו מניחים שכתובות הדואר של הלקוחות זמינות ב- audience insights ושהעדפות קידום המכירות שלהם נותחו כדי לזהות את החברים בפלח.</span><span class="sxs-lookup"><span data-stu-id="71a9e-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="71a9e-121">ה [פלח שהגדרת ב- audience insights](segments.md) נקרא **ChurnProneCustomers** ובכוונתך לשלוח ללקוחות אלה את קידום הדואר.</span><span class="sxs-lookup"><span data-stu-id="71a9e-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="צילום מסך של דף הפלחים שהפלח ChurnProneCustomers נוצר בו.":::

<span data-ttu-id="71a9e-123">דואר ההצעה שברצונך לשלוח יכלול את השם הפרטי, שם המשפחה, ואת תאריך סיום המנוי של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="71a9e-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="71a9e-124">הוא מעדכן את הלקוחות לגבי ההנחה שהם יקבלו אם יחדשו את המנוי שלהם לפני שיסתיים.</span><span class="sxs-lookup"><span data-stu-id="71a9e-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="71a9e-125">ייצוא קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="71a9e-125">Export your target audience</span></span>

<span data-ttu-id="71a9e-126">לאחר שקהל היעד שלנו זוהה, נוכל להגדיר את הייצוא מ- audience insights לחשבון אחסון Blob של Azure.</span><span class="sxs-lookup"><span data-stu-id="71a9e-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="71a9e-127">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="71a9e-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="71a9e-128">באריח **אחסון Blob של Azure**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="71a9e-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="אריח 'קביעת תצורה' עבור אחסון Blob של Azure.":::

1. <span data-ttu-id="71a9e-130">ספק **שם תצוגה** עבור יעד ייצוא חדש זה והזן את **שם החשבון**, **מפתח החשבון** ו **הגורם המכיל** של חשבון אחסון Blob של Azure שאליו ברצונך לייצא את הפלח.</span><span class="sxs-lookup"><span data-stu-id="71a9e-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="צילום מסך של תצורת חשבון האחסון. "::: 

   - <span data-ttu-id="71a9e-132">כדי לקבל מידע נוסף אודות אופן מציאת שם החשבון ומפתח החשבון של אחסון Blob של Azure, ראה [ניהול הגדרות חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="71a9e-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="71a9e-133">כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="71a9e-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="71a9e-134">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="71a9e-134">Select **Next**.</span></span>

1. <span data-ttu-id="71a9e-135">בחר את הפלח שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="71a9e-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="71a9e-136">בדוגמה זו, זהו **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="71a9e-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="צילום מסך של ממשק המשתמש לבחירת פלח עם הפלח ChurnProneCustomers שנבחר בו.":::

1. <span data-ttu-id="71a9e-138">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="71a9e-138">Select **Save**.</span></span>

<span data-ttu-id="71a9e-139">לאחר שמירת יעד הייצוא, תמצא אותו ב **ניהול** > **פעולות ייצוא** > **יעדי הייצוא שלי**.</span><span class="sxs-lookup"><span data-stu-id="71a9e-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="צילום מסך עם רשימת פעולות ייצוא ופלח לדוגמה מודגשים.":::

<span data-ttu-id="71a9e-141">כעת באפשרותך [לייצא את הפלח לפי דרישה](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="71a9e-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="71a9e-142">הייצוא יפעל גם בכל [רענון מתוזמן](system.md).</span><span class="sxs-lookup"><span data-stu-id="71a9e-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="71a9e-143">ודא שמספר הרשומות בפלח המיוצא לא חורג ממגבלה המותרת של רישיון Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="71a9e-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="71a9e-144">הנתונים המיוצאים מאוחסנים בגורם המכיל של אחסון Blob של Azure שהגדרת לעיל.</span><span class="sxs-lookup"><span data-stu-id="71a9e-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="71a9e-145">נתיב התיקיה הבא נוצר אוטומטית בגורם המכיל שלך:</span><span class="sxs-lookup"><span data-stu-id="71a9e-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="71a9e-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="71a9e-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="71a9e-147">דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="71a9e-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="71a9e-148">ה- *model.json* עבור הישויות שיוצאו שוכן ברמה *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="71a9e-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="71a9e-149">דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="71a9e-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="71a9e-150">הגדרת Experience Data Model‏ (XDM) ב- Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="71a9e-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="71a9e-151">לפני שניתן יהיה להשתמש בנתונים המיוצאים מ- audience insights בתוך Adobe Experience Platform, עלינו להגדיר את סכימת Experience Data Model וכן [לקבוע את תצורת הנתונים עבור פרופיל הלקוח בזמן אמת](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="71a9e-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="71a9e-152">למד [מהו XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) והבן את [יסודות הרכב הסכימה](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="71a9e-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="71a9e-153">ייבוא נתונים אל Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="71a9e-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="71a9e-154">עכשיו כשהכל מוכן, עלינו לייבא את נתוני קהל המוכנים מ- audience insights אל Adobe Experience Platform כדי ליצור פרופילים.</span><span class="sxs-lookup"><span data-stu-id="71a9e-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="71a9e-155">תחילה, [צור חיבור למקור אחסון Blob של Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="71a9e-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="71a9e-156">לאחר הגדרת חיבור המקור, [קבע תצורה של תזרים נתונים](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) עבור חיבור לאצוות אחסון בענן כדי לייבא את פלט הפלח מ- audience insights אל Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="71a9e-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="71a9e-157">יצירת קהל ב- Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="71a9e-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="71a9e-158">כדי לשלוח את הדואר עבור קמפיין זה, נשתמש ב- Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="71a9e-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="71a9e-159">לאחר ייבוא הנתונים אל Adobe Experience Platform, עלינו [ליצור קהל](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) ב- Adobe Campaign Standard באמצעות הנתונים ב- Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="71a9e-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="71a9e-160">למד כיצד [להשתמש בבונה הפלחים](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) ב- Adobe Campaign Standard כדי להגדיר קהל המבוסס על הנתונים ב- Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="71a9e-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="71a9e-161">יצירה ושליחה של הדואר באמצעות Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="71a9e-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="71a9e-162">צור את תוכן הדואר ולאחר מכן [בדוק ושלח](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) את הדואר שלך.</span><span class="sxs-lookup"><span data-stu-id="71a9e-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="דואר לדוגמה עם הצעת חידוש של Adobe Campaign Standard.":::