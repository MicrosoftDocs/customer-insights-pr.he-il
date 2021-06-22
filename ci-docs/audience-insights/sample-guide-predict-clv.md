---
title: חיזוי ערכי אורך החיים של הלקוח‬ - מדריך לדוגמה
description: השתמש במדריך לדוגמה זה כדי לנסות את מודל החיזוי של ערך אורך החיים של לקוח.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129946"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="136d3-103">חיזוי ערכי אורך החיים של הלקוח‬ (CLV) - מדריך לדוגמה</span><span class="sxs-lookup"><span data-stu-id="136d3-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="136d3-104">מדריך זה יציג לך דוגמה, מקצה לקצה, של ערך אורך חיים של לקוח (CLV) ב- Customer Insights באמצעות נתונים לדוגמה.</span><span class="sxs-lookup"><span data-stu-id="136d3-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="136d3-105">תרחיש</span><span class="sxs-lookup"><span data-stu-id="136d3-105">Scenario</span></span>

<span data-ttu-id="136d3-106">Contoso היא חברה שמייצרת קפה ומכונות קפה באיכות גבוהה.</span><span class="sxs-lookup"><span data-stu-id="136d3-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="136d3-107">היא מוכרת את המוצרים באמצעות אתר האינטרנט Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="136d3-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="136d3-108">החברה רוצה להבין את הערך (ההכנסות) שהלקוחות שלה יכול לייצר ב- 12 החודשים הבאים.</span><span class="sxs-lookup"><span data-stu-id="136d3-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="136d3-109">ידיעת הערך הצפוי של הלקוחות ב- 12 החודשים הבאים תסייע להם להפנות את מאמצי השיווק ללקוחות בעלי ערך גבוה.</span><span class="sxs-lookup"><span data-stu-id="136d3-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="136d3-110">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="136d3-110">Prerequisites</span></span>

- <span data-ttu-id="136d3-111">לפחות [הראשות משתתף](permissions.md) בתובנות לגבי קהלים.</span><span class="sxs-lookup"><span data-stu-id="136d3-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="136d3-112">אנו ממליצים ליישם את השלבים הבאים [בסביבה חדשה](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="136d3-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="136d3-113">משימה 1 - קליטת נתונים</span><span class="sxs-lookup"><span data-stu-id="136d3-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="136d3-114">עיין במאמרים [בנושא קליטת נתונים](data-sources.md) ו[ייבוא מקורות נתונים באמצעות מחברי Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="136d3-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="136d3-115">המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי.</span><span class="sxs-lookup"><span data-stu-id="136d3-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="136d3-116">קליטת נתוני לקוחות מפלטפורמת eCommerce</span><span class="sxs-lookup"><span data-stu-id="136d3-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="136d3-117">צור מקור נתונים בשם **eCommerce**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="136d3-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="136d3-118">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="136d3-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="136d3-119">בזמן עריכת הנתונים, בחר  **המרה**  ולאחר מכן  **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="136d3-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="136d3-120">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="136d3-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="136d3-121">**DateOfBirth**: תאריך</span><span class="sxs-lookup"><span data-stu-id="136d3-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="136d3-122">**CreatedOn**: תאריך/שעה/אזור</span><span class="sxs-lookup"><span data-stu-id="136d3-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המר את תאריך הלידה לתאריך.":::

