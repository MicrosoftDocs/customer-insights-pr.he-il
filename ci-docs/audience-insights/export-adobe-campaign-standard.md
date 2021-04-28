---
title: ייצוא נתוני Customer Insights אל Adobe Campaign Standard
description: למד כיצד להשתמש ב- audience insights ב- Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760282"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="23886-103">שימוש בפלחי Customer Insights ב- Adobe Campaign Standard (preview)‎</span><span class="sxs-lookup"><span data-stu-id="23886-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="23886-104">כמשתמש של Audience Insights עבור Dynamics 365 Customer Insights, ייתכן שיצרת פלחים כדי להפוך את הקמפיינים השיווקיים שלך ליעילים יותר על-ידי התמקדות בקהלים רלוונטיים.</span><span class="sxs-lookup"><span data-stu-id="23886-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="23886-105">כדי להשתמש בפלח מ- Audience Insights ב- Adobe Experience Platform וביישומים כמו Adobe Campaign Standard, עליך לבצע מספר שלבים המתוארים במאמר זה.</span><span class="sxs-lookup"><span data-stu-id="23886-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="תרשים התהליך של השלבים המתוארים במאמר זה.":::

## <a name="prerequisites"></a><span data-ttu-id="23886-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="23886-107">Prerequisites</span></span>

-   <span data-ttu-id="23886-108">רשיון Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="23886-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="23886-109">רישיון Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="23886-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="23886-110">חשבון אחסון Blob של Azure</span><span class="sxs-lookup"><span data-stu-id="23886-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="23886-111">מבט כולל על קמפיין</span><span class="sxs-lookup"><span data-stu-id="23886-111">Campaign Overview</span></span>

<span data-ttu-id="23886-112">כדי להבין טוב יותר כיצד ניתן להשתמש בפלחים מתוך audience insights ב- Adobe Experience Platform, בוא נבחן קמפיין לדוגמה בדוי.</span><span class="sxs-lookup"><span data-stu-id="23886-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="23886-113">נניח שהחברה שלך מציעה שירות חודשי מבוסס מנוי ללקוחות שלך בארצות הברית.</span><span class="sxs-lookup"><span data-stu-id="23886-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="23886-114">ברצונך לזהות לקוחות שהמנויים שלהם אמורים להתחדש בשמונת הימים הקרובים אך טרם חידשו את המנוי.</span><span class="sxs-lookup"><span data-stu-id="23886-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="23886-115">כדי לשמור לקוחות אלה, ברצונך לשלוח להם הצעת קידום מכירות דרך הדואר, באמצעות Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="23886-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="23886-116">בדוגמה זו, אנחנו רוצים להפעיל את קמפיין הדואר לקידום מכירות פעם אחת.</span><span class="sxs-lookup"><span data-stu-id="23886-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="23886-117">מאמר זה אינו מכסה את מקרה השימוש של הפעלת הקמפיין יותר מפעם אחת.</span><span class="sxs-lookup"><span data-stu-id="23886-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="23886-118">עם זאת, ניתן להגדיר audience insights ו- Adobe Campaign Standard כך שיפעלו גם עבור תרחיש קמפיין חוזר.</span><span class="sxs-lookup"><span data-stu-id="23886-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="23886-119">זיהוי קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="23886-119">Identify your target audience</span></span>

<span data-ttu-id="23886-120">בתרחיש שלנו, אנחנו מניחים שכתובות הדואר של הלקוחות זמינות ב- audience insights ושהעדפות קידום המכירות שלהם נותחו כדי לזהות את החברים בפלח.</span><span class="sxs-lookup"><span data-stu-id="23886-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="23886-121">ה [פלח שהגדרת ב- audience insights](segments.md) נקרא **ChurnProneCustomers** ובכוונתך לשלוח ללקוחות אלה את קידום הדואר.</span><span class="sxs-lookup"><span data-stu-id="23886-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="צילום מסך של דף הפלחים שהפלח ChurnProneCustomers נוצר בו.":::

