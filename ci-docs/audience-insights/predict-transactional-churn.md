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
ms.openlocfilehash: f120e9e3cf8d40d913c7fa6a81fbf9facd045e3c
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597190"
---
# <a name="transactional-churn-prediction-preview"></a><span data-ttu-id="f6211-103">חיזוי נטישה של עסקאות (Preview)</span><span class="sxs-lookup"><span data-stu-id="f6211-103">Transactional churn prediction (preview)</span></span>

<span data-ttu-id="f6211-104">חיזוי נטישה של עסקאות עוזר לחזות אם לקוח לא ירכוש עוד את המוצרים או השירותים שלך בחלון זמן נתון.</span><span class="sxs-lookup"><span data-stu-id="f6211-104">Transactional churn prediction helps predict if a customer will no longer purchase your products or services in a given time window.</span></span> <span data-ttu-id="f6211-105">באפשרותך ליצור תחזיות נטישה חדשות דרך **בינה** > **תחזיות**.</span><span class="sxs-lookup"><span data-stu-id="f6211-105">You can create new churn predictions on **Intelligence** > **Predictions**.</span></span> <span data-ttu-id="f6211-106">בחר **התחזיות שלי** כדי לראות חיזויים אחרים שיצרת.</span><span class="sxs-lookup"><span data-stu-id="f6211-106">Select **My predictions** to see other predictions that you've created.</span></span>

