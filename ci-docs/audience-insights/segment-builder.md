---
title: יצירה וניהול של פלחים
description: צור פלחי לקוחות כדי לקבץ אותם על סמך תכונות שונות.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064938"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="f1456-103">יצירה וניהול של פלחים</span><span class="sxs-lookup"><span data-stu-id="f1456-103">Create and manage segments</span></span>

<span data-ttu-id="f1456-104">הגדר מסננים מורכבים סביב ישות הלקוחות המאוחדים והישויות הקשורות אליה.</span><span class="sxs-lookup"><span data-stu-id="f1456-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="f1456-105">כל פלח, לאחר העיבוד, יוצר קבוצה של רשומות לקוחות שתוכל לייצא ולבצע עליה פעולה.</span><span class="sxs-lookup"><span data-stu-id="f1456-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="f1456-106">פלחים מנוהלים בדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="f1456-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="f1456-107">הדוגמה הבאה מדגימה את השימוש ביכולת הפילוח.</span><span class="sxs-lookup"><span data-stu-id="f1456-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="f1456-108">הגדרנו פלח עבור לקוחות שהזמינו סחורות בשווי של 500 דולר לפחות ב- 90 הימים האחרונים *וכן* היו מעורבים בשיחת שירות לקוחות שהוסלמה.</span><span class="sxs-lookup"><span data-stu-id="f1456-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="צילום מסך של ממשק המשתמש לבניית פלחים עם שתי קבוצות שמציינות פלח של לקוחות.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="f1456-110">צור פלח חדש</span><span class="sxs-lookup"><span data-stu-id="f1456-110">Create a new segment</span></span>

