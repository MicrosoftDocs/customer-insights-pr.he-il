---
title: פעילויות של לקוחות
description: הגדר פעילויות של לקוחות והצג אותן בציר זמן של לקוח.
ms.date: 04/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: 0c728fad4ed00d1bf085fed60057211861b3a195
ms.sourcegitcommit: f0855bd7762b1f0a1d3dd5259e23c95e1b0a6a93
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/07/2021
ms.locfileid: "5866408"
---
# <a name="customer-activities"></a><span data-ttu-id="2673f-103">פעילויות של לקוחות</span><span class="sxs-lookup"><span data-stu-id="2673f-103">Customer activities</span></span>

<span data-ttu-id="2673f-104">שלב פעילויות לקוחות מ[מקורות נתונים שונים](data-sources.md) ב- Dynamics 365 Customer Insights כדי ליצור ציר זמן המפרט את הפעילויות באופן כרונולוגי.</span><span class="sxs-lookup"><span data-stu-id="2673f-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="2673f-105">כלול את ציר הזמן ביישומי Dynamics 365 עם הפתרון [תוספת כרטיס לקוח](customer-card-add-in.md), או בלוח המחוונים של Power BI.</span><span class="sxs-lookup"><span data-stu-id="2673f-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="2673f-106">הגדרת פעילות</span><span class="sxs-lookup"><span data-stu-id="2673f-106">Define an activity</span></span>

<span data-ttu-id="2673f-107">מקורות הנתונים שלך יכולים לכלול ישויות עם נתוני עסקאות ופעילות ממקורות נתונים מרובים.</span><span class="sxs-lookup"><span data-stu-id="2673f-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="2673f-108">זהה ישויות אלה ובחר את הפעילויות שתרצה להציג בציר הזמן של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="2673f-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="2673f-109">בחר את הישות הכוללת את פעילות או פעילויות היעד שלך.</span><span class="sxs-lookup"><span data-stu-id="2673f-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="2673f-110">ישות מוכרחה לכלול תכונה אחת לפחות מסוג **תאריך** כדי שתיכלל בציר זמן של לקוח ואין באפשרותך להוסיף ישויות ללא שדות **תאריך**.</span><span class="sxs-lookup"><span data-stu-id="2673f-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="2673f-111">הפקד **הוסף פעילות** מושבת אם לא נמצאה ישות כזאת.</span><span class="sxs-lookup"><span data-stu-id="2673f-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="2673f-112">ב- audience insights, עבור אל **נתונים** > **פעילויות**.</span><span class="sxs-lookup"><span data-stu-id="2673f-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="2673f-113">בחר **הוסף פעילות** כדי להתחיל את החוויה המודרכת עבור תהליך הגדרת הפעילות.</span><span class="sxs-lookup"><span data-stu-id="2673f-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="2673f-114">בשלב **נתוני פעילות**, הגדר את הערכים עבור השדות הבאים:</span><span class="sxs-lookup"><span data-stu-id="2673f-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="2673f-115">**שם פעילות**: בחר שם לפעילות שלך.</span><span class="sxs-lookup"><span data-stu-id="2673f-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="2673f-116">**ישות**: בחר ישות הכוללת נתוני עסקאות או פעילות.</span><span class="sxs-lookup"><span data-stu-id="2673f-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="2673f-117">**מפתח ראשי**: בחר את השדה המזהה באופן ייחודי רשומה.</span><span class="sxs-lookup"><span data-stu-id="2673f-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="2673f-118">הוא לא אמור להכיל ערכים כפולים, ערכים ריקים או ערכים חסרים.</span><span class="sxs-lookup"><span data-stu-id="2673f-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="הגדר את נתוני הפעילות עם שם, ישות ומפתח ראשי.":::

