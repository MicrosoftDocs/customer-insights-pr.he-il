---
title: חיזוי נטישה של עסקאות
description: חזה אם קיימת סכנה שלקוח לא ירכוש עוד את המוצרים או השירותים שלך.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 43fcd37f8dd71e2890334a4cc53d49dae97d63c6
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906857"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="17357-103">חיזוי נטישה של עסקאות (Preview)</span><span class="sxs-lookup"><span data-stu-id="17357-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="17357-104">חיזוי נטישה של עסקאות עוזר לחזות אם לקוח לא ירכוש עוד את המוצרים או השירותים שלך בחלון זמן נתון.</span><span class="sxs-lookup"><span data-stu-id="17357-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="17357-105">באפשרותך ליצור תחזיות נטישה חדשות דרך **בינה** > **תחזיות**.</span><span class="sxs-lookup"><span data-stu-id="17357-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="17357-106">בחר **התחזיות שלי** כדי לראות חיזויים אחרים שיצרת.</span><span class="sxs-lookup"><span data-stu-id="17357-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="17357-107">נסה את ערכת הלימוד עבור חיזוי נטישה של עסקאות באמצעות נתונים לדוגמה: [מדריך לדוגמה של חיזוי נטישה של עסקאות (Preview)](sample-guide-predict-transactional-churn.md).</span><span class="sxs-lookup"><span data-stu-id="17357-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="17357-108">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="17357-108">Prerequisites</span></span>

