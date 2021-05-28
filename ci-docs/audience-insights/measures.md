---
title: יצירה וניהול של מדדים
description: הגדר מדדים לניתוח ולשיקוף הביצועים של העסק שלך.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049251"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="6bd87-103">הגדרה וניהול של מדדים</span><span class="sxs-lookup"><span data-stu-id="6bd87-103">Define and manage measures</span></span>

<span data-ttu-id="6bd87-104">מדדים עוזרים לך להבין טוב יותר התנהגויות של לקוחות וביצועים עסקיים.</span><span class="sxs-lookup"><span data-stu-id="6bd87-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="6bd87-105">הם בוחנים ערכים רלוונטיים מ[פרופילים מאוחדים](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="6bd87-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="6bd87-106">לדוגמא, עסק רוצה לראות את *ההוצאה הכוללת ללקוח* כדי להבין היסטוריית רכישות של לקוח יחיד או למדוד *מכירות כוללות של החברה* כדי להבין את ההכנסות ברמת הצבירה בעסק כולו.</span><span class="sxs-lookup"><span data-stu-id="6bd87-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="6bd87-107">מדדים נוצרים באמצעות בונה המדידה, פלטפורמת שאילתת נתונים עם אופרטורים שונים ואפשרויות מיפוי פשוטות.</span><span class="sxs-lookup"><span data-stu-id="6bd87-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="6bd87-108">זה מאפשר לך לסנן את הנתונים, לקבץ תוצאות, לזהות [נתיבי קשר ישות](relationships.md) ולהציג את הפלט בתצוגה מקדימה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="6bd87-109">השתמש בבונה המדידה כדי לתכנן פעילויות עסקיות על-ידי ביצוע שאילתות על נתוני הלקוח וחילוץ תובנות.</span><span class="sxs-lookup"><span data-stu-id="6bd87-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="6bd87-110">לדוגמה, יצירת מדד של *הוצאות כוללות ללקוח* ו *החזרה כוללת ללקוח* עוזרת לזהות קבוצת לקוחות בעלי הוצאות גבוהות אבל החזרה גבוהה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="6bd87-111">באפשרותך [ליצור פלח](segments.md) כדי לקדם את הפעולות הטובות ביותר הבאות.</span><span class="sxs-lookup"><span data-stu-id="6bd87-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="6bd87-112">בנה את המדד שלך מאפס</span><span class="sxs-lookup"><span data-stu-id="6bd87-112">Build your own measure from scratch</span></span>

<span data-ttu-id="6bd87-113">מקטע זה מדריך אותך ביצירת מדד חדש מאפס.</span><span class="sxs-lookup"><span data-stu-id="6bd87-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="6bd87-114">באפשרותך לבנות מדד עם תכונות נתונים מישויות נתונים בעלות קשר מוגדר לחיבור עם הישות 'לקוח'.</span><span class="sxs-lookup"><span data-stu-id="6bd87-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="6bd87-115">ב- audience insights, עבור אל **מדידות**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="6bd87-116">בחר **חדש** ובחר **בנה בעצמך**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="6bd87-117">בחר **ערוך שם** וספק **שם** עבור המדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="6bd87-118">אם תצורת המדידה החדשה שלך כוללת שני שדות בלבד, למשל, CustomerID וחישוב אחד, הפלט יתווסף כעמודה חדשה לישות שנוצרה על-ידי המערכת, הנקראת Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="6bd87-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="6bd87-119">ותוכל לראות את ערך המדד בפרופיל הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="6bd87-120">מדדים אחרים ייצרו ישויות משלהם.</span><span class="sxs-lookup"><span data-stu-id="6bd87-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="6bd87-121">באזור התצורה בחר בפונקציית הצבירה מתוך התפריט הנפתח **בחר פונקציה**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="6bd87-122">פונקציות צבירה כוללות:</span><span class="sxs-lookup"><span data-stu-id="6bd87-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="6bd87-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="6bd87-123">**Sum**</span></span>
   - <span data-ttu-id="6bd87-124">**ממוצע**</span><span class="sxs-lookup"><span data-stu-id="6bd87-124">**Average**</span></span>
   - <span data-ttu-id="6bd87-125">**מספר**</span><span class="sxs-lookup"><span data-stu-id="6bd87-125">**Count**</span></span>
   - <span data-ttu-id="6bd87-126">**ערך ייחודי לספירה**</span><span class="sxs-lookup"><span data-stu-id="6bd87-126">**Count Unique**</span></span>
   - <span data-ttu-id="6bd87-127">**מרבי**</span><span class="sxs-lookup"><span data-stu-id="6bd87-127">**Max**</span></span>
   - <span data-ttu-id="6bd87-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="6bd87-128">**Min**</span></span>
   - <span data-ttu-id="6bd87-129">**First**: לוקחת את הערך הראשון של רשומת הנתונים</span><span class="sxs-lookup"><span data-stu-id="6bd87-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="6bd87-130">**Last**: לוקחת את הערך האחרון שנוסף לרשומת הנתונים</span><span class="sxs-lookup"><span data-stu-id="6bd87-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="אופרטורים לחישובי מדדים.":::

