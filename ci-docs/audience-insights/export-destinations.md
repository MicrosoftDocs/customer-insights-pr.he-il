---
title: ייצוא נתונים מ- Customer Insights
description: נהל פעולות ייצוא לשיתוף נתונים.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253041"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="e8a2e-103">מבט כולל על פעולות ייצוא (Preview)</span><span class="sxs-lookup"><span data-stu-id="e8a2e-103">Exports (preview) overview</span></span>

<span data-ttu-id="e8a2e-104">הדף **פעולות ייצוא** מציג לך את כל פעולות הייצוא שהוגדרו.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="e8a2e-105">פעולות ייצוא משתפות נתונים ספציפיים עם יישומים שונים.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="e8a2e-106">הן יכולות לכלול פרופילי לקוח או ישויות, תוכניות ופרטי מיפוי.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="e8a2e-107">כל ייצוא דורש [חיבור, שהוגדר על-ידי מנהל מערכת, לניהול אימות וגישה](connections.md).</span><span class="sxs-lookup"><span data-stu-id="e8a2e-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="e8a2e-108">עבור אל **נתונים** > **פעולות ייצוא** להצגת דף פעולות הייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="e8a2e-109">לכל תפקידי המשתמש יש גישה להצגת פעולות ייצוא מוגדרות.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="e8a2e-110">השתמש בשדה החיפוש בסרגל הפקודות כדי למצוא פעולות ייצוא לפי השם, שם החיבור או סוג החיבור שלהן.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="e8a2e-111">הגדרת ייצוא חדש</span><span class="sxs-lookup"><span data-stu-id="e8a2e-111">Set up a new export</span></span>

<span data-ttu-id="e8a2e-112">כדי להגדיר או לערוך ייצוא, אתה זקוק לחיבורים שזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="e8a2e-113">חיבורים תלויים ב[תפקיד המשתמש](permissions.md) שלך:</span><span class="sxs-lookup"><span data-stu-id="e8a2e-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="e8a2e-114">למנהלי מערכת יש גישה לכל החיבורים.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-114">Administrators have access to all connections.</span></span> <span data-ttu-id="e8a2e-115">הם יכולים גם ליצור חיבורים חדשים בעת הגדרת ייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="e8a2e-116">למשתתפים יכולה להיות גישה לחיבורים ספציפיים.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="e8a2e-117">הם תלויים במנהלי מערכת כדי להגדיר ולשתף חיבורים.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="e8a2e-118">רשימת פעולות הייצוא מראה לתורמים אם הם יכולים לערוך או רק להציג ייצוא בעמודה **ההרשאות שלך**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="e8a2e-119">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e8a2e-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="e8a2e-120">המציגים יכולים רק להציג פעולות ייצוא קיימות, אבל לא ליצור אותן.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="e8a2e-121">הגדרת ייצוא חדש</span><span class="sxs-lookup"><span data-stu-id="e8a2e-121">Define a new export</span></span>

1. <span data-ttu-id="e8a2e-122">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8a2e-123">בחר **הוסף ייצוא** כדי ליצור ייצוא חדש.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="e8a2e-124">בחלונית **הגדרת ייצוא**, בחר את החיבור שיש להשתמש בו.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="e8a2e-125">[חיבורים](connections.md) מנוהלים על-ידי מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="e8a2e-126">ספק את הפרטים הדרושים ובחר **שמור** כדי ליצור את הייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="e8a2e-127">הגדרת ייצוא חדש בהתבסס על ייצוא קיים</span><span class="sxs-lookup"><span data-stu-id="e8a2e-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="e8a2e-128">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8a2e-129">ברשימת פעולות הייצוא, בחר את הייצוא שברצונך לשכפל.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="e8a2e-130">בחר **צור שכפול** בשורת הפקודה כדי לפתוח את החלונית **הגדרת ייצוא** עם פרטי הייצוא שנבחר.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="e8a2e-131">סקור והתאם את הייצוא ובחר **שמור** כדי ליצור ייצוא חדש.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="e8a2e-132">ערוך ייצוא</span><span class="sxs-lookup"><span data-stu-id="e8a2e-132">Edit an export</span></span>

1. <span data-ttu-id="e8a2e-133">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8a2e-134">ברשימת פעולות הייצוא, בחר את הייצוא שברצונך לערוך.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="e8a2e-135">בחר **עריכה** בסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="e8a2e-136">שנה את הערכים שברצונך לעדכן ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="e8a2e-137">הצגת פעולות ייצוא ופרטי ייצוא</span><span class="sxs-lookup"><span data-stu-id="e8a2e-137">View exports and export details</span></span>

<span data-ttu-id="e8a2e-138">לאחר יצירת יעדי ייצוא, הם מופיעים תחת **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="e8a2e-139">כל המשתמשים יכולים לראות אילו נתונים משותפים ואת המצב העדכני שלהם.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="e8a2e-140">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8a2e-141">משתמשים ללא הרשאות עריכה שבוחרים **הצג** במקום **ערוך** רואים את פרטי הייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="e8a2e-142">החלונית הצדדית מציגה את תצורת הייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="e8a2e-143">ללא הרשאות עריכה, אינך יכול לשנות ערכים.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="e8a2e-144">בחר **סגור** כדי לחזור לדף פעולות הייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="e8a2e-145">תזמון והפעלה של פעולות ייצוא</span><span class="sxs-lookup"><span data-stu-id="e8a2e-145">Schedule and run exports</span></span>

