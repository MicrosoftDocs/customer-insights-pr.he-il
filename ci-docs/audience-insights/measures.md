---
title: יצירה ועריכה של מדידות
description: הגדר מדדים הקשורים ללקוח לצורך ניתוח והצגת הביצועים של תחומים עסקיים מסוימים.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405907"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="06bf6-103">הגדרה וניהול של מדדים</span><span class="sxs-lookup"><span data-stu-id="06bf6-103">Define and manage measures</span></span>

<span data-ttu-id="06bf6-104">**מדדים** מייצגים מחווני ביצועים מפתח (KPI) המשקפים את הביצועים והתקינות של נושאים עסקיים ספציפיים.</span><span class="sxs-lookup"><span data-stu-id="06bf6-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="06bf6-105">Audience Insights מספק חוויה אינטואיטיבית לבניית סוגים שונים של מדידות, באמצעות בונה שאילתות שאינו דורש ממך לקודד או לאמת את המדידות שלך באופן ידני.</span><span class="sxs-lookup"><span data-stu-id="06bf6-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="06bf6-106">אתה יכול לעקוב אחר המדדים העסקיים בדף **הבית**, לראות מדדים עבור לקוחות ספציפיים ב- **כרטיס לקוח**, ולהשתמש במדדים כדי להגדיר פלחי לקוחות בדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="06bf6-107">יצירת מדד</span><span class="sxs-lookup"><span data-stu-id="06bf6-107">Create a measure</span></span>

<span data-ttu-id="06bf6-108">מקטע זה מנחה אותך ביצירת מדד מההתחלה.</span><span class="sxs-lookup"><span data-stu-id="06bf6-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="06bf6-109">אתה יכול לבנות מדדים עם נתונים ממקורות נתונים מרובים המחוברים דרך ישות הלקוח.</span><span class="sxs-lookup"><span data-stu-id="06bf6-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="06bf6-110">[מגבלות שירות](service-limits.md) מסוימות חלות.</span><span class="sxs-lookup"><span data-stu-id="06bf6-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="06bf6-111">ב- audience insights, עבור אל **מדידות**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="06bf6-112">בחר **מדד חדש**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-112">Select **New measure**.</span></span>

