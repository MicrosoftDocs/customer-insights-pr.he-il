---
title: מדריך לדוגמה לחיזוי של נטישת מנויים
description: השתמש במדריך לדוגמה זה כדי לנסות את מודל החיזוי של נטישת מנויים המוכן לשימוש.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 324e5c19778230dd978b2f4e9156a2dd82b3d2bd
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595519"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="bdfa1-103">מדריך לדוגמה לחיזוי של נטישת מנויים (מהדורת Preview)</span><span class="sxs-lookup"><span data-stu-id="bdfa1-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="bdfa1-104">אנו ננחה אותך ונדגים דוגמה מקצה לקצה של חיזוי של נטישת מנויים באמצעות הנתונים לדוגמה המפורטים להלן.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="bdfa1-105">תרחיש</span><span class="sxs-lookup"><span data-stu-id="bdfa1-105">Scenario</span></span>

<span data-ttu-id="bdfa1-106">Contoso היא חברה המייצרת קפה איכותי ומכונות קפה, שאותם היא מוכרת דרך האתר שלה Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="bdfa1-107">לאחרונה הקימה החברה עסק של מנויים עבור הלקוחות שלה, המספק להם קפה על בסיס קבוע.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="bdfa1-108">מטרתה היא להבין אילו לקוחות הרשומים כמנויים עשויים לבטל את המנוי שלהם בחודשים הקרובים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="bdfa1-109">הידיעה מי מהלקוחות **עשוי לנטוש**, יכולה לעזור לה לחסוך מאמצים שיווקיים על-ידי התמקדות בשימור הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bdfa1-110">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="bdfa1-110">Prerequisites</span></span>