1. <span data-ttu-id="2673f-120">בחר **הבא** כדי לעבור לשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="2673f-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="2673f-121">בשלב **קשר**, קבע את תצורת הפרטים לחיבור נתוני הפעילות שלך ללקוח המתאים.</span><span class="sxs-lookup"><span data-stu-id="2673f-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="2673f-122">שלב זה מציג באופן חזותי את הקשר בין ישויות.</span><span class="sxs-lookup"><span data-stu-id="2673f-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="2673f-123">**ראשון**: שדה זר בישות הפעילות שלך שישמש ליצירת קשר עם ישות אחרת.</span><span class="sxs-lookup"><span data-stu-id="2673f-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="2673f-124">**שני**: ישות לקוח מקור מתאימה שאיתה ישות הפעילות שלך תהיה בקשר.</span><span class="sxs-lookup"><span data-stu-id="2673f-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="2673f-125">באפשרותך להתייחס רק לישויות לקוח מקור המשמשות בתהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="2673f-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="2673f-126">**שלישי**: אם קשר בין ישות פעילות זו לישות לקוח המקור שנבחרה כבר קיים, שם הקשר יהיה במצב לקריאה בלבד.</span><span class="sxs-lookup"><span data-stu-id="2673f-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="2673f-127">אם לא קיים קשר כזה, ייווצר קשר חדש עם השם שאתה מספק בתיבה זו.</span><span class="sxs-lookup"><span data-stu-id="2673f-127">If there no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="הגדר את קשר הישות.":::

1. <span data-ttu-id="2673f-129">בחר **הבא** כדי לעבור לשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="2673f-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="2673f-130">בשלב **איחוד פעילות**, בחר את אירוע הפעילות ואת שעת ההתחלה של הפעילות שלך.</span><span class="sxs-lookup"><span data-stu-id="2673f-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="2673f-131">**שדות נדרשים**</span><span class="sxs-lookup"><span data-stu-id="2673f-131">**Required fields**</span></span>
      1. <span data-ttu-id="2673f-132">**פעילות אירוע**: שדה שהוא האירוע עבור פעילות זו</span><span class="sxs-lookup"><span data-stu-id="2673f-132">**Event activity**: Field that is the event for this activity</span></span>
      2. <span data-ttu-id="2673f-133">**חותמת זמן**: שדה המייצג את שעת ההתחלה של הפעילות שלך.</span><span class="sxs-lookup"><span data-stu-id="2673f-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="2673f-134">**שדות אופציונליים**</span><span class="sxs-lookup"><span data-stu-id="2673f-134">**Optional fields**</span></span>
      1. <span data-ttu-id="2673f-135">**פירוט נוסף**: שדה עם מידע רלוונטי עבור פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="2673f-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      2. <span data-ttu-id="2673f-136">**סמל**: סמל המייצג בצורה הטובה ביותר את סוג הפעילות הזה.</span><span class="sxs-lookup"><span data-stu-id="2673f-136">**Icon**: Icon that best represents this activity type.</span></span>
      3. <span data-ttu-id="2673f-137">**כתובת אינטרנט**: שדה המכיל כתובת URL עם מידע על פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="2673f-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="2673f-138">לדוגמה, מערכת העסקאות המקבלת פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="2673f-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="2673f-139">כתובת אתר זו יכולה להיות כל שדה מתוך מקור נתונים, או שהיא יכולה להיות בנויה כשדה חדש באמצעות המרה‬ של Power Query.</span><span class="sxs-lookup"><span data-stu-id="2673f-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="2673f-140">נתוני כתובת ה- URL יאוחסנו בישות *פעילות מאוחדת*, שניתן לצרוך במורד הזרם באמצעות [ממשקי API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="2673f-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="ציין את נתוני פעילות הלקוח בישות 'פעילות מאוחדת'.":::