3. <span data-ttu-id="06bf6-113">בחר את המדד **סוג**:</span><span class="sxs-lookup"><span data-stu-id="06bf6-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="06bf6-114">**תכונת לקוח**: שדה בודד לכל לקוח המשקף ציון, ערך או מצב עבור הלקוח.</span><span class="sxs-lookup"><span data-stu-id="06bf6-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="06bf6-115">תכונות לקוח נוצרות כתכונות ביישות חדשה שנוצרת על ידי המערכת ונקראת **מדד לקוח**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="06bf6-116">**מדד לקוח**: תובנות על התנהגות לקוחות עם פירוט לפי מדדים שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="06bf6-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="06bf6-117">נוצרת ישות חדשה עבור כל מדד, שיכולה לכלול מספר רשומות לכל לקוח.</span><span class="sxs-lookup"><span data-stu-id="06bf6-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="06bf6-118">**מדד עסקי**: מעקב אחר הביצועים העסקיים ותקינות העסק שלך.</span><span class="sxs-lookup"><span data-stu-id="06bf6-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="06bf6-119">למדדים עסקיים יכולים להיות שני פלטים שונים: פלט מספרי המוצג בדף **הבית** או ישות חדשה שתמצא בדף **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="06bf6-120">ספק **שם** ו **שם תצוגה** אופציונלי ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="06bf6-121">במקטע **ישויות**, בחר את הישות הראשונה מתוך הרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="06bf6-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="06bf6-122">בשלב זה עליך להחליט אם יש צורך בישויות נוספות כחלק מהגדרת המדד שלך.</span><span class="sxs-lookup"><span data-stu-id="06bf6-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="06bf6-123">![הגדרת מדידה](media/measure-definition.png "הגדרת מדידה")</span><span class="sxs-lookup"><span data-stu-id="06bf6-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="06bf6-124">להוספת ישויות נוספות, בחר **הוסף ישות** ובחר ישויות שבהן תרצה להשתמש למדד.</span><span class="sxs-lookup"><span data-stu-id="06bf6-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="06bf6-125">תוכל לבחור רק ישויות שיש להן קשר לישות ההתחלתית שלך.</span><span class="sxs-lookup"><span data-stu-id="06bf6-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="06bf6-126">לקבלת מידע נוסף על הגדרת קשרים, ראה [קשרי גומלין](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="06bf6-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="06bf6-127">לחלופין, באפשרותך להגדיר משתנים.</span><span class="sxs-lookup"><span data-stu-id="06bf6-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="06bf6-128">במקטע **משתנים**, בחר **משתנה חדש**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="06bf6-129">משתנים הם חישובים הנעשים בכל אחת מהרשומות שבחרת.</span><span class="sxs-lookup"><span data-stu-id="06bf6-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="06bf6-130">לדוגמה, סיכום נקודת מכירה (POS) ומכירות מקוונות עבור כל הרשומות של הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="06bf6-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="06bf6-131">הזן **שם** עבור המשתנה.</span><span class="sxs-lookup"><span data-stu-id="06bf6-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="06bf6-132">באזור **ביטוי**, בחר שדה שאיתו תתחיל את החישוב.</span><span class="sxs-lookup"><span data-stu-id="06bf6-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="06bf6-133">הקלד ביטוי באזור **ביטוי** תוך בחירת שדות נוספים שייכללו בחישוב שלך.</span><span class="sxs-lookup"><span data-stu-id="06bf6-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="06bf6-134">נכון לעכשיו, רק ביטויים חשבוניים נתמכים.</span><span class="sxs-lookup"><span data-stu-id="06bf6-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="06bf6-135">בנוסף, חישוב משתנים אינו נתמך עבור ישויות של [נתיבי ישות](relationships.md) שונים.</span><span class="sxs-lookup"><span data-stu-id="06bf6-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="06bf6-136">בחר **סיום**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-136">Select **Done**.</span></span>

11. <span data-ttu-id="06bf6-137">במקטע **הגדרת מדד** תגדיר כיצד היישויות והמשתנים המחושבים שבחרת מצטברים בישות או בתכונה חדשה למדידה.</span><span class="sxs-lookup"><span data-stu-id="06bf6-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="06bf6-138">בחר **ממד חדש**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-138">Select **New dimension**.</span></span> <span data-ttu-id="06bf6-139">אתה יכול לחשוב על ממד כעל פונקציה *קיבוץ לפי*.</span><span class="sxs-lookup"><span data-stu-id="06bf6-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="06bf6-140">פלט הנתונים של ישות המדידה או התכונה יקובץ לפי כל הממדים שהוגדרו.</span><span class="sxs-lookup"><span data-stu-id="06bf6-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="06bf6-141">![בחר מחזור מצטבר](media/measures-businessreport-measure-definition2.png "בחר מחזור מצטבר")</span><span class="sxs-lookup"><span data-stu-id="06bf6-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="06bf6-142">בחר או הזן את המידע הבא כחלק מהגדרת הממד שלך:</span><span class="sxs-lookup"><span data-stu-id="06bf6-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="06bf6-143">**ישות** : אם תגדיר ישות מדד, עליה לכלול תכונה אחת לפחות.</span><span class="sxs-lookup"><span data-stu-id="06bf6-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="06bf6-144">אם תגדיר תכונה של מדד, היא תכלול כברירת מחדל תכונה אחת בלבד.</span><span class="sxs-lookup"><span data-stu-id="06bf6-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="06bf6-145">בחירה זו נוגעת לבחירת הישות שכוללת תכונה זו.</span><span class="sxs-lookup"><span data-stu-id="06bf6-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="06bf6-146">**שדה**: בחר בתכונה הספציפית שתיכלל בישות או בתכונת המדידה.</span><span class="sxs-lookup"><span data-stu-id="06bf6-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="06bf6-147">**מיכל**: בחר אם ברצונך לצבור נתונים על בסיס יומי, חודשי או שנתי.</span><span class="sxs-lookup"><span data-stu-id="06bf6-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="06bf6-148">זוהי בחירה נדרשת רק אם בחרת תכונה מסוג 'תאריך'.</span><span class="sxs-lookup"><span data-stu-id="06bf6-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="06bf6-149">**בתור**: מגדיר את שם השדה החדש.</span><span class="sxs-lookup"><span data-stu-id="06bf6-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="06bf6-150">**שם תצוגה**: מגדיר את שם השדה לתצוגה.</span><span class="sxs-lookup"><span data-stu-id="06bf6-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="06bf6-151">המדד העסקי שלך יישמר כישות בעלת מספר בודד ויופיע בדף **בית**, אלא אם תוסיף ממדים נוספים למדד שלך.</span><span class="sxs-lookup"><span data-stu-id="06bf6-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="06bf6-152">לאחר הוספת ממדים נוספים, המדד *לא* יופיע בדף **בית**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="06bf6-153">לחלופין, הוסף פונקציות צבירה.</span><span class="sxs-lookup"><span data-stu-id="06bf6-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="06bf6-154">כל צבירה שתיצור מביאה לערך חדש בתוך הישות או תכונת המדידה.</span><span class="sxs-lookup"><span data-stu-id="06bf6-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="06bf6-155">פונקציות צבירה נתמכות הן: **מינימום**, **מקסימום**, **ממוצע**, **חציון**, **סכום**, **ספירת ערכים ייחודיים**, **ראשון** (לוקח את הרשומה הראשונה של ערך ממד), ו- **אחרון** (לוקח את הרשומה האחרונה שנוספה לערך ממד).</span><span class="sxs-lookup"><span data-stu-id="06bf6-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="06bf6-156">בחר **שמור** כדי לשמור את השינויים במדד.</span><span class="sxs-lookup"><span data-stu-id="06bf6-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="06bf6-157">נהל את המדדים שלך</span><span class="sxs-lookup"><span data-stu-id="06bf6-157">Manage your measures</span></span>

<span data-ttu-id="06bf6-158">לאחר יצירת מדידה אחת לפחות, תראה רשימת מדידות בדף **מדידות**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="06bf6-159">תמצא מידע על סוג המדידה, היוצר, תאריך ושעת היצירה, תאריך ושעה של העריכה האחרונה, סטטוס (אם המדד פעיל, לא פעיל או נכשל) ותאריך ושעה של הרענון האחרון.</span><span class="sxs-lookup"><span data-stu-id="06bf6-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="06bf6-160">כשאתה בוחר מדד מהרשימה, באפשרותך לראות תצוגה מקדימה של הפלט שלו.</span><span class="sxs-lookup"><span data-stu-id="06bf6-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="06bf6-161">כדי לרענן את כל המדדים שלך בו-זמנית, בחר **רענן הכל** מבלי לבחור מדד ספציפי.</span><span class="sxs-lookup"><span data-stu-id="06bf6-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06bf6-162">![פעולות לניהול מדדים יחידים](media/measure-actions.png "פעולות לניהול מדדים יחידים")</span><span class="sxs-lookup"><span data-stu-id="06bf6-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="06bf6-163">לחלופין, בחר מדד מהרשימה ובצע אחת מהפעולות הבאות:</span><span class="sxs-lookup"><span data-stu-id="06bf6-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="06bf6-164">בחר את שם המדד כדי לראות את הפרטים שלו.</span><span class="sxs-lookup"><span data-stu-id="06bf6-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="06bf6-165">**ערוך** את קביעת התצורה של המדד.</span><span class="sxs-lookup"><span data-stu-id="06bf6-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="06bf6-166">**שנה שם** של המדד.</span><span class="sxs-lookup"><span data-stu-id="06bf6-166">**Rename** the measure.</span></span>
- <span data-ttu-id="06bf6-167">**מחק** את המדד.</span><span class="sxs-lookup"><span data-stu-id="06bf6-167">**Delete** the measure.</span></span>
- <span data-ttu-id="06bf6-168">בחר את שלוש הנקודות (...) ולאחר מכן **רענן** כדי להפעיל את תהליך הרענון עבור המדד.</span><span class="sxs-lookup"><span data-stu-id="06bf6-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="06bf6-169">בחר את שלוש הנקודות (...) ולאחר מכן **הורד** כדי לקבל קובץ ‎.CSV של המדד.</span><span class="sxs-lookup"><span data-stu-id="06bf6-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="06bf6-170">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="06bf6-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="06bf6-171">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="06bf6-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="06bf6-172">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="06bf6-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="06bf6-173">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="06bf6-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="06bf6-174">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="06bf6-174">Next step</span></span>

<span data-ttu-id="06bf6-175">ניתן להשתמש במדדים קיימים כדי ליצור את פלח הלקוחות הראשון שלך בדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="06bf6-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="06bf6-176">לקבלת מידע נוסף, ראה [פלחים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="06bf6-176">For more information, see [Segments](segments.md).</span></span>
