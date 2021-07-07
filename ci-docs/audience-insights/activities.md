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
ms.openlocfilehash: 342aeb33f652d5d60cd25e13969766954bf56370
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304927"
---
# <a name="customer-activities"></a><span data-ttu-id="eb8eb-103">פעילויות של לקוחות</span><span class="sxs-lookup"><span data-stu-id="eb8eb-103">Customer activities</span></span>

<span data-ttu-id="eb8eb-104">שלב פעילויות לקוחות מ[מקורות נתונים שונים](data-sources.md) ב- Dynamics 365 Customer Insights כדי ליצור ציר זמן המפרט את הפעילויות באופן כרונולוגי.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a timeline that lists the activities chronologically.</span></span> <span data-ttu-id="eb8eb-105">כלול את ציר הזמן ביישומי Dynamics 365 עם הפתרון [תוספת כרטיס לקוח](customer-card-add-in.md), או בלוח המחוונים של Power BI.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-105">Include the timeline in Dynamics 365 apps with the [Customer Card add-in](customer-card-add-in.md) solution, or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="eb8eb-106">הגדרת פעילות</span><span class="sxs-lookup"><span data-stu-id="eb8eb-106">Define an activity</span></span>

<span data-ttu-id="eb8eb-107">מקורות הנתונים שלך יכולים לכלול ישויות עם נתוני עסקאות ופעילות ממקורות נתונים מרובים.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-107">Your data sources can include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="eb8eb-108">זהה ישויות אלה ובחר את הפעילויות שתרצה להציג בציר הזמן של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="eb8eb-109">בחר את הישות הכוללת את פעילות או פעילויות היעד שלך.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-109">Choose the entity that includes your target activity or activities.</span></span>

> [!NOTE]
> <span data-ttu-id="eb8eb-110">ישות מוכרחה לכלול תכונה אחת לפחות מסוג **תאריך** כדי שתיכלל בציר זמן של לקוח ואין באפשרותך להוסיף ישויות ללא שדות **תאריך**.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-110">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="eb8eb-111">הפקד **הוסף פעילות** מושבת אם לא נמצאה ישות כזאת.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-111">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="eb8eb-112">ב- audience insights, עבור אל **נתונים** > **פעילויות**.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-112">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="eb8eb-113">בחר **הוסף פעילות** כדי להתחיל את החוויה המודרכת עבור תהליך הגדרת הפעילות.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-113">Select **Add activity** to start the guided experience for the activity setup process.</span></span>

1. <span data-ttu-id="eb8eb-114">בשלב **נתוני פעילות**, הגדר את הערכים עבור השדות הבאים:</span><span class="sxs-lookup"><span data-stu-id="eb8eb-114">In the **Activity data** step, set the values for the following fields:</span></span>

   - <span data-ttu-id="eb8eb-115">**שם פעילות**: בחר שם לפעילות שלך.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-115">**Activity name**: Select a name for your activity.</span></span>
   - <span data-ttu-id="eb8eb-116">**ישות**: בחר ישות הכוללת נתוני עסקאות או פעילות.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-116">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="eb8eb-117">**מפתח ראשי**: בחר את השדה המזהה באופן ייחודי רשומה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-117">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="eb8eb-118">הוא לא אמור להכיל ערכים כפולים, ערכים ריקים או ערכים חסרים.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-118">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="הגדר את נתוני הפעילות עם שם, ישות ומפתח ראשי.":::

1. <span data-ttu-id="eb8eb-120">בחר **הבא** כדי לעבור לשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-120">Select **Next** to go to the next step.</span></span>

1. <span data-ttu-id="eb8eb-121">בשלב **קשר**, קבע את תצורת הפרטים לחיבור נתוני הפעילות שלך ללקוח המתאים.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-121">In the **Relationship** step, configure the details to connect your activity data to its corresponding customer.</span></span> <span data-ttu-id="eb8eb-122">שלב זה מציג באופן חזותי את הקשר בין ישויות.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-122">This step visualizes the connection between entities.</span></span>  

   - <span data-ttu-id="eb8eb-123">**ראשון**: שדה זר בישות הפעילות שלך שישמש ליצירת קשר עם ישות אחרת.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-123">**First**: Foreign field in your activity entity that will be used to establish a relationship with another entity.</span></span>
   - <span data-ttu-id="eb8eb-124">**שני**: ישות לקוח מקור מתאימה שאיתה ישות הפעילות שלך תהיה בקשר.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-124">**Second**: Corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="eb8eb-125">באפשרותך להתייחס רק לישויות לקוח מקור המשמשות בתהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-125">You can only relate to source customer entities that are used in the data unification process.</span></span>
   - <span data-ttu-id="eb8eb-126">**שלישי**: אם קשר בין ישות פעילות זו לישות לקוח המקור שנבחרה כבר קיים, שם הקשר יהיה במצב לקריאה בלבד.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-126">**Third**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="eb8eb-127">אם לא קיים קשר כזה, ייווצר קשר חדש עם השם שתזין בתיבה זו.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-127">If no such relationship exists, a new relationship will be created with the name you provide in this box.</span></span>

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="הגדר את קשר הישות.":::

