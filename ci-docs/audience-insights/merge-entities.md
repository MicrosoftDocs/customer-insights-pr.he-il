---
title: מיזוג ישויות באיחוד נתונים
description: מזג ישויות ליצירת פרופילי לקוח מאוחדים.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597834"
---
# <a name="merge-entities"></a><span data-ttu-id="5bd9e-103">מיזוג ישויות</span><span class="sxs-lookup"><span data-stu-id="5bd9e-103">Merge entities</span></span>

<span data-ttu-id="5bd9e-104">שלב המיזוג הוא השלב האחרון בתהליך איחוד נתונים.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="5bd9e-105">מטרתו ליישב נתונים סותרים.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="5bd9e-106">דוגמאות לנתונים סותרים יכולות לכלול שם לקוח שנמצא בשני מערכי הנתונים שלך אך מופיע מעט אחרת בכל אחת מהן ("גרנט מארשל" לעומת "גרנט מרשל"), או מספר טלפון ששונה מבחינת הפורמט (617-803-091X לעומת 617803091X).</span><span class="sxs-lookup"><span data-stu-id="5bd9e-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="5bd9e-107">מיזוג של נקודות הנתונים הסותרות מתבצע על בסיס תכונה-לתכונה.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="5bd9e-108">לאחר השלמת [שלב ההתאמה](match-entities.md), תתחיל את שלב המיזוג על-ידי בחירה באריח **מיזוג** בדף **איחוד**.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="5bd9e-109">סקור המלצות מערכת</span><span class="sxs-lookup"><span data-stu-id="5bd9e-109">Review system recommendations</span></span>

<span data-ttu-id="5bd9e-110">בדף **מיזוג**, בחר וכלול תכונות שימוזגו בתוך ישות פרופיל הלקוח המאוחד שלך (התוצאה של תהליך התצורה).</span><span class="sxs-lookup"><span data-stu-id="5bd9e-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="5bd9e-111">חלק מהתכונות ממוזגות באופן אוטומטי על ידי המערכת.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="5bd9e-112">הצג תכונות ממוזגות</span><span class="sxs-lookup"><span data-stu-id="5bd9e-112">View merged attributes</span></span>

<span data-ttu-id="5bd9e-113">לצפייה בתכונות הכלולות באחת מהתכונות הממוזגות באופן אוטומטי, בחר בתכונה הממוזגת הזו.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="5bd9e-114">שתי התכונות המרכיבות את התכונה הממוזגת מוצגות בשתי שורות חדשות מתחת לתכונה הממוזגת.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5bd9e-115">![בחר תכונה ממוזגת](media/configure-data-merge-profile-attributes.png "בחר תכונה ממוזגת")</span><span class="sxs-lookup"><span data-stu-id="5bd9e-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="5bd9e-116">הפרד תכונות ממוזגות</span><span class="sxs-lookup"><span data-stu-id="5bd9e-116">Separate merged attributes</span></span>

<span data-ttu-id="5bd9e-117">כדי להפריד או לבטל מיזוג של אחת מהתכונות הממוזגות אוטומטית, מצא את התכונה בטבלה **תכונות פרופיל**.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="5bd9e-118">בחר בלחצן שלוש הנקודות (...).</span><span class="sxs-lookup"><span data-stu-id="5bd9e-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="5bd9e-119">ברשימה הנפתחת, בחר **הפרד שדות**.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="5bd9e-120">הסר תכונות ממוזגות</span><span class="sxs-lookup"><span data-stu-id="5bd9e-120">Remove merged attributes</span></span>

<span data-ttu-id="5bd9e-121">כדי לא לכלול תכונה מהישות הסופית של פרופיל הלקוח, מצא אותה בטבלה **תכונות פרופיל**.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="5bd9e-122">בחר בלחצן שלוש הנקודות (...).</span><span class="sxs-lookup"><span data-stu-id="5bd9e-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="5bd9e-123">ברשימה הנפתחת, בחר **ללא מיזוג**.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="5bd9e-124">התכונה מועברת אל המקטע **הוסר מרשומת הלקוח**.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="5bd9e-125">הוסף ידנית תכונה ממוזגת</span><span class="sxs-lookup"><span data-stu-id="5bd9e-125">Manually add a merged attribute</span></span>