1. <span data-ttu-id="6bd87-132">בחר **הוסף תכונה** כדי לבחור את הנתונים הדרושים לך ליצירת מדד זה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="6bd87-133">בחר את הכרטיסיה **תכונות**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="6bd87-134">ישות נתונים: בחר את הישות הכוללת את התכונה שברצונך למדוד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="6bd87-135">תכונת נתונים: בחר את התכונה שבה ברצונך להשתמש בפונקציית הצבירה כדי לחשב את המדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="6bd87-136">ניתן לבחור תכונה אחת בלבד בכל פעם.</span><span class="sxs-lookup"><span data-stu-id="6bd87-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="6bd87-137">באפשרותך גם לבחור תכונת נתונים ממדד קיים על-ידי בחירת הכרטיסיה **מדדים**. לחלופין, באפשרותך לחפש ישות או שם מדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="6bd87-138">בחר **הוסף** כדי להוסיף את התכונה שנבחרה למדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="בחר תכונה לשימוש בחישובים.":::

1. <span data-ttu-id="6bd87-140">כדי לבנות מדדים מורכבים יותר, באפשרותך להוסיף תכונות נוספות או להשתמש באופרטורים מתמטיים בפונקציית המדד שלך.</span><span class="sxs-lookup"><span data-stu-id="6bd87-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="צור מדד מורכב עם אופרטורים מתמטיים.":::

1. <span data-ttu-id="6bd87-142">כדי להוסיף מסננים, בחר באפשרות **מסנן** באזור התצורה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="6bd87-143">במקטע **הוסף תכונה** של החלונית **מסננים**, בחר את התכונה שברצונך להשתמש בה ליצירת מסננים.</span><span class="sxs-lookup"><span data-stu-id="6bd87-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="6bd87-144">הגדר את אופרטורי הסינון כדי להגדיר את המסנן עבור כל תכונה שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="6bd87-145">בחר **החל** כדי להוסיף את המסננים למדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="6bd87-146">כדי להוסיף ממדים, בחר באפשרות **ממד** באזור התצורה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="6bd87-147">ממדים יוצגו כעמודות בישות פלט המדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="6bd87-148">בחר **ערוך ממדים** כדי להוסיף תכונות נתונים שברצונך לקבץ לפיהן את ערכי המדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="6bd87-149">לדוגמה, עיר או מגדר.</span><span class="sxs-lookup"><span data-stu-id="6bd87-149">For example, city or gender.</span></span> <span data-ttu-id="6bd87-150">כברירת מחדל, הממד *מזהה לקוח* נבחר כדי ליצור *מדדים ברמת לקוח*.</span><span class="sxs-lookup"><span data-stu-id="6bd87-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="6bd87-151">באפשרותך להסיר את ממד ברירת המחדל אם ברצונך ליצור *מדדים ברמת עסק*.</span><span class="sxs-lookup"><span data-stu-id="6bd87-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="6bd87-152">בחר **בוצע** כדי להוסיף את הממדים למדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="6bd87-153">אם קיימים ערכים בנתונים שלך שעליך להחליף במספר שלם, לדוגמה, החלף את *null* ב- *0*, בחר **כללים**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="6bd87-154">קבע את תצורת הכלל והקפד לבחור רק מספרים שלמים כתחליפים.</span><span class="sxs-lookup"><span data-stu-id="6bd87-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="6bd87-155">אם קיימים נתיבים מרובים בין ישות הנתונים שמיפית לישות *לקוח*, עליך לבחור באחד מ[נתיבי קשר הישות](relationships.md) שנקבעו.</span><span class="sxs-lookup"><span data-stu-id="6bd87-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="6bd87-156">תוצאות המדידה עשויות להשתנות בהתאם לנתיב שנבחר.</span><span class="sxs-lookup"><span data-stu-id="6bd87-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="6bd87-157">בחר **העדפות נתונים** ובחר את נתיב הישות שיש להשתמש בו לזיהוי המדד שלך.</span><span class="sxs-lookup"><span data-stu-id="6bd87-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="6bd87-158">אם קיים נתיב אחד בלבד אל הישות *לקוח*, פקד זה לא יופיע.</span><span class="sxs-lookup"><span data-stu-id="6bd87-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="6bd87-159">בחר **בוצע** כדי להחיל את הבחירה שלך.</span><span class="sxs-lookup"><span data-stu-id="6bd87-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="בחר את נתיב הישות עבור המדד.":::