1. <span data-ttu-id="eb8eb-129">בחר **הבא** כדי לעבור לשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-129">Select **Next** to go to the next step.</span></span> 

1. <span data-ttu-id="eb8eb-130">בשלב **איחוד פעילות**, בחר את אירוע הפעילות ואת שעת ההתחלה של הפעילות שלך.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-130">In the **Activity unification** step, choose the activity event and the start time of your activity.</span></span> 
   - <span data-ttu-id="eb8eb-131">**שדות נדרשים**</span><span class="sxs-lookup"><span data-stu-id="eb8eb-131">**Required fields**</span></span>
      - <span data-ttu-id="eb8eb-132">**פעילות אירוע**: שדה שהוא האירוע עבור פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-132">**Event activity**: Field that is the event for this activity.</span></span>
      - <span data-ttu-id="eb8eb-133">**חותמת זמן**: שדה המייצג את שעת ההתחלה של הפעילות שלך.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-133">**Timestamp**: Field that represents the start time of your activity.</span></span>

   - <span data-ttu-id="eb8eb-134">**שדות אופציונליים**</span><span class="sxs-lookup"><span data-stu-id="eb8eb-134">**Optional fields**</span></span>
      - <span data-ttu-id="eb8eb-135">**פירוט נוסף**: שדה עם מידע רלוונטי עבור פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-135">**Additional detail**: Field with relevant information for this activity.</span></span>
      - <span data-ttu-id="eb8eb-136">**סמל**: סמל המייצג בצורה הטובה ביותר את סוג הפעילות הזה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-136">**Icon**: Icon that best represents this activity type.</span></span>
      - <span data-ttu-id="eb8eb-137">**כתובת אינטרנט**: שדה המכיל כתובת URL עם מידע על פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-137">**Web address**: Field containing a URL with information about this activity.</span></span> <span data-ttu-id="eb8eb-138">לדוגמה, מערכת העסקאות המקבלת פעילות זו.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-138">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="eb8eb-139">כתובת אתר זו יכולה להיות כל שדה מתוך מקור נתונים, או שהיא יכולה להיות בנויה כשדה חדש באמצעות המרה‬ של Power Query.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-139">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="eb8eb-140">נתוני כתובת ה- URL יאוחסנו בישות *פעילות מאוחדת*, שניתן לצרוך במורד הזרם באמצעות [ממשקי API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="eb8eb-140">The URL data will be stored in the *Unified Activity* entity, which can be consumed downstream using [APIs](apis.md).</span></span>
   
   :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="ציין את נתוני פעילות הלקוח בישות 'פעילות מאוחדת'.":::

1. <span data-ttu-id="eb8eb-142">בחר **הבא** כדי לעבור לשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-142">Select **Next** to move to the next step.</span></span> <span data-ttu-id="eb8eb-143">באפשרותך לבחור **סיים ובדוק** כדי לשמור את הפעילות כעת כשסוג הפעילות מוגדר ל **אחר**.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-143">You can select **Finish and review** to save the activity now with the activity type set to **Other**.</span></span> 

1. <span data-ttu-id="eb8eb-144">בשלב **סוג פעילות**, בחר את סוג הפעילות ולבחירתך, בחר אם ברצונל למפות באופן סמנטי חלק מסוגי הפעילות לשימוש באזורים אחרים של Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-144">In the **Activity Type** step, choose the activity type and optionally select if you want to semantically map some of the activity types for use in other areas of Customer Insights.</span></span> <span data-ttu-id="eb8eb-145">כיום, ניתן למפות את סוגי הפעילות *מינוי* ו *SalesOrderLine* לאחר הסכמה למפות את השדות.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-145">Currently, *Subscription* and *SalesOrderLine* activity types can be semantically mapped after agreeing to map the fields.</span></span> <span data-ttu-id="eb8eb-146">אם סוג פעילות אינו רלוונטי לפעילות החדשה, באפשרותך לבחור *אחר* או *צור חדש* עבור סוג פעילות מותאם אישית.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-146">If an activity type isn't relevant for the new activity, you can choose *Other* or *Create new* for a custom activity type.</span></span>