1. <span data-ttu-id="136d3-124">בשדה 'שם' בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="136d3-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="136d3-125">**שמור** את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="136d3-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="136d3-126">קליטת נתוני רכישה מקוונים</span><span class="sxs-lookup"><span data-stu-id="136d3-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="136d3-127">הוסף ערכת נתונים נוספת לאותו מקור נתונים **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="136d3-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="136d3-128">בחר שוב את המחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="136d3-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="136d3-129">הזן את כתובת ה- URL עבור נתוני **רכישות מקוונות** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="136d3-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="136d3-130">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="136d3-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="136d3-131">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="136d3-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="136d3-132">**PurchasedOn**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="136d3-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="136d3-133">**TotalPrice**: מטבע</span><span class="sxs-lookup"><span data-stu-id="136d3-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="136d3-134">בשדה **שם** בחלונית הצדדית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="136d3-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="136d3-135">**שמור** את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="136d3-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="136d3-136">קליטת נתוני לקוחות מסכמת loyalty</span><span class="sxs-lookup"><span data-stu-id="136d3-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="136d3-137">צור מקור נתונים בשם **LoyaltyScheme**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="136d3-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="136d3-138">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="136d3-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="136d3-139">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="136d3-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="136d3-140">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="136d3-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="136d3-141">**DateOfBirth**: תאריך</span><span class="sxs-lookup"><span data-stu-id="136d3-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="136d3-142">**RewardsPoints**: מספר שלם</span><span class="sxs-lookup"><span data-stu-id="136d3-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="136d3-143">**CreatedOn**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="136d3-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="136d3-144">בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="136d3-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="136d3-145">**שמור** את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="136d3-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="136d3-146">קלוט נתוני לקוחות מביקורות של אתרים</span><span class="sxs-lookup"><span data-stu-id="136d3-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="136d3-147">צור מקור נתונים בשם **Website**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="136d3-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="136d3-148">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="136d3-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="136d3-149">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="136d3-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="136d3-150">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="136d3-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="136d3-151">**ReviewRating**: מספר עשרוני</span><span class="sxs-lookup"><span data-stu-id="136d3-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="136d3-152">**ReviewDate**: תאריך</span><span class="sxs-lookup"><span data-stu-id="136d3-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="136d3-153">בשדה 'שם' בחלונית השמאלית, שנה את שם מקור הנתונים מ **שאילתה** ל **ביקורות**.</span><span class="sxs-lookup"><span data-stu-id="136d3-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="136d3-154">**שמור** את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="136d3-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="136d3-155">משימה 2 - איחוד נתונים</span><span class="sxs-lookup"><span data-stu-id="136d3-155">Task 2 - Data unification</span></span>

<span data-ttu-id="136d3-156">לאחר קליטת הנתונים, כעת נתחיל בתהליך איחוד הנתונים ליצירת פרופיל לקוח מאוחד.</span><span class="sxs-lookup"><span data-stu-id="136d3-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="136d3-157">לקבלת מידע נוסף, ראה [איחוד נתונים](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="136d3-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="136d3-158">מיפוי</span><span class="sxs-lookup"><span data-stu-id="136d3-158">Map</span></span>