- <span data-ttu-id="17357-109">לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="17357-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="17357-110">ידע עסקי כדי להבין מה המשמעות של הנטישה עבור העסק שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="17357-111">אנו תומכים בהגדרות נטישה מבוססת-זמן, כלומר שלקוח נחשב למי שנטש לאחר פרק זמן ללא רכישות.</span><span class="sxs-lookup"><span data-stu-id="17357-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="17357-112">נתונים על העסקאות/רכישות שלך וההיסטוריה שלהן:</span><span class="sxs-lookup"><span data-stu-id="17357-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="17357-113">מזהי עסקאות להבחנה בין רכישות/עסקאות.</span><span class="sxs-lookup"><span data-stu-id="17357-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="17357-114">מזהי לקוחות כדי להתאים עסקאות ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="17357-115">תאריכי אירוע עסקה, המגדירים את התאריכים שבהם התרחשה העסקה.</span><span class="sxs-lookup"><span data-stu-id="17357-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="17357-116">סכמת הנתונים הסמנטית לרכישות/עסקאות דורשת את המידע הבא:</span><span class="sxs-lookup"><span data-stu-id="17357-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="17357-117">**מזהה עסקה:** מזהה ייחודי של רכישה או עסקה.</span><span class="sxs-lookup"><span data-stu-id="17357-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="17357-118">**תאריך עסקה:** תאריך הרכישה או העסקה.</span><span class="sxs-lookup"><span data-stu-id="17357-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="17357-119">**שווי העסקה:** המטבע/סכום הערך המספרי של העסקה/פריט.</span><span class="sxs-lookup"><span data-stu-id="17357-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="17357-120">(אופציונלי) **מזהה מוצר ייחודי:** מזהה המוצר או השירות שנרכש אם הנתונים שלך הם ברמת פריט שורה.</span><span class="sxs-lookup"><span data-stu-id="17357-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="17357-121">(אופציונלי) **אם עסקה זו הייתה החזרה:** שדה true/false המזהה אם העסקה הייתה החזרה או לא.</span><span class="sxs-lookup"><span data-stu-id="17357-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="17357-122">אם **שווי העסקה** שלילי, אנו גם נשתמש במידע זה כדי להסיק החזרה.</span><span class="sxs-lookup"><span data-stu-id="17357-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="17357-123">(אופציונלי) נתונים על פעילויות לקוחות:</span><span class="sxs-lookup"><span data-stu-id="17357-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="17357-124">מזהי פעילות כדי להבחין בפעילויות מאותו סוג.</span><span class="sxs-lookup"><span data-stu-id="17357-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="17357-125">מזהי לקוחות כדי למפות פעילויות של הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="17357-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="17357-126">מידע על הפעילויות כולל את השם והתאריך של הפעילות.</span><span class="sxs-lookup"><span data-stu-id="17357-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="17357-127">סכמת הנתונים הסמנטית לפעילות לקוחות כוללת:</span><span class="sxs-lookup"><span data-stu-id="17357-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="17357-128">**מפתח ראשי:** מזהה ייחודי לפעילות.</span><span class="sxs-lookup"><span data-stu-id="17357-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="17357-129">לדוגמה, ביקור באתר או רשומת שימוש המציגים שהלקוח ניסה דוגמית של המוצר שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="17357-130">**חותמת זמן:** התאריך והשעה של האירוע שזוהו על ידי המפתח הראשי.</span><span class="sxs-lookup"><span data-stu-id="17357-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="17357-131">**אירוע:** שם האירוע שבו ברצונך להשתמש.</span><span class="sxs-lookup"><span data-stu-id="17357-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="17357-132">לדוגמא, שדה שנקרא "UserAction" בחנות מכולת עשוי להיות שימוש בקופון על-ידי הלקוח.</span><span class="sxs-lookup"><span data-stu-id="17357-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="17357-133">**פרטים:** מידע מפורט על האירוע.</span><span class="sxs-lookup"><span data-stu-id="17357-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="17357-134">לדוגמה, שדה בשם "CouponValue" בחנות מכולת עשוי להיות ערך המטבע של הקופון.</span><span class="sxs-lookup"><span data-stu-id="17357-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>
- <span data-ttu-id="17357-135">מאפייני נתונים מוצעים:</span><span class="sxs-lookup"><span data-stu-id="17357-135">Suggested data characteristics:</span></span>
    - <span data-ttu-id="17357-136">נתונים היסטוריים מספיקים: נתוני עסקה עבור לפחות פי שתיים מחלון הזמן שנבחר.</span><span class="sxs-lookup"><span data-stu-id="17357-136">Sufficient historical data: Transaction data for at least double the selected time window.</span></span> <span data-ttu-id="17357-137">רצוי שנתיים עד שלוש שנים של נתוני מנוי.</span><span class="sxs-lookup"><span data-stu-id="17357-137">Preferably, two to three years of subscription data.</span></span> 
    - <span data-ttu-id="17357-138">רכישות מרובות ללקוח: באופן אידיאלי לפחות שתי עסקאות לכל לקוח.</span><span class="sxs-lookup"><span data-stu-id="17357-138">Multiple purchases per customer: Ideally at least two transactions per customer.</span></span>
    - <span data-ttu-id="17357-139">מספר לקוחות: לפחות 10 פרופילי לקוח, רצוי יותר מ- 1,000 לקוחות ייחודיים.</span><span class="sxs-lookup"><span data-stu-id="17357-139">Number of customers: At least 10 customer profiles, preferably more than 1,000 unique customers.</span></span> <span data-ttu-id="17357-140">המודל ייכשל עם פחות מ- 10 לקוחות ונתונים היסטוריים לא מספיקים.</span><span class="sxs-lookup"><span data-stu-id="17357-140">The model will fail with fewer than 10 customers and insufficient historical data.</span></span>
    - <span data-ttu-id="17357-141">השלמת הנתונים: פחות מ- 20% מהערכים החסרים בשדה הנתונים של הישות שסופקה.</span><span class="sxs-lookup"><span data-stu-id="17357-141">Data completeness: Less than 20% of missing values in the data field of the entity provided.</span></span>

