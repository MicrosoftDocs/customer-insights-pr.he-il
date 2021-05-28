---
title: פלחים מוצעים על סמך פעילות.
description: אפשר ללמידת מכונה לעזור לך למצוא פלחים חדשים ומעניינים על סמך פעילות של לקוחות.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034077"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="f4edb-103">פלחים מוצעים על סמך נתוני פעילות (גירסת Preview)</span><span class="sxs-lookup"><span data-stu-id="f4edb-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="f4edb-104">גלה פלחים מעניינים של הלקוחות שלך על סמך נתוני פעילות של לקוחות ש- Customer Insights מעבד.</span><span class="sxs-lookup"><span data-stu-id="f4edb-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="f4edb-105">דוגמאות לנתוני פעילות הן עסקאות, משך שיחת תמיכה, רכישות או החזרות.</span><span class="sxs-lookup"><span data-stu-id="f4edb-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="f4edb-106">כדי להציע פלחים, מתבצע ניתוח של נתוני הפעילות מבחינת עדכניות, תדירות וערך כספי (או משך).</span><span class="sxs-lookup"><span data-stu-id="f4edb-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="f4edb-107">לחלופין, תוכל ליצור [פלחים מוצעים לשיפור המדדים או להבנה טובה יותר של הגורמים המשפיעים על תכונה](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="f4edb-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="הכרטיסיה 'פלחים מוצעים' מציגה הצעות לפלחים עבור פלחים מבוססי פעילות ומבוססי תכונות.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="f4edb-109">סיווג לקוחות לפי פעילות</span><span class="sxs-lookup"><span data-stu-id="f4edb-109">Categorize customers by activity</span></span>

<span data-ttu-id="f4edb-110">כאשר [נתוני פעילות](activities.md) זמינים ב- Customer Insights, אנו יכולים ליצור הצעות שמייצגות קבוצות של לקוחות:</span><span class="sxs-lookup"><span data-stu-id="f4edb-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="f4edb-111">הלקוחות הפעילים ביותר</span><span class="sxs-lookup"><span data-stu-id="f4edb-111">most active customers</span></span> 
- <span data-ttu-id="f4edb-112">לקוחות שביצעו הכי הרבה רכישות</span><span class="sxs-lookup"><span data-stu-id="f4edb-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="f4edb-113">לקוחות שהניבו הכי הרבה הכנסות</span><span class="sxs-lookup"><span data-stu-id="f4edb-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="f4edb-114">לקוחות שלא היו פעילים לאחרונה</span><span class="sxs-lookup"><span data-stu-id="f4edb-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="f4edb-115">לקוחות שמקיימים אינטראקציה עם העסק שלך לעתים קרובות</span><span class="sxs-lookup"><span data-stu-id="f4edb-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="f4edb-116">אם יש לך עסק קמעונאי, תוכל לגלות אילו לקוחות מניבים הכי הרבה הכנסות ולתגמל אותם בשובר.</span><span class="sxs-lookup"><span data-stu-id="f4edb-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="f4edb-117">לחלופין, תוכל לזהות לקוחות מזדמנים ולהציע להם להצטרף לתוכנית תגמולים כדי שהם יבקרו בעסק שלך לעתים קרובות יותר.</span><span class="sxs-lookup"><span data-stu-id="f4edb-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="f4edb-118">אם אתה בעסקי בריאות המספקים שירותי בריאות לציבור והמטרה שלך היא למזער את ההוצאות עבור מטופלים בודדים.</span><span class="sxs-lookup"><span data-stu-id="f4edb-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="f4edb-119">אחת הדרכים לעשות זאת היא לצמצם את הביקורים החוזרים על-ידי מתן הטיפול המיטבי ביותר במספר ביקורים נמוך ככל האפשר.</span><span class="sxs-lookup"><span data-stu-id="f4edb-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="f4edb-120">במקרה זה, המטרה שלך היא לשמור על תדירות נמוכה של ביקורים ולמזער את העלות החוזרת עבור המטופלים.</span><span class="sxs-lookup"><span data-stu-id="f4edb-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="f4edb-121">לחלופין, תוכל לזהות פלחים של מטופלים שיש להם תורים תכופים ועלויות חוזרות גבוהות ולנתח את המקרים הללו לשיפור הטיפול בפרט.</span><span class="sxs-lookup"><span data-stu-id="f4edb-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="f4edb-122">נתונים נדרשים</span><span class="sxs-lookup"><span data-stu-id="f4edb-122">Required data</span></span>

<span data-ttu-id="f4edb-123">ההצעות נוצרות על סמך נתוני הקלט שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="f4edb-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="f4edb-124">פרופילי לקוחות: כל הלקוחות או החברים של פלח ספציפי.</span><span class="sxs-lookup"><span data-stu-id="f4edb-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="f4edb-125">פרק זמן: בחודש שעבר, בשנה שעברה, או בכל מסגרת זמן מותאמת אישית.</span><span class="sxs-lookup"><span data-stu-id="f4edb-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="f4edb-126">סוג פעילות: רכישות, עסקאות קמעונאיות, עסקאות מקוונות, מקרי תמיכה בלקוחות, מנויים וכן הלאה.</span><span class="sxs-lookup"><span data-stu-id="f4edb-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="f4edb-127">ישות ב- Customer Insights המכילה את נתוני הפעילות: הישות UnifiedActivity או הישות לפעילות ספציפית.</span><span class="sxs-lookup"><span data-stu-id="f4edb-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="f4edb-128">ממדים שיש לכלול: עדכניות, תדירות או ממד כספי, בהתאם לדרישות העסק שלך.</span><span class="sxs-lookup"><span data-stu-id="f4edb-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="f4edb-129">יצירת פלחים מוצעים</span><span class="sxs-lookup"><span data-stu-id="f4edb-129">Generate suggested segments</span></span>

