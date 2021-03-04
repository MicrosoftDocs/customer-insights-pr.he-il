---
title: פעילויות של לקוחות
description: הגדר פעילויות של לקוחות והצג אותן בציר זמן של לקוח.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267433"
---
# <a name="customer-activities"></a><span data-ttu-id="f7cf5-103">פעילויות של לקוחות</span><span class="sxs-lookup"><span data-stu-id="f7cf5-103">Customer activities</span></span>

<span data-ttu-id="f7cf5-104">שלב פעילויות של לקוחות מ[מקורות נתונים שונים](data-sources.md) ב- Dynamics 365 Customer Insights כדי ליצור ציר זמן של לקוח המפרט את הפעילויות בסדר כרונולוגי.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="f7cf5-105">אתה יכול לכלול את ציר הזמן ביישומי Customer Engagement ב- Dynamics 365 דרך [תוספת כרטיס לקוח](customer-card-add-in.md), או בלוח מחוונים של Power BI.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="f7cf5-106">הגדרת פעילות</span><span class="sxs-lookup"><span data-stu-id="f7cf5-106">Define an activity</span></span>

<span data-ttu-id="f7cf5-107">מקורות הנתונים שלך כוללים ישויות עם נתוני עסקאות ופעילות ממקורות נתונים מרובים.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="f7cf5-108">זהה ישויות אלה ובחר את הפעילויות שתרצה להציג בציר הזמן של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="f7cf5-109">בחר את הישות הכוללת את פעילות או פעילויות היעד שלך.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="f7cf5-110">ב- audience insights, עבור אל **נתונים** > **פעילויות**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="f7cf5-111">בחר **הוסף פעילות**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f7cf5-112">ישות מוכרחה לכלול תכונה אחת לפחות מסוג **תאריך** כדי שתיכלל בציר זמן של לקוח ואין באפשרותך להוסיף ישויות ללא שדות **תאריך**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="f7cf5-113">הפקד **הוסף פעילות** מושבת אם לא נמצאה ישות כזאת.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="f7cf5-114">בחלונית **הוסף פעילות**, הגדר את הערכים עבור השדות הבאים:</span><span class="sxs-lookup"><span data-stu-id="f7cf5-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="f7cf5-115">**ישות**: בחר ישות הכוללת נתוני עסקאות או פעילות.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="f7cf5-116">**מפתח ראשי**: בחר את השדה המזהה באופן ייחודי רשומה.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="f7cf5-117">הוא לא אמור להכיל ערכים כפולים, ערכים ריקים או ערכים חסרים.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="f7cf5-118">**חותמת זמן**: בחר את השדה המייצג את שעת ההתחלה של הפעילות שלך.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="f7cf5-119">**אירוע**: בחר את השדה שהוא האירוע עבור הפעילות.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="f7cf5-120">**כתובת אתר אינטרנט**: בחר את שדה המייצג כתובת אתר המספק מידע נוסף על פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="f7cf5-121">לדוגמה, מערכת העסקאות המקבלת פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="f7cf5-122">כתובת אתר זו יכולה להיות כל שדה מתוך מקור נתונים, או שהיא יכולה להיות בנויה כשדה חדש באמצעות המרה‬ של Power Query.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="f7cf5-123">נתוני URL אלה יאוחסנו בישות הפעילות המאוחדת, שאותה ניתן לצרוך במורד הזרם באמצעות ממשקי API.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="f7cf5-124">**פרטים**: לחלופין, בחר את השדה שהתווסף לקבלת פרטים נוספים.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="f7cf5-125">**סמל**: לחלופין, בחר בסמל המייצג פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="f7cf5-126">**סוג הפעילות**: הגדר את ההתייחסות לסוג הפעילות ל- Common Data Model המתאר בצורה הטובה ביותר את ההגדרה הסמנטית של הפעילות.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="f7cf5-127">במקטע **הגדרת קשר**, קבע את תצורת הפרטים לחיבור נתוני הפעילות שלך ללקוח המתאים שלה.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="f7cf5-128">**שדה ישות פעילות**: בחר את השדה בישות הפעילות שלך שישמש ליצירת קשר עם ישות אחרת.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="f7cf5-129">**ישות לקוח**: בחר את ישות הלקוח של המקור המתאימה שאיתה ישות הפעילות תהיה בקשר.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="f7cf5-130">באפשרותך להתייחס רק לישויות לקוח מקור אלה המשמשות בתהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="f7cf5-131">**שדה ישות לקוח**: שדה זה מציג את המפתח הראשי של ישות הלקוח של המקור כפי שנבחר בתהליך המפה.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="f7cf5-132">שדה מפתח ראשי זה בישות הלקוח של המקור משמש ליצירת קשר עם ישות הפעילות.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="f7cf5-133">**שם**: אם כבר קיים קשר בין ישות פעילות זו לבין ישות הלקוח של המקור שנבחר, שם הקשר יהיה במצב לקריאה בלבד.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="f7cf5-134">אם לא קיים קשר כזה, קשר חדש ייווצר עם השם שסופק כאן.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7cf5-135">![הגדרת קשר הישות](media/activities-entities-define.png "הגדרת קשר הישות")</span><span class="sxs-lookup"><span data-stu-id="f7cf5-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="f7cf5-136">בחר **שמור** כדי להחיל את השינויים.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="f7cf5-137">בדף **פעילויות**, בחר **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="f7cf5-138">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="f7cf5-139">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="f7cf5-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="f7cf5-140">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="f7cf5-141">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="f7cf5-142">עריכת פעילות</span><span class="sxs-lookup"><span data-stu-id="f7cf5-142">Edit an activity</span></span>

1. <span data-ttu-id="f7cf5-143">ב- audience insights, עבור אל **נתונים** > **פעילויות**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="f7cf5-144">בחר את ישות הפעילות שברצונך לערוך ובחר **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="f7cf5-145">לחלופין, באפשרותך לרחף מעל שורת הישות ולבחור את סמל **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="f7cf5-146">לחץ על סמל **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="f7cf5-147">בחלונית **ערוך פעילות**, עדכן את הערכים ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="f7cf5-148">בדף **פעילויות**, בחר **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="f7cf5-149">מחיקת פעילות</span><span class="sxs-lookup"><span data-stu-id="f7cf5-149">Delete an activity</span></span>

1. <span data-ttu-id="f7cf5-150">ב- audience insights, עבור אל **נתונים** > **פעילויות**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="f7cf5-151">בחר את ישות הפעילות שברצונך להסיר ובחר **מחק**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="f7cf5-152">לחלופין, באפשרותך לרחף מעל שורת הישות ולבחור את סמל **מחק**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="f7cf5-153">בנוסף, באפשרותך לבחור ישויות פעילות מרובות שיימחקו בבת אחת.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7cf5-154">![עריכה או מחיקה של קשר הישות](media/activities-entities-edit-delete.png "עריכה או מחיקה של קשר הישות.").</span><span class="sxs-lookup"><span data-stu-id="f7cf5-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="f7cf5-155">בחר בסמל **מחק**.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="f7cf5-156">אשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="f7cf5-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]