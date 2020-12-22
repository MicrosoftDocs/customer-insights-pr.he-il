---
title: חיזוי נטישה של עסקאות
description: חזה אם קיימת סכנה שלקוח לא ירכוש עוד את המוצרים או השירותים שלך.
ms.date: 11/12/2020
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f3cbbf99a6cecba2aab2cf85428d53e5df8346e4
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644404"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="c123e-103">חיזוי נטישה של עסקאות (Preview)</span><span class="sxs-lookup"><span data-stu-id="c123e-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="c123e-104">חיזוי נטישה של עסקאות עוזר לחזות אם לקוח לא ירכוש עוד את המוצרים או השירותים שלך בחלון זמן נתון.</span><span class="sxs-lookup"><span data-stu-id="c123e-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="c123e-105">באפשרותך ליצור תחזיות נטישה חדשות דרך **בינה** > **תחזיות**.</span><span class="sxs-lookup"><span data-stu-id="c123e-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="c123e-106">בחר **התחזיות שלי** כדי לראות חיזויים אחרים שיצרת.</span><span class="sxs-lookup"><span data-stu-id="c123e-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="c123e-107">נסה את ערכת הלימוד עבור חיזוי נטישה של עסקאות באמצעות נתונים לדוגמה: [מדריך לדוגמה של חיזוי נטישה של עסקאות (Preview)](sample-guide-predict-transactional-churn.md).</span><span class="sxs-lookup"><span data-stu-id="c123e-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c123e-108">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="c123e-108">Prerequisites</span></span>

- <span data-ttu-id="c123e-109">לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c123e-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="c123e-110">ידע עסקי כדי להבין מה המשמעות של הנטישה עבור העסק שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="c123e-111">אנו תומכים בהגדרות נטישה מבוססת-זמן, כלומר שלקוח נחשב למי שנטש לאחר פרק זמן ללא רכישות.</span><span class="sxs-lookup"><span data-stu-id="c123e-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="c123e-112">נתונים על העסקאות/רכישות שלך וההיסטוריה שלהן:</span><span class="sxs-lookup"><span data-stu-id="c123e-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="c123e-113">מזהי עסקאות להבחנה בין רכישות/עסקאות.</span><span class="sxs-lookup"><span data-stu-id="c123e-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="c123e-114">מזהי לקוחות כדי להתאים עסקאות ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="c123e-115">תאריכי אירוע עסקה, המגדירים את התאריכים שבהם התרחשה העסקה.</span><span class="sxs-lookup"><span data-stu-id="c123e-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="c123e-116">סכמת הנתונים הסמנטית לרכישות/עסקאות דורשת את המידע הבא:</span><span class="sxs-lookup"><span data-stu-id="c123e-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="c123e-117">**מזהה עסקה:** מזהה ייחודי של רכישה או עסקה.</span><span class="sxs-lookup"><span data-stu-id="c123e-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="c123e-118">**תאריך עסקה:** תאריך הרכישה או העסקה.</span><span class="sxs-lookup"><span data-stu-id="c123e-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="c123e-119">**שווי העסקה:** המטבע/סכום הערך המספרי של העסקה/פריט.</span><span class="sxs-lookup"><span data-stu-id="c123e-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="c123e-120">(אופציונלי) **מזהה מוצר ייחודי:** מזהה המוצר או השירות שנרכש אם הנתונים שלך הם ברמת פריט שורה.</span><span class="sxs-lookup"><span data-stu-id="c123e-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="c123e-121">(אופציונלי) **אם עסקה זו הייתה החזרה:** שדה true/false המזהה אם העסקה הייתה החזרה או לא.</span><span class="sxs-lookup"><span data-stu-id="c123e-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="c123e-122">אם **שווי העסקה** שלילי, אנו גם נשתמש במידע זה כדי להסיק החזרה.</span><span class="sxs-lookup"><span data-stu-id="c123e-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="c123e-123">(אופציונלי) נתונים על פעילויות לקוחות:</span><span class="sxs-lookup"><span data-stu-id="c123e-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="c123e-124">מזהי פעילות כדי להבחין בפעילויות מאותו סוג.</span><span class="sxs-lookup"><span data-stu-id="c123e-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="c123e-125">מזהי לקוחות כדי למפות פעילויות של הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="c123e-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="c123e-126">מידע על הפעילויות כולל את השם והתאריך של הפעילות.</span><span class="sxs-lookup"><span data-stu-id="c123e-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="c123e-127">סכמת הנתונים הסמנטית לפעילות לקוחות כוללת:</span><span class="sxs-lookup"><span data-stu-id="c123e-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="c123e-128">**מפתח ראשי:** מזהה ייחודי לפעילות.</span><span class="sxs-lookup"><span data-stu-id="c123e-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="c123e-129">לדוגמה, ביקור באתר או רשומת שימוש המציגים שהלקוח ניסה דוגמית של המוצר שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="c123e-130">**חותמת זמן:** התאריך והשעה של האירוע שזוהו על ידי המפתח הראשי.</span><span class="sxs-lookup"><span data-stu-id="c123e-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="c123e-131">**אירוע:** שם האירוע שבו ברצונך להשתמש.</span><span class="sxs-lookup"><span data-stu-id="c123e-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="c123e-132">לדוגמא, שדה שנקרא "UserAction" בחנות מכולת עשוי להיות שימוש בקופון על-ידי הלקוח.</span><span class="sxs-lookup"><span data-stu-id="c123e-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="c123e-133">**פרטים:** מידע מפורט על האירוע.</span><span class="sxs-lookup"><span data-stu-id="c123e-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="c123e-134">לדוגמה, שדה בשם "CouponValue" בחנות מכולת עשוי להיות ערך המטבע של הקופון.</span><span class="sxs-lookup"><span data-stu-id="c123e-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="c123e-135">יצירת חיזוי נטישה של עסקאות</span><span class="sxs-lookup"><span data-stu-id="c123e-135">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="c123e-136">ב- Customer Insights, עבור אל **בינה** > **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="c123e-136">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="c123e-137">בחר את האריח **מודל נטישת לקוחות (Preview)** ובחר **השתמש במודל זה**.</span><span class="sxs-lookup"><span data-stu-id="c123e-137">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="c123e-138">בחלונית **מודל נטישת לקוחות**, בחר **עסקה** ובחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="c123e-138">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="צילום מסך עם אפשרות העסקה שנבחרה בחלונית מודל נטישת לקוחות.":::