1. <span data-ttu-id="6bd87-161">כדי להוסיף חישובים נוספים למדד, בחר **חישוב חדש**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="6bd87-162">באפשרותך להשתמש רק בישויות באותו נתיב ישות לצורך חישובים חדשים.</span><span class="sxs-lookup"><span data-stu-id="6bd87-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="6bd87-163">חישובים נוספים יוצגו כעמודות חדשות בישות פלט המדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="6bd87-164">בחר **...** בחישוב כדי **לשכפל**, **לשנות שם** או **להסיר** חישוב ממדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="6bd87-165">באזור **תצוגה מקדימה**, תראה את סכימת הנתונים של ישות פלט המדד, לרבות מסננים וממדים.</span><span class="sxs-lookup"><span data-stu-id="6bd87-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="6bd87-166">התצוגה המקדימה מגיבה באופן דינמי לשינויים בתצורה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="6bd87-167">בחר **הפעל** כדי לחשב תוצאות עבור המדד שהוגדר.</span><span class="sxs-lookup"><span data-stu-id="6bd87-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="6bd87-168">בחר **שמור וסגור** אם ברצונך לשמור על התצורה הנוכחית ולהפעיל את המדד מאוחר יותר.</span><span class="sxs-lookup"><span data-stu-id="6bd87-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="6bd87-169">עבור אל **מדדים** כדי לראות את המדד החדש שנוצר ברשימה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="6bd87-170">השתמש בתבנית לבניית מדד</span><span class="sxs-lookup"><span data-stu-id="6bd87-170">Use a template to build a measure</span></span>

