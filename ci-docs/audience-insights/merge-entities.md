---
title: מיזוג ישויות באיחוד נתונים
description: מזג ישויות ליצירת פרופילי לקוח מאוחדים.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085577"
---
# <a name="merge-entities"></a><span data-ttu-id="68dc9-103">מיזוג ישויות</span><span class="sxs-lookup"><span data-stu-id="68dc9-103">Merge entities</span></span>

<span data-ttu-id="68dc9-104">שלב המיזוג הוא השלב האחרון בתהליך איחוד נתונים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="68dc9-105">מטרתו ליישב נתונים סותרים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="68dc9-106">דוגמאות לנתונים סותרים יכולות לכלול שם לקוח שנמצא בשני מערכי הנתונים שלך אך מופיע מעט אחרת בכל אחת מהן ("גרנט מארשל" לעומת "גרנט מרשל"), או מספר טלפון ששונה מבחינת הפורמט (617-803-091X לעומת 617803091X).</span><span class="sxs-lookup"><span data-stu-id="68dc9-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="68dc9-107">מיזוג של נקודות הנתונים הסותרות מתבצע על בסיס תכונה-לתכונה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="דף מיזוג בתהליך איחוד הנתונים המציג טבלה עם שדות שמוזגו המגדירים את פרופיל הלקוח המאוחד.":::

<span data-ttu-id="68dc9-109">לאחר השלמת [שלב ההתאמה](match-entities.md), תתחיל את שלב המיזוג על-ידי בחירה באריח **מיזוג** בדף **איחוד**.</span><span class="sxs-lookup"><span data-stu-id="68dc9-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="68dc9-110">סקור המלצות מערכת</span><span class="sxs-lookup"><span data-stu-id="68dc9-110">Review system recommendations</span></span>

<span data-ttu-id="68dc9-111">ב **נתונים** > **איחוד** > **מיזוג**, אתה בוחר ומחריג תכונות למיזוג בתוך ישות הפרופיל של הלקוח המאוחד שלך.</span><span class="sxs-lookup"><span data-stu-id="68dc9-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="68dc9-112">פרופיל הלקוח המאוחד הוא תוצאה של תהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="68dc9-113">חלק מהתכונות ממוזגות באופן אוטומטי על ידי המערכת.</span><span class="sxs-lookup"><span data-stu-id="68dc9-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="68dc9-114">כדי להציג את התכונות הכלולות באחת מהתכונות שלך שמוזגו באופן אוטומטי, בחר את התכונה שמוזגה בכרטיסיה **שדות לקוח** של הטבלה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="68dc9-115">התכונות המרכיבות את התכונה הממוזגת מופיעות בשתי שורות חדשות מתחת לתכונה הממוזגת.</span><span class="sxs-lookup"><span data-stu-id="68dc9-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="68dc9-116">הפרדה, שינוי שם, החרגה ועריכה של שדות שמוזגו</span><span class="sxs-lookup"><span data-stu-id="68dc9-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="68dc9-117">ניתן לשנות את האופן שבו מעבדת המערכת תכונות ממוזגות כדי ליצור את פרופיל הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="68dc9-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="68dc9-118">בחר **הצג עוד** ובחר מה ברצונך לשנות.</span><span class="sxs-lookup"><span data-stu-id="68dc9-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="האפשרויות בתפריט הנפתח 'הצג עוד' לניהול תכונות ממוזגות.":::

<span data-ttu-id="68dc9-120">לקבלת מידע נוסף, עיין במקטעים הבאים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="68dc9-121">הפרדת שדות ממוזגים</span><span class="sxs-lookup"><span data-stu-id="68dc9-121">Separate merged fields</span></span>

