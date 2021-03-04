---
title: מדריך לדוגמה לחיזוי נטישה של עסקאות
description: השתמש במדריך לדוגמה זה כדי לנסות את המודל לחיזוי נטישה של עסקאות המוכן לשימוש.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 81540ad2f490cf566f031233543b3cb6aa838033
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269791"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="0c5cd-103">מדריך לדוגמה לחיזוי נטישה של עסקאות (מהדורת Preview)</span><span class="sxs-lookup"><span data-stu-id="0c5cd-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="0c5cd-104">מדריך זה ינחה אותך וידגים דוגמה מקצה לקצה של חיזוי נטישה של עסקאות ב- Customer Insights באמצעות הנתונים המפורטים להלן.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="0c5cd-105">כל הנתונים המופיעים במדריך זה אינם נתונים אמיתיים של לקוחות והם חלק מערכת נתונים של Contoso הנמצאת בסביבת *הדגמה* במנוי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="0c5cd-106">תרחיש</span><span class="sxs-lookup"><span data-stu-id="0c5cd-106">Scenario</span></span>

<span data-ttu-id="0c5cd-107">Contoso היא חברה המייצרת קפה איכותי ומכונות קפה, שאותם היא מוכרת דרך האתר שלה Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="0c5cd-108">מטרת החברה היא לדעת אילו לקוחות, שבדרך כלל רוכשים את המוצרים שלהם על בסיס קבוע, יפסיקו להיות לקוחות פעילים ב- 60 הימים הקרובים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="0c5cd-109">הידיעה מי מהלקוחות **עשוי לנטוש**, יכולה לעזור לה לחסוך מאמצים שיווקיים על-ידי התמקדות בשימור הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0c5cd-110">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="0c5cd-110">Prerequisites</span></span>