<span data-ttu-id="6bd87-171">באפשרותך להשתמש בתבניות מוגדרות מראש של מדדים נפוצים כדי ליצור אותן.</span><span class="sxs-lookup"><span data-stu-id="6bd87-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="6bd87-172">תיאורים מפורטים של התבניות וחוויה מודרכת עוזרים לך ביצירת מדדים יעילים.</span><span class="sxs-lookup"><span data-stu-id="6bd87-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="6bd87-173">תבניות מבוססות על נתונים ממופים מהישות *פעילות מאוחדת*.</span><span class="sxs-lookup"><span data-stu-id="6bd87-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="6bd87-174">לכן ודא שהגדרת את [פעילויות לקוח](activities.md) לפני שאתה יוצר מדד מתבנית.</span><span class="sxs-lookup"><span data-stu-id="6bd87-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="6bd87-175">תבניות מדד זמינות:</span><span class="sxs-lookup"><span data-stu-id="6bd87-175">Available measure templates:</span></span> 
- <span data-ttu-id="6bd87-176">ערך עסקה ממוצע (ATV)</span><span class="sxs-lookup"><span data-stu-id="6bd87-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="6bd87-177">ערך עסקה כולל</span><span class="sxs-lookup"><span data-stu-id="6bd87-177">Total transaction value</span></span>
- <span data-ttu-id="6bd87-178">הכנסה יומית ממוצעת</span><span class="sxs-lookup"><span data-stu-id="6bd87-178">Average daily revenue</span></span>
- <span data-ttu-id="6bd87-179">הכנסה שנתית ממוצעת</span><span class="sxs-lookup"><span data-stu-id="6bd87-179">Average yearly revenue</span></span>
- <span data-ttu-id="6bd87-180">ספירת עסקאות</span><span class="sxs-lookup"><span data-stu-id="6bd87-180">Transaction count</span></span>
- <span data-ttu-id="6bd87-181">נקודות מועדון לקוחות שהושגו</span><span class="sxs-lookup"><span data-stu-id="6bd87-181">Loyalty points earned</span></span>
- <span data-ttu-id="6bd87-182">נקודות מועדון לקוחות שמומשו</span><span class="sxs-lookup"><span data-stu-id="6bd87-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="6bd87-183">יתרת נקודות במועדון לקוחות</span><span class="sxs-lookup"><span data-stu-id="6bd87-183">Loyalty points balance</span></span>
- <span data-ttu-id="6bd87-184">משך חיים של לקוח פעיל</span><span class="sxs-lookup"><span data-stu-id="6bd87-184">Active customer lifespan</span></span>
- <span data-ttu-id="6bd87-185">משך חברות במועדון לקוחות</span><span class="sxs-lookup"><span data-stu-id="6bd87-185">Loyalty membership duration</span></span>
- <span data-ttu-id="6bd87-186">זמן מאז הרכישה האחרונה</span><span class="sxs-lookup"><span data-stu-id="6bd87-186">Time since last purchase</span></span>

<span data-ttu-id="6bd87-187">ההליך הבא מתאר את השלבים לבניית מדד חדש באמצעות תבנית.</span><span class="sxs-lookup"><span data-stu-id="6bd87-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="6bd87-188">ב- audience insights, עבור אל **מדידות**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="6bd87-189">בחר **חדש** ובחר **בחר תבנית**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="צילום מסך של התפריט הנפתח בעת יצירת מדד חדש עם הדגשה בתבנית.":::

1. <span data-ttu-id="6bd87-191">מצא את התבנית שמתאימה לצרכיך ובחר **בחר תבנית**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="6bd87-192">סקור את הנתונים הנדרשים ובחר **תחילת העבודה** אם כל הנתונים נמצאים ברשותך.</span><span class="sxs-lookup"><span data-stu-id="6bd87-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="6bd87-193">בחלונית **ערוך שם**, הגדר את השם עבור המדד וישות הפלט שלך.</span><span class="sxs-lookup"><span data-stu-id="6bd87-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="6bd87-194">בחר **סיום**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-194">Select **Done**.</span></span>

1. <span data-ttu-id="6bd87-195">במקטע **הגדר פרק זמן**, הגדר את מסגרת הזמן של הנתונים שיש להשתמש בהם.</span><span class="sxs-lookup"><span data-stu-id="6bd87-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="6bd87-196">בחר אם ברצונך שהמדד החדש יכסה את ערכת הנתונים השלמה על-ידי בחירת **כל הזמן**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="6bd87-197">לחלופין, אם ברצונך שהמדד יתמקד ב **פרק זמן ספציפי**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="צילום מסך המציג את מקטע פרק הזמן בעת קביעת התצורה של מדד מתבנית.":::

