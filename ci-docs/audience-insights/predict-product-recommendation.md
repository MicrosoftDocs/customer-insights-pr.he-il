---
title: חיזוי המלצות על מוצרים
description: בצע חיזוי של המוצר שהלקוח עשוי לרכוש או לקיים איתם אינטראקציה.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 5ae78b6bbc51fd8a25bc408050a23479698a1414
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598064"
---
# <a name="product-recommendation-prediction-preview"></a><span data-ttu-id="54e3f-103">חיזוי המלצות על מוצרים (Preview)</span><span class="sxs-lookup"><span data-stu-id="54e3f-103">Product recommendation prediction (preview)</span></span>

<span data-ttu-id="54e3f-104">מודל ההמלצה על מוצרים יוצר ערכות של המלצות מוצר חזויות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-104">The product recommendation model creates sets of predictive product recommendations.</span></span> <span data-ttu-id="54e3f-105">ההמלצות מבוססות על התנהגות רכישה קודמת ועל לקוחות בעלי דפוסי רכישה דומים.</span><span class="sxs-lookup"><span data-stu-id="54e3f-105">Recommendations are based on previous purchase behavior and customers with similar purchase patterns.</span></span> <span data-ttu-id="54e3f-106">באפשרותך ליצור חיזויים חדשים של המלצות על מוצרים בדף **בינה** > **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-106">You can create new product recommendation predictions on the **Intelligence** > **Predictions** page.</span></span> <span data-ttu-id="54e3f-107">בחר **התחזיות שלי** כדי לראות חיזויים אחרים שיצרת.</span><span class="sxs-lookup"><span data-stu-id="54e3f-107">Select **My predictions** to see other predictions that you've created.</span></span>

<span data-ttu-id="54e3f-108">המלצות על מוצרים עשויות להיות כפופות לחוקים ולתקנות המקומיים וכן לציפיות הלקוחות, אשר המודל אינו מיועד לקחת בחשבון באופן ספציפי.</span><span class="sxs-lookup"><span data-stu-id="54e3f-108">Product recommendations may be subject to local laws and regulations as well as customer expectations, which the model is not built to specifically take into account.</span></span>  <span data-ttu-id="54e3f-109">כמשתמש ביכולת חיזוי זו, **עליך לסקור את ההמלצות לפני מסירתן ללקוחות** כדי לוודא שאתה מציית לכל החוקים והתקנות החלים, וכן לציפיות הלקוחות למה שאתה עשוי להמליץ עליו.</span><span class="sxs-lookup"><span data-stu-id="54e3f-109">As a user of this predictive capability, **you must review the recommendations prior to delivering them to your customers** to ensure you are complying with any applicable laws or regulations, as well as customer expectations for what you may recommend.</span></span> 

<span data-ttu-id="54e3f-110">בנוסף, הפלט של מודל זה יספק לך המלצות על סמך מזהה המוצר.</span><span class="sxs-lookup"><span data-stu-id="54e3f-110">Additionally, the output of this model will give you recommendations based on the product ID.</span></span> <span data-ttu-id="54e3f-111">מנגנון המסירה שלך יצטרך לקחת מזהי מוצר חזויים ולמפות אותם לתוכן המתאים ללקוחות שלך כדי לכסות על התאמה לשפות אחרות, תוכן תמונה ותוכן או התנהגות אחרים הספציפיים לעסק.</span><span class="sxs-lookup"><span data-stu-id="54e3f-111">Your delivery mechanism will need to take predicted product IDs and map them to appropriate content for your customers to account for localization, image content, and other business specific content or behavior.</span></span>

## <a name="sample-guide"></a><span data-ttu-id="54e3f-112">מדריך לדוגמה</span><span class="sxs-lookup"><span data-stu-id="54e3f-112">Sample Guide</span></span>

