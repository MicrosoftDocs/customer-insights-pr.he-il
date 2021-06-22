---
title: מדריך לדוגמה של חיזוי המלצות על מוצרים
description: השתמש במדריך לדוגמה זה כדי לנסות את המודל לחיזוי המלצות על מוצרים המוכן לשימוש.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: b136084316da5ae17a8428236381f69e5c21f9ea
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129900"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="a4f78-103">מדריך לדוגמה של חיזוי המלצות על מוצרים (Preview)</span><span class="sxs-lookup"><span data-stu-id="a4f78-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="a4f78-104">אנו ננחה אותך ונדגים דוגמה מקצה לקצה של חיזוי המלצות על מוצרים באמצעות הנתונים לדוגמה המפורטים להלן.</span><span class="sxs-lookup"><span data-stu-id="a4f78-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="a4f78-105">תרחיש</span><span class="sxs-lookup"><span data-stu-id="a4f78-105">Scenario</span></span>

<span data-ttu-id="a4f78-106">Contoso היא חברה שמייצרת קפה ומכונות קפה באיכות גבוהה, ומוכרת אותם באמצעות אתר האינטרנט Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="a4f78-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="a4f78-107">המטרה שלה היא להבין על אילו מוצרים עליה להמליץ ללקוחות החוזרים שלה.</span><span class="sxs-lookup"><span data-stu-id="a4f78-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="a4f78-108">הידיעה מה לקוחות **עשויים לרכוש בסבירות גבוהה יותר** יכולה לעזור לה לחסוך במאמצי השיווק על-ידי התמקדות בפריטים ספציפיים.</span><span class="sxs-lookup"><span data-stu-id="a4f78-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4f78-109">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="a4f78-109">Prerequisites</span></span>