<span data-ttu-id="5bd9e-126">כדי להוסיף תכונה ממוזגת, עבור אל הדף **מיזוג**.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="5bd9e-127">בחר **הוסף תכונה ממוזגת**.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="5bd9e-128">ספק **שם** כדי לזהות אותה בדף **מיזוג** אחר כך.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="5bd9e-129">לחלופין, ספק **שם תצוגה** שיופיע ביישות פרופיל הלקוח המאוחדת.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="5bd9e-130">הגדר את **בחר תכונות כפולות** כדי לבחור את התכונות שברצונך למזג מהישויות התואמות.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="5bd9e-131">אתה יכול גם לחפש תכונות.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="5bd9e-132">הגדר את **דרג לפי חשיבות** כדי להעדיף תכונה אחת על פני האחרות.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="5bd9e-133">לדוגמה, אם הישות *WebAccountCSV* כוללת את הנתונים המדויקים ביותר של התכונה *שמות מלאים*, תוכל להעדיף ישות זו על פני *ContactCSV* על ידי בחירה באפשרות *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="5bd9e-134">כתוצאה מכך, *WebAccountCSV* עוברת לעדיפות ראשונה, ואילו *ContactCSV* עוברת לעדיפות שנייה בעת משיכת ערכים עבור התכונה *שם מלא*.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="5bd9e-135">הרץ את המיזוג שלך</span><span class="sxs-lookup"><span data-stu-id="5bd9e-135">Run your merge</span></span>

<span data-ttu-id="5bd9e-136">בין אם אתה ממזג ידנית תכונות או מאפשר למערכת למזג אותן, אתה תמיד יכול להריץ את המיזוג.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="5bd9e-137">בחר **הפעל** בדף **מיזוג** כדי להתחיל בתהליך.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5bd9e-138">![שמור והפעל מיזוג נתונים](media/configure-data-merge-save-run.png "שמור והפעל מיזוג נתונים")</span><span class="sxs-lookup"><span data-stu-id="5bd9e-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="5bd9e-139">כדי לבצע שינויים נוספים ולהפעיל מחדש את הצעד, באפשרותך לבטל מיזוג מתבצע.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="5bd9e-140">בחר **מרענן...** ובחר **בטל משימה** בחלונית הצדדית שמופיעה.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="5bd9e-141">לאחר שטקסט **מרענן...** משתנה ל **בוצע בהצלחה**, המיזוג הושלם ונפתרו סתירות בנתונים שלך בהתאם למדיניות שהגדרת.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="5bd9e-142">תכונות ממוזגות ולא ממוזגות נכללות בישות הפרופיל המאוחד.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="5bd9e-143">תכונות לא כלולות אינן נכללות בישות הפרופיל המאוחד.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="5bd9e-144">אם זו לא הייתה הפעם הראשונה שבה הפעלת מיזוג בהצלחה, כל התהליכים במורד הזרם, לרבות העשרה, פילוח ומדדים יופעלו מחדש באופן אוטומטי.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="5bd9e-145">לאחר שכל התהליכים במורד הזרם הופעלו מחדש, פרופילי הלקוח ישקפו את כל השינויים שביצעת.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="5bd9e-146">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="5bd9e-147">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="5bd9e-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="5bd9e-148">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="5bd9e-149">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="5bd9e-150">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="5bd9e-150">Next Step</span></span>

<span data-ttu-id="5bd9e-151">הגדר [פעילויות](activities.md), [העשרה](enrichment-microsoft-graph.md), או [קשרים](relationships.md) לקבלת תובנות נוספות על הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="5bd9e-152">אם כבר הגדרת תצורה של פעילויות, העשרה או קשרים, או אם הגדרת פלחים, הם יעובדו באופן אוטומטי כדי להשתמש בנתוני הלקוח העדכניים ביותר.</span><span class="sxs-lookup"><span data-stu-id="5bd9e-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>




[!INCLUDE[footer-include](../includes/footer-banner.md)]