---
title: ייצוא נתונים מ- Customer Insights
description: נהל פעולות ייצוא לשיתוף נתונים.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896144"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="7daea-103">מבט כולל על פעולות ייצוא (Preview)</span><span class="sxs-lookup"><span data-stu-id="7daea-103">Exports (preview) overview</span></span>

<span data-ttu-id="7daea-104">הדף **פעולות ייצוא** מציג לך את כל פעולות הייצוא שהוגדרו.</span><span class="sxs-lookup"><span data-stu-id="7daea-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="7daea-105">פעולות ייצוא משתפות נתונים ספציפיים עם יישומים שונים.</span><span class="sxs-lookup"><span data-stu-id="7daea-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="7daea-106">הן יכולות לכלול פרופילי לקוח או ישויות, תוכניות ופרטי מיפוי.</span><span class="sxs-lookup"><span data-stu-id="7daea-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="7daea-107">כל ייצוא דורש [חיבור, שהוגדר על-ידי מנהל מערכת, לניהול אימות וגישה](connections.md).</span><span class="sxs-lookup"><span data-stu-id="7daea-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7daea-108">עד מרץ 2021, פעולות ייצוא יצרו חיבור לשירות המתאים באופן אוטומטי.</span><span class="sxs-lookup"><span data-stu-id="7daea-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="7daea-109">פעולות ייצוא דורשות כעת [חיבור, שנוצר ושותף על-ידי מנהל מערכת](connections.md) לפני שתוכל ליצור אותן.</span><span class="sxs-lookup"><span data-stu-id="7daea-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="7daea-110">עבור אל **נתונים** > **פעולות ייצוא** להצגת דף פעולות הייצוא.</span><span class="sxs-lookup"><span data-stu-id="7daea-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="7daea-111">לכל תפקידי המשתמש יש גישה להצגת פעולות ייצוא מוגדרות.</span><span class="sxs-lookup"><span data-stu-id="7daea-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="7daea-112">השתמש בשדה החיפוש בסרגל הפקודות כדי למצוא פעולות ייצוא לפי השם, שם החיבור או סוג החיבור שלהן.</span><span class="sxs-lookup"><span data-stu-id="7daea-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="7daea-113">הגדרת ייצוא חדש</span><span class="sxs-lookup"><span data-stu-id="7daea-113">Set up a new export</span></span>

<span data-ttu-id="7daea-114">כדי להגדיר או לערוך ייצוא, אתה זקוק לחיבורים שזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="7daea-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="7daea-115">חיבורים תלויים ב[תפקיד המשתמש](permissions.md) שלך:</span><span class="sxs-lookup"><span data-stu-id="7daea-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="7daea-116">למנהלי מערכת יש גישה לכל החיבורים.</span><span class="sxs-lookup"><span data-stu-id="7daea-116">Administrators have access to all connections.</span></span> <span data-ttu-id="7daea-117">הם יכולים גם ליצור חיבורים חדשים בעת הגדרת ייצוא.</span><span class="sxs-lookup"><span data-stu-id="7daea-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="7daea-118">למשתתפים יכולה להיות גישה לחיבורים ספציפיים.</span><span class="sxs-lookup"><span data-stu-id="7daea-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="7daea-119">הם תלויים במנהלי מערכת כדי להגדיר ולשתף חיבורים.</span><span class="sxs-lookup"><span data-stu-id="7daea-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="7daea-120">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="7daea-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="7daea-121">המציגים יכולים רק להציג פעולות ייצוא קיימות, אבל לא ליצור אותן.</span><span class="sxs-lookup"><span data-stu-id="7daea-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="7daea-122">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="7daea-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7daea-123">בחר **הוסף ייצוא** כדי ליצור יעד ייצוא חדש.</span><span class="sxs-lookup"><span data-stu-id="7daea-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="7daea-124">בחלונית **הגדרת ייצוא**, בחר את החיבור שיש להשתמש בו.</span><span class="sxs-lookup"><span data-stu-id="7daea-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="7daea-125">[חיבורים](connections.md) מנוהלים על-ידי מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="7daea-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="7daea-126">ספק את הפרטים הדרושים ובחר **שמור** כדי ליצור את הייצוא.</span><span class="sxs-lookup"><span data-stu-id="7daea-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="7daea-127">ערוך ייצוא</span><span class="sxs-lookup"><span data-stu-id="7daea-127">Edit an export</span></span>

1. <span data-ttu-id="7daea-128">בחר את שלוש הנקודות האנכיות עבור יעד הייצוא שברצונך לערוך.</span><span class="sxs-lookup"><span data-stu-id="7daea-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="7daea-129">בחר **ערוך** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="7daea-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="7daea-130">שנה את הערכים שברצונך לעדכן ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="7daea-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="7daea-131">הצגת פעולות ייצוא ופרטי ייצוא</span><span class="sxs-lookup"><span data-stu-id="7daea-131">View Exports and export details</span></span>

<span data-ttu-id="7daea-132">לאחר יצירת יעדי ייצוא, הם מופיעים ב **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="7daea-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="7daea-133">כל המשתמשים יכולים לראות אילו נתונים משותפים ואת המצב העדכני שלהם.</span><span class="sxs-lookup"><span data-stu-id="7daea-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="7daea-134">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="7daea-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7daea-135">משתמשים ללא הרשאות עריכה שבוחרים **הצג** במקום **ערוך** רואים את פרטי הייצוא.</span><span class="sxs-lookup"><span data-stu-id="7daea-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="7daea-136">חלונית צד זו מציגה את הגדרת הייצוא הזה.</span><span class="sxs-lookup"><span data-stu-id="7daea-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="7daea-137">ללא הרשאות עריכה, אינך יכול לשנות ערכים.</span><span class="sxs-lookup"><span data-stu-id="7daea-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="7daea-138">בחר **סגור** כדי לחזור לדף פעולות הייצוא.</span><span class="sxs-lookup"><span data-stu-id="7daea-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="7daea-139">הפעלת פעולות ייצוא לפי דרישה</span><span class="sxs-lookup"><span data-stu-id="7daea-139">Run exports on demand</span></span>

<span data-ttu-id="7daea-140">לאחר קביעת התצורה של ייצוא, הוא יפעל עם כל [רענון מתוזמן](system.md#schedule-tab) כל עוד יש לו חיבור פעיל.</span><span class="sxs-lookup"><span data-stu-id="7daea-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="7daea-141">כדי לייצא נתונים מבלי להמתין לרענון מתוזמן, עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="7daea-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="7daea-142">עומדות בפניך שתי אפשרויות:</span><span class="sxs-lookup"><span data-stu-id="7daea-142">You have two options:</span></span>

- <span data-ttu-id="7daea-143">כדי להפעיל את כל פעולות הייצוא, בחר **הפעל הכל** בסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="7daea-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="7daea-144">כדי להפעיל ייצוא יחיד, בחר את שלוש הנקודות (...) בפריט הרשימה ובחר **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="7daea-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="7daea-145">הסרת ייצוא</span><span class="sxs-lookup"><span data-stu-id="7daea-145">Remove an Export</span></span>

1. <span data-ttu-id="7daea-146">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="7daea-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="7daea-147">בחר את שלוש הנקודות האנכיות עבור הייצוא שברצונך להסיר.</span><span class="sxs-lookup"><span data-stu-id="7daea-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="7daea-148">בחר **הסר** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="7daea-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="7daea-149">אשר את ההסרה על-ידי בחירת **הסר** במסך האישור.</span><span class="sxs-lookup"><span data-stu-id="7daea-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