<span data-ttu-id="f1456-111">ישנן מספר דרכים ליצור פלח חדש.</span><span class="sxs-lookup"><span data-stu-id="f1456-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="f1456-112">מקטע זה מתאר כיצד ליצור *פלח ריק* מאפס.</span><span class="sxs-lookup"><span data-stu-id="f1456-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="f1456-113">ניתן גם ליצור *פלח מהיר* על סמך הישויות הקיימות או להשתמש במודלים של למידת מכונה כדי להשיג *פלחים מוצעים*.</span><span class="sxs-lookup"><span data-stu-id="f1456-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="f1456-114">למידע נוסף: [מבט כולל על פלחים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f1456-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="f1456-115">בזמן יצירת פלח, ניתן לשמור טיוטה.</span><span class="sxs-lookup"><span data-stu-id="f1456-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="f1456-116">הוא יישמר כפלח לא פעיל ולא ניתן להפעיל אותו אם הוא נגמר בתצורה חוקית.</span><span class="sxs-lookup"><span data-stu-id="f1456-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="f1456-117">עבור לדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="f1456-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="f1456-118">בחר **חדש** > **פלח ריק**.</span><span class="sxs-lookup"><span data-stu-id="f1456-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="f1456-119">בחלונית **פלח חדש**, בחר סוג פלח:</span><span class="sxs-lookup"><span data-stu-id="f1456-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="f1456-120">**פלחים דינאמיים** [רענן](segments.md#refresh-segments) בלוח זמנים חוזר.</span><span class="sxs-lookup"><span data-stu-id="f1456-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="f1456-121">**פלחים סטטיים** הפעל פעם אחת בזמן שאתה יוצר אותם.</span><span class="sxs-lookup"><span data-stu-id="f1456-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="f1456-122">ספק **שם ישות פלט** עבור הפלח.</span><span class="sxs-lookup"><span data-stu-id="f1456-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="f1456-123">לחלופין, ספק שם תצוגה ותיאור המסייע בזיהוי הפלח.</span><span class="sxs-lookup"><span data-stu-id="f1456-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="f1456-124">בחר **הבא** כדי לעבור אל הדף **בונה הפלחים** שבו ניתן להגדיר קבוצה.</span><span class="sxs-lookup"><span data-stu-id="f1456-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="f1456-125">קבוצה היא קבוצה של לקוחות.</span><span class="sxs-lookup"><span data-stu-id="f1456-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="f1456-126">בחר את הישות שכוללת את התכונה שלפיה ברצונך לבצע את הפילוח.</span><span class="sxs-lookup"><span data-stu-id="f1456-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="f1456-127">בחר את התכונה שלפיה יש לפלח.</span><span class="sxs-lookup"><span data-stu-id="f1456-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="f1456-128">תכונה זו יכולה להיות בעלת אחד מארבעה סוגי ערכים: מספרי, מחרוזת, תאריך או בוליאני.</span><span class="sxs-lookup"><span data-stu-id="f1456-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="f1456-129">בחר אופרטור וערך עבור התכונה שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="f1456-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1456-130">![התאם אישית מסנן קבוצה](media/customer-group-numbers.png "מסנן קבוצה מותאם אישית")</span><span class="sxs-lookup"><span data-stu-id="f1456-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="f1456-131">מספר</span><span class="sxs-lookup"><span data-stu-id="f1456-131">Number</span></span> |<span data-ttu-id="f1456-132">הגדרה</span><span class="sxs-lookup"><span data-stu-id="f1456-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="f1456-133">1</span><span class="sxs-lookup"><span data-stu-id="f1456-133">1</span></span>     |<span data-ttu-id="f1456-134">Entity</span><span class="sxs-lookup"><span data-stu-id="f1456-134">Entity</span></span>          |
   |<span data-ttu-id="f1456-135">2</span><span class="sxs-lookup"><span data-stu-id="f1456-135">2</span></span>     |<span data-ttu-id="f1456-136">מאפיין</span><span class="sxs-lookup"><span data-stu-id="f1456-136">Attribute</span></span>          |
   |<span data-ttu-id="f1456-137">3</span><span class="sxs-lookup"><span data-stu-id="f1456-137">3</span></span>    |<span data-ttu-id="f1456-138">אופרטור</span><span class="sxs-lookup"><span data-stu-id="f1456-138">Operator</span></span>         |
   |<span data-ttu-id="f1456-139">4</span><span class="sxs-lookup"><span data-stu-id="f1456-139">4</span></span>    |<span data-ttu-id="f1456-140">ערך</span><span class="sxs-lookup"><span data-stu-id="f1456-140">Value</span></span>         |

   1. <span data-ttu-id="f1456-141">כדי להוסיף תנאים לקבוצה, אתה יכול להשתמש בשני אופרטורים לוגיים:</span><span class="sxs-lookup"><span data-stu-id="f1456-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="f1456-142">אופרטור **AND**: יש לעמוד בשני התנאים כחלק מתהליך הפילוח.</span><span class="sxs-lookup"><span data-stu-id="f1456-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="f1456-143">אפשרות זו שימושית ביותר כאשר אתה מגדיר תנאים בין ישויות שונות.</span><span class="sxs-lookup"><span data-stu-id="f1456-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="f1456-144">אופרטור **OR**: צריך להתקיים אחד מהתנאים כחלק מתהליך הפילוח.</span><span class="sxs-lookup"><span data-stu-id="f1456-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="f1456-145">אפשרות זו שימושית ביותר כאשר אתה מגדיר מספר תנאים לאותה ישות.</span><span class="sxs-lookup"><span data-stu-id="f1456-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f1456-146">![האופרטור OR כאשר צריך לעמוד באחד מהתנאים](media/segmentation-either-condition.png "האופרטור OR כאשר צריך לעמוד באחד מהתנאים")</span><span class="sxs-lookup"><span data-stu-id="f1456-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="f1456-147">כרגע ניתן לקנן את האופרטור **OR** תחת **AND**, אך לא להפך.</span><span class="sxs-lookup"><span data-stu-id="f1456-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="f1456-148">כל קבוצה תואמת לקבוצת לקוחות.</span><span class="sxs-lookup"><span data-stu-id="f1456-148">Each group matches set of customers.</span></span> <span data-ttu-id="f1456-149">ניתן לשלב קבוצות כך שיכללו את הלקוחות הדרושים למקרה העסקי שלך.</span><span class="sxs-lookup"><span data-stu-id="f1456-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="f1456-150">בחר **הוסף קבוצה**.</span><span class="sxs-lookup"><span data-stu-id="f1456-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f1456-151">![הוסף קבוצת לקוחות](media/customer-group-add-group.png "הוסף קבוצת לקוחות")</span><span class="sxs-lookup"><span data-stu-id="f1456-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="f1456-152">בחר אחד מ‏‫אופרטורי ההגדרה: **איחוד**,**הצלבה**, או **מלבד**.</span><span class="sxs-lookup"><span data-stu-id="f1456-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1456-153">![קבוצת לקוחות הוסף איחוד](media/customer-group-union.png "קבוצת לקוחות הוסף איחוד")</span><span class="sxs-lookup"><span data-stu-id="f1456-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="f1456-154">**איחוד** מאחד בין שתי הקבוצות.</span><span class="sxs-lookup"><span data-stu-id="f1456-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="f1456-155">**חיתוך** חופף בין שתי הקבוצות.</span><span class="sxs-lookup"><span data-stu-id="f1456-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="f1456-156">רק נתונים שהם *משותפים* לשתי הקבוצות נשמרים בקבוצה המאוחדת.</span><span class="sxs-lookup"><span data-stu-id="f1456-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="f1456-157">**למעט** משלב בין שתי הקבוצות.</span><span class="sxs-lookup"><span data-stu-id="f1456-157">**Except** combines the two groups.</span></span> <span data-ttu-id="f1456-158">רק נתונים בקבוצה A שהם *אינם משותפים* לנתונים בקבוצה B נשמרים.</span><span class="sxs-lookup"><span data-stu-id="f1456-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="f1456-159">אם הישות מחוברת לישות הלקוח המאוחד דרך [קשרים](relationships.md), עליך להגדיר את נתיב הקשר ליצירת פלח חוקי.</span><span class="sxs-lookup"><span data-stu-id="f1456-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="f1456-160">הוסף את הישויות מנתיב הקשר עד שתוכל לבחור את הישות **לקוח: CustomerInsights** מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="f1456-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="f1456-161">לאחר מכן, בחר **כל הרשומות** עבור כל שלב.</span><span class="sxs-lookup"><span data-stu-id="f1456-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f1456-162">![נתיב קשר במהלך יצירת פלח](media/segments-multiple-relationships.png "נתיב קשר במהלך יצירת פלח")</span><span class="sxs-lookup"><span data-stu-id="f1456-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="f1456-163">כברירת מחדל, פלחים יוצרים ישות פלט המכילה את כל התכונות של פרופילי לקוחות שמתאימים למסננים שהוגדרו.</span><span class="sxs-lookup"><span data-stu-id="f1456-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="f1456-164">אם פלח מבוסס על ישויות אחרות מלבד הישות *לקוח*, באפשרותך להוסיף תכונות נוספות מישויות אלה לישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="f1456-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="f1456-165">בחר **תכונות פרוייקט** כדי לבחור את התכונות שיצורפו לישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="f1456-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="f1456-166">דוגמה: פלח מבוסס על ישות המכילה נתוני פעילות לקוחות שקשורים לישות *לקוח*.</span><span class="sxs-lookup"><span data-stu-id="f1456-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="f1456-167">הפלח מחפש את כל הלקוחות שהתקשרו לתמיכה ב- 60 הימים האחרונים.</span><span class="sxs-lookup"><span data-stu-id="f1456-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="f1456-168">באפשרותך לבחור לצרף את משך השיחה ואת מספר השיחות לכל רשומות הלקוחות התואמות בישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="f1456-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="f1456-169">מידע זה עשוי להיות שימושי לשליחת דואר עם קישורים שימושיים למאמרי עזרה מקוונים ושאלות נפוצות ללקוחות שהתקשרו לעתים קרובות.</span><span class="sxs-lookup"><span data-stu-id="f1456-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="f1456-170">תכונות חזויות פועלות רק עבור ישויות שיש להן קשר גומלין מסוג אחד-לרבים עם ישות הלקוח.</span><span class="sxs-lookup"><span data-stu-id="f1456-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="f1456-171">לדוגמה, לקוח אחד יכול להיות בעל מספר מנויים.</span><span class="sxs-lookup"><span data-stu-id="f1456-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="f1456-172">ניתן לחזות תכונות רק מישות המשמשת בכל קבוצה של שאילתות פלחים שאתה בונה.</span><span class="sxs-lookup"><span data-stu-id="f1456-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="f1456-173">תכונות חזויות נלקחות בחשבון בעת שימוש ב‏‫אופרטורי הגדרה.</span><span class="sxs-lookup"><span data-stu-id="f1456-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="f1456-174">בחר **שמור** כדי לשמור את הפלח.</span><span class="sxs-lookup"><span data-stu-id="f1456-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="f1456-175">הפלח יישמר ויעובד אם כל הדרישות תקפות.</span><span class="sxs-lookup"><span data-stu-id="f1456-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="f1456-176">אחרת, הוא יישמר כטיוטה.</span><span class="sxs-lookup"><span data-stu-id="f1456-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="f1456-177">בחר **חזרה לפלחים** כדי לחזור אל דף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="f1456-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="f1456-178">פלחים מהירים</span><span class="sxs-lookup"><span data-stu-id="f1456-178">Quick segments</span></span>

<span data-ttu-id="f1456-179">פלחים מהירים מאפשרים לך לבנות פלחים פשוטים עם אופרטור יחיד במהירות, להשגה מהירה יותר של תובנות.</span><span class="sxs-lookup"><span data-stu-id="f1456-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="f1456-180">בדף **פלחים**, בחר **חדש** > **צור מ**.</span><span class="sxs-lookup"><span data-stu-id="f1456-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="f1456-181">בחר את האפשרות **פרופילים** כדי לבנות פלח המבוסס על הישות *לקוח מאוחד*.</span><span class="sxs-lookup"><span data-stu-id="f1456-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="f1456-182">בחר את האפשרות **מדידות** כדי לבנות פלח מסביב למדדים שיצרת בעבר.</span><span class="sxs-lookup"><span data-stu-id="f1456-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="f1456-183">בחר את האפשרות **בינה** כדי לבנות פלח לפי אחת מישויות הפלט שיצרת באמצעות היכולות **חיזויים** או **מודלים מותאמים אישית**.</span><span class="sxs-lookup"><span data-stu-id="f1456-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="f1456-184">בתיבת הדו-שיח **פלח מהיר חדש**, בחר תכונה מהרשימה הנפתחת **שדה**.</span><span class="sxs-lookup"><span data-stu-id="f1456-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="f1456-185">המערכת תספק כמה תובנות נוספות שיעזרו לך ליצור פלחים טובים יותר של הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="f1456-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="f1456-186">בשדות הקטגוריות נציג את 10 הספירות המובילות של לקוחות.</span><span class="sxs-lookup"><span data-stu-id="f1456-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="f1456-187">בחר **ערך** ובחר **סקירה**.</span><span class="sxs-lookup"><span data-stu-id="f1456-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="f1456-188">עבור תכונה מספרית, המערכת תציג איזה ערך תכונה נופל באחוזון של כל לקוח.</span><span class="sxs-lookup"><span data-stu-id="f1456-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="f1456-189">בחר **אופרטור** ו **ערך** ובחר **סקירה**.</span><span class="sxs-lookup"><span data-stu-id="f1456-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="f1456-190">המערכת תספק לך **גודל פלח משוער**.</span><span class="sxs-lookup"><span data-stu-id="f1456-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="f1456-191">אתה יכול לבחור אם לייצר את הפלח שהגדרת, או לבדוק אותו תחילה כדי לקבל גודל פלח שונה.</span><span class="sxs-lookup"><span data-stu-id="f1456-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f1456-192">![שם ואומדן עבור פלח מהיר](media/quick-segment-name.png "שם ואומדן עבור פלח מהיר")</span><span class="sxs-lookup"><span data-stu-id="f1456-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="f1456-193">תן **שם** לפלח.</span><span class="sxs-lookup"><span data-stu-id="f1456-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="f1456-194">או הזן **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="f1456-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="f1456-195">בחר **שמור** כדי ליצור את הפלח.</span><span class="sxs-lookup"><span data-stu-id="f1456-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="f1456-196">לאחר סיום העיבוד של הפלח, אתה יכול להציג אותו כמו כל פלח אחר שיצרת.</span><span class="sxs-lookup"><span data-stu-id="f1456-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f1456-197">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="f1456-197">Next steps</span></span>

<span data-ttu-id="f1456-198">[ייצא פלח](export-destinations.md) וחקור את [כרטיס לקוח](customer-card-add-in.md) ו [מחברים](export-power-bi.md) כדי לקבל תובנות ברמת הלקוח.</span><span class="sxs-lookup"><span data-stu-id="f1456-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
