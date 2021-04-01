---
title: ייצוא נתוני Customer Insights אל Adobe Campaign Standard
description: למד כיצד להשתמש ב- audience insights ב- Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596316"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="c0110-103">שימוש בפלחי Customer Insights ב- Adobe Campaign Standard (preview)‎</span><span class="sxs-lookup"><span data-stu-id="c0110-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="c0110-104">כמשתמש של Audience Insights עבור Dynamics 365 Customer Insights, ייתכן שיצרת פלחים כדי להפוך את הקמפיינים השיווקיים שלך ליעילים יותר על-ידי התמקדות בקהלים רלוונטיים.</span><span class="sxs-lookup"><span data-stu-id="c0110-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="c0110-105">כדי להשתמש בפלח מ- Audience Insights ב- Adobe Experience Platform וביישומים כמו Adobe Campaign Standard, עליך לבצע מספר שלבים המתוארים במאמר זה.</span><span class="sxs-lookup"><span data-stu-id="c0110-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="תרשים התהליך של השלבים המתוארים במאמר זה.":::

## <a name="prerequisites"></a><span data-ttu-id="c0110-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="c0110-107">Prerequisites</span></span>

-   <span data-ttu-id="c0110-108">רשיון Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="c0110-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="c0110-109">רישיון Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c0110-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="c0110-110">חשבון אחסון Blob של Azure</span><span class="sxs-lookup"><span data-stu-id="c0110-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="c0110-111">מבט כולל על קמפיין</span><span class="sxs-lookup"><span data-stu-id="c0110-111">Campaign Overview</span></span>

<span data-ttu-id="c0110-112">כדי להבין טוב יותר כיצד ניתן להשתמש בפלחים מתוך audience insights ב- Adobe Experience Platform, בוא נבחן קמפיין לדוגמה בדוי.</span><span class="sxs-lookup"><span data-stu-id="c0110-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="c0110-113">נניח שהחברה שלך מציעה שירות חודשי מבוסס מנוי ללקוחות שלך בארצות הברית.</span><span class="sxs-lookup"><span data-stu-id="c0110-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="c0110-114">ברצונך לזהות לקוחות שהמנויים שלהם אמורים להתחדש בשמונת הימים הקרובים אך טרם חידשו את המנוי.</span><span class="sxs-lookup"><span data-stu-id="c0110-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="c0110-115">כדי לשמור לקוחות אלה, ברצונך לשלוח להם הצעת קידום מכירות דרך הדואר, באמצעות Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c0110-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="c0110-116">בדוגמה זו, אנחנו רוצים להפעיל את קמפיין הדואר לקידום מכירות פעם אחת.</span><span class="sxs-lookup"><span data-stu-id="c0110-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="c0110-117">מאמר זה אינו מכסה את מקרה השימוש של הפעלת הקמפיין יותר מפעם אחת.</span><span class="sxs-lookup"><span data-stu-id="c0110-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="c0110-118">עם זאת, ניתן להגדיר audience insights ו- Adobe Campaign Standard כך שיפעלו גם עבור תרחיש קמפיין חוזר.</span><span class="sxs-lookup"><span data-stu-id="c0110-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="c0110-119">זיהוי קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="c0110-119">Identify your target audience</span></span>

<span data-ttu-id="c0110-120">בתרחיש שלנו, אנחנו מניחים שכתובות הדואר של הלקוחות זמינות ב- audience insights ושהעדפות קידום המכירות שלהם נותחו כדי לזהות את החברים בפלח.</span><span class="sxs-lookup"><span data-stu-id="c0110-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="c0110-121">ה [פלח שהגדרת ב- audience insights](segments.md) נקרא **ChurnProneCustomers** ובכוונתך לשלוח ללקוחות אלה את קידום הדואר.</span><span class="sxs-lookup"><span data-stu-id="c0110-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="צילום מסך של דף הפלחים שהפלח ChurnProneCustomers נוצר בו.":::