<span data-ttu-id="23886-123">דואר ההצעה שברצונך לשלוח יכלול את השם הפרטי, שם המשפחה, ואת תאריך סיום המנוי של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="23886-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="23886-124">הוא מעדכן את הלקוחות לגבי ההנחה שהם יקבלו אם יחדשו את המנוי שלהם לפני שיסתיים.</span><span class="sxs-lookup"><span data-stu-id="23886-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="23886-125">ייצוא קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="23886-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="23886-126">קביעת תצורה של חיבור</span><span class="sxs-lookup"><span data-stu-id="23886-126">Configure a connection</span></span>

<span data-ttu-id="23886-127">לאחר שקהל היעד שלנו זוהה, נוכל להגדיר את הייצוא מ- audience insights לחשבון אחסון Blob של Azure.</span><span class="sxs-lookup"><span data-stu-id="23886-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="23886-128">בתובנות קהלים, עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="23886-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="23886-129">בחר **הוסף חיבור** ובחר **Adobe Campaign** כדי לקבוע את תצורת החיבור או בחר **הגדר** באריח **Adobe Campaign**</span><span class="sxs-lookup"><span data-stu-id="23886-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="אריח תצורה עבור Adobe Campaign Standard.":::

1. <span data-ttu-id="23886-131">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="23886-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="23886-132">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="23886-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="23886-133">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="23886-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="23886-134">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="23886-134">Choose who can use this connection.</span></span> <span data-ttu-id="23886-135">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="23886-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="23886-136">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="23886-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="23886-137">הזן את **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** של חשבון אחסון Blob של Azure שלך שאליו ברצונך לייצא את הפלח.</span><span class="sxs-lookup"><span data-stu-id="23886-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="צילום מסך של תצורת חשבון האחסון. "::: 

   - <span data-ttu-id="23886-139">כדי לקבל מידע נוסף אודות אופן מציאת שם החשבון ומפתח החשבון של אחסון Blob של Azure, ראה [ניהול הגדרות חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="23886-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="23886-140">כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="23886-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="23886-141">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="23886-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="23886-142">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="23886-142">Configure an export</span></span>

<span data-ttu-id="23886-143">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="23886-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="23886-144">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="23886-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="23886-145">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="23886-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="23886-146">כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="23886-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="23886-147">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Adobe Campaign.</span><span class="sxs-lookup"><span data-stu-id="23886-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="23886-148">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="23886-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="23886-149">בחר את הפלח שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="23886-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="23886-150">בדוגמה זו, זהו **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="23886-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="צילום מסך של ממשק המשתמש לבחירת פלח עם הפלח ChurnProneCustomers שנבחר בו.":::

1. <span data-ttu-id="23886-152">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="23886-152">Select **Next**.</span></span>

1. <span data-ttu-id="23886-153">כעת אנחנו ממפים את שדות **מקור** מפלח audience insights אל שמות השדה **יעד** בסכימת הפרופיל של Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="23886-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="מיפוי שדות עבור מחבר Adobe Campaign Standard.":::

   <span data-ttu-id="23886-155">אם ברצונך להוסיף תכונות נוספות, בחר **הוסף תכונה**.</span><span class="sxs-lookup"><span data-stu-id="23886-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="23886-156">שם היעד יכול להיות שונה משם שדה המקור, כך שתוכל עדיין למפות את פלט הפלח מ- audience insights ל- Adobe Campaign Standard אם לשדות אין שם זהה בשתי המערכות.</span><span class="sxs-lookup"><span data-stu-id="23886-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="23886-157">כתובת דואר משמשת כשדה זהות, אך באפשרותך להשתמש בכל מזהה אחר מפרופיל הלקוח של audience insights כדי למפות נתונים ל- Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="23886-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="23886-158">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="23886-158">Select **Save**.</span></span>

<span data-ttu-id="23886-159">לאחר שמירת יעד הייצוא, תמצא אותו תחת **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="23886-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="23886-160">כעת באפשרותך [לייצא את הפלח לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="23886-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="23886-161">הייצוא יפעל גם בכל [רענון מתוזמן](system.md).</span><span class="sxs-lookup"><span data-stu-id="23886-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="23886-162">ודא שמספר הרשומות בפלח המיוצא לא חורג ממגבלה המותרת של רישיון Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="23886-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="23886-163">הנתונים המיוצאים מאוחסנים בגורם המכיל של אחסון Blob של Azure שהגדרת לעיל.</span><span class="sxs-lookup"><span data-stu-id="23886-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="23886-164">נתיב התיקיה הבא נוצר אוטומטית בגורם המכיל שלך:</span><span class="sxs-lookup"><span data-stu-id="23886-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="23886-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="23886-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="23886-166">דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="23886-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="23886-167">קביעת התצורה של Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="23886-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="23886-168">כאשר פלח מ-audience insights מיוצא, הוא כולל את העמודות שבחרת בעת הגדרת יעד הייצוא בשלב הקודם.</span><span class="sxs-lookup"><span data-stu-id="23886-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="23886-169">ניתן להשתמש בנתונים אלה כדי [ליצור פרופילים ב- Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="23886-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="23886-170">כדי להשתמש בפלח ב- Adobe Campaign Standard, עלינו להרחיב את סכימת הפרופיל ב- Adobe Campaign Standard כך שתכלול שני שדות נוספים.</span><span class="sxs-lookup"><span data-stu-id="23886-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="23886-171">למד כיצד [להרחיב את משאב הפרופיל](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) עם שדות חדשים ב- Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="23886-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="23886-172">בדוגמה שלנו, שדות אלה הם *שם פלח ותאריך פלח (אופציונלי).*</span><span class="sxs-lookup"><span data-stu-id="23886-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="23886-173">אנחנו נשתמש בשדות אלה כדי לזהות את הפרופילים ב- Adobe Campaign Standard שאנחנו רוצים להתמקד בהם עבור קמפיין זה.</span><span class="sxs-lookup"><span data-stu-id="23886-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="23886-174">אם אין רשומות אחרות ב- Adobe Campaign Standard, מלבד מה שבכוונתך לייבא, תוכל לדלג על שלב זה.</span><span class="sxs-lookup"><span data-stu-id="23886-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="23886-175">ייבוא נתונים אל Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="23886-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="23886-176">עכשיו כשהכל מוכן, עלינו לייבא את נתוני קהל המוכנים מ- audience insights אל Adobe Campaign Standard כדי ליצור פרופילים.</span><span class="sxs-lookup"><span data-stu-id="23886-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="23886-177">למד [כיצד לייבא פרופילים ב- Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) באמצעות זרימת עבודה.</span><span class="sxs-lookup"><span data-stu-id="23886-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="23886-178">זרימת העבודה של הייבוא בתמונה למטה הוגדרה לפעול כל 8 שעות ומחפשת פלחי audience insights שיוצאו (קובץ ‎.csv באחסון Blob של Azure).</span><span class="sxs-lookup"><span data-stu-id="23886-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="23886-179">זרימת העבודה מחלצת את תוכן קובץ ה- ‎.csv בסדר עמודות שצוין.</span><span class="sxs-lookup"><span data-stu-id="23886-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="23886-180">זרימת עבודה זו נבנתה על מנת לבצע טיפול בסיסי בשגיאות ולהבטיח שלכל רשומה יש כתובת דואר לפני שילוב הנתונים ב- Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="23886-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="23886-181">זרימת העבודה גם מחלצת את שם הפלח משם הקובץ לפני העלאתו לנתוני פרופיל ACS.</span><span class="sxs-lookup"><span data-stu-id="23886-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="צילום מסך של זרימת עבודה לייבוא בממשק המשתמש של Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="23886-183">אחזור הקהל ב- Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="23886-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="23886-184">לאחר ייבוא הנתונים ל- Adobe Campaign Standard, [באפשרותך ליצור זרימת עבודה](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ו [לבצע שאילתה](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) של הלקוחות בהתבסס על *שם פלח* ו *תאריך הפלח* כדי לבחור פרופילים שזוהו עבור הקמפיין לדוגמה שלנו.</span><span class="sxs-lookup"><span data-stu-id="23886-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="23886-185">יצירה ושליחה של הדואר באמצעות Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="23886-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="23886-186">צור את תוכן הדואר ולאחר מכן [בדוק ושלח](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) את הדואר שלך.</span><span class="sxs-lookup"><span data-stu-id="23886-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="דואר לדוגמה עם הצעת חידוש של Adobe Campaign Standard.":::