<span data-ttu-id="68dc9-122">כדי להפריד בין שדות ממוזגים, מצא את התכונה בטבלה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="68dc9-123">שדות מופרדים מופיעים כנקודות נתונים בודדות בפרופיל הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="68dc9-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="68dc9-124">בחר את השדה שמוזג.</span><span class="sxs-lookup"><span data-stu-id="68dc9-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="68dc9-125">בחר **הצג עוד** ובחר **הפרד שדות**.</span><span class="sxs-lookup"><span data-stu-id="68dc9-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="68dc9-126">אשר את ההפרדה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-126">Confirm the separation.</span></span>

1. <span data-ttu-id="68dc9-127">בחר **שמור** ו **הפעל** כדי לעבד את השינויים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="68dc9-128">שנה את שם השדות הממוזגים</span><span class="sxs-lookup"><span data-stu-id="68dc9-128">Rename merged fields</span></span>

<span data-ttu-id="68dc9-129">שנה את שם התצוגה של התכונות הממוזגות.</span><span class="sxs-lookup"><span data-stu-id="68dc9-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="68dc9-130">לא ניתן לשנות את השם של ישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="68dc9-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="68dc9-131">בחר את השדה שמוזג.</span><span class="sxs-lookup"><span data-stu-id="68dc9-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="68dc9-132">בחר **הצג עוד** ובחר **שנה שם**.</span><span class="sxs-lookup"><span data-stu-id="68dc9-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="68dc9-133">אשר את שם התצוגה שהשתנה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="68dc9-134">בחר **שמור** ו **הפעל** כדי לעבד את השינויים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="68dc9-135">החרגה של שדות שמוזגו</span><span class="sxs-lookup"><span data-stu-id="68dc9-135">Exclude merged fields</span></span>

<span data-ttu-id="68dc9-136">אל תכלול תכונה בפרופיל הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="68dc9-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="68dc9-137">אם נעשה שימוש בשדה בתהליכים אחרים, לדוגמה בפלח, הסר אותו מהתהליכים הללו לפני שתחריג אותו מפרופיל הלקוח.</span><span class="sxs-lookup"><span data-stu-id="68dc9-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="68dc9-138">בחר את השדה שמוזג.</span><span class="sxs-lookup"><span data-stu-id="68dc9-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="68dc9-139">בחר **הצג עוד** ובחר **אל תכלול**.</span><span class="sxs-lookup"><span data-stu-id="68dc9-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="68dc9-140">אשר את ההחרגה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="68dc9-141">בחר **שמור** ו **הפעל** כדי לעבד את השינויים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="68dc9-142">בדף **מיזוג**, בחר **שדות לא כלולים** כדי לראות את הרשימה של כל השדות שלא נכללו.</span><span class="sxs-lookup"><span data-stu-id="68dc9-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="68dc9-143">חלונית זו מאפשרת לך להוסיף חזרה שדות שלא נכללו.</span><span class="sxs-lookup"><span data-stu-id="68dc9-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="68dc9-144">שילוב ידני של שדות</span><span class="sxs-lookup"><span data-stu-id="68dc9-144">Manually combine fields</span></span>

<span data-ttu-id="68dc9-145">ציין תכונה שמוזגה באופן ידני.</span><span class="sxs-lookup"><span data-stu-id="68dc9-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="68dc9-146">בדף **מיזוג**, בחר **שלב שדות**.</span><span class="sxs-lookup"><span data-stu-id="68dc9-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="68dc9-147">ספק **שם** ו **שם שדה פלט**.</span><span class="sxs-lookup"><span data-stu-id="68dc9-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="68dc9-148">בחר שדה להוספה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-148">Choose a field to add.</span></span> <span data-ttu-id="68dc9-149">בחר **הוסף שדות** כדי לשלב שדות נוספים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="68dc9-150">אשר את ההחרגה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="68dc9-151">בחר **שמור** ו **הפעל** כדי לעבד את השינויים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="68dc9-152">שינוי סדר השדות</span><span class="sxs-lookup"><span data-stu-id="68dc9-152">Change the order of fields</span></span>