1. <span data-ttu-id="6bd87-199">במקטע הבא, בחר **הוסף נתונים** כדי לבחור את הפעילויות ולמפות את הנתונים המתאימים מישות *פעילות מאוחדת* שלך.</span><span class="sxs-lookup"><span data-stu-id="6bd87-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="6bd87-200">שלב 1 מתוך 2: תחת **סוג פעילות**, בחר את סוג הישות שבה ברצונך להשתמש.</span><span class="sxs-lookup"><span data-stu-id="6bd87-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="6bd87-201">עבור **פעילויות**, בחר את הישויות שברצונך למפות.</span><span class="sxs-lookup"><span data-stu-id="6bd87-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="6bd87-202">שלב 2 מתוך 2: בחר את התכונה מתוך הישות *פעילות מאוחדת* עבור הרכיב הנדרש על-ידי הנוסחה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="6bd87-203">לדוגמה, עבור ערך עסקה ממוצע, זו התכונה המייצגת את ערך העסקה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="6bd87-204">עבור **חותמת זמן של פעילות**, בחר את התכונה מהישות 'פעילות מאוחדת' המייצגת את התאריך והשעה של הפעילות.</span><span class="sxs-lookup"><span data-stu-id="6bd87-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="6bd87-205">לאחר שמיפוי הנתונים הצליח, באפשרותך לראות את המצב כ **הושלם** ואת שם הפעילויות והתכונות הממופות.</span><span class="sxs-lookup"><span data-stu-id="6bd87-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="צילום מסך של תצורת תבנית של מדד שהושלם.":::

1. <span data-ttu-id="6bd87-207">באפשרותך לבחור כעת **הפעל** כדי לחשב את תוצאות המדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="6bd87-208">כדי למקד אותה בהמשך, בחר **שמור טיוטה**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="6bd87-209">נהל את המדדים שלך</span><span class="sxs-lookup"><span data-stu-id="6bd87-209">Manage your measures</span></span>

<span data-ttu-id="6bd87-210">באפשרותך למצוא את רשימת המדדים בדף **מדדים**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="6bd87-211">תמצא מידע אודות סוג המדד, היוצר, תאריך היצירה, המצב והמדינה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="6bd87-212">כשתבחר מדד מהרשימה, תוכל להציג בתצוגה מקדימה את הפלט ולהוריד קובץ ‎.CSV</span><span class="sxs-lookup"><span data-stu-id="6bd87-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="6bd87-213">כדי לרענן את כל המדדים שלך בו-זמנית, בחר **רענן הכל** מבלי לבחור מדד ספציפי.</span><span class="sxs-lookup"><span data-stu-id="6bd87-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6bd87-214">![פעולות לניהול מדדים יחידים](media/measure-actions.png "פעולות לניהול מדדים יחידים")</span><span class="sxs-lookup"><span data-stu-id="6bd87-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="6bd87-215">בחר מדד מהרשימה עבור האפשרויות הבאות:</span><span class="sxs-lookup"><span data-stu-id="6bd87-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="6bd87-216">בחר את שם המדד כדי לראות את הפרטים שלו.</span><span class="sxs-lookup"><span data-stu-id="6bd87-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="6bd87-217">**ערוך** את קביעת התצורה של המדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="6bd87-218">**רענן** את המדד בהתבסס על הנתונים העדכניים ביותר.</span><span class="sxs-lookup"><span data-stu-id="6bd87-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="6bd87-219">**שנה שם** של המדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-219">**Rename** the measure.</span></span>
- <span data-ttu-id="6bd87-220">**מחק** את המדד.</span><span class="sxs-lookup"><span data-stu-id="6bd87-220">**Delete** the measure.</span></span>
- <span data-ttu-id="6bd87-221">**הפעל** או **בטל הפעלה**.</span><span class="sxs-lookup"><span data-stu-id="6bd87-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="6bd87-222">מדדים לא פעילים לא יעברו רענון במהלך [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6bd87-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="6bd87-223">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="6bd87-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6bd87-224">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6bd87-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6bd87-225">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6bd87-226">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="6bd87-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="6bd87-227">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="6bd87-227">Next step</span></span>

<span data-ttu-id="6bd87-228">באפשרותך להשתמש במדדים קיימים ליצירת [פלח לקוחות](segments.md).</span><span class="sxs-lookup"><span data-stu-id="6bd87-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