1. <span data-ttu-id="eb8eb-147">בחר **הבא** כדי לעבור לשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-147">Select **Next** to move to the next step.</span></span> 

1. <span data-ttu-id="eb8eb-148">בשלב **סקירה**, אמת את הבחירות שלך.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-148">In the **Review** step, verify your selections.</span></span> <span data-ttu-id="eb8eb-149">חזור לאחד השלבים הקודמים ועדכן את המידע במקרה הצורך.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-149">Go back to any of the previous steps and update the information if necessary.</span></span>

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="סקור את השדות שצוינו עבור פעילות.":::
   
1. <span data-ttu-id="eb8eb-151">בחר **שמור פעילות** כדי להחיל את השינויים שלך ובחר **בוצע** כדי לחזור אל **נתונים** > **פעילויות**.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-151">Select **Save activity** to apply your changes and select **Done** to go back to **Data** > **Activities**.</span></span> <span data-ttu-id="eb8eb-152">כאן תראה אילו פעילויות מוגדרות להצגה בציר הזמן.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-152">Here you see which activities are set to show in the timeline.</span></span> 

1. <span data-ttu-id="eb8eb-153">בדף **פעילויות**, בחר **הפעל** כדי לעבד את הפעילות.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-153">On the **Activities** page, select **Run** to process the activity.</span></span> 

> [!TIP]
> <span data-ttu-id="eb8eb-154">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-154">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="eb8eb-155">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="eb8eb-155">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="eb8eb-156">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-156">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="eb8eb-157">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-157">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>


## <a name="manage-existing-activities"></a><span data-ttu-id="eb8eb-158">ניהול פעילויות קיימות</span><span class="sxs-lookup"><span data-stu-id="eb8eb-158">Manage existing activities</span></span>

<span data-ttu-id="eb8eb-159">ב **נתונים** > **פעילויות**, באפשרותך להציג את כל הפעילויות ששמרת ולנהל אותן.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-159">On **Data** > **Activities**, you can view all your saved activities, and manage them.</span></span> <span data-ttu-id="eb8eb-160">כל פעילות מיוצגת על-ידי שורה הכוללת גם פרטים על המקור, הישות וסוג הפעילות.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-160">Each activity is represented by a row that also includes details about the source, the entity, and the activity type.</span></span>

<span data-ttu-id="eb8eb-161">הפעולות הבאות זמינות בעת בחירה בפעילות.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-161">The following actions are available when you select an activity.</span></span> 

- <span data-ttu-id="eb8eb-162">**עריכה**: פתיחת הגדרת הפעילות בשלב הסקירה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-162">**Edit**: Opens the activity setup on the review step.</span></span> <span data-ttu-id="eb8eb-163">באפשרותך לשנות כל פרט תצורה או את כל התצורה דרך שלב זה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-163">You can change any or all of the current configuration from this step.</span></span> <span data-ttu-id="eb8eb-164">לאחר שינוי התצורה, בחר **שמור פעילות** ולאחר מכן בחר **הפעל** כדי לעבד את השינויים.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-164">After changing the configuration, select **Save activity** and then select **Run** to process the changes.</span></span>

- <span data-ttu-id="eb8eb-165">**שנה שם**: פותח תיבת דו-שיח שבה ניתן להזין שם אחר עבור הפעילות שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-165">**Rename**: Opens a dialog where you can enter a different name for the selected activity.</span></span> <span data-ttu-id="eb8eb-166">בחר **שמור** כדי להחיל את השינויים.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-166">Select **Save** to apply your changes.</span></span>

- <span data-ttu-id="eb8eb-167">**מחיקה**: פתיחת תיבת דו-שיח לאישור המחיקה של הפעילות שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-167">**Delete**: Opens a dialog to confirm the deletion of the selected activity.</span></span> <span data-ttu-id="eb8eb-168">באפשרותך גם למחוק יותר מפעילות אחת בבת אחת על-ידי בחירת הפעילויות ולאחר מכן בחירת סמל המחיקה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-168">You can also delete more than one activity at once by selecting the activities and then selecting the delete icon.</span></span> <span data-ttu-id="eb8eb-169">בחר **מחק** כדי לאשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="eb8eb-169">Select **Delete** to confirm the deletion.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