- <span data-ttu-id="bdfa1-111">לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="bdfa1-112">אנו ממליצים ליישם את השלבים הבאים [בסביבה חדשה](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa1-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="bdfa1-113">משימה 1 - קליטת נתונים</span><span class="sxs-lookup"><span data-stu-id="bdfa1-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="bdfa1-114">עיין בעיקר במאמרים [אודות קליטת נתונים](data-sources.md) ו[ייבוא מקורות נתונים באמצעות מחברים של Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa1-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="bdfa1-115">המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="bdfa1-116">קליטת נתוני לקוחות מפלטפורמת eCommerce</span><span class="sxs-lookup"><span data-stu-id="bdfa1-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="bdfa1-117">צור מקור נתונים בשם **eCommerce**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bdfa1-118">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="bdfa1-119">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bdfa1-120">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="bdfa1-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bdfa1-121">**DateOfBirth**: תאריך</span><span class="sxs-lookup"><span data-stu-id="bdfa1-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="bdfa1-122">**CreatedOn**: תאריך/שעה/אזור</span><span class="sxs-lookup"><span data-stu-id="bdfa1-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המר את תאריך הלידה לתאריך.":::

1. <span data-ttu-id="bdfa1-124">בשדה **שם** בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="bdfa1-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="bdfa1-125">שמור את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="bdfa1-126">קליטת נתוני לקוחות מסכמת loyalty</span><span class="sxs-lookup"><span data-stu-id="bdfa1-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="bdfa1-127">צור מקור נתונים בשם **LoyaltyScheme**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bdfa1-128">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="bdfa1-129">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bdfa1-130">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="bdfa1-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bdfa1-131">**DateOfBirth**: תאריך</span><span class="sxs-lookup"><span data-stu-id="bdfa1-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="bdfa1-132">**RewardsPoints**: מספר שלם</span><span class="sxs-lookup"><span data-stu-id="bdfa1-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="bdfa1-133">**CreatedOn**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="bdfa1-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="bdfa1-134">בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="bdfa1-135">שמור את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="bdfa1-136">קליטת פרטי מנוי</span><span class="sxs-lookup"><span data-stu-id="bdfa1-136">Ingest subscription information</span></span>

1. <span data-ttu-id="bdfa1-137">צור מקור נתונים בשם **SubscriptionHistory**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bdfa1-138">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="bdfa1-139">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bdfa1-140">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="bdfa1-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bdfa1-141">**SubscriptioID**: מספר שלם</span><span class="sxs-lookup"><span data-stu-id="bdfa1-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="bdfa1-142">**SubscriptionAmount**: מטבע</span><span class="sxs-lookup"><span data-stu-id="bdfa1-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="bdfa1-143">**SubscriptionEndDate**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="bdfa1-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="bdfa1-144">**SubscriptionStartDate**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="bdfa1-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="bdfa1-145">**TransactionDate**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="bdfa1-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="bdfa1-146">**IsRecurring**:‏ True/False</span><span class="sxs-lookup"><span data-stu-id="bdfa1-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="bdfa1-147">**Is_auto_renew**: ‏True/False</span><span class="sxs-lookup"><span data-stu-id="bdfa1-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="bdfa1-148">**RecurringFrequencyInMonths**: מספר שלם</span><span class="sxs-lookup"><span data-stu-id="bdfa1-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="bdfa1-149">בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="bdfa1-150">שמור את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="bdfa1-151">קלוט נתוני לקוחות מביקורות של אתרים</span><span class="sxs-lookup"><span data-stu-id="bdfa1-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="bdfa1-152">צור מקור נתונים בשם **Website**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="bdfa1-153">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="bdfa1-154">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="bdfa1-155">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="bdfa1-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="bdfa1-156">**ReviewRating**: מספר שלם</span><span class="sxs-lookup"><span data-stu-id="bdfa1-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="bdfa1-157">**ReviewDate**: תאריך</span><span class="sxs-lookup"><span data-stu-id="bdfa1-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="bdfa1-158">בשדה 'שם' בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="bdfa1-159">משימה 2 - איחוד נתונים</span><span class="sxs-lookup"><span data-stu-id="bdfa1-159">Task 2 - Data unification</span></span>

<span data-ttu-id="bdfa1-160">לאחר קליטת הנתונים אנו מתחילים כעת בתהליך **מיפוי, התאמה, מיזוג** כדי ליצור פרופיל לקוח מאוחד.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="bdfa1-161">לקבלת מידע נוסף, ראה [איחוד נתונים](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa1-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="bdfa1-162">מיפוי</span><span class="sxs-lookup"><span data-stu-id="bdfa1-162">Map</span></span>

1. <span data-ttu-id="bdfa1-163">לאחר קליטת הנתונים, מפה את אנשי הקשר מנתוני eCommerce ו- Loyalty לסוגי נתונים נפוצים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="bdfa1-164">עבור אל **נתונים** > **איחוד** > **מיפוי**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="bdfa1-165">בחר את הישויות המייצגות את פרופיל הלקוח – **eCommerceContacts** ו- **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="איחוד מקורות הנתונים ecommerce ו- loyalty.":::

1. <span data-ttu-id="bdfa1-167">בחר **ContactId** כמפתח העיקרי עבור **eCommerceContacts** ו- **LoyaltyID** כמפתח העיקרי עבור **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="איחוד LoyaltyId כמפתח ראשי.":::

### <a name="match"></a><span data-ttu-id="bdfa1-169">התאמה</span><span class="sxs-lookup"><span data-stu-id="bdfa1-169">Match</span></span>

1. <span data-ttu-id="bdfa1-170">עבור אל הכרטיסיה **התאמה** ובחר **הגדר סדר**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="bdfa1-171">ברשימה הנפתחת **ראשי**, בחר **eCommerceContacts : eCommerce** כמקור הראשי וכלול את כל הרשומות.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="bdfa1-172">ברשימה הנפתחת **ישות 2**, בחר **loyCustomers : LoyaltyScheme** וכלול את כל הרשומות.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="איחוד התאמה של eCommerce ו- Loyalty.":::

1. <span data-ttu-id="bdfa1-174">בחר **צור כלל חדש**</span><span class="sxs-lookup"><span data-stu-id="bdfa1-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="bdfa1-175">הוסף את התנאי הראשון שלך באמצעות FullName.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="bdfa1-176">עבור eCommerceContacts בחר **FullName** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="bdfa1-177">עבור loyCustomers בחר **FullName** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="bdfa1-178">בחר את הרשימה הנפתחת **נרמל** ובחר **סוג (טלפון, שם, כתובת, ...)**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="bdfa1-179">הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="bdfa1-180">הזן את השם **FullName, Email** עבור הכלל החדש.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="bdfa1-181">הוסף תנאי שני לכתובת הדואר האלקטרוני על-ידי בחירה **הוסף תנאי**</span><span class="sxs-lookup"><span data-stu-id="bdfa1-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="bdfa1-182">לישות eCommerceContacts, בחר **דואר** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="bdfa1-183">לישות loyCustomers, בחר **דואר** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="bdfa1-184">השאר את השדה 'נרמל' ריק.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="bdfa1-185">הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="איחוד כלל התאמה עבור שם ודואר אלקטרוני.":::

7. <span data-ttu-id="bdfa1-187">בחר **שמור** ו **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="bdfa1-188">מזג</span><span class="sxs-lookup"><span data-stu-id="bdfa1-188">Merge</span></span>

1. <span data-ttu-id="bdfa1-189">עבור לכרטיסיה **מיזוג**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="bdfa1-190">ב- **ContactId** עבור הישות **loyCustomers**, שנה את שם התצוגה ל- **ContactIdLOYALTY** כדי להבחין בינה לבין מספרי זהות אחרים שנקלטו.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="שינוי שם ל- contactid מ- loyalty id.":::

1. <span data-ttu-id="bdfa1-192">בחר **שמור** ו **הפעל** כדי להתחיל בתהליך המיזוג.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="bdfa1-193">משימה 3 - הגדר את חיזוי נטישת המנויים</span><span class="sxs-lookup"><span data-stu-id="bdfa1-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="bdfa1-194">מכיוון שפרופילי הלקוחות המאוחדים קיימים, אנו יכולים כעת להפעיל את חיזוי נטישת המנויים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="bdfa1-195">לקבלת השלבים המפורטים, עיין במאמר [חיזוי נטישה של מנויים (מהדורת Preview)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa1-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="bdfa1-196">עבור אל **בינה** > **גילוי** ובחר להשתמש ב **מודל נטישת לקוחות**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="bdfa1-197">בחר את האפשרות **מנוי** ובחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="bdfa1-198">תן שם למודל **OOB Subscription Churn Prediction** ולישות הפלט **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="bdfa1-199">הגדר שני תנאים עבור מודל הנטישה:</span><span class="sxs-lookup"><span data-stu-id="bdfa1-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="bdfa1-200">**ימים מסיום המנוי**: **לפחות 60** ימים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="bdfa1-201">אם לקוח אינו מחדש את המנוי בפרק זמן זה לאחר תום המנוי שלו, הוא נחשב כלקוח שנטש.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="bdfa1-202">**הגדרת נטישה**: **לפחות 93** ימים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="bdfa1-203">משך הזמן שבמהלכו מנבא המודל אילו לקוחות עשויים לנטוש.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="bdfa1-204">ככל שתבחן את העתיד הרחוק יותר, כך יהיו התוצאות מדויקות פחות.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="בחר את מנופי המודל 'חלון חיזוי' ו'הגדרת נטישה'.":::

1. <span data-ttu-id="bdfa1-206">בחר **הוסף נתונים נדרשים** ובחר **הוסף נתונים** להיסטוריית המנויים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="bdfa1-207">הוסף את הישות **Subscription: SubscriptionHistory** ומפה את השדות מ- eCommerce לשדות המתאימים הנדרשים על-ידי המודל.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="bdfa1-208">הצטרף לישות **Subscription : SubscriptionHistory** עם **eCommerceContacts : eCommerce**, תן שם לקשר **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="הצטרף לישויות eCommerce.":::

1. <span data-ttu-id="bdfa1-210">תחת '‏‫פעילויות של לקוחות‬', הוסף את הישות **webReviews : Website** ומפה את השדות מ- webReviews לשדות המתאימים הנדרשים על-ידי המודל.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="bdfa1-211">מפתח ראשי: ReviewId</span><span class="sxs-lookup"><span data-stu-id="bdfa1-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="bdfa1-212">חותמת זמן: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="bdfa1-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="bdfa1-213">אירוע: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="bdfa1-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="bdfa1-214">הגדר פעילות עבור ביקורות של אתרים.‬</span><span class="sxs-lookup"><span data-stu-id="bdfa1-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="bdfa1-215">בחר את הפעילות **סקירה** והצטרף לישות **webReviews : Website** עם **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="bdfa1-216">בחר **הבא** כדי להגדיר את לוח הזמנים של המודל.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="bdfa1-217">המודל צריך לעבור הדרכה שוטפת כדי ללמוד דפוסים חדשים בעת קליטת נתונים חדשים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="bdfa1-218">עבור דוגמה זו, בחר **חודשי**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="bdfa1-219">לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="bdfa1-220">משימה 4 - סקירת תוצאות המודל והסברים</span><span class="sxs-lookup"><span data-stu-id="bdfa1-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="bdfa1-221">הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="bdfa1-222">כעת תוכל לעיין בהסברים אודות מודל נטישת המנויים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="bdfa1-223">למידע נוסף, ראה [סקירת מצב החיזוי ותוצאותיו](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="bdfa1-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="bdfa1-224">משימה 5 - יצירת פלח של לקוחות בסיכון גבוה לנטישה</span><span class="sxs-lookup"><span data-stu-id="bdfa1-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="bdfa1-225">הפעלת מודל הייצור יוצרת ישות חדשה שניתן לראות ב **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="bdfa1-226">ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="bdfa1-227">עבור אל **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-227">Go to **Segments**.</span></span> <span data-ttu-id="bdfa1-228">בחר **חדש** ובחר **צור מתוך** > **בינה**.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="יצירת פלח עם פלט המודל.":::

1. <span data-ttu-id="bdfa1-230">בחר את נקודת הקצה **OOBSubscriptionChurnPrediction** והגדר את הפלח:</span><span class="sxs-lookup"><span data-stu-id="bdfa1-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="bdfa1-231">שדה: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="bdfa1-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="bdfa1-232">אופרטור: גדול מ</span><span class="sxs-lookup"><span data-stu-id="bdfa1-232">Operator: greater than</span></span>
   - <span data-ttu-id="bdfa1-233">ערך: 0.6</span><span class="sxs-lookup"><span data-stu-id="bdfa1-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="הגדרת פלח של נטישת מנויים‬.":::

<span data-ttu-id="bdfa1-235">כעת יש לך פלח שמתעדכן באופן דינאמי, המזהה לקוחות בסיכון גבוה לנטישה עבור עסק זה של מנויים.</span><span class="sxs-lookup"><span data-stu-id="bdfa1-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="bdfa1-236">למידע נוסף: [יצירה וניהול של פלחים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="bdfa1-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]