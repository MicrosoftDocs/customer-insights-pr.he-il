---
title: ייצוא נתונים מ- Customer Insights
description: נהל פעולות ייצוא לשיתוף נתונים.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016615"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="b5a67-103">מבט כולל על פעולות ייצוא (Preview)</span><span class="sxs-lookup"><span data-stu-id="b5a67-103">Exports (preview) overview</span></span>

<span data-ttu-id="b5a67-104">הדף **פעולות ייצוא** מציג לך את כל פעולות הייצוא שהוגדרו.</span><span class="sxs-lookup"><span data-stu-id="b5a67-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="b5a67-105">פעולות ייצוא משתפות נתונים ספציפיים עם יישומים שונים.</span><span class="sxs-lookup"><span data-stu-id="b5a67-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="b5a67-106">הן יכולות לכלול פרופילי לקוח או ישויות, תוכניות ופרטי מיפוי.</span><span class="sxs-lookup"><span data-stu-id="b5a67-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="b5a67-107">כל ייצוא דורש [חיבור, שהוגדר על-ידי מנהל מערכת, לניהול אימות וגישה](connections.md).</span><span class="sxs-lookup"><span data-stu-id="b5a67-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="b5a67-108">עבור אל **נתונים** > **פעולות ייצוא** להצגת דף פעולות הייצוא.</span><span class="sxs-lookup"><span data-stu-id="b5a67-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="b5a67-109">לכל תפקידי המשתמש יש גישה להצגת פעולות ייצוא מוגדרות.</span><span class="sxs-lookup"><span data-stu-id="b5a67-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="b5a67-110">השתמש בשדה החיפוש בסרגל הפקודות כדי למצוא פעולות ייצוא לפי השם, שם החיבור או סוג החיבור שלהן.</span><span class="sxs-lookup"><span data-stu-id="b5a67-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="b5a67-111">הגדרת ייצוא חדש</span><span class="sxs-lookup"><span data-stu-id="b5a67-111">Set up a new export</span></span>

<span data-ttu-id="b5a67-112">כדי להגדיר או לערוך ייצוא, אתה זקוק לחיבורים שזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="b5a67-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="b5a67-113">חיבורים תלויים ב[תפקיד המשתמש](permissions.md) שלך:</span><span class="sxs-lookup"><span data-stu-id="b5a67-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="b5a67-114">למנהלי מערכת יש גישה לכל החיבורים.</span><span class="sxs-lookup"><span data-stu-id="b5a67-114">Administrators have access to all connections.</span></span> <span data-ttu-id="b5a67-115">הם יכולים גם ליצור חיבורים חדשים בעת הגדרת ייצוא.</span><span class="sxs-lookup"><span data-stu-id="b5a67-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="b5a67-116">למשתתפים יכולה להיות גישה לחיבורים ספציפיים.</span><span class="sxs-lookup"><span data-stu-id="b5a67-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="b5a67-117">הם תלויים במנהלי מערכת כדי להגדיר ולשתף חיבורים.</span><span class="sxs-lookup"><span data-stu-id="b5a67-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="b5a67-118">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b5a67-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="b5a67-119">המציגים יכולים רק להציג פעולות ייצוא קיימות, אבל לא ליצור אותן.</span><span class="sxs-lookup"><span data-stu-id="b5a67-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="b5a67-120">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="b5a67-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b5a67-121">בחר **הוסף ייצוא** כדי ליצור יעד ייצוא חדש.</span><span class="sxs-lookup"><span data-stu-id="b5a67-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="b5a67-122">בחלונית **הגדרת ייצוא**, בחר את החיבור שיש להשתמש בו.</span><span class="sxs-lookup"><span data-stu-id="b5a67-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="b5a67-123">[חיבורים](connections.md) מנוהלים על-ידי מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="b5a67-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="b5a67-124">ספק את הפרטים הדרושים ובחר **שמור** כדי ליצור את הייצוא.</span><span class="sxs-lookup"><span data-stu-id="b5a67-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="b5a67-125">ערוך ייצוא</span><span class="sxs-lookup"><span data-stu-id="b5a67-125">Edit an export</span></span>

1. <span data-ttu-id="b5a67-126">בחר את שלוש הנקודות האנכיות עבור יעד הייצוא שברצונך לערוך.</span><span class="sxs-lookup"><span data-stu-id="b5a67-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="b5a67-127">בחר **ערוך** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="b5a67-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="b5a67-128">שנה את הערכים שברצונך לעדכן ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="b5a67-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="b5a67-129">הצגת פעולות ייצוא ופרטי ייצוא</span><span class="sxs-lookup"><span data-stu-id="b5a67-129">View Exports and export details</span></span>

<span data-ttu-id="b5a67-130">לאחר יצירת יעדי ייצוא, הם מופיעים ב **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="b5a67-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="b5a67-131">כל המשתמשים יכולים לראות אילו נתונים משותפים ואת המצב העדכני שלהם.</span><span class="sxs-lookup"><span data-stu-id="b5a67-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="b5a67-132">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="b5a67-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b5a67-133">משתמשים ללא הרשאות עריכה שבוחרים **הצג** במקום **ערוך** רואים את פרטי הייצוא.</span><span class="sxs-lookup"><span data-stu-id="b5a67-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="b5a67-134">חלונית צד זו מציגה את הגדרת הייצוא הזה.</span><span class="sxs-lookup"><span data-stu-id="b5a67-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="b5a67-135">ללא הרשאות עריכה, אינך יכול לשנות ערכים.</span><span class="sxs-lookup"><span data-stu-id="b5a67-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="b5a67-136">בחר **סגור** כדי לחזור לדף פעולות הייצוא.</span><span class="sxs-lookup"><span data-stu-id="b5a67-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="b5a67-137">הפעלת פעולות ייצוא לפי דרישה</span><span class="sxs-lookup"><span data-stu-id="b5a67-137">Run exports on demand</span></span>

<span data-ttu-id="b5a67-138">לאחר קביעת התצורה של ייצוא, הוא יפעל עם כל [רענון מתוזמן](system.md#schedule-tab) כל עוד יש לו חיבור פעיל.</span><span class="sxs-lookup"><span data-stu-id="b5a67-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="b5a67-139">כדי לייצא נתונים מבלי להמתין לרענון מתוזמן, עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="b5a67-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="b5a67-140">עומדות בפניך שתי אפשרויות:</span><span class="sxs-lookup"><span data-stu-id="b5a67-140">You have two options:</span></span>

- <span data-ttu-id="b5a67-141">כדי להפעיל את כל פעולות הייצוא, בחר **הפעל הכל** בסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="b5a67-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="b5a67-142">כדי להפעיל ייצוא יחיד, בחר את שלוש הנקודות (...) בפריט הרשימה ובחר **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="b5a67-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="b5a67-143">הסרת ייצוא</span><span class="sxs-lookup"><span data-stu-id="b5a67-143">Remove an Export</span></span>

1. <span data-ttu-id="b5a67-144">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="b5a67-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b5a67-145">בחר את שלוש הנקודות האנכיות עבור הייצוא שברצונך להסיר.</span><span class="sxs-lookup"><span data-stu-id="b5a67-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="b5a67-146">בחר **הסר** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="b5a67-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="b5a67-147">אשר את ההסרה על-ידי בחירת **הסר** במסך האישור.</span><span class="sxs-lookup"><span data-stu-id="b5a67-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