<span data-ttu-id="54e3f-113">אם אתה מעוניין לנסות תכונה זו אך אין לך נתונים להשלמת הדרישות להלן, תוכל [ליצור הטמעה לדוגמה](sample-guide-predict-product-recommendation.md).</span><span class="sxs-lookup"><span data-stu-id="54e3f-113">If you're interested in trying this feature but don't have data to complete the requirements below, you can [create a sample implementation](sample-guide-predict-product-recommendation.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="54e3f-114">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="54e3f-114">Prerequisites</span></span>

- <span data-ttu-id="54e3f-115">לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="54e3f-115">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="54e3f-116">ידע עסקי להבנת סוגים שונים של מוצרים עבור העסק שלך והאופן שבו הלקוחות שלך מקיימים איתו אינטראקציה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-116">Business knowledge to understand different types of products for your business and how your customers interact with them.</span></span> <span data-ttu-id="54e3f-117">אנו תומכים בהמלצה על מוצרים שנרכשו בעבר על-ידי הלקוחות שלך או המלצות על מוצרים חדשים.</span><span class="sxs-lookup"><span data-stu-id="54e3f-117">We support recommending products that have been previously purchased by your customers or recommendations for new products.</span></span>
- <span data-ttu-id="54e3f-118">נתונים על העסקאות, הרכישות וההיסטוריה שלהן:</span><span class="sxs-lookup"><span data-stu-id="54e3f-118">Data about transactions, purchases, and their history:</span></span>
    - <span data-ttu-id="54e3f-119">מזהי עסקאות להבחנה בין רכישות או עסקאות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-119">Transaction identifiers to distinguish purchases or transactions.</span></span>
    - <span data-ttu-id="54e3f-120">מזהי לקוחות למיפוי עסקאות ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="54e3f-120">Customer identifiers to map transactions to your customers.</span></span>
    - <span data-ttu-id="54e3f-121">תאריכי אירוע עסקה המציינים תאריכים שבהם התרחשה העסקה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-121">Transaction event dates that specify dates the transaction occurred on.</span></span>
    - <span data-ttu-id="54e3f-122">(אופציונלי) פרטי מזהה מוצר עבור העסקה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-122">(Optional) Product ID information for the transaction.</span></span>
    - <span data-ttu-id="54e3f-123">(אופציונלי) אם עסקה היא החזרה או לא.</span><span class="sxs-lookup"><span data-stu-id="54e3f-123">(Optional) If a transaction is a return or not.</span></span>
    - <span data-ttu-id="54e3f-124">סכמת הנתונים הסמנטית דורשת את המידע הבא:</span><span class="sxs-lookup"><span data-stu-id="54e3f-124">The semantic data schema requires the following information:</span></span>
        - <span data-ttu-id="54e3f-125">**מזהה עסקה:** מזהה ייחודי של רכישה או עסקה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-125">**Transaction ID:** A unique identifier of a purchase or transaction.</span></span>
        - <span data-ttu-id="54e3f-126">**תאריך עסקה:** תאריך הרכישה או העסקה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-126">**Transaction date:** The date the of the purchase or transaction.</span></span>
        - <span data-ttu-id="54e3f-127">**שווי העסקה:** הערך המספרי של הרכישה או העסקה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-127">**Value of the transaction:** The numerical value of the purchase or transaction.</span></span>
        - <span data-ttu-id="54e3f-128">**מזהה מוצר ייחודי:** מזהה המוצר או השירות שנרכש אם הנתונים שלך הם ברמת פריט שורה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-128">**Unique product ID:** The ID of the product or service purchased if your data is at a line item level.</span></span>
        - <span data-ttu-id="54e3f-129">(אופציונלי) **רכישה או החזרה:** שדה true/false המזהה אם העסקה הייתה החזרה או לא.</span><span class="sxs-lookup"><span data-stu-id="54e3f-129">(Optional) **Purchase or return:** A true/false field that identifies if the transaction was a return or not.</span></span> <span data-ttu-id="54e3f-130">אם **שווי העסקה** שלילי, אנו גם נשתמש במידע זה כדי להסיק החזרה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-130">If the **Value of the transaction** is negative, we will also use this information to infer a return.</span></span>


## <a name="create-a-product-recommendation-prediction"></a><span data-ttu-id="54e3f-131">יצירת חיזוי המלצות על מוצרים</span><span class="sxs-lookup"><span data-stu-id="54e3f-131">Create a product recommendation prediction</span></span>

1. <span data-ttu-id="54e3f-132">ב- Customer Insights, עבור אל **בינה** > **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-132">In Customer Insights, go to **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="54e3f-133">בחר את האריח **מודל המלצות על מוצרים (Preview)** ובחר **השתמש במודל זה**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-133">Select the **Product recommendations model (preview)** tile and select **Use this model**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54e3f-134">![אריח מודל המלצות על מוצרים עם הלחצן 'השתמש במודל זה'](media/product-recommendation-usethismodel.PNG "אריח מודל המלצות על מוצרים עם הלחצן 'השתמש במודל זה'")</span><span class="sxs-lookup"><span data-stu-id="54e3f-134">![Product Recommendation model tile with Use this model button](media/product-recommendation-usethismodel.PNG "Product Recommendation model tile with Use this model button")</span></span>

1. <span data-ttu-id="54e3f-135">סקור את המידע אודות דרישות המודל.</span><span class="sxs-lookup"><span data-stu-id="54e3f-135">Review the information about the model requirements.</span></span> <span data-ttu-id="54e3f-136">אם יש לך את הנתונים הדרושים, בחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-136">If you have the required data, select **Get started**.</span></span>

### <a name="name-model"></a><span data-ttu-id="54e3f-137">מתן שם למודל</span><span class="sxs-lookup"><span data-stu-id="54e3f-137">Name model</span></span>

1. <span data-ttu-id="54e3f-138">תן שם למודל כדי להבדיל אותו ממודלים אחרים.</span><span class="sxs-lookup"><span data-stu-id="54e3f-138">Provide a name for the model to distinguish it from other models.</span></span>

1. <span data-ttu-id="54e3f-139">הזן שם עבור ישות הפלט באמצעות אותיות ומספרים בלבד, ללא רווחים.</span><span class="sxs-lookup"><span data-stu-id="54e3f-139">Enter a name for the output entity using letters and numbers only, without any spaces.</span></span> <span data-ttu-id="54e3f-140">זה השם שבו ישות המודל תשתמש.</span><span class="sxs-lookup"><span data-stu-id="54e3f-140">That's the name that the model entity will use.</span></span> <span data-ttu-id="54e3f-141">לאחר מכן בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-141">Then, select **Next**.</span></span>

### <a name="define-product-recommendation-configuration"></a><span data-ttu-id="54e3f-142">הגדרת תצורת המלצות על מוצרים</span><span class="sxs-lookup"><span data-stu-id="54e3f-142">Define product recommendation configuration</span></span>

1. <span data-ttu-id="54e3f-143">הגדר את **מספר המוצרים** שברצונך להמליץ ללקוח.</span><span class="sxs-lookup"><span data-stu-id="54e3f-143">Set the **Number of products** you want to recommend to a customer.</span></span> <span data-ttu-id="54e3f-144">ערך זה תלוי באופן שבו שיטת המסירה שלך ממלאת נתונים.</span><span class="sxs-lookup"><span data-stu-id="54e3f-144">This value depends on how your delivery method fills data.</span></span> <span data-ttu-id="54e3f-145">אם באפשרותך להמליץ על שלושה מוצרים, הגדר ערך זה בהתאם.</span><span class="sxs-lookup"><span data-stu-id="54e3f-145">If you can recommend three products, set this value accordingly.</span></span>
   
   >[!TIP]
   > <span data-ttu-id="54e3f-146">אתה יכול לבחור **שמור וסגור** בכל עת כדי לשמור את החיזוי כטיוטה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-146">You can select **Save and close** at any time to save the prediction as a draft.</span></span> <span data-ttu-id="54e3f-147">תמצא את חיזוי הטיוטה בכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-147">You'll find the draft prediction in the **My predictions** tab.</span></span>

1. <span data-ttu-id="54e3f-148">בחר אם ברצונך **להציע מוצרים שלקוחות רכשו לאחרונה**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-148">Choose if you want to **Suggest products customers have recently purchased**.</span></span>

1. <span data-ttu-id="54e3f-149">אם בחרת *לא* להמליץ על מוצרים שנרכשו לאחרונה, הגדר את **חלון מבט לאחור**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-149">If you've selected to *not* recommend recently purchased products, set the **Look back window**.</span></span> <span data-ttu-id="54e3f-150">הגדרה זו מציינת את מסגרת זמן שהמודל לוקח בחשבון לפני שהוא ממליץ שוב על המוצר למשתמש.</span><span class="sxs-lookup"><span data-stu-id="54e3f-150">This setting specifies the time frame the model considers before recommending the product to the user again.</span></span> <span data-ttu-id="54e3f-151">לדוגמה, ציין שלקוח רוכש מחשב נייד כל שנתיים.</span><span class="sxs-lookup"><span data-stu-id="54e3f-151">For example, indicate a customer purchases a laptop every 2 years.</span></span> <span data-ttu-id="54e3f-152">חלון זה יסתכל על היסטוריית הרכישות בשנתיים האחרונות, ואם הוא ימצא פריט, הפריט יסונן מההמלצות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-152">This window will look at the purchase history for the last 2 years, and if they find an item, the item will be filtered from the recommendations.</span></span>

1. <span data-ttu-id="54e3f-153">בחר **הבא**</span><span class="sxs-lookup"><span data-stu-id="54e3f-153">Select **Next**</span></span>

### <a name="add-required-data"></a><span data-ttu-id="54e3f-154">הוספת נתונים נדרשים</span><span class="sxs-lookup"><span data-stu-id="54e3f-154">Add required data</span></span>

1. <span data-ttu-id="54e3f-155">בחר **הוסף נתונים** עבור **היסטוריית עסקאות לקוח** ובחר בישות המספקת את המידע על היסטוריית העסקאות/הרכישות כמתואר ב[דרישות מוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="54e3f-155">Select **Add data** for **Customer transaction history** and choose the entity that provides the transaction/purchase history information as described in the [prerequisites](#prerequisites).</span></span>

1. <span data-ttu-id="54e3f-156">מפה את השדות הסמנטיים לתכונות בישות היסטוריית הרכישות שלך ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-156">Map the semantic fields to attributes within your purchase history entity and select **Next**.</span></span> <span data-ttu-id="54e3f-157">לתיאורים של השדות, בדוק את [ה‏‫דרישות המוקדמות](#prerequisites).</span><span class="sxs-lookup"><span data-stu-id="54e3f-157">For descriptions of the fields, have a look at the [prerequisites](#prerequisites).</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54e3f-158">![הגדרת קשר הישות](media/product-recommendation-purchasehistorymapping.PNG "דף היסטוריית רכישות המציג תכונות סמנטיות הממופות לשדות בישות היסטוריית הרכישות שנבחרה")</span><span class="sxs-lookup"><span data-stu-id="54e3f-158">![Define the entity relationship](media/product-recommendation-purchasehistorymapping.PNG "Purchase history page showing semantic attributes that are mapped to fields in the selected purchase history entity")</span></span>

1. <span data-ttu-id="54e3f-159">אם השדות אינם מלאים, הגדר את הקשר מישות היסטוריית הרכישות שלך לישות *לקוח*.</span><span class="sxs-lookup"><span data-stu-id="54e3f-159">If the fields aren't filled in, configure the relationship from your purchase history entity to the *Customer* entity.</span></span>
    1. <span data-ttu-id="54e3f-160">בחר את **ישות היסטוריית הרכישות**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-160">Select the **Purchase history entity**.</span></span>
    1. <span data-ttu-id="54e3f-161">בחר את **שדה** המזהה את הלקוח בישות היסטוריית הרכישות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-161">Select the **Field** that identifies the customer in the purchase history entity.</span></span> <span data-ttu-id="54e3f-162">עליו להתייחס למזהה הלקוח העיקרי של הישות *לקוח* שלך.</span><span class="sxs-lookup"><span data-stu-id="54e3f-162">It needs to relate to the primary customer ID of your *Customer* entity.</span></span>
    1. <span data-ttu-id="54e3f-163">בחר את **ישות לקוח** שמתאימה לישות הלקוח העיקרית שלך.</span><span class="sxs-lookup"><span data-stu-id="54e3f-163">Select the **Customer entity** that matches your primary customer entity.</span></span>
    1. <span data-ttu-id="54e3f-164">הקלד שם המתאר את הקשר.</span><span class="sxs-lookup"><span data-stu-id="54e3f-164">Enter a name that describes the relationship.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="54e3f-165">![דף היסטוריית הרכישות המציג את היצירה של קשר עם הלקוח](media/model-purchase-join.png "דף היסטוריית הרכישות המציג את היצירה של קשר עם הלקוח")</span><span class="sxs-lookup"><span data-stu-id="54e3f-165">![Purchase history page showing the creation of a relationship to customer](media/model-purchase-join.png "Purchase history page showing the creation of a relationship to customer")</span></span>

1. <span data-ttu-id="54e3f-166">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-166">Select **Save**.</span></span>

1. <span data-ttu-id="54e3f-167">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-167">Select **Next**.</span></span>

### <a name="set-schedule-and-review-configuration"></a><span data-ttu-id="54e3f-168">הגדרת לוח זמנים ובדיקת תצורה</span><span class="sxs-lookup"><span data-stu-id="54e3f-168">Set schedule and review configuration</span></span>

1. <span data-ttu-id="54e3f-169">הגדר שכיחות כדי לאמן מחדש את המודל שלך.</span><span class="sxs-lookup"><span data-stu-id="54e3f-169">Set a frequency to retrain your model.</span></span> <span data-ttu-id="54e3f-170">הגדרה זו חשובה כדי לעדכן את דיוק החיזויים כאשר נתונים חדשים מיובאים אל Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="54e3f-170">This setting is important to update the accuracy of predictions as new data is imported into Customer Insights.</span></span> <span data-ttu-id="54e3f-171">מרבית העסקים יכולים לבצע אימון פעם בחודש ולקבל דיוק טוב לחיזוי שלהם.</span><span class="sxs-lookup"><span data-stu-id="54e3f-171">Most businesses can retrain once per month and get a good accuracy for their prediction.</span></span>

1. <span data-ttu-id="54e3f-172">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-172">Select **Next**.</span></span>

1. <span data-ttu-id="54e3f-173">בדוק את ההגדרה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-173">Review the configuration.</span></span> <span data-ttu-id="54e3f-174">אתה יכול לחזור לכל חלק בתצורת החיזוי על ידי בחירה באפשרות **ערוך** מתחת לערך המוצג.</span><span class="sxs-lookup"><span data-stu-id="54e3f-174">You can go back to any part of the prediction configuration by selecting **Edit** under the shown value.</span></span> <span data-ttu-id="54e3f-175">לחלופין, תוכל לבחור שלב תצורה במחוון ההתקדמות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-175">Or you can select a configuration step from the progress indicator.</span></span>

1. <span data-ttu-id="54e3f-176">אם כל הערכים מוגדרים כהלכה, בחר **שמור והפעל** כדי להתחיל בתהליך החיזוי.</span><span class="sxs-lookup"><span data-stu-id="54e3f-176">If all values are configured correctly, select **Save and run** to begin the prediction process.</span></span> <span data-ttu-id="54e3f-177">בכרטיסיה **החיזויים שלי**, תוכל לראות את מצב החיזויים שלך.</span><span class="sxs-lookup"><span data-stu-id="54e3f-177">On the **My predictions** tab, you can see the status of your predictions.</span></span> <span data-ttu-id="54e3f-178">התהליך עשוי להימשך מספר שעות עד להשלמתו, תלוי בכמות הנתונים המשמשים בחיזוי.</span><span class="sxs-lookup"><span data-stu-id="54e3f-178">The process may take several hours to complete depending on the amount of data used in the prediction.</span></span>

## <a name="review-a-prediction-status-and-results"></a><span data-ttu-id="54e3f-179">סקור את מצב החיזוי והתוצאות</span><span class="sxs-lookup"><span data-stu-id="54e3f-179">Review a prediction status and results</span></span>

1. <span data-ttu-id="54e3f-180">עבור אל **החיזויים שלי** ב- **בינה** > **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-180">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54e3f-181">![תצוגה של דף החיזויים שלי](media/product-recommendation-mypredictions.PNG "תצוגה של דף החיזויים שלי")</span><span class="sxs-lookup"><span data-stu-id="54e3f-181">![View of the My Predictions page](media/product-recommendation-mypredictions.PNG "View of the My Predictions page")</span></span>

1. <span data-ttu-id="54e3f-182">בחר בחיזוי שברצונך לבדוק.</span><span class="sxs-lookup"><span data-stu-id="54e3f-182">Select the prediction you want to review.</span></span>
   - <span data-ttu-id="54e3f-183">**שם חיזוי:** שם החיזוי שניתן בעת היצירה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-183">**Prediction name:** The name of the prediction provided when creating it.</span></span>
   - <span data-ttu-id="54e3f-184">**סוג חיזוי:** סוג המודל המשמש לחיזוי</span><span class="sxs-lookup"><span data-stu-id="54e3f-184">**Prediction type:** The type of model used for the prediction</span></span>
   - <span data-ttu-id="54e3f-185">**ישות פלט:** שם הישות לאחסון פלט החיזוי.</span><span class="sxs-lookup"><span data-stu-id="54e3f-185">**Output entity:** Name of the entity to store the output of the prediction.</span></span> <span data-ttu-id="54e3f-186">אתה יכול למצוא ישות עם שם זה ב- **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-186">You can find an entity with this name on **Data** > **Entities**.</span></span>
   - <span data-ttu-id="54e3f-187">**שדה חזוי:** שדה זה מאוכלס רק עבור סוגים מסוימים של תחזיות, ואינו משמש בחיזוי נטישות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-187">**Predicted field:** This field is populated only for some types of predictions, and isn't used in churn prediction.</span></span>
   - <span data-ttu-id="54e3f-188">**מצב:** המצב הנוכחי של הפעלת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="54e3f-188">**Status:** The current status of the prediction's run.</span></span>
        - <span data-ttu-id="54e3f-189">**בתור:** החיזוי ממתין כרגע לתהליכים אחרים שיפעלו.</span><span class="sxs-lookup"><span data-stu-id="54e3f-189">**Queued:** The prediction is currently waiting for other processes to run.</span></span>
        - <span data-ttu-id="54e3f-190">**מרענן:** החיזוי מריץ כעת את שלב ה"ניקוד" של העיבוד כדי לייצר תוצאות שיזרמו ליישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="54e3f-190">**Refreshing:** The prediction is currently running the "score" stage of processing to produce results that will flow into the output entity.</span></span>
        - <span data-ttu-id="54e3f-191">**נכשל:** החיזוי נכשל.</span><span class="sxs-lookup"><span data-stu-id="54e3f-191">**Failed:** the prediction has failed.</span></span> <span data-ttu-id="54e3f-192">בחר **יומנים** לפרטים נוספים.</span><span class="sxs-lookup"><span data-stu-id="54e3f-192">Select **Logs** for more details.</span></span>
        - <span data-ttu-id="54e3f-193">**הצליח:** החיזוי הצליח.</span><span class="sxs-lookup"><span data-stu-id="54e3f-193">**Succeeded:** the prediction has succeeded.</span></span> <span data-ttu-id="54e3f-194">בחר **הצג** מתחת לשלוש הנקודות האנכיות כדי לבדוק את החיזוי</span><span class="sxs-lookup"><span data-stu-id="54e3f-194">Select **View** under the vertical ellipses to review the prediction</span></span>
   - <span data-ttu-id="54e3f-195">**נערך:** התאריך שבו השתנתה הגדרת החיזוי.</span><span class="sxs-lookup"><span data-stu-id="54e3f-195">**Edited:** The date the configuration for the prediction was changed.</span></span>
   - <span data-ttu-id="54e3f-196">**רענון אחרון:** התאריך שבו בוצע רענון של תוצאות החיזוי בישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="54e3f-196">**Last refreshed:** The date the prediction refreshed results in the output entity.</span></span>

1. <span data-ttu-id="54e3f-197">בחר את שלוש הנקודות האנכיות לצד החיזוי שתרצה לבדוק את התוצאות שלו ובחר **הצג**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-197">Select the vertical ellipses next to the prediction you want to review results for and select **View**.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="54e3f-198">![תצוגה של אפשרויות בתפריט שלוש הנקודות האנכיות לחיזוי כולל עריכה, רענון, הצגה, יומנים ומחיקה](media/product-recommendation-verticalellipses.PNG "תצוגה של אפשרויות בתפריט שלוש הנקודות האנכיות לחיזוי כולל עריכה, רענון, הצגה, יומנים ומחיקה")</span><span class="sxs-lookup"><span data-stu-id="54e3f-198">![View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete](media/product-recommendation-verticalellipses.PNG "View of options in the vertical ellipses menu for a prediction including edit, refresh, view, logs, and delete")</span></span>

1. <span data-ttu-id="54e3f-199">ישנם שלושה חלקים עיקריים של נתונים בדף התוצאות:</span><span class="sxs-lookup"><span data-stu-id="54e3f-199">There are three primary sections of data within the results page:</span></span>
    1. <span data-ttu-id="54e3f-200">**ביצועי מודל אימון:** A, B או C הם ציונים אפשריים.</span><span class="sxs-lookup"><span data-stu-id="54e3f-200">**Training model performance:** A, B, or C are possible scores.</span></span> <span data-ttu-id="54e3f-201">ניקוד זה מציין את ביצועי החיזוי ויכול לעזור לך לקבל את ההחלטה להשתמש בתוצאות המאוחסנות בישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="54e3f-201">This score indicates the performance of the prediction, and can help you make the decision to use the results stored in the output entity.</span></span>
        - <span data-ttu-id="54e3f-202">הניקוד נקבע על פי הכללים הבאים:</span><span class="sxs-lookup"><span data-stu-id="54e3f-202">Scores are determined based on the following rules:</span></span>
            - <span data-ttu-id="54e3f-203">**A** המודל ייחשב לאיכות **A** אם המדד "Success @ K" הוא לפחות 10% יותר מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="54e3f-203">**A** The model will be considered **A** quality if the "Success @ K" metric is at least 10% more the baseline.</span></span> 
            - <span data-ttu-id="54e3f-204">**B** המודל ייחשב לאיכות **B** אם המדד "Success @ K" הוא 0 עד 10% יותר מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="54e3f-204">**B** The model will be considered **B** quality if the "Success @ K" metric is 0 to 10% more than the baseline.</span></span>
            - <span data-ttu-id="54e3f-205">**C** המודל ייחשב לאיכות **C** אם המדד "Success @ K" נמוך מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="54e3f-205">**C** The model will be considered **C** quality if the "Success @ K" metric is less than than the baseline.</span></span>
               
               > [!div class="mx-imgBorder"]
               > <span data-ttu-id="54e3f-206">![תצוגה של תוצאות ביצועי המודל](media/product-recommendation-modelperformance.PNG "תצוגה של תוצאות ביצועי המודל")</span><span class="sxs-lookup"><span data-stu-id="54e3f-206">![View of the model performance result](media/product-recommendation-modelperformance.PNG "View of the model performance result")</span></span>
            - <span data-ttu-id="54e3f-207">**בסיס**: המודל לוקח את המוצרים המומלצים ביותר לפי ספירת הרכישות בקרב כל הלקוחות, ומשתמש בכללים שנלמדו המזוהים על-ידי המודל כדי ליצור ערכת המלצות עבור הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-207">**Baseline**: The model takes the top most recommended products by purchase count across all customers, and uses learned rules identified by the model to create a set of recommendations for the customers.</span></span> <span data-ttu-id="54e3f-208">החיזויים מושווים לאחר מכן למוצרים המובילים, כפי שחושבו על-ידי מספר הלקוחות שרכשו את המוצר.</span><span class="sxs-lookup"><span data-stu-id="54e3f-208">The predictions are then compared to the top products, as calculated by the number of customers that had purchased the product.</span></span> <span data-ttu-id="54e3f-209">אם ללקוח יש לפחות מוצר אחד במוצרים המומלצים שלו שנראה גם במוצרים הנרכשים המובילים, הוא נחשב לחלק מהבסיס.</span><span class="sxs-lookup"><span data-stu-id="54e3f-209">If a customer has at least one product in their recommended products that was also seen in the top purchased products, they're considered a part of the baseline.</span></span> <span data-ttu-id="54e3f-210">אם ל- 10 מהלקוחות הללו היה מוצר מומלץ שנרכש מתוך 100 לקוחות בסך הכל, הבסיס היה 10%.</span><span class="sxs-lookup"><span data-stu-id="54e3f-210">If there were 10 of these customers that had a recommended product purchased out of 100 total customers, the baseline would be 10%.</span></span>
            - <span data-ttu-id="54e3f-211">**Success @ K**: באמצעות ערכת אימות של פרק הזמן של העסקאות, המלצות נוצרות עבור כל הלקוחות ומושוות כנגד ערכת האימות של עסקאות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-211">**Success @ K**: Using a validation set of time period of transactions, recommendations are created for all customers and compared against the validation set of transactions.</span></span> <span data-ttu-id="54e3f-212">לדוגמה, בפרק זמן של 12 חודשים, ניתן להקצות את חודש 12 כערכת אימות של נתונים.</span><span class="sxs-lookup"><span data-stu-id="54e3f-212">For example, in a 12 month period, month 12 might be set aside as a validation set of data.</span></span> <span data-ttu-id="54e3f-213">אם המודל חוזה לפחות דבר אחד שהיית רוכש בחודש 12 בהתבסס על מה שהוא למד מ- 11 החודשים הקודמים, הלקוח היה מגדיל את מדד "Success @ K".</span><span class="sxs-lookup"><span data-stu-id="54e3f-213">If the model predicts at least one thing you would purchase in month 12 based on what it learned from the previous 11 months, the customer would increase the "Success @ K" metric.</span></span>
    
    1. <span data-ttu-id="54e3f-214">**המוצרים המוצעים ביותר (עם ספירה):** חמשת המוצרים המובילים שנחזו עבור הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="54e3f-214">**Most suggested products (with tally):** The top 5 products that were predicted for your customers.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="54e3f-215">![גרף המציג את 5 המוצרים המומלצים ביותר](media/product-recommendation-topproducts.PNG "גרף המציג את 5 המוצרים המומלצים ביותר")</span><span class="sxs-lookup"><span data-stu-id="54e3f-215">![Graph showing the top 5 most recommended products](media/product-recommendation-topproducts.PNG "Graph showing the top 5 most recommended products")</span></span>
    
    1. <span data-ttu-id="54e3f-216">**המלצות על מוצרים ברמת מהימנות גבוהה:** דוגמה של המלצות שסופקה ללקוחות שלך שהמודל מאמין שקיימת סבירות גבוהה לכך שהלקוח ירכוש אותן.</span><span class="sxs-lookup"><span data-stu-id="54e3f-216">**High-confidence product recommendations:** A sample of recommendations provided to your customers that the model believes are likely to be purchased by the customer.</span></span>
       > [!div class="mx-imgBorder"]
       > <span data-ttu-id="54e3f-217">![רשימה המציגה הצעות בעלות מהימנות גבוהה עבור ערכה נבחרת של לקוחות בודדים](media/product-recommendation-highconfidence.PNG "רשימה המציגה הצעות בעלות מהימנות גבוהה עבור ערכה נבחרת של לקוחות בודדים")</span><span class="sxs-lookup"><span data-stu-id="54e3f-217">![List showing high confidence suggestions for a select set of individual customers](media/product-recommendation-highconfidence.PNG "List showing high confidence suggestions for a select set of individual customers")</span></span>

## <a name="fix-a-failed-prediction"></a><span data-ttu-id="54e3f-218">תיקון של חיזוי כושל</span><span class="sxs-lookup"><span data-stu-id="54e3f-218">Fix a failed prediction</span></span>

1. <span data-ttu-id="54e3f-219">עבור אל **החיזויים שלי** ב- **בינה** > **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-219">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="54e3f-220">בחר את החיזוי שתרצה להציג ביומני שגיאה ובחר **יומנים**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-220">Select the prediction you would like to view error logs for and select **Logs**.</span></span>

1. <span data-ttu-id="54e3f-221">סקירת כל השגיאות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-221">Review all the errors.</span></span> <span data-ttu-id="54e3f-222">יש מספר סוגים של שגיאות שיכולות להתרחש, והם מתארים איזה מצב גרם לשגיאה.</span><span class="sxs-lookup"><span data-stu-id="54e3f-222">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="54e3f-223">לדוגמה, שגיאה כי אין מספיק נתונים כדי לחזות במדויק נפתרת בדרך כלל על ידי טעינת נתונים נוספים ל- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="54e3f-223">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="54e3f-224">רענן חיזוי</span><span class="sxs-lookup"><span data-stu-id="54e3f-224">Refresh a prediction</span></span>

<span data-ttu-id="54e3f-225">החיזויים עוברים רענון באופן אוטומטי באותו [לוח זמנים שבו הנתונים שלך עוברים רענון](system.md#schedule-tab) כפי שמוגדר בהגדרות.</span><span class="sxs-lookup"><span data-stu-id="54e3f-225">Predictions automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span>

1. <span data-ttu-id="54e3f-226">עבור אל **החיזויים שלי** ב- **בינה** > **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-226">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="54e3f-227">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך לרענן.</span><span class="sxs-lookup"><span data-stu-id="54e3f-227">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="54e3f-228">בחר **רענן**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-228">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="54e3f-229">מחק חיזוי</span><span class="sxs-lookup"><span data-stu-id="54e3f-229">Delete a prediction</span></span>

<span data-ttu-id="54e3f-230">מחיקת חיזוי גם תסיר את ישות הפלט שלו.</span><span class="sxs-lookup"><span data-stu-id="54e3f-230">Deleting a prediction will also remove its output entity.</span></span>

1. <span data-ttu-id="54e3f-231">עבור אל **החיזויים שלי** ב- **בינה** > **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-231">Go to the **My predictions** tab on **Intelligence** > **Predictions**.</span></span>

1. <span data-ttu-id="54e3f-232">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך למחוק.</span><span class="sxs-lookup"><span data-stu-id="54e3f-232">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="54e3f-233">בחר **מחק**.</span><span class="sxs-lookup"><span data-stu-id="54e3f-233">Select **Delete**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]