> [!TIP]
> <span data-ttu-id="f6211-107">נסה את ערכת הלימוד עבור חיזוי נטישה של עסקאות באמצעות נתונים לדוגמה: [מדריך לדוגמה של חיזוי נטישה של עסקאות (Preview)](sample-guide-predict-transactional-churn.md).</span><span class="sxs-lookup"><span data-stu-id="f6211-107">Try the tutorial for a translactional churn prediction using sample data: [Transactional churn prediction (preview) sample guide](sample-guide-predict-transactional-churn.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6211-108">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="f6211-108">Prerequisites</span></span>

- <span data-ttu-id="f6211-109">לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f6211-109">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="f6211-110">ידע עסקי כדי להבין מה המשמעות של הנטישה עבור העסק שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-110">Business knowledge to understand what churn means for your business.</span></span> <span data-ttu-id="f6211-111">אנו תומכים בהגדרות נטישה מבוססת-זמן, כלומר שלקוח נחשב למי שנטש לאחר פרק זמן ללא רכישות.</span><span class="sxs-lookup"><span data-stu-id="f6211-111">We support time-based churn definitions, meaning a customer is considered to have churned after a period of no purchases.</span></span>
- <span data-ttu-id="f6211-112">נתונים על העסקאות/רכישות שלך וההיסטוריה שלהן:</span><span class="sxs-lookup"><span data-stu-id="f6211-112">Data about your transactions/purchases and their history:</span></span>
    - <span data-ttu-id="f6211-113">מזהי עסקאות להבחנה בין רכישות/עסקאות.</span><span class="sxs-lookup"><span data-stu-id="f6211-113">Transaction identifiers to distinguish purchases/transactions.</span></span>
    - <span data-ttu-id="f6211-114">מזהי לקוחות כדי להתאים עסקאות ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-114">Customer identifiers to match transactions to your customers.</span></span>
    - <span data-ttu-id="f6211-115">תאריכי אירוע עסקה, המגדירים את התאריכים שבהם התרחשה העסקה.</span><span class="sxs-lookup"><span data-stu-id="f6211-115">Transaction event dates, which define the dates the transaction occurred on.</span></span>
    - <span data-ttu-id="f6211-116">סכמת הנתונים הסמנטית לרכישות/עסקאות דורשת את המידע הבא:</span><span class="sxs-lookup"><span data-stu-id="f6211-116">The semantic data schema for purchases/transactions requires the following information:</span></span>
        - <span data-ttu-id="f6211-117">**מזהה עסקה:** מזהה ייחודי של רכישה או עסקה.</span><span class="sxs-lookup"><span data-stu-id="f6211-117">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="f6211-118">**תאריך עסקה:** תאריך הרכישה או העסקה.</span><span class="sxs-lookup"><span data-stu-id="f6211-118">**Transaction Date:** The date of the purchase or transaction.</span></span>
        - <span data-ttu-id="f6211-119">**שווי העסקה:** המטבע/סכום הערך המספרי של העסקה/פריט.</span><span class="sxs-lookup"><span data-stu-id="f6211-119">**Value of the transaction:** The currency/numerical value amount of the transaction/item.</span></span>
        - <span data-ttu-id="f6211-120">(אופציונלי) **מזהה מוצר ייחודי:** מזהה המוצר או השירות שנרכש אם הנתונים שלך הם ברמת פריט שורה.</span><span class="sxs-lookup"><span data-stu-id="f6211-120">(Optional) **Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="f6211-121">(אופציונלי) **אם עסקה זו הייתה החזרה:** שדה true/false המזהה אם העסקה הייתה החזרה או לא.</span><span class="sxs-lookup"><span data-stu-id="f6211-121">(Optional) **Whether this transaction was a return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="f6211-122">אם **שווי העסקה** שלילי, אנו גם נשתמש במידע זה כדי להסיק החזרה.</span><span class="sxs-lookup"><span data-stu-id="f6211-122">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>
- <span data-ttu-id="f6211-123">(אופציונלי) נתונים על פעילויות לקוחות:</span><span class="sxs-lookup"><span data-stu-id="f6211-123">(Optional) Data about customer activities:</span></span>
    - <span data-ttu-id="f6211-124">מזהי פעילות כדי להבחין בפעילויות מאותו סוג.</span><span class="sxs-lookup"><span data-stu-id="f6211-124">Activity identifiers to distinguish activities of the same type.</span></span>
    - <span data-ttu-id="f6211-125">מזהי לקוחות כדי למפות פעילויות של הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="f6211-125">Customer identifiers to map activities to your customers.</span></span>
    - <span data-ttu-id="f6211-126">מידע על הפעילויות כולל את השם והתאריך של הפעילות.</span><span class="sxs-lookup"><span data-stu-id="f6211-126">Activity information containing the name and date of the activity.</span></span>
    - <span data-ttu-id="f6211-127">סכמת הנתונים הסמנטית לפעילות לקוחות כוללת:</span><span class="sxs-lookup"><span data-stu-id="f6211-127">The semantic data schema for customer activities includes:</span></span>
        - <span data-ttu-id="f6211-128">**מפתח ראשי:** מזהה ייחודי לפעילות.</span><span class="sxs-lookup"><span data-stu-id="f6211-128">**Primary key:** A unique identifier for an activity.</span></span> <span data-ttu-id="f6211-129">לדוגמה, ביקור באתר או רשומת שימוש המציגים שהלקוח ניסה דוגמית של המוצר שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-129">For example, a website visit or a usage record showing the customer tried a sample of your product.</span></span>
        - <span data-ttu-id="f6211-130">**חותמת זמן:** התאריך והשעה של האירוע שזוהו על ידי המפתח הראשי.</span><span class="sxs-lookup"><span data-stu-id="f6211-130">**Timestamp:** The date and time of the event identified by the primary key.</span></span>
        - <span data-ttu-id="f6211-131">**אירוע:** שם האירוע שבו ברצונך להשתמש.</span><span class="sxs-lookup"><span data-stu-id="f6211-131">**Event:** The name of the event you want to use.</span></span> <span data-ttu-id="f6211-132">לדוגמא, שדה שנקרא "UserAction" בחנות מכולת עשוי להיות שימוש בקופון על-ידי הלקוח.</span><span class="sxs-lookup"><span data-stu-id="f6211-132">For example, a field called "UserAction" in a grocery store might be a coupon use by the customer.</span></span>
        - <span data-ttu-id="f6211-133">**פרטים:** מידע מפורט על האירוע.</span><span class="sxs-lookup"><span data-stu-id="f6211-133">**Details:** Detailed information about the event.</span></span> <span data-ttu-id="f6211-134">לדוגמה, שדה בשם "CouponValue" בחנות מכולת עשוי להיות ערך המטבע של הקופון.</span><span class="sxs-lookup"><span data-stu-id="f6211-134">For example, a field called "CouponValue" in a grocery store might be the currency value of the coupon.</span></span>

## <a name="create-a-transactional-churn-prediction"></a><span data-ttu-id="f6211-135">יצירת חיזוי נטישה של עסקאות</span><span class="sxs-lookup"><span data-stu-id="f6211-135">Create a transactional churn prediction</span></span>

1. <span data-ttu-id="f6211-136">ב- Customer Insights, עבור אל **בינה** > **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="f6211-136">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="f6211-137">בחר את האריח **מודל נטישת לקוחות (Preview)** ובחר **השתמש במודל זה**.</span><span class="sxs-lookup"><span data-stu-id="f6211-137">Select the **Customer churn model (preview)** tile and select **Use this model**.</span></span>
   
1. <span data-ttu-id="f6211-138">בחלונית **מודל נטישת לקוחות**, בחר **עסקה** ובחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="f6211-138">In the **Customer churn model** pane, choose **Transactional** and select **Get started**.</span></span>

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="צילום מסך עם אפשרות העסקה שנבחרה בחלונית מודל נטישת לקוחות.":::

### <a name="name-model"></a><span data-ttu-id="f6211-140">מתן שם למודל</span><span class="sxs-lookup"><span data-stu-id="f6211-140">Name model</span></span>

1. <span data-ttu-id="f6211-141">תן שם למודל כדי להבדיל אותו ממודלים אחרים.</span><span class="sxs-lookup"><span data-stu-id="f6211-141">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="f6211-142">תן שם לישות הפלט שכולל אותיות ומספרים בלבד, ללא רווחים.</span><span class="sxs-lookup"><span data-stu-id="f6211-142">Provide a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="f6211-143">זה השם שבו ישות המודל תשתמש.</span><span class="sxs-lookup"><span data-stu-id="f6211-143">That's the name that the model entity will use.</span></span> 

1. <span data-ttu-id="f6211-144">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f6211-144">Select **Next**.</span></span>

### <a name="define-customer-churn"></a><span data-ttu-id="f6211-145">הגדרת נטישת לקוחות</span><span class="sxs-lookup"><span data-stu-id="f6211-145">Define customer churn</span></span>

1. <span data-ttu-id="f6211-146">הגדר חלון של ימים לחיזוי נטישה עבורו בשדה **זהה לקוחות שעלולים לנטוש בטווח הזמן הבא**.</span><span class="sxs-lookup"><span data-stu-id="f6211-146">Set a window of days to predict churn for in the **Identify customers who may churn in the next** field.</span></span> <span data-ttu-id="f6211-147">לדוגמה, חזה את הסיכון לנטישה עבור הלקוחות שלך במשך 90 הימים הבאים כדי להתאים למאמצי השימור השיווקיים שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-147">For example, predict the risk of churn for your customers over the next 90 days to align to your marketing retention efforts.</span></span> <span data-ttu-id="f6211-148">חיזוי סיכון לנטישה עבור פרק זמן ארוך או קצר יותר עשוי להקשות על הטיפול בגורמים בפרופיל סיכון הנטישה שלך, אבל זה תלוי בדרישות העסקיות הספציפיות.</span><span class="sxs-lookup"><span data-stu-id="f6211-148">Predicting churn risk for a longer or shorter period of time can make it more difficult to address the factors in your churn risk profile, but it depends on your specific business requirements.</span></span> 
   >[!TIP]
   > <span data-ttu-id="f6211-149">אתה יכול לבחור **שמור וסגור** בכל עת כדי לשמור את החיזוי כטיוטה.</span><span class="sxs-lookup"><span data-stu-id="f6211-149">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="f6211-150">תמצא את הטיוטה של החיזוי בכרטיסיה **התחזיות שלי** כדי להמשיך.</span><span class="sxs-lookup"><span data-stu-id="f6211-150">You'll find the draft prediction in the **My predictions** tab to continue.</span></span>

1. <span data-ttu-id="f6211-151">הזן את מספר הימים להגדרת נטישה בשדה **לקוח נחשב כלקוח שנטש אם הוא לא ביצע רכישות ב:**.</span><span class="sxs-lookup"><span data-stu-id="f6211-151">Enter the number of days to define churn in the **A customer has churned if they've made no purchases in:** field.</span></span> <span data-ttu-id="f6211-152">לדוגמא, אם לקוח לא ביצע רכישות ב- 30 הימים האחרונים, הוא עשוי להיחשב כלקוח שנטש עבור העסק שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-152">For example, if a customer has made no purchases in the last 30 days, they might be considered as churned for your business.</span></span> 

1. <span data-ttu-id="f6211-153">בחר **הבא** כדי להמשיך</span><span class="sxs-lookup"><span data-stu-id="f6211-153">Select **Next** to continue</span></span>

### <a name="add-required-data"></a><span data-ttu-id="f6211-154">הוספת נתונים נדרשים</span><span class="sxs-lookup"><span data-stu-id="f6211-154">Add required data</span></span>

1. <span data-ttu-id="f6211-155">בחר **הוסף נתונים** עבור **היסטוריית רכישות** ובחר בישות המספקת את המידע על היסטוריית העסקאות/הרכישות כמתואר ב[דרישות מוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="f6211-155">Select **Add data** for **Purchase history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="f6211-156">מפה את השדות הסמנטיים לתכונות בישות היסטוריית הרכישות שלך ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f6211-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="f6211-157">לתיאורים של השדות, בדוק את [ה‏‫דרישות המוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="f6211-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="מפה שדות סמנטיים של היסטוריית הרכישות.":::

1. <span data-ttu-id="f6211-159">אם השדות שלהלן אינם מאוכלסים, הגדר את הקשר מישות היסטוריית הרכישות שלך לישות 'לקוח'.</span><span class="sxs-lookup"><span data-stu-id="f6211-159">If the fields below aren't populated, configure the relationship from your purchase history entity to the Customer entity.</span></span>
    1. <span data-ttu-id="f6211-160">בחר את **ישות היסטוריית הרכישות**.</span><span class="sxs-lookup"><span data-stu-id="f6211-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="f6211-161">בחר את **שדה** המזהה את הלקוח בישות היסטוריית הרכישות.</span><span class="sxs-lookup"><span data-stu-id="f6211-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="f6211-162">עליו להתייחס למזהה הלקוח העיקרי של ישות הלקוח שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-162">It needs to relate to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="f6211-163">בחר את **ישות לקוח** שמתאימה לישות הלקוח העיקרית שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="f6211-164">הקלד שם המתאר את הקשר.</span><span class="sxs-lookup"><span data-stu-id="f6211-164">Enter a name that describes the relationship.</span></span>

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="דף היסטוריית הרכישות המציג את היצירה של קשר עם הלקוח.":::
   
1. <span data-ttu-id="f6211-166">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f6211-166">Select **Next**.</span></span>

1. <span data-ttu-id="f6211-167">לחלופין, בחר **הוסף נתונים** עבור **פעילויות לקוח**.</span><span class="sxs-lookup"><span data-stu-id="f6211-167">Optionally, select **Add data** for **Customer activities**.</span></span> <span data-ttu-id="f6211-168">בחר את הישות המספקת את פרטי פעילות הלקוח כמתואר בדרישות המוקדמות.</span><span class="sxs-lookup"><span data-stu-id="f6211-168">Choose the entity that provides the customer activity information as described in the prerequisites.</span></span>

1. <span data-ttu-id="f6211-169">מפה את השדות הסמנטיים לתכונות בישות פעילות הלקוח שלך ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f6211-169">Map the semantic fields to attributes within your customer activity entity and select **Next**.</span></span> <span data-ttu-id="f6211-170">לתיאורים של השדות, בדוק את [ה‏‫דרישות המוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="f6211-170">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="מפה שדות לקוחות לנתוני עסקאות.":::

1. <span data-ttu-id="f6211-172">בחר סוג פעילות שתואם את סוג הפעילות של הלקוח שאתה מגדיר.</span><span class="sxs-lookup"><span data-stu-id="f6211-172">Select an activity type that matches to the type of customer activity you're configuring.</span></span> <span data-ttu-id="f6211-173">בחר **צור חדש** ובחר סוג פעילות זמין או צור סוג חדש.</span><span class="sxs-lookup"><span data-stu-id="f6211-173">Select **Create new** and choose an available activity type or create a new type.</span></span>

1. <span data-ttu-id="f6211-174">יהיה עליך להגדיר את הקשר בין ישות פעילות הלקוח לישות הלקוח.</span><span class="sxs-lookup"><span data-stu-id="f6211-174">You'll need to configure the relationship from your customer activity entity to the Customer entity.</span></span>
    1. <span data-ttu-id="f6211-175">בחר את השדה המזהה את הלקוח בטבלת פעילות הלקוח.</span><span class="sxs-lookup"><span data-stu-id="f6211-175">Select the field that identifies the customer in the customer activity table.</span></span> <span data-ttu-id="f6211-176">הוא עשוי להיות קשור ישירות למזהה הלקוח הראשי של הישות 'לקוח' שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-176">It can be directly related to the primary customer ID of your Customer entity.</span></span>
    1. <span data-ttu-id="f6211-177">בחר את ישות לקוח שמתאימה לישות הלקוח העיקרית שלך</span><span class="sxs-lookup"><span data-stu-id="f6211-177">Select the Customer entity that matches your primary Customer entity</span></span>
    1. <span data-ttu-id="f6211-178">הקלד שם המתאר את הקשר.</span><span class="sxs-lookup"><span data-stu-id="f6211-178">Enter a name that describes the relationship.</span></span>

1. <span data-ttu-id="f6211-179">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="f6211-179">Select **Save**.</span></span>

1. <span data-ttu-id="f6211-180">אם יש לך פעילויות אחרות של לקוחות שברצונך לכלול, חזור על השלבים לעיל.</span><span class="sxs-lookup"><span data-stu-id="f6211-180">If you have any other customer activities you would like to include, repeat the steps above.</span></span>

1. <span data-ttu-id="f6211-181">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f6211-181">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="f6211-182">הגדרת לוח זמנים ובדיקת תצורה</span><span class="sxs-lookup"><span data-stu-id="f6211-182">Set schedule and review configuration</span></span>

1. <span data-ttu-id="f6211-183">הגדר שכיחות כדי לאמן מחדש את המודל שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-183">Set a frequency to retrain your model.</span></span> <span data-ttu-id="f6211-184">הגדרה זו חשובה כדי לעדכן את דיוק החיזויים כאשר נתונים חדשים מעובדים.</span><span class="sxs-lookup"><span data-stu-id="f6211-184">This setting is important to update the accuracy of predictions as new data is ingested.</span></span> <span data-ttu-id="f6211-185">מרבית העסקים יכולים לבצע אימון פעם בחודש ולקבל דיוק טוב לחיזוי שלהם.</span><span class="sxs-lookup"><span data-stu-id="f6211-185">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="f6211-186">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f6211-186">Select **Next**.</span></span>

1. <span data-ttu-id="f6211-187">סקור את תצורת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="f6211-187">Review the configuration of the prediction.</span></span> <span data-ttu-id="f6211-188">באפשרותך לחזור לשלבים הקודמים על-ידי בחירת **ערוך** תחת הערך המוצג.</span><span class="sxs-lookup"><span data-stu-id="f6211-188">You can go back to prior steps by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="f6211-189">לחלופין, תוכל לבחור שלב תצורה במחוון ההתקדמות.</span><span class="sxs-lookup"><span data-stu-id="f6211-189">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="f6211-190">אם כל הערכים מוגדרים כהלכה, בחר **שמור והפעל** כדי להתחיל בתהליך החיזוי.</span><span class="sxs-lookup"><span data-stu-id="f6211-190">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="f6211-191">בכרטיסיה **החיזויים שלי**, תוכל לראות את מצב החיזויים שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-191">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="f6211-192">התהליך עשוי להימשך מספר שעות עד להשלמתו, תלוי בכמות הנתונים המשמשים בחיזוי.</span><span class="sxs-lookup"><span data-stu-id="f6211-192">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="f6211-193">סקור את מצב החיזוי והתוצאות</span><span class="sxs-lookup"><span data-stu-id="f6211-193">Review a prediction status and results</span></span>

1. <span data-ttu-id="f6211-194">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="f6211-194">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="f6211-195">בחר בחיזוי שברצונך לבדוק.</span><span class="sxs-lookup"><span data-stu-id="f6211-195">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="f6211-196">**שם חיזוי:** שם החיזוי שסופק בעת יצירתו.</span><span class="sxs-lookup"><span data-stu-id="f6211-196">**Prediction name:** Name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="f6211-197">**סוג חיזוי:** סוג המודל המשמש עבור החיזוי</span><span class="sxs-lookup"><span data-stu-id="f6211-197">**Prediction type:** Type of model used for the prediction</span></span>
   - <span data-ttu-id="f6211-198">**ישות פלט:** שם הישות לאחסון פלט החיזוי.</span><span class="sxs-lookup"><span data-stu-id="f6211-198">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="f6211-199">אתה יכול למצוא ישות עם שם זה ב- **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="f6211-199">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="f6211-200">**שדה חזוי:** שדה זה מאוכלס רק עבור סוגים מסוימים של תחזיות, ואינו משמש בחיזוי נטישות.</span><span class="sxs-lookup"><span data-stu-id="f6211-200">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="f6211-201">**מצב:** מצב הפעלת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="f6211-201">**Status:** Status of the prediction run.</span></span>
        - <span data-ttu-id="f6211-202">**הוצב בתור:** חיזוי ממתין להפעלת תהליכים אחרים.</span><span class="sxs-lookup"><span data-stu-id="f6211-202">**Queued:** Prediction is waiting for other processes to run.</span></span>
        - <span data-ttu-id="f6211-203">**מרענן:** חיזוי פועל כעת כדי ליצור תוצאות שיזרמו לישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="f6211-203">**Refreshing:** Prediction is currently running to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="f6211-204">**נכשל:** הפעלת החיזוי נכשלה.</span><span class="sxs-lookup"><span data-stu-id="f6211-204">**Failed:** Prediction run has failed.</span></span> <span data-ttu-id="f6211-205">[סקור את יומני הרישום](#troubleshoot-a-failed-prediction) לקבלת פרטים נוספים.</span><span class="sxs-lookup"><span data-stu-id="f6211-205">[Review the logs](#troubleshoot-a-failed-prediction) for more details.</span></span>
        - <span data-ttu-id="f6211-206">**הצליח:** החיזוי הצליח.</span><span class="sxs-lookup"><span data-stu-id="f6211-206">**Succeeded:** Prediction has succeeded.</span></span> <span data-ttu-id="f6211-207">בחר **הצג** מתחת לשלוש הנקודות האנכיות כדי לבדוק את החיזוי</span><span class="sxs-lookup"><span data-stu-id="f6211-207">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="f6211-208">**נערך:** התאריך שבו השתנתה הגדרת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="f6211-208">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="f6211-209">**רענון אחרון:** התאריך שבו בוצע רענון של תוצאות החיזוי בישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="f6211-209">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="f6211-210">בחר את שלוש הנקודות האנכיות לצד החיזוי שתרצה לבדוק את התוצאות שלו ובחר **הצג**.</span><span class="sxs-lookup"><span data-stu-id="f6211-210">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>

   :::image type="content" source="media/model-subs-view.PNG" alt-text="פקד תצוגה להצגת תוצאות של חיזוי.":::   

1. <span data-ttu-id="f6211-212">ישנם שלושה חלקים עיקריים של נתונים בדף התוצאות:</span><span class="sxs-lookup"><span data-stu-id="f6211-212">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="f6211-213">**ביצועי מודל אימון:** A, B או C הם ציונים אפשריים.</span><span class="sxs-lookup"><span data-stu-id="f6211-213">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="f6211-214">ניקוד זה מציין את ביצועי החיזוי ויכול לעזור לך לקבל את ההחלטה להשתמש בתוצאות המאוחסנות בישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="f6211-214">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span> <span data-ttu-id="f6211-215">הניקוד נקבע על פי הכללים הבאים:</span><span class="sxs-lookup"><span data-stu-id="f6211-215">Scores are determined based on the following rules:</span></span>
         
         - <span data-ttu-id="f6211-216">**A** כאשר המודל ניבא במדויק לפחות 50% מכלל התחזיות, וכאשר אחוז התחזיות המדויקות עבור לקוחות שנטשו גדול משיעור הבסיס ב- 10% לפחות.</span><span class="sxs-lookup"><span data-stu-id="f6211-216">**A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is greater than the baseline rate by at least 10%.</span></span>
            
         - <span data-ttu-id="f6211-217">**B** כאשר המודל ניבא במדויק לפחות 50% מכלל התחזיות, וכאשר אחוז התחזיות המדויקות עבור לקוחות שנטשו גדול בעד 10% מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="f6211-217">**B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of accurate predictions for customers who churned is up to 10% greater than the baseline.</span></span>
            
         - <span data-ttu-id="f6211-218">**C** כאשר המודל ניבא במדויק פחות מ- 50% מכלל התחזיות, או כאשר אחוזי התחזיות המדויקות עבור הלקוחות שנטשו קטנים מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="f6211-218">**C** when the model accurately predicted less 50% of the total predictions, or when the percentage of accurate predictions for customers who churned is less than the baseline.</span></span>
               
         - <span data-ttu-id="f6211-219">**בסיס** לוקח את קלט חלון הזמן של החיזוי עבור המודל (לדוגמה, שנה אחת) והמודל יוצר חלקים שונים של זמן על-ידי חלוקה שלו ב- 2 עד שהוא מגיע לחודש אחד או פחות.</span><span class="sxs-lookup"><span data-stu-id="f6211-219">**Baseline** takes the prediction time window input for the model (for example, one year) and the model creates different fractions of time by dividing it by 2 until it reaches one month or less.</span></span> <span data-ttu-id="f6211-220">הוא משתמש בחלקים אלה כדי ליצור כלל עסקי עבור לקוחות שלא רכשו במסגרת זמן זו.</span><span class="sxs-lookup"><span data-stu-id="f6211-220">It uses these fractions to create a business rule for customers who have not purchased in this time frame.</span></span> <span data-ttu-id="f6211-221">לקוחות אלה נחשבים ללקוחות שנטשו.</span><span class="sxs-lookup"><span data-stu-id="f6211-221">These customers are considered as churned.</span></span> <span data-ttu-id="f6211-222">הכלל העסקי מבוסס הזמן עם היכולת הגבוהה ביותר לחזות מי עשוי לנטוש נבחר כמודל בסיסי.</span><span class="sxs-lookup"><span data-stu-id="f6211-222">The time-based business rule with the highest ability to predict who is likely to churn is chosen as baseline model.</span></span>
            
    1. <span data-ttu-id="f6211-223">**הסבירות לנטוש (מספר לקוחות):** קבוצות של לקוחות בהתבסס על הסיכון החזוי שלהם לנטוש.</span><span class="sxs-lookup"><span data-stu-id="f6211-223">**Likelihood to churn (number of customers):** Groups of customers based on their predicted risk of churn.</span></span> <span data-ttu-id="f6211-224">נתונים אלה יכולים לעזור לך מאוחר יותר אם ברצונך ליצור פלח של לקוחות עם סיכון גבוה לנטישה.</span><span class="sxs-lookup"><span data-stu-id="f6211-224">This data can help you later if you want to create a segment of customers with high churn risk.</span></span> <span data-ttu-id="f6211-225">פלחים כאלה עוזרים להבין היכן כדאי לקצץ בחברות בפלח.</span><span class="sxs-lookup"><span data-stu-id="f6211-225">Such segments help to understand where your cutoff should be for segment membership.</span></span>
       
    1. <span data-ttu-id="f6211-226">**הגורמים המשפיעים ביותר:** ישנם גורמים רבים אשר נלקחים בחשבון בעת יצירת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="f6211-226">**Most influential factors:** There are many factors that are taken into account when creating your prediction.</span></span> <span data-ttu-id="f6211-227">לכל אחד מהגורמים יש חשיבות משלו המחושבת עבור התחזיות המצטברות שמודל יוצר.</span><span class="sxs-lookup"><span data-stu-id="f6211-227">Each of the factors has its importance calculated for the aggregated predictions a model creates.</span></span> <span data-ttu-id="f6211-228">אתה יכול להשתמש בגורמים אלה כדי לסייע באימות תוצאות החיזוי שלך.</span><span class="sxs-lookup"><span data-stu-id="f6211-228">You can use these factors to help validate your prediction results.</span></span> <span data-ttu-id="f6211-229">לחלופין, תוכל להשתמש במידע זה מאוחר יותר כדי [ליצור פלחים](segments.md), מה שעשוי לעזור להשפיע על סיכויי הנטישה של הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="f6211-229">Or you can use this information later to [create segments](segments.md) that could help influence churn risk for customers.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="f6211-230">פתור בעיה של חיזוי שנכשל</span><span class="sxs-lookup"><span data-stu-id="f6211-230">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="f6211-231">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="f6211-231">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="f6211-232">בחר את שלוש הנקודות האנכיות לצד התחזית שברצונך להציג יומני שגיאה עבורה.</span><span class="sxs-lookup"><span data-stu-id="f6211-232">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="f6211-233">בחר **יומנים**.</span><span class="sxs-lookup"><span data-stu-id="f6211-233">Select **Logs**.</span></span>

1. <span data-ttu-id="f6211-234">סקירת כל השגיאות.</span><span class="sxs-lookup"><span data-stu-id="f6211-234">Review all the errors.</span></span> <span data-ttu-id="f6211-235">יש מספר סוגים של שגיאות שיכולות להתרחש, והם מתארים איזה מצב גרם לשגיאה.</span><span class="sxs-lookup"><span data-stu-id="f6211-235">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="f6211-236">לדוגמה, שגיאה כי אין מספיק נתונים כדי לחזות במדויק נפתרת בדרך כלל על ידי טעינת נתונים נוספים ל- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f6211-236">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="f6211-237">רענן חיזוי</span><span class="sxs-lookup"><span data-stu-id="f6211-237">Refresh a prediction</span></span>

<span data-ttu-id="f6211-238">החיזוי יחודש באופן אוטומטי באותו [תזמון של רענון הנתונים](system.md#schedule-tab) כפי שהוגדר בהגדרות.</span><span class="sxs-lookup"><span data-stu-id="f6211-238">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="f6211-239">באפשרותך לרענן אותם גם באופן ידני.</span><span class="sxs-lookup"><span data-stu-id="f6211-239">You can refresh them manually too.</span></span>

1. <span data-ttu-id="f6211-240">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="f6211-240">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="f6211-241">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך לרענן.</span><span class="sxs-lookup"><span data-stu-id="f6211-241">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="f6211-242">בחר **רענן**.</span><span class="sxs-lookup"><span data-stu-id="f6211-242">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="f6211-243">מחק חיזוי</span><span class="sxs-lookup"><span data-stu-id="f6211-243">Delete a prediction</span></span>

<span data-ttu-id="f6211-244">מחיקת חיזוי גם מסירה את ישות הפלט שלו.</span><span class="sxs-lookup"><span data-stu-id="f6211-244">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="f6211-245">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="f6211-245">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="f6211-246">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך למחוק.</span><span class="sxs-lookup"><span data-stu-id="f6211-246">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="f6211-247">בחר **מחק**.</span><span class="sxs-lookup"><span data-stu-id="f6211-247">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]