- <span data-ttu-id="0c5cd-111">לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="0c5cd-112">אנו ממליצים ליישם את השלבים הבאים [בסביבה חדשה](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="0c5cd-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="0c5cd-113">משימה 1 - קליטת נתונים</span><span class="sxs-lookup"><span data-stu-id="0c5cd-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="0c5cd-114">עיין בעיקר במאמרים [אודות קליטת נתונים](data-sources.md) ו[ייבוא מקורות נתונים באמצעות מחברים של Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0c5cd-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="0c5cd-115">המידע הבא מניח שאתה מכיר את תהליך קליטת הנתונים באופן כללי.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="0c5cd-116">קליטת נתוני לקוחות מפלטפורמת eCommerce</span><span class="sxs-lookup"><span data-stu-id="0c5cd-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="0c5cd-117">צור מקור נתונים בשם **eCommerce**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="0c5cd-118">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="0c5cd-119">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="0c5cd-120">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="0c5cd-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="0c5cd-121">**DateOfBirth**: תאריך</span><span class="sxs-lookup"><span data-stu-id="0c5cd-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="0c5cd-122">**CreatedOn**: תאריך/שעה/אזור</span><span class="sxs-lookup"><span data-stu-id="0c5cd-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="0c5cd-123">![המרת תאריך הלידה לתאריך](media/ecommerce-dob-date.PNG "המרת תאריך הלידה לתאריך")</span><span class="sxs-lookup"><span data-stu-id="0c5cd-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="0c5cd-124">בשדה **שם** בחלונית הימנית, שנה את שם מקור נתונים שלך מ **שאילתה** ל- **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="0c5cd-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="0c5cd-125">שמור את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="0c5cd-126">קליטת נתוני רכישה מקוונים</span><span class="sxs-lookup"><span data-stu-id="0c5cd-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="0c5cd-127">הוסף ערכת נתונים נוספת לאותו מקור נתונים **eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="0c5cd-128">בחר שוב את המחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="0c5cd-129">הזן את כתובת ה- URL עבור נתוני **רכישות מקוונות** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="0c5cd-130">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="0c5cd-131">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="0c5cd-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="0c5cd-132">**PurchasedOn**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="0c5cd-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="0c5cd-133">**TotalPrice**: מטבע</span><span class="sxs-lookup"><span data-stu-id="0c5cd-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="0c5cd-134">בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="0c5cd-135">שמור את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="0c5cd-136">קליטת נתוני לקוחות מסכמת loyalty</span><span class="sxs-lookup"><span data-stu-id="0c5cd-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="0c5cd-137">צור מקור נתונים בשם **LoyaltyScheme**, בחר באפשרות הייבוא ובחר במחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="0c5cd-138">הזן את כתובת ה- URL עבור אנשי קשר של eCommerce https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="0c5cd-139">בזמן עריכת הנתונים, בחר **המרה** ולאחר מכן **השתמש בשורה הראשונה ככותרות**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="0c5cd-140">עדכן את סוג הנתונים עבור העמודות המפורטות להלן:</span><span class="sxs-lookup"><span data-stu-id="0c5cd-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="0c5cd-141">**DateOfBirth**: תאריך</span><span class="sxs-lookup"><span data-stu-id="0c5cd-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="0c5cd-142">**RewardsPoints**: מספר שלם</span><span class="sxs-lookup"><span data-stu-id="0c5cd-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="0c5cd-143">**CreatedOn**: תאריך/שעה</span><span class="sxs-lookup"><span data-stu-id="0c5cd-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="0c5cd-144">בשדה **שם** בחלונית הימנית, שנה את שם מקור הנתונים שלך מ **שאילתה** ל- **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="0c5cd-145">שמור את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="0c5cd-146">משימה 2 - איחוד נתונים</span><span class="sxs-lookup"><span data-stu-id="0c5cd-146">Task 2 - Data unification</span></span>

<span data-ttu-id="0c5cd-147">לאחר קליטת הנתונים אנו מתחילים כעת בתהליך **מיפוי, התאמה, מיזוג** כדי ליצור פרופיל לקוח מאוחד.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="0c5cd-148">לקבלת מידע נוסף, ראה [איחוד נתונים](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="0c5cd-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="0c5cd-149">מיפוי</span><span class="sxs-lookup"><span data-stu-id="0c5cd-149">Map</span></span>

1. <span data-ttu-id="0c5cd-150">לאחר קליטת הנתונים, מפה את אנשי הקשר מנתוני eCommerce ו- Loyalty לסוגי נתונים נפוצים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="0c5cd-151">עבור אל **נתונים** > **איחוד** > **מיפוי**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="0c5cd-152">בחר את הישויות המייצגות את פרופיל הלקוח – **eCommerceContacts** ו- **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="איחוד מקורות הנתונים ecommerce ו- loyalty.":::

1. <span data-ttu-id="0c5cd-154">בחר **ContactId** כמפתח העיקרי עבור **eCommerceContacts** ו- **LoyaltyID** כמפתח העיקרי עבור **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="איחוד LoyaltyId כמפתח ראשי.":::

### <a name="match"></a><span data-ttu-id="0c5cd-156">התאמה</span><span class="sxs-lookup"><span data-stu-id="0c5cd-156">Match</span></span>

1. <span data-ttu-id="0c5cd-157">עבור אל הכרטיסיה **התאמה** ובחר **הגדר סדר**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="0c5cd-158">ברשימה הנפתחת **ראשי**, בחר **eCommerceContacts : eCommerce** כמקור הראשי וכלול את כל הרשומות.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-158">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="0c5cd-159">ברשימה הנפתחת **ישות 2**, בחר **loyCustomers : LoyaltyScheme** וכלול את כל הרשומות.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-159">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="איחוד התאמה של eCommerce ו- Loyalty.":::

1. <span data-ttu-id="0c5cd-161">בחר **צור כלל חדש**</span><span class="sxs-lookup"><span data-stu-id="0c5cd-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="0c5cd-162">הוסף את התנאי הראשון שלך באמצעות FullName.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="0c5cd-163">עבור eCommerceContacts בחר **FullName** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-163">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="0c5cd-164">עבור loyCustomers בחר **FullName** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-164">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="0c5cd-165">בחר את הרשימה הנפתחת **נרמל** ובחר **סוג (טלפון, שם, כתובת, ...)**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="0c5cd-166">הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="0c5cd-167">הזן את השם **FullName, Email** עבור הכלל החדש.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="0c5cd-168">הוסף תנאי שני לכתובת הדואר האלקטרוני על-ידי בחירה **הוסף תנאי**</span><span class="sxs-lookup"><span data-stu-id="0c5cd-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="0c5cd-169">לישות eCommerceContacts, בחר **דואר** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-169">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="0c5cd-170">לישות loyCustomers, בחר **דואר** ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-170">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="0c5cd-171">השאר את השדה 'נרמל' ריק.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="0c5cd-172">הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="איחוד כלל התאמה עבור שם ודואר אלקטרוני.":::

7. <span data-ttu-id="0c5cd-174">בחר **שמור** ו **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="0c5cd-175">מזג</span><span class="sxs-lookup"><span data-stu-id="0c5cd-175">Merge</span></span>

1. <span data-ttu-id="0c5cd-176">עבור לכרטיסיה **מיזוג**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="0c5cd-177">ב- **ContactId** עבור הישות **loyCustomers**, שנה את שם התצוגה ל- **ContactIdLOYALTY** כדי להבחין בינה לבין מספרי זהות אחרים שנקלטו.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="שינוי שם ל- contactid מ- loyalty id.":::

1. <span data-ttu-id="0c5cd-179">בחר **שמור** ו **הפעל** כדי להתחיל בתהליך המיזוג.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="0c5cd-180">משימה 3 - הגדר את חיזוי נטישת העסקאות</span><span class="sxs-lookup"><span data-stu-id="0c5cd-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="0c5cd-181">מכיוון שפרופילי הלקוחות המאוחדים קיימים, אנו יכולים כעת להפעיל את חיזוי נטישת המנויים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="0c5cd-182">לקבלת השלבים המפורטים, עיין במאמר [חיזוי נטישה של מנויים (מהדורת Preview)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="0c5cd-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="0c5cd-183">עבור אל **בינה** > **גילוי** ובחר להשתמש ב **מודל נטישת לקוחות**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="0c5cd-184">בחר את האפשרות **עסקאות** ובחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="0c5cd-185">תן שם למודל **OOB eCommerce Transaction Churn Prediction** ולישות הפלט **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="0c5cd-186">הגדר שני תנאים עבור מודל הנטישה:</span><span class="sxs-lookup"><span data-stu-id="0c5cd-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="0c5cd-187">**חלון חיזוי**: **לפחות 60** ימים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="0c5cd-188">הגדרה זו קובעת כמה רחוק בעתיד אנו רוצים לחזות את נטישת הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="0c5cd-189">**הגדרת נטישה**: **לפחות 60** ימים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="0c5cd-190">משך הזמן ללא רכישה שלאחריה נחשב הלקוח כלקוח שנטש.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="בחר את מנופי המודל 'חלון חיזוי' ו'הגדרת נטישה'.":::

1. <span data-ttu-id="0c5cd-192">בחר **היסטוריית רכישות‬ (נדרש)** ובחר **הוסף נתונים** עבור היסטוריית רכישות.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="0c5cd-193">הוסף את הישות **eCommercePurchases : eCommerce** ומפה את השדות מ- eCommerce לשדות המתאימים הנדרשים על-ידי המודל.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="0c5cd-194">הצטרף לישות **eCommercePurchases: eCommerce** עם **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="הצטרף לישויות eCommerce.":::

1. <span data-ttu-id="0c5cd-196">בחר **הבא** כדי להגדיר את לוח הזמנים של המודל.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="0c5cd-197">המודל צריך לעבור הדרכה שוטפת כדי ללמוד דפוסים חדשים בעת קליטת נתונים חדשים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="0c5cd-198">עבור דוגמה זו, בחר **חודשי**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="0c5cd-199">לאחר בדיקה של כל הפרטים, בחר **שמור והפעל**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="0c5cd-200">משימה 4 - סקירת תוצאות המודל והסברים</span><span class="sxs-lookup"><span data-stu-id="0c5cd-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="0c5cd-201">הנח למודל להשלים את ההדרכה ואת ניקוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="0c5cd-202">כעת תוכל לעיין בהסברים אודות מודל נטישת המנויים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="0c5cd-203">למידע נוסף, ראה [סקירת מצב החיזוי ותוצאותיו](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="0c5cd-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="0c5cd-204">משימה 5 - יצירת פלח של לקוחות בסיכון גבוה לנטישה</span><span class="sxs-lookup"><span data-stu-id="0c5cd-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="0c5cd-205">הפעלת מודל הייצור יוצרת ישות חדשה שניתן לראות ב **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="0c5cd-206">ניתן ליצור פלח חדש המבוסס על הישות שנוצרה על-ידי המודל.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="0c5cd-207">עבור אל **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-207">Go to **Segments**.</span></span> <span data-ttu-id="0c5cd-208">בחר **חדש** ובחר **צור מתוך** > **בינה**.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="יצירת פלח עם פלט המודל.":::

1. <span data-ttu-id="0c5cd-210">בחר את נקודת הקצה **OOBSubscriptionChurnPrediction** והגדר את הפלח:</span><span class="sxs-lookup"><span data-stu-id="0c5cd-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="0c5cd-211">שדה: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="0c5cd-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="0c5cd-212">אופרטור: גדול מ</span><span class="sxs-lookup"><span data-stu-id="0c5cd-212">Operator: greater than</span></span>
   - <span data-ttu-id="0c5cd-213">ערך: 0.6</span><span class="sxs-lookup"><span data-stu-id="0c5cd-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="הגדרת פלח של נטישת מנויים‬.":::

<span data-ttu-id="0c5cd-215">כעת יש לך פלח שמתעדכן באופן דינאמי, המזהה לקוחות בסיכון גבוה לנטישה עבור עסק זה של מנויים.</span><span class="sxs-lookup"><span data-stu-id="0c5cd-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="0c5cd-216">למידע נוסף: [יצירה וניהול של פלחים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0c5cd-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]