<span data-ttu-id="e8a2e-146">לכל ייצוא שתגדיר יש לוח זמנים לרענון.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="e8a2e-147">במהלך הרענון, המערכת מחפשת נתונים חדשים או מעודכנים שיש לכלול בייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="e8a2e-148">כברירת מחדל, פעולות ייצוא מופעלות כחלק מכל [רענון מתוזמן של המערכת](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e8a2e-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e8a2e-149">באפשרותך להתאים אישית את לוח הזמנים של הרענון או לכבות אותו להפעלת פעולות ייצוא באופן ידני.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="e8a2e-150">לוחות הזמנים לייצוא תלויים במצב הסביבה.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="e8a2e-151">אם מתבצעים עדכונים ב[יחסי התלות](system.md#refresh-policies) כאשר ייצוא מתוזמן אמור להתחיל, המערכת תסיים תחילה את עיבוד יחסי התלות ולאחר מכן תפעיל את הייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="e8a2e-152">באפשרותך לראות מתי בוצע הרענון האחרון של ייצוא בעמודה **בוצע רענון**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="e8a2e-153">תזמון פעולות ייצוא</span><span class="sxs-lookup"><span data-stu-id="e8a2e-153">Schedule exports</span></span>

<span data-ttu-id="e8a2e-154">באפשרותך להגדיר לוחות זמנים לרענון מותאמים אישית לפעולות ייצוא בודדות או לכמה פעולות ייצוא בבת אחת.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="e8a2e-155">לוח הזמנים המוגדר כרגע מופיע בעמודה **לוח זמנים** של רשימת הייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="e8a2e-156">ההרשאה לשינוי לוח הזמנים זהה לזו של [עריכה והגדרה של פעולות ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e8a2e-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="e8a2e-157">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8a2e-158">בחר את הייצוא שברצונך לתזמן.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="e8a2e-159">בחר **תזמן** בסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="e8a2e-160">בחלונית **‏‫לוח זמנים לייצוא‬**, הגדר את האפשרות **הפעלת לוח זמנים** למצב **מופעל** כדי להפעיל את הייצוא באופן אוטומטי.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="e8a2e-161">הגדר אפשרות זו למצב **כבוי** כדי לבצע רענון באופן ידני.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="e8a2e-162">עבור פעולות ייצוא המוגדרות לרענון אוטומטי, בחר ערך **מופע חוזר** וציין את הפרטים עבורו.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="e8a2e-163">הזמן שהוגדר חל על כל המופעים של מופע חוזר.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="e8a2e-164">זה הזמן שבו צריך להתחיל הרענון של הייצוא.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="e8a2e-165">החל והפעל את השינויים על-ידי בחירה באפשרות **שמור**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="e8a2e-166">בעת עריכת לוח הזמנים לכמה פעולות ייצוא, עליך לבחור באחת האפשרויות תחת **‏‫השאר או עקוף לוחות זמנים‬**:</span><span class="sxs-lookup"><span data-stu-id="e8a2e-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="e8a2e-167">**‏‫השאר לוחות זמנים נפרדים‬**: השאר את לוח הזמנים שהוגדר בעבר עבור פעולות הייצוא הנבחרות ורק השבת או הפעל אותו לפי הצורך.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="e8a2e-168">**‏‫הגדר לוח זמנים חדש עבור כל פעולות הייצוא שנבחרו‬** : עקוף את לוחות הזמנים הקיים של פעולות הייצוא שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="e8a2e-169">הפעלת פעולות ייצוא לפי דרישה</span><span class="sxs-lookup"><span data-stu-id="e8a2e-169">Run exports on demand</span></span>

<span data-ttu-id="e8a2e-170">כדי לייצא נתונים מבלי להמתין לרענון מתוזמן, עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="e8a2e-171">כדי להפעיל את כל פעולות הייצוא, בחר **הפעל הכל** בסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="e8a2e-172">פעולה זו תפעיל רק פעולות ייצוא שיש להן לוח זמנים פעיל.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="e8a2e-173">כדי להפעיל פעולת ייצוא יחידה, בחר אותה ברשימה ולאחר מכן בחר **הפעל** בשורת הפקודה.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="e8a2e-174">כך תוכל להפעיל פעולות ייצוא ללא לוח זמנים פעיל.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="e8a2e-175">הסרת ייצוא</span><span class="sxs-lookup"><span data-stu-id="e8a2e-175">Remove an Export</span></span>

1. <span data-ttu-id="e8a2e-176">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e8a2e-177">‏‏בחר את הייצוא שברצונך להסיר.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="e8a2e-178">בחר **הסר** בסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="e8a2e-179">אשר את ההסרה על-ידי בחירת **הסר** במסך האישור.</span><span class="sxs-lookup"><span data-stu-id="e8a2e-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