1. <span data-ttu-id="136d3-159">לאחר קליטת הנתונים, מפה את אנשי הקשר מנתוני eCommerce ו- Loyalty לסוגי נתונים נפוצים.</span><span class="sxs-lookup"><span data-stu-id="136d3-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="136d3-160">עבור אל **נתונים** > **איחוד** > **מיפוי**.</span><span class="sxs-lookup"><span data-stu-id="136d3-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="136d3-161">בחר את הישויות המייצגות את פרופיל הלקוח – **eCommerceContacts** ו- **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="136d3-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="136d3-162">לאחר מכן, בחר **החל**.</span><span class="sxs-lookup"><span data-stu-id="136d3-162">Then, select **Apply**.</span></span>

   ![איחוד מקורות הנתונים ecommerce ו- loyalty.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="136d3-164">בחר **ContactId** כמפתח העיקרי עבור **eCommerceContacts** ו- **LoyaltyID** כמפתח העיקרי עבור **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="136d3-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![איחוד LoyaltyId כמפתח ראשי.](media/unify-loyaltyid.png)

1. <span data-ttu-id="136d3-166">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="136d3-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="136d3-167">התאמה</span><span class="sxs-lookup"><span data-stu-id="136d3-167">Match</span></span>

1. <span data-ttu-id="136d3-168">עבור אל הכרטיסיה **התאמה** ובחר **הגדר סדר**.</span><span class="sxs-lookup"><span data-stu-id="136d3-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="136d3-169">ברשימה הנפתחת **ראשי**, בחר **eCommerceContacts : eCommerce** כמקור הראשי וכלול את כל הרשומות.</span><span class="sxs-lookup"><span data-stu-id="136d3-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="136d3-170">ברשימה הנפתחת **ישות 2**, בחר **loyCustomers : LoyaltyScheme** וכלול את כל הרשומות.</span><span class="sxs-lookup"><span data-stu-id="136d3-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![איחוד התאמה של eCommerce ו- Loyalty.](media/unify-match-order.png)

1. <span data-ttu-id="136d3-172">בחר **הוסף כלל**</span><span class="sxs-lookup"><span data-stu-id="136d3-172">Select **Add rule**</span></span>

1. <span data-ttu-id="136d3-173">הוסף את התנאי הראשון שלך באמצעות FullName.</span><span class="sxs-lookup"><span data-stu-id="136d3-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="136d3-174">עבור eCommerceContacts בחר **FullName** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="136d3-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="136d3-175">עבור loyCustomers בחר **FullName** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="136d3-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="136d3-176">בחר את הרשימה הנפתחת **נרמל** ובחר **סוג (טלפון, שם, כתובת, ...)**.</span><span class="sxs-lookup"><span data-stu-id="136d3-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="136d3-177">הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.</span><span class="sxs-lookup"><span data-stu-id="136d3-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="136d3-178">הזן את השם **FullName, Email** עבור הכלל החדש.</span><span class="sxs-lookup"><span data-stu-id="136d3-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="136d3-179">הוסף תנאי שני לכתובת הדואר האלקטרוני על-ידי בחירה **הוסף תנאי**</span><span class="sxs-lookup"><span data-stu-id="136d3-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="136d3-180">לישות eCommerceContacts, בחר **דואר** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="136d3-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="136d3-181">לישות loyCustomers, בחר **דואר** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="136d3-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="136d3-182">השאר את השדה 'נרמל' ריק.</span><span class="sxs-lookup"><span data-stu-id="136d3-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="136d3-183">הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.</span><span class="sxs-lookup"><span data-stu-id="136d3-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![איחוד כלל התאמה עבור שם ודואר אלקטרוני.](media/unify-match-rule.png)

1. <span data-ttu-id="136d3-185">בחר **סיום**.</span><span class="sxs-lookup"><span data-stu-id="136d3-185">Select **Done**.</span></span>

1. <span data-ttu-id="136d3-186">בחר **שמור** ו **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="136d3-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="136d3-187">מזג</span><span class="sxs-lookup"><span data-stu-id="136d3-187">Merge</span></span>

1. <span data-ttu-id="136d3-188">עבור לכרטיסיה **מיזוג**.</span><span class="sxs-lookup"><span data-stu-id="136d3-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="136d3-189">ב- **ContactId** עבור הישות **loyCustomers**, שנה את שם התצוגה ל- **ContactIdLOYALTY** כדי להבחין בינה לבין מספרי זהות אחרים שנקלטו.</span><span class="sxs-lookup"><span data-stu-id="136d3-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![שינוי שם ל- contactid מ- loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="136d3-191">בחר **שמור** ו **הפעל תהליכי מיזוג ומורד הזרם**.</span><span class="sxs-lookup"><span data-stu-id="136d3-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="136d3-192">משימה 3 - קביעת תצורה של חיזוי ערך אורך החיים של לקוח</span><span class="sxs-lookup"><span data-stu-id="136d3-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="136d3-193">בעזרת פרופילי הלקוח המאוחד, כעת נוכל להפעיל חיזוי של ערך אורך החיים של לקוח.</span><span class="sxs-lookup"><span data-stu-id="136d3-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="136d3-194">לקבלת שלבים מפורטים, ראה [‏‫חיזויי ערך אורך החיים של הלקוח (Preview)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="136d3-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="136d3-195">עבור אל **בינה**  > **חיזויים** ובחר את **מודל ערך אורך החיים של הלקוח**.</span><span class="sxs-lookup"><span data-stu-id="136d3-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="136d3-196">עבור על המידע בחלונית הצדדית ובחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="136d3-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="136d3-197">הענק שם למודל **חיזוי OOB eCommerce CLV** וישות הפלט **‎OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="136d3-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="136d3-198">הגדר העדפות מודל עבור מודל ה- CLV:</span><span class="sxs-lookup"><span data-stu-id="136d3-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="136d3-199">**‏‫תקופת זמן חיזוי‬**: **12 חודשים או שנה אחת**.</span><span class="sxs-lookup"><span data-stu-id="136d3-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="136d3-200">הגדרה זו קובעת לאיזה מרחק בעתיד יש לחזות את ערך אורך החיים של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="136d3-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="136d3-201">**לקוחות פעילים**: ציין מה המשמעות של לקוחות פעילים עבור העסק שלך.</span><span class="sxs-lookup"><span data-stu-id="136d3-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="136d3-202">הגדר את מסגרת הזמן ההיסטורית שבה ללקוח חייבת להיות עסקה אחת לפחות כדי להיחשב כפעיל.</span><span class="sxs-lookup"><span data-stu-id="136d3-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="136d3-203">המודל יחזה CLV רק עבור לקוחות פעילים.</span><span class="sxs-lookup"><span data-stu-id="136d3-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="136d3-204">בחר אם ברצונך לאפשר למודל לחשב את פרק הזמן בהתבסס על נתוני עסקאות היסטוריים או לספק מסגרת זמן ספציפית.</span><span class="sxs-lookup"><span data-stu-id="136d3-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="136d3-205">במדריך לדוגמה זה, אנו **מאפשרים למודל לחשב את מרווח הרכישה**, זוהי אפשרות ברירת המחדל.</span><span class="sxs-lookup"><span data-stu-id="136d3-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="136d3-206">**לקוחות בעלי ערך גבוה**: הגדר לקוחות בעלי ערך גבוה כאחוזון מהלקוחות המשתלמים ביותר.</span><span class="sxs-lookup"><span data-stu-id="136d3-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="136d3-207">המודל שמשתמש בקלט זה כדי לספק תוצאות שמתאימות להגדרה העסקית של לקוחות בעלי ערך גבוה.</span><span class="sxs-lookup"><span data-stu-id="136d3-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="136d3-208">תוכל לבחור לאפשר למודל להגדיר לקוחות בעלי ערך גבוה.</span><span class="sxs-lookup"><span data-stu-id="136d3-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="136d3-209">המודל משתמש בכלל היוריסטי שגוזר את האחוזון.</span><span class="sxs-lookup"><span data-stu-id="136d3-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="136d3-210">באפשרותך גם להגדיר לקוחות בעלי ערך גבוה כאחוזון מהלקוחות העתידיים המשתלמים ביותר.</span><span class="sxs-lookup"><span data-stu-id="136d3-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="136d3-211">במדריך לדוגמה זה, אנו מגדירים באופן ידני לקוחות הבעלי הערך הגבוה כ- **30% מהלקוחות המשתלמים הפעילים המובילים** ולאחר מכן בוחרים **הבא**.</span><span class="sxs-lookup"><span data-stu-id="136d3-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="שלב ההעדפות בחוויה המודרכת עבור מודל CLV.":::

1. <span data-ttu-id="136d3-213">בשלב **נתונים נדרשים**, בחר **הוסף נתונים** כדי לספק את נתוני היסטוריית העסקאות.</span><span class="sxs-lookup"><span data-stu-id="136d3-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="136d3-214">הוסף את הישות **eCommercePurchases: eCommerce** ומפה את התכונות הנדרשות על-ידי המודל:</span><span class="sxs-lookup"><span data-stu-id="136d3-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="136d3-215">מזהה עסקה: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="136d3-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="136d3-216">תאריך עסקה: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="136d3-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="136d3-217">סכום עסקה: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="136d3-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="136d3-218">מזהה מוצר: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="136d3-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="136d3-219">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="136d3-219">Select **Next**.</span></span>

1. <span data-ttu-id="136d3-220">הגדר את הקשר בין הישות **eCommercePurchases: eCommerce** לישות  **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="136d3-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="136d3-221">השלב **נתונים נוספים (אופציונלי)** מאפשר להוסיף נתוני פעילות לקוחות נוספים.</span><span class="sxs-lookup"><span data-stu-id="136d3-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="136d3-222">נתונים אלה יכולים לעזור להשיג יותר תובנות לגבי אינטראקציות של הלקוחות עם העסק שלך, ובכך לתרום ל- CLV.</span><span class="sxs-lookup"><span data-stu-id="136d3-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="136d3-223">הוספת אינטראקציות מרכזיות עם הלקוחות כמו יומני רשת, יומני שירות לקוחות או היסטוריית תוכניות הטבות יכולה לשפר את דיוק התחזיות.</span><span class="sxs-lookup"><span data-stu-id="136d3-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="136d3-224">בחר **הוסף נתונים** כדי לכלול נתוני פעילות לקוחות נוספים.</span><span class="sxs-lookup"><span data-stu-id="136d3-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="136d3-225">הוסף את ישות פעילות הלקוחות ומפה את שמות השדות שלה לשדות המתאימים הנדרשים על-ידי המודל:</span><span class="sxs-lookup"><span data-stu-id="136d3-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="136d3-226">ישות פעילות לקוחות: ביקורות: אתר אינטרנט</span><span class="sxs-lookup"><span data-stu-id="136d3-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="136d3-227">מפתח ראשי: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="136d3-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="136d3-228">חותמת זמן: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="136d3-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="136d3-229">אירוע (שם פעילות): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="136d3-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="136d3-230">פרטים (סכום או ערך): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="136d3-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="136d3-231">בחר **הבא** וקבע את התצורה של הפעילות ושל הקשר בין נתוני העסקאות לנתוני הלקוח:</span><span class="sxs-lookup"><span data-stu-id="136d3-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="136d3-232">סוג פעילות: בחר סוג קיים</span><span class="sxs-lookup"><span data-stu-id="136d3-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="136d3-233">תווית פעילות: סקירה</span><span class="sxs-lookup"><span data-stu-id="136d3-233">Activity label: Review</span></span>
   - <span data-ttu-id="136d3-234">תווית מקבילה: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="136d3-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="136d3-235">ישות לקוח: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="136d3-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="136d3-236">קשר: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="136d3-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="136d3-237">בחר **הבא** כדי להגדיר את לוח הזמנים של המודל.</span><span class="sxs-lookup"><span data-stu-id="136d3-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="136d3-238">יש להמשיך לתרגל את המודל כדי ללמוד דפוסים חדשים כאשר נתונים חדשים נקלטים.</span><span class="sxs-lookup"><span data-stu-id="136d3-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="136d3-239">לדוגמא זו, בחר **חודשי**.</span><span class="sxs-lookup"><span data-stu-id="136d3-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="136d3-240">לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**.</span><span class="sxs-lookup"><span data-stu-id="136d3-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="136d3-241">משימה 4 - סקירת תוצאות המודל והסברים</span><span class="sxs-lookup"><span data-stu-id="136d3-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="136d3-242">הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="136d3-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="136d3-243">בשלב הבא תוכלו לסקור את התוצאות וההסברים של מודל CLV.</span><span class="sxs-lookup"><span data-stu-id="136d3-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="136d3-244">למידע נוסף, ראה [סקירת מצב החיזוי ותוצאותיו](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="136d3-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="136d3-245">משימה 5 - יצירת פלח של לקוחות בעלי ערך גבוה</span><span class="sxs-lookup"><span data-stu-id="136d3-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="136d3-246">הפעלת המודל יוצרת ישות חדשה, שמופיעה תחת **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="136d3-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="136d3-247">ניתן ליצור פלח לקוחות חדש בהתבסס על הישות שנוצרה על-ידי המודל.</span><span class="sxs-lookup"><span data-stu-id="136d3-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="136d3-248">עבור אל **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="136d3-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="136d3-249">בחר **חדש** ובחר **צור מתוך** > **בינה**.</span><span class="sxs-lookup"><span data-stu-id="136d3-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![יצירת פלח עם פלט המודל.](media/segment-intelligence.png)

1. <span data-ttu-id="136d3-251">בחר בישות  **OOBeCommerceCLVPrediction** והגדר את הפלח:</span><span class="sxs-lookup"><span data-stu-id="136d3-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="136d3-252">שדה: CLVScore</span><span class="sxs-lookup"><span data-stu-id="136d3-252">Field: CLVScore</span></span>
  - <span data-ttu-id="136d3-253">אופרטור: גדול מ</span><span class="sxs-lookup"><span data-stu-id="136d3-253">Operator: greater than</span></span>
  - <span data-ttu-id="136d3-254">ערך: 1500</span><span class="sxs-lookup"><span data-stu-id="136d3-254">Value: 1500</span></span>

1. <span data-ttu-id="136d3-255">בחר **סקירה** ו **שמור** את הפלח.</span><span class="sxs-lookup"><span data-stu-id="136d3-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="136d3-256">כעת יש לך פלח שמזהה לקוחות שצפויים לייצר הכנסות בגובה של יותר מ- $1500 ב- 12 החודשים הבאים.</span><span class="sxs-lookup"><span data-stu-id="136d3-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="136d3-257">פלח זה מתעדכן באופן דינאמי כאשר נקלטים נתונים נוספים.</span><span class="sxs-lookup"><span data-stu-id="136d3-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="136d3-258">למידע נוסף: [יצירה וניהול של פלחים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="136d3-258">For more information, see [Create and manage segments](segments.md).</span></span>