- <span data-ttu-id="a4f78-110">לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a4f78-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="a4f78-111">אנו ממליצים ליישם את השלבים הבאים [בסביבה חדשה](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="a4f78-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="a4f78-112">משימה 1 - קליטת נתונים</span><span class="sxs-lookup"><span data-stu-id="a4f78-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="a4f78-113">עיין בעיקר במאמרים [אודות קליטת נתונים](data-sources.md) ו[ייבוא מקורות נתונים באמצעות מחברים של Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a4f78-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="a4f78-114">המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי.</span><span class="sxs-lookup"><span data-stu-id="a4f78-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="a4f78-115">קליטת נתוני לקוחות מפלטפורמת eCommerce</span><span class="sxs-lookup"><span data-stu-id="a4f78-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="a4f78-116">צור מקור נתונים בשם **eCommerce**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a4f78-117">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="a4f78-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="a4f78-118">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a4f78-119">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="a4f78-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a4f78-120">**DateOfBirth**: תאריך</span><span class="sxs-lookup"><span data-stu-id="a4f78-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a4f78-121">**CreatedOn**: תאריך/שעה/אזור</span><span class="sxs-lookup"><span data-stu-id="a4f78-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="המר את תאריך הלידה לתאריך.":::

5. <span data-ttu-id="a4f78-123">בשדה 'שם' בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="a4f78-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="a4f78-124">**שמור** את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="a4f78-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="a4f78-125">קליטת נתוני רכישה מקוונים</span><span class="sxs-lookup"><span data-stu-id="a4f78-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="a4f78-126">הוסף ערכת נתונים נוספת לאותו מקור נתונים **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="a4f78-127">בחר שוב את המחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="a4f78-128">הזן את כתובת ה- URL עבור נתוני **רכישות מקוונות** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="a4f78-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="a4f78-129">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a4f78-130">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="a4f78-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a4f78-131">**PurchasedOn**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="a4f78-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="a4f78-132">**TotalPrice**: מטבע</span><span class="sxs-lookup"><span data-stu-id="a4f78-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="a4f78-133">בשדה **שם** בחלונית הצדדית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="a4f78-134">**שמור** את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="a4f78-134">**Save** the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="a4f78-135">קליטת נתוני לקוחות מסכמת loyalty</span><span class="sxs-lookup"><span data-stu-id="a4f78-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="a4f78-136">צור מקור נתונים בשם **LoyaltyScheme**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="a4f78-137">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="a4f78-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="a4f78-138">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="a4f78-139">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="a4f78-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="a4f78-140">**DateOfBirth**: תאריך</span><span class="sxs-lookup"><span data-stu-id="a4f78-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="a4f78-141">**RewardsPoints**: מספר שלם</span><span class="sxs-lookup"><span data-stu-id="a4f78-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="a4f78-142">**CreatedOn**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="a4f78-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="a4f78-143">בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="a4f78-144">**שמור** את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="a4f78-144">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="a4f78-145">משימה 2 - איחוד נתונים</span><span class="sxs-lookup"><span data-stu-id="a4f78-145">Task 2 - Data unification</span></span>

<span data-ttu-id="a4f78-146">לאחר קליטת הנתונים, כעת נתחיל בתהליך איחוד הנתונים ליצירת פרופיל לקוח מאוחד.</span><span class="sxs-lookup"><span data-stu-id="a4f78-146">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="a4f78-147">לקבלת מידע נוסף, ראה [איחוד נתונים](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="a4f78-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="a4f78-148">מיפוי</span><span class="sxs-lookup"><span data-stu-id="a4f78-148">Map</span></span>

1. <span data-ttu-id="a4f78-149">לאחר קליטת הנתונים, מפה את אנשי הקשר מנתוני eCommerce ו- Loyalty לסוגי נתונים נפוצים.</span><span class="sxs-lookup"><span data-stu-id="a4f78-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="a4f78-150">עבור אל **נתונים** > **איחוד** > **מיפוי**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="a4f78-151">בחר את הישויות המייצגות את פרופיל הלקוח – **eCommerceContacts** ו- **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![איחוד מקורות הנתונים ecommerce ו- loyalty.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="a4f78-153">בחר **ContactId** כמפתח העיקרי עבור **eCommerceContacts** ו- **LoyaltyID** כמפתח העיקרי עבור **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![איחוד LoyaltyId כמפתח ראשי.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="a4f78-155">התאמה</span><span class="sxs-lookup"><span data-stu-id="a4f78-155">Match</span></span>

1. <span data-ttu-id="a4f78-156">עבור אל הכרטיסיה **התאמה** ובחר **הגדר סדר**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="a4f78-157">ברשימה הנפתחת **ראשי**, בחר **eCommerceContacts : eCommerce** כמקור הראשי וכלול את כל הרשומות.</span><span class="sxs-lookup"><span data-stu-id="a4f78-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="a4f78-158">ברשימה הנפתחת **ישות 2**, בחר **loyCustomers : LoyaltyScheme** וכלול את כל הרשומות.</span><span class="sxs-lookup"><span data-stu-id="a4f78-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![איחוד התאמה של eCommerce ו- Loyalty.](media/unify-match-order.png)

4. <span data-ttu-id="a4f78-160">בחר **צור כלל חדש**</span><span class="sxs-lookup"><span data-stu-id="a4f78-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="a4f78-161">הוסף את התנאי הראשון שלך באמצעות FullName.</span><span class="sxs-lookup"><span data-stu-id="a4f78-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="a4f78-162">עבור eCommerceContacts בחר **FullName** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="a4f78-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="a4f78-163">עבור loyCustomers בחר **FullName** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="a4f78-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="a4f78-164">בחר את הרשימה הנפתחת **נרמל** ובחר **סוג (טלפון, שם, כתובת, ...)**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="a4f78-165">הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="a4f78-166">הזן את השם **FullName, Email** עבור הכלל החדש.</span><span class="sxs-lookup"><span data-stu-id="a4f78-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="a4f78-167">הוסף תנאי שני לכתובת הדואר האלקטרוני על-ידי בחירה **הוסף תנאי**</span><span class="sxs-lookup"><span data-stu-id="a4f78-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="a4f78-168">לישות eCommerceContacts, בחר **דואר** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="a4f78-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="a4f78-169">לישות loyCustomers, בחר **דואר** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="a4f78-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="a4f78-170">השאר את השדה 'נרמל' ריק.</span><span class="sxs-lookup"><span data-stu-id="a4f78-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="a4f78-171">הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![איחוד כלל התאמה עבור שם ודואר אלקטרוני.](media/unify-match-rule.png)

7. <span data-ttu-id="a4f78-173">בחר **שמור** ו **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="a4f78-174">מזג</span><span class="sxs-lookup"><span data-stu-id="a4f78-174">Merge</span></span>

1. <span data-ttu-id="a4f78-175">עבור לכרטיסיה **מיזוג**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="a4f78-176">ב- **ContactId** עבור הישות **loyCustomers**, שנה את שם התצוגה ל- **ContactIdLOYALTY** כדי להבחין בינה לבין מספרי זהות אחרים שנקלטו.</span><span class="sxs-lookup"><span data-stu-id="a4f78-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![שינוי שם ל- contactid מ- loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="a4f78-178">בחר **שמור** ו **הפעל** כדי להתחיל בתהליך המיזוג.</span><span class="sxs-lookup"><span data-stu-id="a4f78-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="a4f78-179">משימה 3 - קביעת התצורה של חיזוי המלצות על מוצרים</span><span class="sxs-lookup"><span data-stu-id="a4f78-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="a4f78-180">מכיוון שפרופילי הלקוחות המאוחדים קיימים, אנו יכולים כעת להפעיל את חיזוי נטישת המנויים.</span><span class="sxs-lookup"><span data-stu-id="a4f78-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="a4f78-181">עבור אל **בינה** > **חיזוי** ובחר **המלצות על מוצרים**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="a4f78-182">בחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-182">Select **Get started**.</span></span>

1. <span data-ttu-id="a4f78-183">קרא למודל **OOB Product Recommendation Model Prediction** ולישות הפלט **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="a4f78-184">הגדר שלושה תנאים עבור המודל:</span><span class="sxs-lookup"><span data-stu-id="a4f78-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="a4f78-185">**מספר המוצרים**: הגדר ערך זה ל- **5**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="a4f78-186">הגדרה זו מגדירה על כמה מוצרים ברצונך להמליץ ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="a4f78-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="a4f78-187">**‏‫רכישות חוזרות צפויות**: בחר **כן** כדי לציין שברצונך לכלול בהמלצה מוצרים שהלקוחות רכשו בעבר.</span><span class="sxs-lookup"><span data-stu-id="a4f78-187">**Repeat purchases expected**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="a4f78-188">**חלון מבט לאחור:** בחר לפחות **365 יום**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="a4f78-189">הגדרה זו מגדירה עד איזו נקודת זמן בעבר המודל יבחן את פעילות הלקוח כדי להשתמש בה כקלט בהמלצות שלו.</span><span class="sxs-lookup"><span data-stu-id="a4f78-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="העדפות מודל עבור מודל ההמלצות על מוצרים.":::

1. <span data-ttu-id="a4f78-191">בחר **נתונים נדרשים** ובחר **הוסף נתונים** עבור היסטוריית רכישות.</span><span class="sxs-lookup"><span data-stu-id="a4f78-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="a4f78-192">הוסף את הישות **eCommercePurchases : eCommerce** ומפה את השדות מ- eCommerce לשדות המתאימים הנדרשים על-ידי המודל.</span><span class="sxs-lookup"><span data-stu-id="a4f78-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="a4f78-193">הצטרף לישות **eCommercePurchases: eCommerce** עם **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![הצטרף לישויות eCommerce.](media/model-purchase-join.png)

1. <span data-ttu-id="a4f78-195">בחר **הבא** כדי להגדיר את לוח הזמנים של המודל.</span><span class="sxs-lookup"><span data-stu-id="a4f78-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="a4f78-196">המודל צריך לעבור הדרכה שוטפת כדי ללמוד דפוסים חדשים בעת קליטת נתונים חדשים.</span><span class="sxs-lookup"><span data-stu-id="a4f78-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="a4f78-197">עבור דוגמה זו, בחר **חודשי**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="a4f78-198">לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="a4f78-199">משימה 4 - סקירת תוצאות המודל והסברים</span><span class="sxs-lookup"><span data-stu-id="a4f78-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="a4f78-200">הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="a4f78-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="a4f78-201">כעת תוכל לעיין בהסברים אודות מודל ההמלצות על מוצרים.</span><span class="sxs-lookup"><span data-stu-id="a4f78-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="a4f78-202">למידע נוסף, ראה [סקירת מצב החיזוי ותוצאותיו](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="a4f78-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="a4f78-203">משימה 5 - יצירת פלח עבור מוצרים שנרכשים בתדירות גבוהה</span><span class="sxs-lookup"><span data-stu-id="a4f78-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="a4f78-204">הפעלת מודל הייצור יוצרת ישות חדשה שניתן לראות ב **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="a4f78-205">ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.</span><span class="sxs-lookup"><span data-stu-id="a4f78-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="a4f78-206">עבור אל **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-206">Go to **Segments**.</span></span> <span data-ttu-id="a4f78-207">בחר **חדש** ובחר **צור מתוך** > **בינה**.</span><span class="sxs-lookup"><span data-stu-id="a4f78-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![יצירת פלח עם פלט המודל.](media/segment-intelligence.png)

1. <span data-ttu-id="a4f78-209">בחר את נקודת הקצה **OOBProductRecommendationModelPrediction** והגדר את הפלח:</span><span class="sxs-lookup"><span data-stu-id="a4f78-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="a4f78-210">שדה: מזהה מוצר</span><span class="sxs-lookup"><span data-stu-id="a4f78-210">Field: ProductID</span></span>
   - <span data-ttu-id="a4f78-211">אופרטור: Value</span><span class="sxs-lookup"><span data-stu-id="a4f78-211">Operator: Value</span></span>
   - <span data-ttu-id="a4f78-212">ערך: בחר את שלושת מזהי המוצר המובילים</span><span class="sxs-lookup"><span data-stu-id="a4f78-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="צור פלח מתוצאות המודל.":::

<span data-ttu-id="a4f78-214">כעת יש לך פלח שעודכן באופן דינמי אשר מזהה את הלקוחות בעלי המוכנות הגדולה יותר לרכוש את שלושת המוצרים המומלצים ביותר</span><span class="sxs-lookup"><span data-stu-id="a4f78-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="a4f78-215">למידע נוסף: [יצירה וניהול של פלחים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="a4f78-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