<span data-ttu-id="c0110-123">דואר ההצעה שברצונך לשלוח יכלול את השם הפרטי, שם המשפחה, ואת תאריך סיום המנוי של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="c0110-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="c0110-124">הוא מעדכן את הלקוחות לגבי ההנחה שהם יקבלו אם יחדשו את המנוי שלהם לפני שיסתיים.</span><span class="sxs-lookup"><span data-stu-id="c0110-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="c0110-125">ייצוא קהל היעד שלך</span><span class="sxs-lookup"><span data-stu-id="c0110-125">Export your target audience</span></span>

<span data-ttu-id="c0110-126">לאחר שקהל היעד שלנו זוהה, נוכל להגדיר את הייצוא מ- audience insights לחשבון אחסון Blob של Azure.</span><span class="sxs-lookup"><span data-stu-id="c0110-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="c0110-127">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="c0110-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c0110-128">באריח **Adobe Campaign**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="c0110-128">In the **Adobe Campaign** tile, select **Set up**.</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="אריח תצורה עבור Adobe Campaign Standard.":::

1. <span data-ttu-id="c0110-130">ספק **שם תצוגה** עבור יעד ייצוא חדש זה והזן את **שם החשבון**, **מפתח החשבון** ו **הגורם המכיל** של חשבון אחסון Blob של Azure שאליו ברצונך לייצא את הפלח.</span><span class="sxs-lookup"><span data-stu-id="c0110-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="צילום מסך של תצורת חשבון האחסון. "::: 

   - <span data-ttu-id="c0110-132">כדי לקבל מידע נוסף אודות אופן מציאת שם החשבון ומפתח החשבון של אחסון Blob של Azure, ראה [ניהול הגדרות חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="c0110-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="c0110-133">כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="c0110-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="c0110-134">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="c0110-134">Select **Next**.</span></span>

1. <span data-ttu-id="c0110-135">בחר את הפלח שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="c0110-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="c0110-136">בדוגמה זו, זהו **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c0110-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="צילום מסך של ממשק המשתמש לבחירת פלח עם הפלח ChurnProneCustomers שנבחר בו.":::

1. <span data-ttu-id="c0110-138">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="c0110-138">Select **Next**.</span></span>

1. <span data-ttu-id="c0110-139">כעת אנחנו ממפים את שדות **מקור** מפלח audience insights אל שמות השדה **יעד** בסכימת הפרופיל של Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c0110-139">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="מיפוי שדות עבור מחבר Adobe Campaign Standard.":::

   <span data-ttu-id="c0110-141">אם ברצונך להוסיף תכונות נוספות, בחר **הוסף תכונה**.</span><span class="sxs-lookup"><span data-stu-id="c0110-141">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="c0110-142">שם היעד יכול להיות שונה משם שדה המקור, כך שתוכל עדיין למפות את פלט הפלח מ- audience insights ל- Adobe Campaign Standard אם לשדות אין שם זהה בשתי המערכות.</span><span class="sxs-lookup"><span data-stu-id="c0110-142">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c0110-143">כתובת דואר משמשת כשדה זהות, אך באפשרותך להשתמש בכל מזהה אחר מפרופיל הלקוח של audience insights כדי למפות נתונים ל- Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c0110-143">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="c0110-144">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="c0110-144">Select **Save**.</span></span>

<span data-ttu-id="c0110-145">לאחר שמירת יעד הייצוא, תמצא אותו ב **ניהול** > **פעולות ייצוא** > **יעדי הייצוא שלי**.</span><span class="sxs-lookup"><span data-stu-id="c0110-145">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="צילום מסך עם רשימת פעולות ייצוא ופלח לדוגמה מודגשים.":::

<span data-ttu-id="c0110-147">כעת באפשרותך [לייצא את הפלח לפי דרישה](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="c0110-147">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="c0110-148">הייצוא יפעל גם בכל [רענון מתוזמן](system.md).</span><span class="sxs-lookup"><span data-stu-id="c0110-148">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c0110-149">ודא שמספר הרשומות בפלח המיוצא לא חורג ממגבלה המותרת של רישיון Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c0110-149">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="c0110-150">הנתונים המיוצאים מאוחסנים בגורם המכיל של אחסון Blob של Azure שהגדרת לעיל.</span><span class="sxs-lookup"><span data-stu-id="c0110-150">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="c0110-151">נתיב התיקיה הבא נוצר אוטומטית בגורם המכיל שלך:</span><span class="sxs-lookup"><span data-stu-id="c0110-151">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="c0110-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="c0110-152">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="c0110-153">דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="c0110-153">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="c0110-154">קביעת התצורה של Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c0110-154">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="c0110-155">כאשר פלח מ-audience insights מיוצא, הוא כולל את העמודות שבחרת בעת הגדרת יעד הייצוא בשלב הקודם.</span><span class="sxs-lookup"><span data-stu-id="c0110-155">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="c0110-156">ניתן להשתמש בנתונים אלה כדי [ליצור פרופילים ב- Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="c0110-156">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="c0110-157">כדי להשתמש בפלח ב- Adobe Campaign Standard, עלינו להרחיב את סכימת הפרופיל ב- Adobe Campaign Standard כך שתכלול שני שדות נוספים.</span><span class="sxs-lookup"><span data-stu-id="c0110-157">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="c0110-158">למד כיצד [להרחיב את משאב הפרופיל](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) עם שדות חדשים ב- Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c0110-158">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="c0110-159">בדוגמה שלנו, שדות אלה הם *שם פלח ותאריך פלח (אופציונלי).*</span><span class="sxs-lookup"><span data-stu-id="c0110-159">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="c0110-160">אנחנו נשתמש בשדות אלה כדי לזהות את הפרופילים ב- Adobe Campaign Standard שאנחנו רוצים להתמקד בהם עבור קמפיין זה.</span><span class="sxs-lookup"><span data-stu-id="c0110-160">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="c0110-161">אם אין רשומות אחרות ב- Adobe Campaign Standard, מלבד מה שבכוונתך לייבא, תוכל לדלג על שלב זה.</span><span class="sxs-lookup"><span data-stu-id="c0110-161">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="c0110-162">ייבוא נתונים אל Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c0110-162">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="c0110-163">עכשיו כשהכל מוכן, עלינו לייבא את נתוני קהל המוכנים מ- audience insights אל Adobe Campaign Standard כדי ליצור פרופילים.</span><span class="sxs-lookup"><span data-stu-id="c0110-163">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="c0110-164">למד [כיצד לייבא פרופילים ב- Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) באמצעות זרימת עבודה.</span><span class="sxs-lookup"><span data-stu-id="c0110-164">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="c0110-165">זרימת העבודה של הייבוא בתמונה למטה הוגדרה לפעול כל 8 שעות ומחפשת פלחי audience insights שיוצאו (קובץ ‎.csv באחסון Blob של Azure).</span><span class="sxs-lookup"><span data-stu-id="c0110-165">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="c0110-166">זרימת העבודה מחלצת את תוכן קובץ ה- ‎.csv בסדר עמודות שצוין.</span><span class="sxs-lookup"><span data-stu-id="c0110-166">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="c0110-167">זרימת עבודה זו נבנתה על מנת לבצע טיפול בסיסי בשגיאות ולהבטיח שלכל רשומה יש כתובת דואר לפני שילוב הנתונים ב- Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="c0110-167">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="c0110-168">זרימת העבודה גם מחלצת את שם הפלח משם הקובץ לפני העלאתו לנתוני פרופיל ACS.</span><span class="sxs-lookup"><span data-stu-id="c0110-168">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="צילום מסך של זרימת עבודה לייבוא בממשק המשתמש של Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="c0110-170">אחזור הקהל ב- Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c0110-170">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="c0110-171">לאחר ייבוא הנתונים ל- Adobe Campaign Standard, [באפשרותך ליצור זרימת עבודה](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ו [לבצע שאילתה](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) של הלקוחות בהתבסס על *שם פלח* ו *תאריך הפלח* כדי לבחור פרופילים שזוהו עבור הקמפיין לדוגמה שלנו.</span><span class="sxs-lookup"><span data-stu-id="c0110-171">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="c0110-172">יצירה ושליחה של הדואר באמצעות Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="c0110-172">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="c0110-173">צור את תוכן הדואר ולאחר מכן [בדוק ושלח](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) את הדואר שלך.</span><span class="sxs-lookup"><span data-stu-id="c0110-173">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="דואר לדוגמה עם הצעת חידוש של Adobe Campaign Standard.":::