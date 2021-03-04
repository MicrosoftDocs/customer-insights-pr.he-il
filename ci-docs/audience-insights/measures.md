---
title: יצירה וניהול של מדדים
description: הגדר מדדים לניתוח ולשיקוף הביצועים של העסק שלך.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269929"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="8e0bb-103">הגדרה וניהול של מדדים</span><span class="sxs-lookup"><span data-stu-id="8e0bb-103">Define and manage measures</span></span>

<span data-ttu-id="8e0bb-104">מדדים עוזרים לך להבין טוב יותר את התנהגויות הלקוחות ואת הביצועים העסקיים על-ידי אחזור ערכים רלוונטיים מ[פרופילים מאוחדים](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="8e0bb-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="8e0bb-105">לדוגמה, עסק רוצה לראות את *ההוצאות הכוללות ללקוח* כדי להבין את היסטוריית הרכישות של לקוח יחיד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="8e0bb-106">לחלופין, מדוד *מכירות כוללות של החברה* כדי להבין את ההכנסות ברמת הצבירה בעסק השלם.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="8e0bb-107">מדדים נוצרים באמצעות בונה המדידה, פלטפורמת שאילתת נתונים עם אופרטורים שונים ואפשרויות מיפוי פשוטות.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="8e0bb-108">זה מאפשר לך לסנן את הנתונים, לקבץ תוצאות, לזהות [נתיבי קשר ישות](relationships.md) ולהציג את הפלט בתצוגה מקדימה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="8e0bb-109">השתמש בבונה המדידה כדי לתכנן פעילויות עסקיות על-ידי ביצוע שאילתות על נתוני הלקוח וחילוץ תובנות.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="8e0bb-110">לדוגמה, יצירת מדד של *הוצאות כוללות ללקוח* ו *החזרה כוללת ללקוח* עוזרת לזהות קבוצת לקוחות בעלי הוצאות גבוהות אבל החזרה גבוהה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="8e0bb-111">באפשרותך [ליצור פלח](segments.md) כדי לקדם את הפעולות הטובות ביותר הבאות.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="8e0bb-112">יצירת מדד</span><span class="sxs-lookup"><span data-stu-id="8e0bb-112">Create a measure</span></span>

<span data-ttu-id="8e0bb-113">מקטע זה מדריך אותך ביצירת מדד חדש מאפס.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="8e0bb-114">באפשרותך לבנות מדד עם תכונות נתונים מישויות נתונים בעלות קשר מוגדר לחיבור עם הישות 'לקוח'.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="8e0bb-115">ב- audience insights, עבור אל **מדידות**.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="8e0bb-116">בחר **New**.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-116">Select **New**.</span></span>

1. <span data-ttu-id="8e0bb-117">בחר **ערוך שם** וספק **שם** עבור המדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="8e0bb-118">אם תצורת המדד החדשה שלך כוללת שני שדות בלבד, לדוגמה, 'מזהה לקוח' וחישוב אחד, הפלט יתווסף כעמודה חדשה לישות שנוצרה על-ידי המערכת הנקראת Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="8e0bb-119">ותוכל לראות את ערך המדד בפרופיל הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="8e0bb-120">מדדים אחרים ייצרו ישויות משלהם.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="8e0bb-121">באזור התצורה בחר בפונקציית הצבירה מתוך התפריט הנפתח **בחר פונקציה**.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="8e0bb-122">פונקציות צבירה כוללות:</span><span class="sxs-lookup"><span data-stu-id="8e0bb-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="8e0bb-123">**Sum**</span><span class="sxs-lookup"><span data-stu-id="8e0bb-123">**Sum**</span></span>
   - <span data-ttu-id="8e0bb-124">**ממוצע**</span><span class="sxs-lookup"><span data-stu-id="8e0bb-124">**Average**</span></span>
   - <span data-ttu-id="8e0bb-125">**מספר**</span><span class="sxs-lookup"><span data-stu-id="8e0bb-125">**Count**</span></span>
   - <span data-ttu-id="8e0bb-126">**ערך ייחודי לספירה**</span><span class="sxs-lookup"><span data-stu-id="8e0bb-126">**Count Unique**</span></span>
   - <span data-ttu-id="8e0bb-127">**מרבי**</span><span class="sxs-lookup"><span data-stu-id="8e0bb-127">**Max**</span></span>
   - <span data-ttu-id="8e0bb-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="8e0bb-128">**Min**</span></span>
   - <span data-ttu-id="8e0bb-129">**First**: לוקחת את הערך הראשון של רשומת הנתונים</span><span class="sxs-lookup"><span data-stu-id="8e0bb-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="8e0bb-130">**Last**: לוקחת את הערך האחרון שנוסף לרשומת הנתונים</span><span class="sxs-lookup"><span data-stu-id="8e0bb-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="אופרטורים לחישובי מדדים.":::

1. <span data-ttu-id="8e0bb-132">בחר **הוסף תכונה** כדי לבחור את הנתונים הדרושים לך ליצירת מדד זה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="8e0bb-133">בחר את הכרטיסיה **תכונות**.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="8e0bb-134">ישות נתונים: בחר את הישות הכוללת את התכונה שברצונך למדוד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="8e0bb-135">תכונת נתונים: בחר את התכונה שבה ברצונך להשתמש בפונקציית הצבירה כדי לחשב את המדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="8e0bb-136">ניתן לבחור תכונה אחת בלבד בכל פעם.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="8e0bb-137">באפשרותך גם לבחור תכונת נתונים ממדד קיים על-ידי בחירת הכרטיסיה **מדדים**. לחלופין, באפשרותך לחפש ישות או שם מדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="8e0bb-138">בחר **הוסף** כדי להוסיף את התכונה שנבחרה למדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="בחר תכונה לשימוש בחישובים.":::

1. <span data-ttu-id="8e0bb-140">כדי לבנות מדדים מורכבים יותר, באפשרותך להוסיף תכונות נוספות או להשתמש באופרטורים מתמטיים בפונקציית המדד שלך.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="צור מדד מורכב עם אופרטורים מתמטיים.":::

1. <span data-ttu-id="8e0bb-142">כדי להוסיף מסננים, בחר באפשרות **מסנן** באזור התצורה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="8e0bb-143">במקטע **הוסף תכונה** של החלונית **מסננים**, בחר את התכונה שברצונך להשתמש בה ליצירת מסננים.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="8e0bb-144">הגדר את אופרטורי הסינון כדי להגדיר את המסנן עבור כל תכונה שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="8e0bb-145">בחר **החל** כדי להוסיף את המסננים למדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="8e0bb-146">כדי להוסיף ממדים, בחר באפשרות **ממד** באזור התצורה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="8e0bb-147">ממדים יוצגו כעמודות בישות פלט המדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="8e0bb-148">בחר **ערוך ממדים** כדי להוסיף תכונות נתונים שברצונך לקבץ לפיהן את ערכי המדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="8e0bb-149">לדוגמה, עיר או מגדר.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-149">For example, city or gender.</span></span> <span data-ttu-id="8e0bb-150">כברירת מחדל, הממד *מזהה לקוח* נבחר כדי ליצור *מדדים ברמת לקוח*.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="8e0bb-151">באפשרותך להסיר את ממד ברירת המחדל אם ברצונך ליצור *מדדים ברמת עסק*.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="8e0bb-152">בחר **בוצע** כדי להוסיף את הממדים למדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="8e0bb-153">אם קיימים נתיבים מרובים בין ישות הנתונים שמיפית לישות 'לקוח', עליך לבחור באחד מ[נתיבי קשר הישות](relationships.md) שנקבעו.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-153">If there are multiple paths between the data entity you mapped and the Customer entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="8e0bb-154">תוצאות המדידה עשויות להשתנות בהתאם לנתיב שנבחר.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-154">Measure results can vary depending on the selected path.</span></span>
   1. <span data-ttu-id="8e0bb-155">בחר **העדפות נתונים** ובחר את נתיב הישות שיש להשתמש בו לזיהוי המדד שלך.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span>
   1. <span data-ttu-id="8e0bb-156">בחר **בוצע** כדי להחיל את הבחירה שלך.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-156">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="בחר את נתיב הישות עבור המדד.":::

1. <span data-ttu-id="8e0bb-158">כדי להוסיף חישובים נוספים למדד, בחר **חישוב חדש**.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-158">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="8e0bb-159">באפשרותך להשתמש רק בישויות באותו נתיב ישות לצורך חישובים חדשים.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-159">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="8e0bb-160">חישובים נוספים יוצגו כעמודות חדשות בישות פלט המדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-160">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="8e0bb-161">בחר **...** בחישוב כדי **לשכפל**, **לשנות שם** או **להסיר** חישוב ממדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-161">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="8e0bb-162">באזור **תצוגה מקדימה**, תראה את סכימת הנתונים של ישות פלט המדד, לרבות מסננים וממדים.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-162">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="8e0bb-163">התצוגה המקדימה מגיבה באופן דינמי לשינויים בתצורה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-163">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="8e0bb-164">בחר **הפעל** כדי לחשב תוצאות עבור המדד שהוגדר.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-164">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="8e0bb-165">בחר **שמור וסגור** אם ברצונך לשמור על התצורה הנוכחית ולהפעיל את המדד מאוחר יותר.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-165">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="8e0bb-166">עבור אל **מדדים** כדי לראות את המדד החדש שנוצר ברשימה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-166">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="8e0bb-167">נהל את המדדים שלך</span><span class="sxs-lookup"><span data-stu-id="8e0bb-167">Manage your measures</span></span>

<span data-ttu-id="8e0bb-168">לאחר [יצירת מדד](#create-a-measure), תראה רשימת מדדים בדף **מדדים**.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-168">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="8e0bb-169">תמצא מידע אודות סוג המדד, היוצר, תאריך היצירה, המצב והמדינה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-169">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="8e0bb-170">כשתבחר מדד מהרשימה, תוכל להציג בתצוגה מקדימה את הפלט ולהוריד קובץ ‎.CSV</span><span class="sxs-lookup"><span data-stu-id="8e0bb-170">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="8e0bb-171">כדי לרענן את כל המדדים שלך בו-זמנית, בחר **רענן הכל** מבלי לבחור מדד ספציפי.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-171">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8e0bb-172">![פעולות לניהול מדדים יחידים](media/measure-actions.png "פעולות לניהול מדדים יחידים")</span><span class="sxs-lookup"><span data-stu-id="8e0bb-172">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="8e0bb-173">בחר מדד מהרשימה עבור האפשרויות הבאות:</span><span class="sxs-lookup"><span data-stu-id="8e0bb-173">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="8e0bb-174">בחר את שם המדד כדי לראות את הפרטים שלו.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-174">Select the measure name to see its details.</span></span>
- <span data-ttu-id="8e0bb-175">**ערוך** את קביעת התצורה של המדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-175">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="8e0bb-176">**רענן** את המדד בהתבסס על הנתונים העדכניים ביותר.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-176">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="8e0bb-177">**שנה שם** של המדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-177">**Rename** the measure.</span></span>
- <span data-ttu-id="8e0bb-178">**מחק** את המדד.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-178">**Delete** the measure.</span></span>
- <span data-ttu-id="8e0bb-179">**הפעל** או **בטל הפעלה**.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-179">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="8e0bb-180">מדדים לא פעילים לא יעברו רענון במהלך [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8e0bb-180">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="8e0bb-181">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="8e0bb-182">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="8e0bb-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="8e0bb-183">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="8e0bb-184">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="8e0bb-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="8e0bb-185">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="8e0bb-185">Next step</span></span>

<span data-ttu-id="8e0bb-186">באפשרותך להשתמש במדדים קיימים ליצירת [פלח לקוחות](segments.md).</span><span class="sxs-lookup"><span data-stu-id="8e0bb-186">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]