> [!NOTE]
> <span data-ttu-id="17357-142">לעסק עם תדירות רכישות לקוח גבוהה (מדי כמה שבועות), מומלץ לבחור חלון חיזוי קצר יותר והגדרת נטישה.</span><span class="sxs-lookup"><span data-stu-id="17357-142">For a business with high customer purchase frequency (every few weeks) it's recommended to select a shorter prediction window and churn definition.</span></span> <span data-ttu-id="17357-143">עבור תדירות רכישות נמוכה (מדי מספר חודשים או פעם בשנה), בחר חלון חיזוי ארוך יותר והגדרת נטישה.</span><span class="sxs-lookup"><span data-stu-id="17357-143">For low purchase frequency (every few months or once a year), choose a longer prediction window and churn definition.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="17357-144">יצירת חיזוי נטישה של עסקאות</span><span class="sxs-lookup"><span data-stu-id="17357-144">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="17357-145">ב- Customer Insights, עבור אל **בינה** > **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="17357-145">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="17357-146">בחר את האריח **מודל נטישת לקוחות (Preview)** ובחר **השתמש במודל זה**.</span><span class="sxs-lookup"><span data-stu-id="17357-146">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="17357-147">בחלונית **מודל נטישת לקוחות**, בחר **עסקה** ובחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="17357-147">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="צילום מסך עם אפשרות העסקה שנבחרה בחלונית מודל נטישת לקוחות.":::

### <a name="name-model"></a><span data-ttu-id="17357-149">מתן שם למודל</span><span class="sxs-lookup"><span data-stu-id="17357-149">Name model</span></span>

1. <span data-ttu-id="17357-150">תן שם למודל כדי להבדיל אותו ממודלים אחרים.</span><span class="sxs-lookup"><span data-stu-id="17357-150">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="17357-151">תן שם לישות הפלט שכולל אותיות ומספרים בלבד, ללא רווחים.</span><span class="sxs-lookup"><span data-stu-id="17357-151">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="17357-152">זה השם שבו ישות המודל תשתמש.</span><span class="sxs-lookup"><span data-stu-id="17357-152">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="17357-153">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="17357-153">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="17357-154">הגדרת נטישת לקוחות</span><span class="sxs-lookup"><span data-stu-id="17357-154">Define customer churn</span></span>

1. <span data-ttu-id="17357-155">הגדר חלון של ימים לחיזוי נטישה עבורו בשדה **זהה לקוחות שעלולים לנטוש בטווח הזמן הבא**.</span><span class="sxs-lookup"><span data-stu-id="17357-155">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="17357-156">לדוגמה, חזה את הסיכון לנטישה עבור הלקוחות שלך במשך 90 הימים הבאים כדי להתאים למאמצי השימור השיווקיים שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-156">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="17357-157">חיזוי סיכון לנטישה עבור פרק זמן ארוך או קצר יותר עשוי להקשות על הטיפול בגורמים בפרופיל סיכון הנטישה שלך, אבל זה תלוי בדרישות העסקיות הספציפיות.</span><span class="sxs-lookup"><span data-stu-id="17357-157">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="17357-158">אתה יכול לבחור **שמור וסגור** בכל עת כדי לשמור את החיזוי כטיוטה.</span><span class="sxs-lookup"><span data-stu-id="17357-158">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="17357-159">תמצא את הטיוטה של החיזוי בכרטיסיה **התחזיות שלי** כדי להמשיך.</span><span class="sxs-lookup"><span data-stu-id="17357-159">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="17357-160">הזן את מספר הימים להגדרת נטישה בשדה **לקוח נחשב כלקוח שנטש אם הוא לא ביצע רכישות ב:**.</span><span class="sxs-lookup"><span data-stu-id="17357-160">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="17357-161">לדוגמא, אם לקוח לא ביצע רכישות ב- 30 הימים האחרונים, הוא עשוי להיחשב כלקוח שנטש עבור העסק שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-161">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="17357-162">בחר **הבא** כדי להמשיך</span><span class="sxs-lookup"><span data-stu-id="17357-162">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="17357-163">הוספת נתונים נדרשים</span><span class="sxs-lookup"><span data-stu-id="17357-163">Add required data</span></span>