### <a name="name-model"></a><span data-ttu-id="c123e-140">מתן שם למודל</span><span class="sxs-lookup"><span data-stu-id="c123e-140">Name model</span></span>

1. <span data-ttu-id="c123e-141">תן שם למודל כדי להבדיל אותו ממודלים אחרים.</span><span class="sxs-lookup"><span data-stu-id="c123e-141">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="c123e-142">תן שם לישות הפלט שכולל אותיות ומספרים בלבד, ללא רווחים.</span><span class="sxs-lookup"><span data-stu-id="c123e-142">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="c123e-143">זה השם שבו ישות המודל תשתמש.</span><span class="sxs-lookup"><span data-stu-id="c123e-143">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="c123e-144">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="c123e-144">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="c123e-145">הגדרת נטישת לקוחות</span><span class="sxs-lookup"><span data-stu-id="c123e-145">Define customer churn</span></span>

1. <span data-ttu-id="c123e-146">הגדר חלון של ימים לחיזוי נטישה עבורו בשדה **זהה לקוחות שעלולים לנטוש בטווח הזמן הבא**.</span><span class="sxs-lookup"><span data-stu-id="c123e-146">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="c123e-147">לדוגמה, חזה את הסיכון לנטישה עבור הלקוחות שלך במשך 90 הימים הבאים כדי להתאים למאמצי השימור השיווקיים שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-147">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="c123e-148">חיזוי סיכון לנטישה עבור פרק זמן ארוך או קצר יותר עשוי להקשות על הטיפול בגורמים בפרופיל סיכון הנטישה שלך, אבל זה תלוי בדרישות העסקיות הספציפיות.</span><span class="sxs-lookup"><span data-stu-id="c123e-148">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="c123e-149">אתה יכול לבחור **שמור וסגור** בכל עת כדי לשמור את החיזוי כטיוטה.</span><span class="sxs-lookup"><span data-stu-id="c123e-149">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="c123e-150">תמצא את הטיוטה של החיזוי בכרטיסיה **התחזיות שלי** כדי להמשיך.</span><span class="sxs-lookup"><span data-stu-id="c123e-150">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="c123e-151">הזן את מספר הימים להגדרת נטישה בשדה **לקוח נחשב כלקוח שנטש אם הוא לא ביצע רכישות ב:**.</span><span class="sxs-lookup"><span data-stu-id="c123e-151">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="c123e-152">לדוגמא, אם לקוח לא ביצע רכישות ב- 30 הימים האחרונים, הוא עשוי להיחשב כלקוח שנטש עבור העסק שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-152">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="c123e-153">בחר **הבא** כדי להמשיך</span><span class="sxs-lookup"><span data-stu-id="c123e-153">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="c123e-154">הוספת נתונים נדרשים</span><span class="sxs-lookup"><span data-stu-id="c123e-154">Add required data</span></span>