1. <span data-ttu-id="2673f-142">בחר **הבא** כדי לעבור לשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="2673f-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="2673f-143">באפשרותך לבחור **סיים ובדוק** כדי לשמור את הפעילות כעת כשסוג הפעילות מוגדר ל **אחר**.</span><span class="sxs-lookup"><span data-stu-id="2673f-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="2673f-144">בשלב **סוג פעילות**, בחר את סוג הפעילות ולבחירתך, בחר אם ברצונל למפות באופן סמנטי חלק מסוגי הפעילות לשימוש באזורים אחרים של Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2673f-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="2673f-145">לעת עתה, סוגי הפעילות *מנוי* & *שורת הזמנת מכירות* ניתנים למיפוי באופן סמנטי לאחר ההסכמה למפות את השדות.</span><span class="sxs-lookup"><span data-stu-id="2673f-145">Currently, *Subscription* & *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="2673f-146">אם סוג פעילות אינו רלוונטי לפעילות החדשה, באפשרותך לבחור *אחר* או *צור חדש* עבור סוג פעילות מותאם אישית.</span><span class="sxs-lookup"><span data-stu-id="2673f-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="2673f-147">בחר **הבא** כדי לעבור לשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="2673f-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="2673f-148">בשלב **סקירה**, אמת את הבחירות שלך.</span><span class="sxs-lookup"><span data-stu-id="2673f-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="2673f-149">עליך לחזור לכל אחד מהשלבים הקודמים ולעדכן את המידע, במידת הצורך.</span><span class="sxs-lookup"><span data-stu-id="2673f-149">You go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="סקור את השדות שצוינו עבור פעילות.":::
   
1. <span data-ttu-id="2673f-151">בחר **שמור פעילות** כדי להחיל את השינויים שלך ובחר **בוצע** כדי לחזור אל **נתונים** > **פעילויות**.</span><span class="sxs-lookup"><span data-stu-id="2673f-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="2673f-152">כאן תראה אילו פעילויות מוגדרות להצגה בציר הזמן.</span><span class="sxs-lookup"><span data-stu-id="2673f-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="2673f-153">בדף **פעילויות**, בחר **הפעל** כדי לעבד את הפעילות.</span><span class="sxs-lookup"><span data-stu-id="2673f-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="2673f-154">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="2673f-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2673f-155">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2673f-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2673f-156">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="2673f-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2673f-157">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="2673f-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="2673f-158">ניהול פעילויות קיימות</span><span class="sxs-lookup"><span data-stu-id="2673f-158">Manage existing activities</span></span>

<span data-ttu-id="2673f-159">ב **נתונים** > **פעילויות**, באפשרותך להציג את כל הפעילויות ששמרת ולנהל אותן.</span><span class="sxs-lookup"><span data-stu-id="2673f-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="2673f-160">כל פעילות מיוצגת על-ידי שורה הכוללת גם פרטים על המקור, הישות וסוג הפעילות.</span><span class="sxs-lookup"><span data-stu-id="2673f-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="2673f-161">הפעולות הבאות זמינות בעת בחירה בפעילות.</span><span class="sxs-lookup"><span data-stu-id="2673f-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="2673f-162">**עריכה**: פתיחת הגדרת הפעילות בשלב הסקירה.</span><span class="sxs-lookup"><span data-stu-id="2673f-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="2673f-163">באפשרותך לשנות כל פרט תצורה או את כל התצורה דרך שלב זה.</span><span class="sxs-lookup"><span data-stu-id="2673f-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="2673f-164">לאחר שינוי התצורה, בחר **שמור פעילות** ולאחר מכן בחר **הפעל** כדי לעבד את השינויים.</span><span class="sxs-lookup"><span data-stu-id="2673f-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="2673f-165">**שינוי שם**: פתיחת תיבת דו-שיח שבה ניתן להזין שם שונה עבור הפעילות שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="2673f-165">**Rename**: Opens a dialog where to enter a different name for the selected activity.</span></span> <span data-ttu-id="2673f-166">בחר **שמור** כדי להחיל את השינויים.</span><span class="sxs-lookup"><span data-stu-id="2673f-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="2673f-167">**מחיקה**: פתיחת תיבת דו-שיח לאישור המחיקה של הפעילות שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="2673f-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="2673f-168">באפשרותך גם למחוק יותר מפעילות אחת בבת אחת על-ידי בחירת הפעילויות ולאחר מכן בחירת סמל המחיקה.</span><span class="sxs-lookup"><span data-stu-id="2673f-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="2673f-169">בחר **מחק** כדי לאשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="2673f-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