1. <span data-ttu-id="f4edb-130">עבור אל **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="f4edb-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="f4edb-131">בחר את הכרטיסיה **הצעות (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="f4edb-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="f4edb-132">בחר **חפש הצעות חדשות** ובחר **ראה או צפה את התנהגות הלקוח‬**.</span><span class="sxs-lookup"><span data-stu-id="f4edb-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="f4edb-133">בחר **התחל** כדי להפעיל את החוויה המודרכת.</span><span class="sxs-lookup"><span data-stu-id="f4edb-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="השלב הראשון של אשף קביעת התצורה עבור פלח מוצע על סמך פעילות.":::

1. <span data-ttu-id="f4edb-135">ספק את נתוני הקלט הנדרשים ובחר **הבא** כדי להמשיך.</span><span class="sxs-lookup"><span data-stu-id="f4edb-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="f4edb-136">בחר לקוחות: כלול את כל הלקוחות או פלח ספציפי.</span><span class="sxs-lookup"><span data-stu-id="f4edb-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="f4edb-137">בחר פעילות: בחר את סוג הפעילות ואת הישויות המתארים את הפעילות.</span><span class="sxs-lookup"><span data-stu-id="f4edb-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="f4edb-138">העדפות: הגדר את פרק הזמן שיש לקחת בחשבון, את הגורמים להצעות ומפה את התכונות.</span><span class="sxs-lookup"><span data-stu-id="f4edb-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="f4edb-139">עיין בקלט שלך ובחר **הפעל** כדי להפעיל את המודל וליצור הצעות.</span><span class="sxs-lookup"><span data-stu-id="f4edb-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="f4edb-140">בהתאם למספר פרופילי הלקוח והפעילויות שנבחרו, השלמת הפעולה עשויה להימשך מספר דקות.</span><span class="sxs-lookup"><span data-stu-id="f4edb-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="f4edb-141">לאחר יצירת ההצעות, תוכל לסנן אותן לפי הממד או הערך שאתה הכי מעוניין בו.</span><span class="sxs-lookup"><span data-stu-id="f4edb-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="f4edb-142">הצגת פרטים של פלח מוצע</span><span class="sxs-lookup"><span data-stu-id="f4edb-142">View details of a suggested segment</span></span>

<span data-ttu-id="f4edb-143">לאחר יצירת ההצעות, תמצא אותן ברשימה **פלחים** > **הצעות (Preview)** במקטע **הצעות מבוססות פעילות**.</span><span class="sxs-lookup"><span data-stu-id="f4edb-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="חלונית צד מורחבת מציגה נתונים מפורטים של פלח מוצע.":::

<span data-ttu-id="f4edb-145">בחר **ראה הצעה** בפלח מוצע כדי להציג את הפרטים של אותו פלח.</span><span class="sxs-lookup"><span data-stu-id="f4edb-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="f4edb-146">חלונית הצד מספקת פרטים כמו היקף כל ממד בהשוואה לקבוצת היעד.</span><span class="sxs-lookup"><span data-stu-id="f4edb-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="f4edb-147">היא גם מדגישה את מספר החברים הפוטנציאליים בפלח ואת האחוז המקביל של כלל הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="f4edb-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="f4edb-148">אם ברצונך לשמור את ההצעה כפלח, בחר **צור פלח**.</span><span class="sxs-lookup"><span data-stu-id="f4edb-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="f4edb-149">שמירת הצעה כפלח</span><span class="sxs-lookup"><span data-stu-id="f4edb-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="f4edb-150">עבור אל **פלחים** > **הצעות (Preview)**.</span><span class="sxs-lookup"><span data-stu-id="f4edb-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="f4edb-151">בחר את הפלח שברצונך לשמור.</span><span class="sxs-lookup"><span data-stu-id="f4edb-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="f4edb-152">בחלונית הצד, בחר **צור פלח**.</span><span class="sxs-lookup"><span data-stu-id="f4edb-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="f4edb-153">לאחר שמירת הפלח, הוא יופיע ברשימת הפלחים בכרטיסיה **כל הפלחים**. כעת ניתן [לרענן או למחוק אותו בדומה לכל פלח אחר](segments.md).</span><span class="sxs-lookup"><span data-stu-id="f4edb-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="f4edb-154">לא ניתן לערוך את פרטי הפלח.</span><span class="sxs-lookup"><span data-stu-id="f4edb-154">You can't edit the segment details.</span></span> <span data-ttu-id="f4edb-155">עם זאת, ניתן לשנות את קריטריוני הקלט עבור ההצעות וליצור הצעות שונות.</span><span class="sxs-lookup"><span data-stu-id="f4edb-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="f4edb-156">רענון או עריכה של ערכת הצעות</span><span class="sxs-lookup"><span data-stu-id="f4edb-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="f4edb-157">עבור אל **פלחים** > **הצעות (Preview)** וחפש את הפלח במקטע **הצעות מבוססות פעילות**.</span><span class="sxs-lookup"><span data-stu-id="f4edb-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="f4edb-158">בחר **רענן הצעות** כדי לרענן את ההצעות תוך שמירת התכונות המוגדרות.</span><span class="sxs-lookup"><span data-stu-id="f4edb-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="f4edb-159">לחלופין, בחר **ערוך הצעות** כדי לשנות את התכונות שהוגדרו.</span><span class="sxs-lookup"><span data-stu-id="f4edb-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="f4edb-160">המערכת תפעיל מחדש את התהליך, תיצור הצעות לפלחים על סמך הנתונים העדכניים ביותר ותחליף את ההצעות הנוכחיות.</span><span class="sxs-lookup"><span data-stu-id="f4edb-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
