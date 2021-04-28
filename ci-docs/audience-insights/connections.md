---
title: חיבורים לשירותים אחרים מתוך Customer Insights.
description: שתף נתונים עם שירותים אחרים.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 106dbc26f95b309821d738e1484b1eaa79dd225b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896098"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="f48f5-103">מבט כולל על חיבורים (Preview)</span><span class="sxs-lookup"><span data-stu-id="f48f5-103">Connections (preview) overview</span></span>

<span data-ttu-id="f48f5-104">חיבורים הם המפתח כדי לאפשר שיתוף נתונים אל Customer Insights וממנו.</span><span class="sxs-lookup"><span data-stu-id="f48f5-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="f48f5-105">כל חיבור יוצר שיתוף נתונים עם שירות ספציפי.</span><span class="sxs-lookup"><span data-stu-id="f48f5-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="f48f5-106">חיבורים הם הבסיס ל[קביעת תצורה של העשרות של צד שלישי](enrichment-hub.md) ו[קביעת תצורה של פעולות ייצוא](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f48f5-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="f48f5-107">ניתן להשתמש באותו חיבור מספר פעמים.</span><span class="sxs-lookup"><span data-stu-id="f48f5-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="f48f5-108">לדוגמא, חיבור אחד ל- Dynamics 365 Marketing פועל עבור פעולות ייצוא מרובות וחיבור Leadspace אחד יכול לשמש למספר העשרות.</span><span class="sxs-lookup"><span data-stu-id="f48f5-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="f48f5-109">עבור אל **ניהול** > **חיבורים** כדי ליצור ולהציג חיבורים.</span><span class="sxs-lookup"><span data-stu-id="f48f5-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="f48f5-110">הכרטיסיה **חיבורים** מציגה לך את כל החיבורים הפעילים.</span><span class="sxs-lookup"><span data-stu-id="f48f5-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="f48f5-111">הרשימה מציגה שורה לכל חיבור.</span><span class="sxs-lookup"><span data-stu-id="f48f5-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="f48f5-112">קבל סקירה מהירה, תיאור, וגלה מה באפשרותך לעשות עם כל אפשרות הרחבה בכרטיסיה **גילוי**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="f48f5-113">פעולות ייצוא</span><span class="sxs-lookup"><span data-stu-id="f48f5-113">Exports</span></span>

<span data-ttu-id="f48f5-114">רק מנהלי מערכת יכולים להגדיר חיבורים חדשים, אך הם יכולים להעניק גישה למשתתפים לשימוש בחיבורים קיימים.</span><span class="sxs-lookup"><span data-stu-id="f48f5-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="f48f5-115">מנהלי מערכת שולטים במיקום שאליו נתונים יכולים להגיע, משתתפים מגדירים את תוכן המנה ואת התדירות המתאימים לצרכיהם.</span><span class="sxs-lookup"><span data-stu-id="f48f5-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="f48f5-116">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f48f5-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="f48f5-117">העשרות</span><span class="sxs-lookup"><span data-stu-id="f48f5-117">Enrichments</span></span>

<span data-ttu-id="f48f5-118">רק מנהלי מערכת יכולים להגדיר חיבורים חדשים, אך החיבורים שנוצרו זמינים תמיד גם למנהלי מערכת וגם למשתתפים.</span><span class="sxs-lookup"><span data-stu-id="f48f5-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="f48f5-119">מנהלי מערכת מנהלים אישורים ומעניקים הסכמה להעברת נתונים.</span><span class="sxs-lookup"><span data-stu-id="f48f5-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="f48f5-120">לאחר מכן הן מנהלי מערכת והן משתתפים יכולים להשתמש בחיבורים עבור העשרות.</span><span class="sxs-lookup"><span data-stu-id="f48f5-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="f48f5-121">הוסף חיבור חדש</span><span class="sxs-lookup"><span data-stu-id="f48f5-121">Add a new connection</span></span>

<span data-ttu-id="f48f5-122">כדי להוסיף חיבורים, אתה זקוק ל[הרשאות מנהל מערכת](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f48f5-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="f48f5-123">אם אתה מתחבר לשירותים אחרים של Microsoft, אנחנו מניחים ששני השירותים הם באותו ארגון.</span><span class="sxs-lookup"><span data-stu-id="f48f5-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="f48f5-124">עבור אל **ניהול** > **חיבורים (preview)**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="f48f5-125">עבור לכרטיסיה **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="f48f5-126">בחר **הוסף חיבור** כדי ליצור חיבור חדש.</span><span class="sxs-lookup"><span data-stu-id="f48f5-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="f48f5-127">בחר מהתפריט הנפתח את סוג החיבור שברצונך ליצור.</span><span class="sxs-lookup"><span data-stu-id="f48f5-127">Choose from the drop-down menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="f48f5-128">בחלונית **הגדרת חיבור**, ספק את הפרטים הדרושים.</span><span class="sxs-lookup"><span data-stu-id="f48f5-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="f48f5-129">**שם תצוגה** וסוג החיבור מתארים חיבור.</span><span class="sxs-lookup"><span data-stu-id="f48f5-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="f48f5-130">מומלץ לבחור שם המסביר את המטרה והיעד של חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="f48f5-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="f48f5-131">השדות המדויקים תלויים בשירות שאליו אתה מתחבר.</span><span class="sxs-lookup"><span data-stu-id="f48f5-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="f48f5-132">באפשרותך לקבל מידע על פרטי סוג חיבור ספציפי במאמר על שירות היעד.</span><span class="sxs-lookup"><span data-stu-id="f48f5-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="f48f5-133">כדי ליצור את החיבור, בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="f48f5-134">באפשרותך גם לבחור **הגדר** באריח בכרטיסיה **גלה**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="f48f5-135">אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא</span><span class="sxs-lookup"><span data-stu-id="f48f5-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="f48f5-136">בעת הגדרה או עריכה של חיבור ייצוא, בחר אילו משתמשים מורשים להשתמש בחיבור ספציפי זה כדי להגדיר [פעולות ייצוא](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f48f5-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="f48f5-137">כברירת מחדל, חיבור זמין למשתמשים בעלי תפקיד מנהל מערכת.</span><span class="sxs-lookup"><span data-stu-id="f48f5-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="f48f5-138">באפשרותך לשנות הגדרה זו תחת **בחר מי יכול להשתמש בחיבור זה** ואפשר למשתמשים עם תפקיד משתתף להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="f48f5-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="f48f5-139">משתתפים לא יוכלו להציג את החיבור או לערוך אותו.</span><span class="sxs-lookup"><span data-stu-id="f48f5-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="f48f5-140">הם יראו את שם התצוגה ואת סוג התצוגה רק בעת יצירת ייצוא.</span><span class="sxs-lookup"><span data-stu-id="f48f5-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="f48f5-141">על-ידי שיתוף חיבור, אתה מאפשר למשתתפים להשתמש בחיבור.</span><span class="sxs-lookup"><span data-stu-id="f48f5-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="f48f5-142">משתתפים יראו חיבורים משותפים כאשר יגדירו פעולות ייצוא.</span><span class="sxs-lookup"><span data-stu-id="f48f5-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="f48f5-143">הם יכולים לנהל כל ייצוא המשתמש בחיבור ספציפי זה.</span><span class="sxs-lookup"><span data-stu-id="f48f5-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="f48f5-144">באפשרותך לשנות הגדרה זו תוך שמירה על פעולות הייצוא שכבר הוגדרו על-ידי משתתפים.</span><span class="sxs-lookup"><span data-stu-id="f48f5-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="f48f5-145">עריכת חיבור</span><span class="sxs-lookup"><span data-stu-id="f48f5-145">Edit a connection</span></span>

1. <span data-ttu-id="f48f5-146">עבור אל **ניהול** > **חיבורים (preview)**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="f48f5-147">עבור לכרטיסיה **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="f48f5-148">בחר את שלוש הנקודות האנכיות עבור החיבור שברצונך לערוך.</span><span class="sxs-lookup"><span data-stu-id="f48f5-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="f48f5-149">בחר **Edit**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-149">Select **Edit**.</span></span>

1. <span data-ttu-id="f48f5-150">שנה את הערכים שברצונך לעדכן ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="f48f5-151">הסרת חיבור</span><span class="sxs-lookup"><span data-stu-id="f48f5-151">Remove a connection</span></span>

<span data-ttu-id="f48f5-152">אם החיבור שאתה מסיר משמש העשרות או פעולות ייצוא, עליך תחילה לנתק או להסיר אותן.</span><span class="sxs-lookup"><span data-stu-id="f48f5-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="f48f5-153">תיבת הדו-שיח להסרה תנחה אותך אל ההעשרות או פעולות הייצוא הרלוונטיות.</span><span class="sxs-lookup"><span data-stu-id="f48f5-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> <span data-ttu-id="f48f5-154">העשרות ופעולות ייצוא מנותקות הופכות ללא פעילות.</span><span class="sxs-lookup"><span data-stu-id="f48f5-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="f48f5-155">הפעל אותן מחדש על-ידי הוספת חיבור נוסף בדף [העשרות](enrichment-hub.md) או [פעולות ייצוא](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f48f5-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="f48f5-156">עבור אל **ניהול** > **חיבורים (preview)**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="f48f5-157">עבור לכרטיסיה **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="f48f5-158">בחר את שלוש הנקודות האנכיות עבור החיבור שברצונך להסיר.</span><span class="sxs-lookup"><span data-stu-id="f48f5-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="f48f5-159">בחר **הסר** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="f48f5-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="f48f5-160">תופיע תיבת דו-שיח לאישור.</span><span class="sxs-lookup"><span data-stu-id="f48f5-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="f48f5-161">אם קיימות העשרות או פעולות ייצוא המשתמשות בחיבור זה, בחר את הלחצן כדי לראות מה משתמש בחיבור.</span><span class="sxs-lookup"><span data-stu-id="f48f5-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="f48f5-162">**פעולות ייצוא:** באפשרותך לבחור להסיר או לנתק את פעולות הייצוא כדי שתוכל להסיר את החיבור.</span><span class="sxs-lookup"><span data-stu-id="f48f5-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="f48f5-163">כדי לנתק ייצוא, מנהלי מערכת יכולים להשתמש בפעולה **ניתוק**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="f48f5-164">פעולה זו זמינה לייצוא יחיד ולמספר פעולות ייצוא נבחרות.</span><span class="sxs-lookup"><span data-stu-id="f48f5-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="f48f5-165">על-ידי ניתוק אתה שומר על תצורת הייצוא, אך היא לא תפעל עד שחיבור נוסף יתווסף אליה.</span><span class="sxs-lookup"><span data-stu-id="f48f5-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="f48f5-166">**העשרות:** באפשרותך לבחור להסיר או להשבית את ההעשרות כדי שתוכל להסיר את החיבור.</span><span class="sxs-lookup"><span data-stu-id="f48f5-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="f48f5-167">כאשר לחיבור אין עוד יחסי תלות, חזור אל **ניהול** > **חיבורים** ונסה להסיר שוב את החיבור.</span><span class="sxs-lookup"><span data-stu-id="f48f5-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="f48f5-168">כדי לאשר את המחיקה, בחר **הסר**.</span><span class="sxs-lookup"><span data-stu-id="f48f5-168">To confirm the deletion select **Remove**.</span></span>