1. <span data-ttu-id="c123e-155">בחר **הוסף נתונים** עבור **היסטוריית רכישות** ובחר בישות המספקת את המידע על היסטוריית העסקאות/הרכישות כמתואר ב[דרישות מוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="c123e-155">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="c123e-156">מפה את השדות הסמנטיים לתכונות בישות היסטוריית הרכישות שלך ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="c123e-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="c123e-157">לתיאורים של השדות, בדוק את [ה‏‫דרישות המוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="c123e-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="מפה שדות סמנטיים של היסטוריית הרכישות.":::

1. <span data-ttu-id="c123e-159">אם השדות שלהלן אינם מאוכלסים, הגדר את הקשר מישות היסטוריית הרכישות שלך לישות 'לקוח'.</span><span class="sxs-lookup"><span data-stu-id="c123e-159">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="c123e-160">בחר את **ישות היסטוריית הרכישות**.</span><span class="sxs-lookup"><span data-stu-id="c123e-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="c123e-161">בחר את **שדה** המזהה את הלקוח בישות היסטוריית הרכישות.</span><span class="sxs-lookup"><span data-stu-id="c123e-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="c123e-162">עליו להתייחס למזהה הלקוח העיקרי של ישות הלקוח שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-162">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="c123e-163">בחר את **ישות לקוח** שמתאימה לישות הלקוח העיקרית שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="c123e-164">הקלד שם המתאר את הקשר.</span><span class="sxs-lookup"><span data-stu-id="c123e-164">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="דף היסטוריית הרכישות המציג את היצירה של קשר עם הלקוח.":::
   
1. <span data-ttu-id="c123e-166">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="c123e-166">Select **Next**.</span></span>

1. <span data-ttu-id="c123e-167">לחלופין, בחר **הוסף נתונים** עבור **פעילויות לקוח**.</span><span class="sxs-lookup"><span data-stu-id="c123e-167">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="c123e-168">בחר את הישות המספקת את פרטי פעילות הלקוח כמתואר בדרישות המוקדמות.</span><span class="sxs-lookup"><span data-stu-id="c123e-168">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="c123e-169">מפה את השדות הסמנטיים לתכונות בישות פעילות הלקוח שלך ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="c123e-169">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="c123e-170">לתיאורים של השדות, בדוק את [ה‏‫דרישות המוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="c123e-170">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="c123e-171">בחר סוג פעילות שתואם את סוג הפעילות של הלקוח שאתה מגדיר.</span><span class="sxs-lookup"><span data-stu-id="c123e-171">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="c123e-172">בחר **צור חדש** ובחר סוג פעילות זמין או צור סוג חדש.</span><span class="sxs-lookup"><span data-stu-id="c123e-172">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="c123e-173">יהיה עליך להגדיר את הקשר בין ישות פעילות הלקוח לישות הלקוח.</span><span class="sxs-lookup"><span data-stu-id="c123e-173">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="c123e-174">בחר את השדה המזהה את הלקוח בטבלת פעילות הלקוח.</span><span class="sxs-lookup"><span data-stu-id="c123e-174">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="c123e-175">הוא עשוי להיות קשור ישירות למזהה הלקוח הראשי של הישות 'לקוח' שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-175">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="c123e-176">בחר את ישות לקוח שמתאימה לישות הלקוח העיקרית שלך</span><span class="sxs-lookup"><span data-stu-id="c123e-176">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="c123e-177">הקלד שם המתאר את הקשר.</span><span class="sxs-lookup"><span data-stu-id="c123e-177">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="c123e-178">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="c123e-178">Select **Save**.</span></span>

1. <span data-ttu-id="c123e-179">אם יש לך פעילויות אחרות של לקוחות שברצונך לכלול, חזור על השלבים לעיל.</span><span class="sxs-lookup"><span data-stu-id="c123e-179">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="c123e-180">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="c123e-180">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="c123e-181">הגדרת לוח זמנים ובדיקת תצורה</span><span class="sxs-lookup"><span data-stu-id="c123e-181">Set schedule and review configuration</span></span>

1. <span data-ttu-id="c123e-182">הגדר שכיחות כדי לאמן מחדש את המודל שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-182">Set a frequency to retrain your model.</span></span> <span data-ttu-id="c123e-183">הגדרה זו חשובה כדי לעדכן את דיוק החיזויים כאשר נתונים חדשים מעובדים.</span><span class="sxs-lookup"><span data-stu-id="c123e-183">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="c123e-184">מרבית העסקים יכולים לבצע אימון פעם בחודש ולקבל דיוק טוב לחיזוי שלהם.</span><span class="sxs-lookup"><span data-stu-id="c123e-184">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="c123e-185">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="c123e-185">Select **Next**.</span></span>

1. <span data-ttu-id="c123e-186">סקור את תצורת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="c123e-186">Review the configuration of the prediction.</span></span> <span data-ttu-id="c123e-187">באפשרותך לחזור לשלבים הקודמים על-ידי בחירת **ערוך** תחת הערך המוצג.</span><span class="sxs-lookup"><span data-stu-id="c123e-187">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="c123e-188">לחלופין, תוכל לבחור שלב תצורה במחוון ההתקדמות.</span><span class="sxs-lookup"><span data-stu-id="c123e-188">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="c123e-189">אם כל הערכים מוגדרים כהלכה, בחר **שמור והפעל** כדי להתחיל בתהליך החיזוי.</span><span class="sxs-lookup"><span data-stu-id="c123e-189">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="c123e-190">בכרטיסיה **החיזויים שלי**, תוכל לראות את מצב החיזויים שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-190">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="c123e-191">התהליך עשוי להימשך מספר שעות עד להשלמתו, תלוי בכמות הנתונים המשמשים בחיזוי.</span><span class="sxs-lookup"><span data-stu-id="c123e-191">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="c123e-192">סקור את מצב החיזוי והתוצאות</span><span class="sxs-lookup"><span data-stu-id="c123e-192">Review a prediction status and results</span></span>

1. <span data-ttu-id="c123e-193">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="c123e-193">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c123e-194">בחר בחיזוי שברצונך לבדוק.</span><span class="sxs-lookup"><span data-stu-id="c123e-194">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="c123e-195">**שם חיזוי:** שם החיזוי שסופק בעת יצירתו.</span><span class="sxs-lookup"><span data-stu-id="c123e-195">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="c123e-196">**סוג חיזוי:** סוג המודל המשמש עבור החיזוי</span><span class="sxs-lookup"><span data-stu-id="c123e-196">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="c123e-197">**ישות פלט:** שם הישות לאחסון פלט החיזוי.</span><span class="sxs-lookup"><span data-stu-id="c123e-197">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="c123e-198">אתה יכול למצוא ישות עם שם זה ב- **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="c123e-198">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="c123e-199">**שדה חזוי:** שדה זה מאוכלס רק עבור סוגים מסוימים של תחזיות, ואינו משמש בחיזוי נטישות.</span><span class="sxs-lookup"><span data-stu-id="c123e-199">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="c123e-200">**מצב:** מצב הפעלת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="c123e-200">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="c123e-201">**הוצב בתור:** חיזוי ממתין להפעלת תהליכים אחרים.</span><span class="sxs-lookup"><span data-stu-id="c123e-201">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="c123e-202">**מרענן:** חיזוי פועל כעת כדי ליצור תוצאות שיזרמו לישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="c123e-202">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="c123e-203">**נכשל:** הפעלת החיזוי נכשלה.</span><span class="sxs-lookup"><span data-stu-id="c123e-203">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="c123e-204">[סקור את יומני הרישום](#troubleshoot-a-failed-prediction) לקבלת פרטים נוספים.</span><span class="sxs-lookup"><span data-stu-id="c123e-204">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="c123e-205">**הצליח:** החיזוי הצליח.</span><span class="sxs-lookup"><span data-stu-id="c123e-205">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="c123e-206">בחר **הצג** מתחת לשלוש הנקודות האנכיות כדי לבדוק את החיזוי</span><span class="sxs-lookup"><span data-stu-id="c123e-206">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="c123e-207">**נערך:** התאריך שבו השתנתה הגדרת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="c123e-207">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="c123e-208">**רענון אחרון:** התאריך שבו בוצע רענון של תוצאות החיזוי בישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="c123e-208">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="c123e-209">בחר את שלוש הנקודות האנכיות לצד החיזוי שתרצה לבדוק את התוצאות שלו ובחר **הצג**.</span><span class="sxs-lookup"><span data-stu-id="c123e-209">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="פקד תצוגה להצגת תוצאות של חיזוי.":::   

1. <span data-ttu-id="c123e-211">ישנם שלושה חלקים עיקריים של נתונים בדף התוצאות:</span><span class="sxs-lookup"><span data-stu-id="c123e-211">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="c123e-212">**ביצועי מודל אימון:** A, B או C הם ציונים אפשריים.</span><span class="sxs-lookup"><span data-stu-id="c123e-212">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="c123e-213">ניקוד זה מציין את ביצועי החיזוי ויכול לעזור לך לקבל את ההחלטה להשתמש בתוצאות המאוחסנות בישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="c123e-213">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="c123e-214">הניקוד נקבע על פי הכללים הבאים:</span><span class="sxs-lookup"><span data-stu-id="c123e-214">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="c123e-215">**A** כאשר המודל ניבא במדויק לפחות 50% מכלל התחזיות, וכאשר אחוז התחזיות המדויקות עבור לקוחות שנטשו גדול משיעור הבסיס ב- 10% לפחות.</span><span class="sxs-lookup"><span data-stu-id="c123e-215">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="c123e-216">**B** כאשר המודל ניבא במדויק לפחות 50% מכלל התחזיות, וכאשר אחוז התחזיות המדויקות עבור לקוחות שנטשו גדול בעד 10% מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="c123e-216">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="c123e-217">**C** כאשר המודל ניבא במדויק פחות מ- 50% מכלל התחזיות, או כאשר אחוזי התחזיות המדויקות עבור הלקוחות שנטשו קטנים מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="c123e-217">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="c123e-218">**בסיס** לוקח את קלט חלון הזמן של החיזוי עבור המודל (לדוגמה, שנה אחת) והמודל יוצר חלקים שונים של זמן על-ידי חלוקה שלו ב- 2 עד שהוא מגיע לחודש אחד או פחות.</span><span class="sxs-lookup"><span data-stu-id="c123e-218">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="c123e-219">הוא משתמש בחלקים אלה כדי ליצור כלל עסקי עבור לקוחות שלא רכשו במסגרת זמן זו.</span><span class="sxs-lookup"><span data-stu-id="c123e-219">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="c123e-220">לקוחות אלה נחשבים ללקוחות שנטשו.</span><span class="sxs-lookup"><span data-stu-id="c123e-220">These customers are considered as churned.</span></span> <span data-ttu-id="c123e-221">הכלל העסקי מבוסס הזמן עם היכולת הגבוהה ביותר לחזות מי עשוי לנטוש נבחר כמודל בסיסי.</span><span class="sxs-lookup"><span data-stu-id="c123e-221">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="c123e-222">**הסבירות לנטוש (מספר לקוחות):** קבוצות של לקוחות בהתבסס על הסיכון החזוי שלהם לנטוש.</span><span class="sxs-lookup"><span data-stu-id="c123e-222">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="c123e-223">נתונים אלה יכולים לעזור לך מאוחר יותר אם ברצונך ליצור פלח של לקוחות עם סיכון גבוה לנטישה.</span><span class="sxs-lookup"><span data-stu-id="c123e-223">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="c123e-224">פלחים כאלה עוזרים להבין היכן כדאי לקצץ בחברות בפלח.</span><span class="sxs-lookup"><span data-stu-id="c123e-224">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="c123e-225">**הגורמים המשפיעים ביותר:** ישנם גורמים רבים אשר נלקחים בחשבון בעת יצירת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="c123e-225">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="c123e-226">לכל אחד מהגורמים יש חשיבות משלו המחושבת עבור התחזיות המצטברות שמודל יוצר.</span><span class="sxs-lookup"><span data-stu-id="c123e-226">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="c123e-227">אתה יכול להשתמש בגורמים אלה כדי לסייע באימות תוצאות החיזוי שלך.</span><span class="sxs-lookup"><span data-stu-id="c123e-227">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="c123e-228">לחלופין, תוכל להשתמש במידע זה מאוחר יותר כדי [ליצור פלחים](segments.md), מה שעשוי לעזור להשפיע על סיכויי הנטישה של הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="c123e-228">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="c123e-229">פתור בעיה של חיזוי שנכשל</span><span class="sxs-lookup"><span data-stu-id="c123e-229">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="c123e-230">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="c123e-230">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c123e-231">בחר את שלוש הנקודות האנכיות לצד התחזית שברצונך להציג יומני שגיאה עבורה.</span><span class="sxs-lookup"><span data-stu-id="c123e-231">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="c123e-232">בחר **יומנים**.</span><span class="sxs-lookup"><span data-stu-id="c123e-232">Select **Logs**.</span></span>

1. <span data-ttu-id="c123e-233">סקירת כל השגיאות.</span><span class="sxs-lookup"><span data-stu-id="c123e-233">Review all the errors.</span></span> <span data-ttu-id="c123e-234">יש מספר סוגים של שגיאות שיכולות להתרחש, והם מתארים איזה מצב גרם לשגיאה.</span><span class="sxs-lookup"><span data-stu-id="c123e-234">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="c123e-235">לדוגמה, שגיאה כי אין מספיק נתונים כדי לחזות במדויק נפתרת בדרך כלל על ידי טעינת נתונים נוספים ל- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c123e-235">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="c123e-236">רענן חיזוי</span><span class="sxs-lookup"><span data-stu-id="c123e-236">Refresh a prediction</span></span>

<span data-ttu-id="c123e-237">החיזוי יחודש באופן אוטומטי באותו [תזמון של רענון הנתונים](system.md#schedule-tab) כפי שהוגדר בהגדרות.</span><span class="sxs-lookup"><span data-stu-id="c123e-237">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="c123e-238">באפשרותך לרענן אותם גם באופן ידני.</span><span class="sxs-lookup"><span data-stu-id="c123e-238">You can refresh them manually too.</span></span>

1. <span data-ttu-id="c123e-239">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="c123e-239">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c123e-240">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך לרענן.</span><span class="sxs-lookup"><span data-stu-id="c123e-240">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="c123e-241">בחר **רענן**.</span><span class="sxs-lookup"><span data-stu-id="c123e-241">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="c123e-242">מחק חיזוי</span><span class="sxs-lookup"><span data-stu-id="c123e-242">Delete a prediction</span></span>

<span data-ttu-id="c123e-243">מחיקת חיזוי גם מסירה את ישות הפלט שלו.</span><span class="sxs-lookup"><span data-stu-id="c123e-243">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="c123e-244">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="c123e-244">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="c123e-245">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך למחוק.</span><span class="sxs-lookup"><span data-stu-id="c123e-245">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="c123e-246">בחר **מחק**.</span><span class="sxs-lookup"><span data-stu-id="c123e-246">Select **Delete**.</span></span>
