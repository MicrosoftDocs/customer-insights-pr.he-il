---
title: יצירה וניהול של פלחים
description: צור פלחי לקוחות כדי לקבץ אותם על סמך תכונות שונות.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405916"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="19811-103">יצירה וניהול של פלחים</span><span class="sxs-lookup"><span data-stu-id="19811-103">Create and manage segments</span></span>

<span data-ttu-id="19811-104">פלחי לקוחות מאפשרים לך לקבץ את הלקוחות שלך על סמך מאפיינים דמוגרפיים, עסקיים או תכונות התנהגותיות.</span><span class="sxs-lookup"><span data-stu-id="19811-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="19811-105">אתה יכול להשתמש בפלחים כדי למקד לקמפיינים לקידום מכירות, פעילויות מכירות ופעולות לתמיכה בלקוחות כדי להשיג את היעדים העסקיים שלך.</span><span class="sxs-lookup"><span data-stu-id="19811-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="19811-106">אתה יכול להגדיר מסננים מורכבים סביב ישות פרופיל הלקוח והישויות הקשורות אליו.</span><span class="sxs-lookup"><span data-stu-id="19811-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="19811-107">כל פלח, לאחר העיבוד, יוצר קבוצה של רשומות לקוחות שתוכל לייצא ולבצע עליה פעולה.</span><span class="sxs-lookup"><span data-stu-id="19811-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="19811-108">[מגבלות שירות](service-limits.md) מסוימות חלות.</span><span class="sxs-lookup"><span data-stu-id="19811-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="19811-109">אלא אם צוין אחרת, כל פלחי הלקוחות הם **פלחים דינאמיים**, שמתבצע בהם רענון לפי לוח זמנים חוזר.</span><span class="sxs-lookup"><span data-stu-id="19811-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="19811-110">הדוגמה הבאה מדגימה את השימוש ביכולת הפילוח.</span><span class="sxs-lookup"><span data-stu-id="19811-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="19811-111">הגדרנו פלח עבור לקוחות שהזמינו סחורות בשווי של 500 דולר לפחות ב- 90 הימים האחרונים *וכן* היו מעורבים בשיחת שירות לקוחות שהוסלמה.</span><span class="sxs-lookup"><span data-stu-id="19811-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19811-112">![קבוצות מרובות](media/segmentation-group1-2.png "קבוצות מרובות")</span><span class="sxs-lookup"><span data-stu-id="19811-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="19811-113">צור פלח חדש</span><span class="sxs-lookup"><span data-stu-id="19811-113">Create a new segment</span></span>