1. <span data-ttu-id="17357-164">בחר **הוסף נתונים** עבור **היסטוריית רכישות** ובחר בישות המספקת את המידע על היסטוריית העסקאות/הרכישות כמתואר ב[דרישות מוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="17357-164">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="17357-165">מפה את השדות הסמנטיים לתכונות בישות היסטוריית הרכישות שלך ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="17357-165">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="17357-166">לתיאורים של השדות, בדוק את [ה‏‫דרישות המוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="17357-166">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="מפה שדות סמנטיים של היסטוריית הרכישות.":::

1. <span data-ttu-id="17357-168">אם השדות שלהלן אינם מאוכלסים, הגדר את הקשר מישות היסטוריית הרכישות שלך לישות 'לקוח'.</span><span class="sxs-lookup"><span data-stu-id="17357-168">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="17357-169">בחר את **ישות היסטוריית הרכישות**.</span><span class="sxs-lookup"><span data-stu-id="17357-169">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="17357-170">בחר את **שדה** המזהה את הלקוח בישות היסטוריית הרכישות.</span><span class="sxs-lookup"><span data-stu-id="17357-170">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="17357-171">עליו להתייחס למזהה הלקוח העיקרי של ישות הלקוח שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-171">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="17357-172">בחר את **ישות לקוח** שמתאימה לישות הלקוח העיקרית שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-172">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="17357-173">הקלד שם המתאר את הקשר.</span><span class="sxs-lookup"><span data-stu-id="17357-173">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="דף היסטוריית הרכישות המציג את היצירה של קשר עם הלקוח.":::
   
1. <span data-ttu-id="17357-175">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="17357-175">Select **Next**.</span></span>

1. <span data-ttu-id="17357-176">לחלופין, בחר **הוסף נתונים** עבור **פעילויות לקוח**.</span><span class="sxs-lookup"><span data-stu-id="17357-176">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="17357-177">בחר את הישות המספקת את פרטי פעילות הלקוח כמתואר בדרישות המוקדמות.</span><span class="sxs-lookup"><span data-stu-id="17357-177">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="17357-178">מפה את השדות הסמנטיים לתכונות בישות פעילות הלקוח שלך ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="17357-178">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="17357-179">לתיאורים של השדות, בדוק את [ה‏‫דרישות המוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="17357-179">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="מפה שדות לקוחות לנתוני עסקאות.":::

1. <span data-ttu-id="17357-181">בחר סוג פעילות שתואם את סוג הפעילות של הלקוח שאתה מגדיר.</span><span class="sxs-lookup"><span data-stu-id="17357-181">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="17357-182">בחר **צור חדש** ובחר סוג פעילות זמין או צור סוג חדש.</span><span class="sxs-lookup"><span data-stu-id="17357-182">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="17357-183">יהיה עליך להגדיר את הקשר בין ישות פעילות הלקוח לישות הלקוח.</span><span class="sxs-lookup"><span data-stu-id="17357-183">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="17357-184">בחר את השדה המזהה את הלקוח בטבלת פעילות הלקוח.</span><span class="sxs-lookup"><span data-stu-id="17357-184">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="17357-185">הוא עשוי להיות קשור ישירות למזהה הלקוח הראשי של הישות 'לקוח' שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-185">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="17357-186">בחר את ישות לקוח שמתאימה לישות הלקוח העיקרית שלך</span><span class="sxs-lookup"><span data-stu-id="17357-186">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="17357-187">הקלד שם המתאר את הקשר.</span><span class="sxs-lookup"><span data-stu-id="17357-187">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="17357-188">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="17357-188">Select **Save**.</span></span>

1. <span data-ttu-id="17357-189">אם יש לך פעילויות אחרות של לקוחות שברצונך לכלול, חזור על השלבים לעיל.</span><span class="sxs-lookup"><span data-stu-id="17357-189">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="17357-190">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="17357-190">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="17357-191">הגדרת לוח זמנים ובדיקת תצורה</span><span class="sxs-lookup"><span data-stu-id="17357-191">Set schedule and review configuration</span></span>

1. <span data-ttu-id="17357-192">הגדר שכיחות כדי לאמן מחדש את המודל שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-192">Set a frequency to retrain your model.</span></span> <span data-ttu-id="17357-193">הגדרה זו חשובה כדי לעדכן את דיוק החיזויים כאשר נתונים חדשים מעובדים.</span><span class="sxs-lookup"><span data-stu-id="17357-193">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="17357-194">מרבית העסקים יכולים לבצע אימון פעם בחודש ולקבל דיוק טוב לחיזוי שלהם.</span><span class="sxs-lookup"><span data-stu-id="17357-194">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="17357-195">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="17357-195">Select **Next**.</span></span>

1. <span data-ttu-id="17357-196">סקור את תצורת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="17357-196">Review the configuration of the prediction.</span></span> <span data-ttu-id="17357-197">באפשרותך לחזור לשלבים הקודמים על-ידי בחירת **ערוך** תחת הערך המוצג.</span><span class="sxs-lookup"><span data-stu-id="17357-197">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="17357-198">לחלופין, תוכל לבחור שלב תצורה במחוון ההתקדמות.</span><span class="sxs-lookup"><span data-stu-id="17357-198">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="17357-199">אם כל הערכים מוגדרים כהלכה, בחר **שמור והפעל** כדי להתחיל בתהליך החיזוי.</span><span class="sxs-lookup"><span data-stu-id="17357-199">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="17357-200">בכרטיסיה **החיזויים שלי**, תוכל לראות את מצב החיזויים שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-200">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="17357-201">התהליך עשוי להימשך מספר שעות עד להשלמתו, תלוי בכמות הנתונים המשמשים בחיזוי.</span><span class="sxs-lookup"><span data-stu-id="17357-201">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="17357-202">סקור את מצב החיזוי והתוצאות</span><span class="sxs-lookup"><span data-stu-id="17357-202">Review a prediction status and results</span></span>

1. <span data-ttu-id="17357-203">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="17357-203">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="17357-204">בחר בחיזוי שברצונך לבדוק.</span><span class="sxs-lookup"><span data-stu-id="17357-204">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="17357-205">**שם חיזוי:** שם החיזוי שסופק בעת יצירתו.</span><span class="sxs-lookup"><span data-stu-id="17357-205">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="17357-206">**סוג חיזוי:** סוג המודל המשמש עבור החיזוי</span><span class="sxs-lookup"><span data-stu-id="17357-206">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="17357-207">**ישות פלט:** שם הישות לאחסון פלט החיזוי.</span><span class="sxs-lookup"><span data-stu-id="17357-207">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="17357-208">אתה יכול למצוא ישות עם שם זה ב- **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="17357-208">You can find an entity with this name on **Data** > **Entities**.</span></span>    
     <span data-ttu-id="17357-209">בישות הפלט, *ChurnScore* הוא ההסתברות החזויה לנטישה ו- *IsChurn* הוא תווית בינארית המבוססת על *ChurnScore* עם ערך סף של 0.5.</span><span class="sxs-lookup"><span data-stu-id="17357-209">In the output entity, *ChurnScore* is the predicted probability of churn and *IsChurn* is a binary label based on *ChurnScore* with 0.5 threshold.</span></span> <span data-ttu-id="17357-210">ייתכן שערך הסף של ברירת המחדל לא יפעל עבור התרחיש שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-210">The default threshold might not work for your scenario.</span></span> <span data-ttu-id="17357-211">[צור פלח חדש](segments.md#create-a-new-segment) עם ערך הסף המועדף עליך.</span><span class="sxs-lookup"><span data-stu-id="17357-211">[Create a new segment](segments.md#create-a-new-segment) with your preferred threshold.</span></span>
     <span data-ttu-id="17357-212">לא כל הלקוחות הם בהכרח לקוחות פעילים.</span><span class="sxs-lookup"><span data-stu-id="17357-212">Not all customers are necessarily active customers.</span></span> <span data-ttu-id="17357-213">ייתכן שלחלקם לא הייתה פעילות במשך זמן רב והם נחשבים כבר ללקוחות שנטשו, בהתבסס על הגדרת הנטישה שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-213">Some of them may not have had any activity for a long time and are considered as churned already, based on you churn definition.</span></span> <span data-ttu-id="17357-214">חיזוי הסיכון לנטישה עבור לקוחות שכבר נטשו אינו שימושי משום שאינם קהל היעד שאתה מגלה בו עניין.</span><span class="sxs-lookup"><span data-stu-id="17357-214">Predicting the churn risk for customers who already churned isn't useful because the are not the audience of interest.</span></span>
   - <span data-ttu-id="17357-215">**שדה חזוי:** שדה זה מאוכלס רק עבור סוגים מסוימים של תחזיות, ואינו משמש בחיזוי נטישות.</span><span class="sxs-lookup"><span data-stu-id="17357-215">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="17357-216">**מצב:** מצב הפעלת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="17357-216">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="17357-217">**הוצב בתור:** חיזוי ממתין להפעלת תהליכים אחרים.</span><span class="sxs-lookup"><span data-stu-id="17357-217">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="17357-218">**מרענן:** חיזוי פועל כעת כדי ליצור תוצאות שיזרמו לישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="17357-218">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="17357-219">**נכשל:** הפעלת החיזוי נכשלה.</span><span class="sxs-lookup"><span data-stu-id="17357-219">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="17357-220">[סקור את יומני הרישום](#troubleshoot-a-failed-prediction) לקבלת פרטים נוספים.</span><span class="sxs-lookup"><span data-stu-id="17357-220">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="17357-221">**הצליח:** החיזוי הצליח.</span><span class="sxs-lookup"><span data-stu-id="17357-221">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="17357-222">בחר **הצג** מתחת לשלוש הנקודות האנכיות כדי לבדוק את החיזוי</span><span class="sxs-lookup"><span data-stu-id="17357-222">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="17357-223">**נערך:** התאריך שבו השתנתה הגדרת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="17357-223">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="17357-224">**רענון אחרון:** התאריך שבו בוצע רענון של תוצאות החיזוי בישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="17357-224">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="17357-225">בחר את שלוש הנקודות האנכיות לצד החיזוי שתרצה לבדוק את התוצאות שלו ובחר **הצג**.</span><span class="sxs-lookup"><span data-stu-id="17357-225">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="פקד תצוגה להצגת תוצאות של חיזוי.":::   

1. <span data-ttu-id="17357-227">ישנם שלושה חלקים עיקריים של נתונים בדף התוצאות:</span><span class="sxs-lookup"><span data-stu-id="17357-227">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="17357-228">**ביצועי מודל אימון:** A, B או C הם ציונים אפשריים.</span><span class="sxs-lookup"><span data-stu-id="17357-228">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="17357-229">ניקוד זה מציין את ביצועי החיזוי ויכול לעזור לך לקבל את ההחלטה להשתמש בתוצאות המאוחסנות בישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="17357-229">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="17357-230">הניקוד נקבע על פי הכללים הבאים:</span><span class="sxs-lookup"><span data-stu-id="17357-230">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="17357-231">**A** כאשר המודל ניבא במדויק לפחות 50% מכלל התחזיות, וכאשר אחוז התחזיות המדויקות עבור לקוחות שנטשו גדול משיעור הבסיס ב- 10% לפחות.</span><span class="sxs-lookup"><span data-stu-id="17357-231">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="17357-232">**B** כאשר המודל ניבא במדויק לפחות 50% מכלל התחזיות, וכאשר אחוז התחזיות המדויקות עבור לקוחות שנטשו גדול בעד 10% מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="17357-232">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="17357-233">**C** כאשר המודל ניבא במדויק פחות מ- 50% מכלל התחזיות, או כאשר אחוזי התחזיות המדויקות עבור הלקוחות שנטשו קטנים מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="17357-233">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="17357-234">**בסיס** לוקח את קלט חלון הזמן של החיזוי עבור המודל (לדוגמה, שנה אחת) והמודל יוצר חלקים שונים של זמן על-ידי חלוקה שלו ב- 2 עד שהוא מגיע לחודש אחד או פחות.</span><span class="sxs-lookup"><span data-stu-id="17357-234">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="17357-235">הוא משתמש בחלקים אלה כדי ליצור כלל עסקי עבור לקוחות שלא רכשו במסגרת זמן זו.</span><span class="sxs-lookup"><span data-stu-id="17357-235">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="17357-236">לקוחות אלה נחשבים ללקוחות שנטשו.</span><span class="sxs-lookup"><span data-stu-id="17357-236">These customers are considered as churned.</span></span> <span data-ttu-id="17357-237">הכלל העסקי מבוסס הזמן עם היכולת הגבוהה ביותר לחזות מי עשוי לנטוש נבחר כמודל בסיסי.</span><span class="sxs-lookup"><span data-stu-id="17357-237">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="17357-238">**הסבירות לנטוש (מספר לקוחות):** קבוצות של לקוחות בהתבסס על הסיכון החזוי שלהם לנטוש.</span><span class="sxs-lookup"><span data-stu-id="17357-238">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="17357-239">נתונים אלה יכולים לעזור לך מאוחר יותר אם ברצונך ליצור פלח של לקוחות עם סיכון גבוה לנטישה.</span><span class="sxs-lookup"><span data-stu-id="17357-239">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="17357-240">פלחים כאלה עוזרים להבין היכן כדאי לקצץ בחברות בפלח.</span><span class="sxs-lookup"><span data-stu-id="17357-240">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="17357-241">**הגורמים המשפיעים ביותר:** ישנם גורמים רבים אשר נלקחים בחשבון בעת יצירת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="17357-241">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="17357-242">לכל אחד מהגורמים יש חשיבות משלו המחושבת עבור התחזיות המצטברות שמודל יוצר.</span><span class="sxs-lookup"><span data-stu-id="17357-242">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="17357-243">אתה יכול להשתמש בגורמים אלה כדי לסייע באימות תוצאות החיזוי שלך.</span><span class="sxs-lookup"><span data-stu-id="17357-243">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="17357-244">לחלופין, תוכל להשתמש במידע זה מאוחר יותר כדי [ליצור פלחים](segments.md), מה שעשוי לעזור להשפיע על סיכויי הנטישה של הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="17357-244">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="17357-245">פתור בעיה של חיזוי שנכשל</span><span class="sxs-lookup"><span data-stu-id="17357-245">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="17357-246">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="17357-246">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="17357-247">בחר את שלוש הנקודות האנכיות לצד התחזית שברצונך להציג יומני שגיאה עבורה.</span><span class="sxs-lookup"><span data-stu-id="17357-247">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="17357-248">בחר **יומנים**.</span><span class="sxs-lookup"><span data-stu-id="17357-248">Select **Logs**.</span></span>

1. <span data-ttu-id="17357-249">סקירת כל השגיאות.</span><span class="sxs-lookup"><span data-stu-id="17357-249">Review all the errors.</span></span> <span data-ttu-id="17357-250">יש מספר סוגים של שגיאות שיכולות להתרחש, והם מתארים איזה מצב גרם לשגיאה.</span><span class="sxs-lookup"><span data-stu-id="17357-250">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="17357-251">לדוגמה, שגיאה כי אין מספיק נתונים כדי לחזות במדויק נפתרת בדרך כלל על ידי טעינת נתונים נוספים ל- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="17357-251">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="17357-252">רענן חיזוי</span><span class="sxs-lookup"><span data-stu-id="17357-252">Refresh a prediction</span></span>

<span data-ttu-id="17357-253">החיזוי יחודש באופן אוטומטי באותו [תזמון של רענון הנתונים](system.md#schedule-tab) כפי שהוגדר בהגדרות.</span><span class="sxs-lookup"><span data-stu-id="17357-253">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="17357-254">באפשרותך לרענן אותם גם באופן ידני.</span><span class="sxs-lookup"><span data-stu-id="17357-254">You can refresh them manually too.</span></span>

1. <span data-ttu-id="17357-255">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="17357-255">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="17357-256">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך לרענן.</span><span class="sxs-lookup"><span data-stu-id="17357-256">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="17357-257">בחר **רענן**.</span><span class="sxs-lookup"><span data-stu-id="17357-257">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="17357-258">מחק חיזוי</span><span class="sxs-lookup"><span data-stu-id="17357-258">Delete a prediction</span></span>

<span data-ttu-id="17357-259">מחיקת חיזוי גם מסירה את ישות הפלט שלו.</span><span class="sxs-lookup"><span data-stu-id="17357-259">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="17357-260">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="17357-260">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="17357-261">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך למחוק.</span><span class="sxs-lookup"><span data-stu-id="17357-261">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="17357-262">בחר **מחק**.</span><span class="sxs-lookup"><span data-stu-id="17357-262">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