<span data-ttu-id="68dc9-153">ישויות מסוימות מכילות יותר פרטים מאחרות.</span><span class="sxs-lookup"><span data-stu-id="68dc9-153">Some entities contain more details than others.</span></span> <span data-ttu-id="68dc9-154">אם ישות כוללת את הנתונים העדכניים ביותר אודות שדה, ניתן לתעדף אותם על פני ישויות אחרות בעת מיזוג ערכים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="68dc9-155">בחר את השדה שמוזג.</span><span class="sxs-lookup"><span data-stu-id="68dc9-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="68dc9-156">בחר **הצג עוד** ובחר **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="68dc9-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="68dc9-157">בחלונית **שלב שדות**, בחר **הזז למעלה/למטה** כדי לקבוע את הסדר או לגרור ולשחרר אותם במיקום הרצוי.</span><span class="sxs-lookup"><span data-stu-id="68dc9-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="68dc9-158">אשר את השינוי.</span><span class="sxs-lookup"><span data-stu-id="68dc9-158">Confirm the change.</span></span>

1. <span data-ttu-id="68dc9-159">בחר **שמור** ו **הפעל** כדי לעבד את השינויים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="68dc9-160">הרץ את המיזוג שלך</span><span class="sxs-lookup"><span data-stu-id="68dc9-160">Run your merge</span></span>

<span data-ttu-id="68dc9-161">בין אם אתה ממזג ידנית תכונות או מאפשר למערכת למזג אותן, אתה תמיד יכול להריץ את המיזוג.</span><span class="sxs-lookup"><span data-stu-id="68dc9-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="68dc9-162">בחר **הפעל** בדף **מיזוג** כדי להתחיל בתהליך.</span><span class="sxs-lookup"><span data-stu-id="68dc9-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="68dc9-163">![שמור והפעל מיזוג נתונים](media/configure-data-merge-save-run.png "שמור והפעל מיזוג נתונים")</span><span class="sxs-lookup"><span data-stu-id="68dc9-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="68dc9-164">בחר **הפעל מיזוג בלבד** אם אתה רק רוצה לראות את הפלט בא לידי ביטוי בישות של הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="68dc9-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="68dc9-165">יתבצע רענון בתהליכים במורד הזרם כ[מוגדר בלוח הזמנים לרענון](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="68dc9-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="68dc9-166">בחר **הפעל תהליכי מיזוג ותהליכים במורד הזרם** כדי לרענן את המערכת עם השינויים שלך.</span><span class="sxs-lookup"><span data-stu-id="68dc9-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="68dc9-167">כל התהליכים, כולל ההעשרה, הפלחים והמדדים יופעלו מחדש באופן אוטומטי.</span><span class="sxs-lookup"><span data-stu-id="68dc9-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="68dc9-168">לאחר השלמת כל התהליכים שלך במורד הזרם, פרופילי הלקוחות משקפים את השינויים שביצעת.</span><span class="sxs-lookup"><span data-stu-id="68dc9-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="68dc9-169">כדי לבצע שינויים נוספים ולהפעיל מחדש את השלב, תוכל לבטל מיזוג שמתבצע.</span><span class="sxs-lookup"><span data-stu-id="68dc9-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="68dc9-170">בחר **מרענן...** ובחר **בטל משימה** בחלונית הצדדית שמופיעה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="68dc9-171">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="68dc9-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="68dc9-172">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="68dc9-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="68dc9-173">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="68dc9-174">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="68dc9-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="68dc9-175">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="68dc9-175">Next Step</span></span>

<span data-ttu-id="68dc9-176">הגדר [פעילויות](activities.md), [העשרה](enrichment-hub.md), או [קשרים](relationships.md) לקבלת תובנות נוספות על הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="68dc9-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="68dc9-177">אם כבר הגדרת פעילויות, העשרה או פלחים, יתבצע עיבוד שלהם באופן אוטומטי כדי להשתמש בנתוני הלקוחות העדכניים ביותר.</span><span class="sxs-lookup"><span data-stu-id="68dc9-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