<span data-ttu-id="19811-114">פלחים מנוהלים בדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="19811-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="19811-115">ב- Audience Insights, עבור לדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="19811-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="19811-116">בחר **חדש** > **פלח ריק**.</span><span class="sxs-lookup"><span data-stu-id="19811-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="19811-117">בלוח **פלח חדש**, בחר סוג פלח והזן **שם**.</span><span class="sxs-lookup"><span data-stu-id="19811-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="19811-118">לחלופין, ספק שם תצוגה ותיאור המסייע בזיהוי הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="19811-119">בחר **הבא** כדי לעבור אל הדף **בונה הפלחים** שבו ניתן להגדיר קבוצה.</span><span class="sxs-lookup"><span data-stu-id="19811-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="19811-120">קבוצה היא קבוצה של לקוחות.</span><span class="sxs-lookup"><span data-stu-id="19811-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="19811-121">בחר את הישות שכוללת את התכונה שלפיה ברצונך לבצע את הפילוח.</span><span class="sxs-lookup"><span data-stu-id="19811-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="19811-122">בחר את התכונה שלפיה יש לפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="19811-123">תכונה זו יכולה להיות בעלת אחד מארבעה סוגי ערכים: מספרי, מחרוזת, תאריך או בוליאני.</span><span class="sxs-lookup"><span data-stu-id="19811-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="19811-124">בחר אופרטור וערך עבור התכונה שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="19811-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19811-125">![התאם אישית מסנן קבוצה](media/customer-group-numbers.png "מסנן קבוצה מותאם אישית")</span><span class="sxs-lookup"><span data-stu-id="19811-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="19811-126">מספר</span><span class="sxs-lookup"><span data-stu-id="19811-126">Number</span></span> |<span data-ttu-id="19811-127">הגדרה</span><span class="sxs-lookup"><span data-stu-id="19811-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="19811-128">1</span><span class="sxs-lookup"><span data-stu-id="19811-128">1</span></span>     |<span data-ttu-id="19811-129">Entity</span><span class="sxs-lookup"><span data-stu-id="19811-129">Entity</span></span>          |
   |<span data-ttu-id="19811-130">2</span><span class="sxs-lookup"><span data-stu-id="19811-130">2</span></span>     |<span data-ttu-id="19811-131">תכונה</span><span class="sxs-lookup"><span data-stu-id="19811-131">Attribute</span></span>          |
   |<span data-ttu-id="19811-132">3</span><span class="sxs-lookup"><span data-stu-id="19811-132">3</span></span>    |<span data-ttu-id="19811-133">אופרטור</span><span class="sxs-lookup"><span data-stu-id="19811-133">Operator</span></span>         |
   |<span data-ttu-id="19811-134">4</span><span class="sxs-lookup"><span data-stu-id="19811-134">4</span></span>    |<span data-ttu-id="19811-135">ערך</span><span class="sxs-lookup"><span data-stu-id="19811-135">Value</span></span>         |

8. <span data-ttu-id="19811-136">אם הישות מחוברת לישות הלקוח המאוחד דרך [קשרים](relationships.md), עליך להגדיר את נתיב הקשר ליצירת פלח חוקי.</span><span class="sxs-lookup"><span data-stu-id="19811-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="19811-137">הוסף את הישויות מנתיב הקשר עד שתוכל לבחור את הישות **לקוח: CustomerInsights** מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="19811-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="19811-138">לאחר מכן, בחר **כל הרשומות** עבור כל תנאי.</span><span class="sxs-lookup"><span data-stu-id="19811-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19811-139">![נתיב קשר במהלך יצירת פלח](media/segments-multiple-relationships.png "נתיב קשר במהלך יצירת פלח")</span><span class="sxs-lookup"><span data-stu-id="19811-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="19811-140">בחר **שמור** כדי לשמור את הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="19811-141">הפלח יישמר ויעובד אם כל הדרישות תקפות.</span><span class="sxs-lookup"><span data-stu-id="19811-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="19811-142">אחרת, הוא יישמר כטיוטה.</span><span class="sxs-lookup"><span data-stu-id="19811-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="19811-143">בחר **חזרה לפלחים** כדי לחזור אל דף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="19811-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="19811-144">ניהול פלחים קיימים</span><span class="sxs-lookup"><span data-stu-id="19811-144">Manage existing segments</span></span>

<span data-ttu-id="19811-145">בדף **פלחים**, תוכל להציג את כל הפלחים השמורים ולנהל אותם.</span><span class="sxs-lookup"><span data-stu-id="19811-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="19811-146">כל פלח מיוצג על ידי שורה הכוללת מידע נוסף על הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="19811-147">ניתן למיין את הפלחים בעמודה על-ידי בחירת כותרת העמודה.</span><span class="sxs-lookup"><span data-stu-id="19811-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="19811-148">השתמש בתיבה **חיפוש** בפינה השמאלית העליונה כדי לסנן את הפלחים.</span><span class="sxs-lookup"><span data-stu-id="19811-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19811-149">![אפשרויות לניהול פלח קיים](media/segments-selected-segment.png "אפשרויות לניהול פלח קיים")</span><span class="sxs-lookup"><span data-stu-id="19811-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="19811-150">הפעולה הבאה זמינה כשבוחרים פלח:</span><span class="sxs-lookup"><span data-stu-id="19811-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="19811-151">**הצג** את פרטי הפלח, לרבות מגמת ספירת חברים כדי להציג את החברים בפלח בתצוגה מקדימה.</span><span class="sxs-lookup"><span data-stu-id="19811-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="19811-152">**ערוך** את הפלח כדי לשנות את המאפיינים שלו.</span><span class="sxs-lookup"><span data-stu-id="19811-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="19811-153">**רענן** את הפלח כדי לכלול את הנתונים העדכניים ביותר.</span><span class="sxs-lookup"><span data-stu-id="19811-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="19811-154">**הפעל** או **השבת** את הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="19811-155">לפלחים יש שני מצבים אפשריים - פעיל או לא פעיל.</span><span class="sxs-lookup"><span data-stu-id="19811-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="19811-156">מצבים אלה שימושיים בעת עריכת פלח.</span><span class="sxs-lookup"><span data-stu-id="19811-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="19811-157">עבור פלחים לא פעילים, הגדרת הפלח קיימת, אך היא עדיין לא מכילה לקוחות.</span><span class="sxs-lookup"><span data-stu-id="19811-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="19811-158">כשאתה מפעיל פלח, המצב שלו משתנה מ'לא פעיל' ל'פעיל' והוא מתחיל לחפש לקוחות שתואמים להגדרת הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="19811-159">אם מוגדר [רענון מתוזמן](system.md#schedule-tab), ה **מצב** של פלחים לא פעילים רשום כ **המערכת דילגה** מה שמצביע על כך שלא היה אפילו ניסיון לבצע רענון.</span><span class="sxs-lookup"><span data-stu-id="19811-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="19811-160">כאשר פלח לא פעיל מופעל, הוא יתרענן וייכלל בריענונים מתוזמנים.</span><span class="sxs-lookup"><span data-stu-id="19811-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="19811-161">לחלופין, אתה יכול להשתמש בפונקציונליות **תזמן אחר כך** בתפריט הנפתח **הפעל/השבת** כדי לציין תאריך ושעה עתידיים להפעלה ולביטול של פלח מסוים.</span><span class="sxs-lookup"><span data-stu-id="19811-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="19811-162">**שנה את שם** הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-162">**Rename** the segment.</span></span>
- <span data-ttu-id="19811-163">**הורד** את רשימת החברים כקובץ ‎.CSV</span><span class="sxs-lookup"><span data-stu-id="19811-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="19811-164">האפשרות **הוסף ל:** שולחת את רשימת מזהי הלקוחות שבפלח לעיבוד ביישום אחר.</span><span class="sxs-lookup"><span data-stu-id="19811-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="19811-165">**מחק** את הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="19811-166">רענון פלחים</span><span class="sxs-lookup"><span data-stu-id="19811-166">Refresh segments</span></span>

<span data-ttu-id="19811-167">ניתן לרענן את כל הפלחים בבת אחת על ידי בחירה באפשרות **רענן הכל** בדף **פלחים** או לרענן פלח אחד או מספר פלחים על ידי בחירתם ובחירה באפשרות **רענן**.</span><span class="sxs-lookup"><span data-stu-id="19811-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="19811-168">לחלופין, באפשרותך להגדיר רענון חוזר דרך **מנהל** > **מערכת** > **לוח זמנים**.</span><span class="sxs-lookup"><span data-stu-id="19811-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="19811-169">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="19811-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="19811-170">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="19811-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="19811-171">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="19811-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="19811-172">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="19811-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="19811-173">הורדה וייצוא של פלחים</span><span class="sxs-lookup"><span data-stu-id="19811-173">Download and export segments</span></span>

<span data-ttu-id="19811-174">באפשרותך להוריד את הפלחים שלך לקובץ CSV או לייצא אותם אל Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="19811-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="19811-175">הורדת פלחים לקובץ CSV</span><span class="sxs-lookup"><span data-stu-id="19811-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="19811-176">ב- Audience Insights, עבור לדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="19811-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="19811-177">בחר את שלוש הנקודות באריח של פלח ספציפי.</span><span class="sxs-lookup"><span data-stu-id="19811-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="19811-178">בחר **הורד כ- CSV** מהרשימה הנפתחת של הפעולות.</span><span class="sxs-lookup"><span data-stu-id="19811-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="19811-179">ייצוא פלחים אל Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="19811-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="19811-180">לפני ייצוא הפלחים אל Dynamics 365 Sales, מנהל מערכת צריך [ליצור את יעד הייצוא](export-destinations.md) עבור Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="19811-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="19811-181">ב- Audience Insights, עבור לדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="19811-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="19811-182">בחר את שלוש הנקודות באריח של פלח ספציפי.</span><span class="sxs-lookup"><span data-stu-id="19811-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="19811-183">בחר **הוסף ל** מהרשימה הנפתחת של הפעולות ובחר את יעד הייצוא שברצונך לשלוח אליו את הנתונים.</span><span class="sxs-lookup"><span data-stu-id="19811-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="19811-184">מצב טיוטה לפלחים</span><span class="sxs-lookup"><span data-stu-id="19811-184">Draft mode for segments</span></span>

<span data-ttu-id="19811-185">אם לא מתקיימות כל הדרישות לעיבוד פלח, תוכל לשמור את הפלח כטיוטה ולגשת אליו מהדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="19811-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="19811-186">הוא יישמר כפלח לא פעיל, ולא תוכל להפעיל אותו עד שלא יהיה תקף.</span><span class="sxs-lookup"><span data-stu-id="19811-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="19811-187">הוסף עוד תנאים לקבוצה</span><span class="sxs-lookup"><span data-stu-id="19811-187">Add more conditions to a group</span></span>

<span data-ttu-id="19811-188">כדי להוסיף תנאים לקבוצה, אתה יכול להשתמש בשני אופרטורים לוגיים:</span><span class="sxs-lookup"><span data-stu-id="19811-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="19811-189">אופרטור **AND**: יש לעמוד בשני התנאים כחלק מתהליך הפילוח.</span><span class="sxs-lookup"><span data-stu-id="19811-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="19811-190">אפשרות זו שימושית ביותר כאשר אתה מגדיר תנאים בין ישויות שונות.</span><span class="sxs-lookup"><span data-stu-id="19811-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="19811-191">אופרטור **OR**: צריך להתקיים אחד מהתנאים כחלק מתהליך הפילוח.</span><span class="sxs-lookup"><span data-stu-id="19811-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="19811-192">אפשרות זו שימושית ביותר כאשר אתה מגדיר מספר תנאים לאותה ישות.</span><span class="sxs-lookup"><span data-stu-id="19811-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19811-193">![האופרטור OR כאשר צריך לעמוד באחד מהתנאים](media/segmentation-either-condition.png "האופרטור OR כאשר צריך לעמוד באחד מהתנאים")</span><span class="sxs-lookup"><span data-stu-id="19811-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="19811-194">כרגע ניתן לקנן את האופרטור **OR** תחת **AND**, אך לא להפך.</span><span class="sxs-lookup"><span data-stu-id="19811-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="19811-195">שלב קבוצות מרובות</span><span class="sxs-lookup"><span data-stu-id="19811-195">Combine multiple groups</span></span>

<span data-ttu-id="19811-196">כל קבוצה מייצרת קבוצה מסוימת של לקוחות.</span><span class="sxs-lookup"><span data-stu-id="19811-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="19811-197">באפשרותך לשלב קבוצות אלה כדי לכלול את הלקוחות הדרושים לאירוע העסקי שלך.</span><span class="sxs-lookup"><span data-stu-id="19811-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="19811-198">ב- Audience Insights, עבור לדף **פלחים** ובחר פלח.</span><span class="sxs-lookup"><span data-stu-id="19811-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="19811-199">בחר **הוסף קבוצה**.</span><span class="sxs-lookup"><span data-stu-id="19811-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19811-200">![הוסף קבוצת לקוחות](media/customer-group-add-group.png "הוסף קבוצת לקוחות")</span><span class="sxs-lookup"><span data-stu-id="19811-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="19811-201">בחר באחד מהאופרטורים המוגדרים הבאים: **איחוד**, **הצלבה**, או **למעט**.</span><span class="sxs-lookup"><span data-stu-id="19811-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="19811-202">![קבוצת לקוחות הוסף איחוד](media/customer-group-union.png "קבוצת לקוחות הוסף איחוד")</span><span class="sxs-lookup"><span data-stu-id="19811-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="19811-203">בחר אופרטור של קבוצה כדי להגדיר קבוצה חדשה.</span><span class="sxs-lookup"><span data-stu-id="19811-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="19811-204">שמור קבוצות שונות כדי לקבוע אילו נתונים נשמרים:</span><span class="sxs-lookup"><span data-stu-id="19811-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="19811-205">**איחוד** מאחד בין שתי הקבוצות.</span><span class="sxs-lookup"><span data-stu-id="19811-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="19811-206">**חיתוך** חופף בין שתי הקבוצות.</span><span class="sxs-lookup"><span data-stu-id="19811-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="19811-207">רק נתונים שהם *משותפים* לשתי הקבוצות נשמרים בקבוצה המאוחדת.</span><span class="sxs-lookup"><span data-stu-id="19811-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="19811-208">**למעט** משלב בין שתי הקבוצות.</span><span class="sxs-lookup"><span data-stu-id="19811-208">**Except** combines the two groups.</span></span> <span data-ttu-id="19811-209">רק נתונים בקבוצה A שהם *אינם משותפים* לנתונים בקבוצה B נשמרים.</span><span class="sxs-lookup"><span data-stu-id="19811-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="19811-210">ראה את היסטוריית העיבוד וחברי הפלחים</span><span class="sxs-lookup"><span data-stu-id="19811-210">View processing history and segment members</span></span>

<span data-ttu-id="19811-211">אתה יכול לראות נתונים מאוחדים על פלח על ידי סקירת הפרטים שלו.</span><span class="sxs-lookup"><span data-stu-id="19811-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="19811-212">בדף **פלחים**, בחר את הפלח שברצונך לבדוק.</span><span class="sxs-lookup"><span data-stu-id="19811-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="19811-213">החלק העליון של הדף כולל גרף מגמה המדמה שינויים בספירת החברים.</span><span class="sxs-lookup"><span data-stu-id="19811-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="19811-214">רחף מעל נקודות הנתונים כדי לראות את ספירת החברים בתאריך ספציפי.</span><span class="sxs-lookup"><span data-stu-id="19811-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="19811-215">אתה יכול לעדכן את מסגרת זמן של התצוגה החזותית.</span><span class="sxs-lookup"><span data-stu-id="19811-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="19811-216">![טווח זמנים של פלח](media/segment-time-range.png "טווח זמנים של פלח")</span><span class="sxs-lookup"><span data-stu-id="19811-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="19811-217">החלק התחתון מכיל רשימה של חברי הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="19811-218">שדות המופיעים ברשימה זו מבוססים על התכונות של ישויות הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="19811-219">הרשימה היא תצוגה מקדימה של חברי הפלח התואמים והיא מציגה את 100 הרשומות הראשונות של הפלח, כך שתוכל להעריך אותו במהירות ולעיין בהגדרות שלו במידת הצורך.</span><span class="sxs-lookup"><span data-stu-id="19811-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="19811-220">כדי לראות את כל הרשומות התואמות, עליך [לייצא את הפלח](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="19811-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="19811-221">פלחים מהירים</span><span class="sxs-lookup"><span data-stu-id="19811-221">Quick segments</span></span>

<span data-ttu-id="19811-222">בנוסף לבונה הפלחים, קיים נתיב אחר ליצירת פלחים.</span><span class="sxs-lookup"><span data-stu-id="19811-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="19811-223">פלחים מהירים מאפשרים לך לבנות פלחים פשוטים עם אופרטור יחיד במהירות ועם תובנות מיידיות.</span><span class="sxs-lookup"><span data-stu-id="19811-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="19811-224">בדף **פלחים**, בחר **חדש** > **צור במהירות מ-**.</span><span class="sxs-lookup"><span data-stu-id="19811-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="19811-225">בחר את האפשרות **פרופילים** כדי לבנות פלח המבוסס על ישות הלקוח המאוחדת.</span><span class="sxs-lookup"><span data-stu-id="19811-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="19811-226">בחר **מדדים** כדי לבנות פלח סביב כל אחד מסוגי המאפיינים של לקוחות שיצרת בעבר בדף **מדדים**.</span><span class="sxs-lookup"><span data-stu-id="19811-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="19811-227">בחר את האפשרות **בינה** כדי לבנות פלח לפי אחת מישויות הפלט שיצרת באמצעות היכולות **חיזויים** או **מודלים מותאמים אישית**.</span><span class="sxs-lookup"><span data-stu-id="19811-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="19811-228">בתיבת הדו-שיח **פלח מהיר חדש**, בחר תכונה מהרשימה הנפתחת **שדה**.</span><span class="sxs-lookup"><span data-stu-id="19811-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="19811-229">המערכת תספק כמה תובנות נוספות שיעזרו לך ליצור פלחים טובים יותר של הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="19811-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="19811-230">בשדות הקטגוריות נציג את 10 הספירות המובילות של לקוחות.</span><span class="sxs-lookup"><span data-stu-id="19811-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="19811-231">בחר **ערך** ובחר **סקירה**.</span><span class="sxs-lookup"><span data-stu-id="19811-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="19811-232">עבור תכונה מספרית, המערכת תציג איזה ערך תכונה נופל באחוזון של כל לקוח.</span><span class="sxs-lookup"><span data-stu-id="19811-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="19811-233">בחר **אופרטור** ו **ערך** ובחר **סקירה**.</span><span class="sxs-lookup"><span data-stu-id="19811-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="19811-234">המערכת תספק לך **גודל פלח משוער**.</span><span class="sxs-lookup"><span data-stu-id="19811-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="19811-235">אתה יכול לבחור אם לייצר את הפלח שהגדרת, או לבדוק אותו תחילה כדי לקבל גודל פלח שונה.</span><span class="sxs-lookup"><span data-stu-id="19811-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="19811-236">![שם ואומדן עבור פלח מהיר](media/quick-segment-name.png "שם ואומדן עבור פלח מהיר")</span><span class="sxs-lookup"><span data-stu-id="19811-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="19811-237">תן **שם** לפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="19811-238">או הזן **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="19811-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="19811-239">בחר **שמור** כדי ליצור את הפלח.</span><span class="sxs-lookup"><span data-stu-id="19811-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="19811-240">לאחר סיום העיבוד של הפלח, אתה יכול להציג אותו כמו כל פלח אחר שיצרת.</span><span class="sxs-lookup"><span data-stu-id="19811-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="19811-241">עבור התרחישים הבאים, אנו ממליצים להשתמש בבונה הפלחים ולא ביכולת הפלחים המומלצת:</span><span class="sxs-lookup"><span data-stu-id="19811-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="19811-242">יצירת פלחים עם מסננים בשדות קטגוריים שבהם האופרטור שונה מהאופרטור **הוא**</span><span class="sxs-lookup"><span data-stu-id="19811-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="19811-243">יצירת פלחים עם מסננים בשדות מספריים שבהם האופרטור שונה מהאופרטורים **בין**, **גדול מ-**, או **פחות מ-**</span><span class="sxs-lookup"><span data-stu-id="19811-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="19811-244">יצירת פלחים עם מסננים בשדות סוג תאריך</span><span class="sxs-lookup"><span data-stu-id="19811-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="19811-245">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="19811-245">Next steps</span></span>

<span data-ttu-id="19811-246">[ייצא פלח](export-destinations.md) וחקור את [כרטיס לקוח](customer-card-add-in.md) ו [מחברים](export-power-bi.md) כדי לקבל תובנות ברמת הלקוח.</span><span class="sxs-lookup"><span data-stu-id="19811-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>
