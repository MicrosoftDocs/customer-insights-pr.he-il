---
title: קליטת נתונים דרך מחבר Power Query
description: מחברים למקורות נתונים מבוססים על Power Query.
ms.date: 09/29/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 50c231070ff9930c1ea82971bf4f8541a89d5027
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305892"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="eba03-103">התחבר למקור נתונים של Power Query</span><span class="sxs-lookup"><span data-stu-id="eba03-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="eba03-104">Power Query מציע מערך רחב של מחברים לקליטת נתונים.</span><span class="sxs-lookup"><span data-stu-id="eba03-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="eba03-105">רוב המחברים הללו נתמכים על ידי Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eba03-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="eba03-106">הוספת מקורות נתונים המבוססים על מחברי Power Query בדרך כלל פועלת לפי השלבים המתוארים בסעיף הבא.</span><span class="sxs-lookup"><span data-stu-id="eba03-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="eba03-107">עם זאת, בהתאם למחבר שבו אתה משתמש, נדרש מידע שונה.</span><span class="sxs-lookup"><span data-stu-id="eba03-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="eba03-108">למידע נוסף, עיין בתיעוד של מחברים בודדים ב- [הפניית מחבר של Power Query](/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="eba03-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="eba03-109">צור מקור נתונים חדש</span><span class="sxs-lookup"><span data-stu-id="eba03-109">Create a new data source</span></span>

1. <span data-ttu-id="eba03-110">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="eba03-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="eba03-111">בחר **הוסף מקור נתונים**.</span><span class="sxs-lookup"><span data-stu-id="eba03-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="eba03-112">בחר את השיטה **ייבא נתונים** ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="eba03-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="eba03-113">הזן **שם** עבור מקור נתונים ובחר **הבא** כדי ליצור את מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="eba03-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="eba03-114">קווים מנחים של שם:</span><span class="sxs-lookup"><span data-stu-id="eba03-114">Name guidelines:</span></span> 
   - <span data-ttu-id="eba03-115">התחל עם אות.</span><span class="sxs-lookup"><span data-stu-id="eba03-115">Start with a letter.</span></span>
   - <span data-ttu-id="eba03-116">השתמש באותיות ומספרים בלבד.</span><span class="sxs-lookup"><span data-stu-id="eba03-116">Use letters and numbers only.</span></span> <span data-ttu-id="eba03-117">אסור להזין תווים מיוחדים ורווחים.</span><span class="sxs-lookup"><span data-stu-id="eba03-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="eba03-118">השתמש בין 3 ל- 64 תווים.</span><span class="sxs-lookup"><span data-stu-id="eba03-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="eba03-119">בחר אחד [מהמחברים הזמינים](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="eba03-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="eba03-120">בדוגמה זו אנו בוחרים את המחבר **טקסט/CSV**.</span><span class="sxs-lookup"><span data-stu-id="eba03-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="eba03-121">הזן את הפרטים הנדרשים ב- **הגדרות חיבור** עבור המחבר שנבחר ובחר **הבא** כדי לראות תצוגה מקדימה של הנתונים.</span><span class="sxs-lookup"><span data-stu-id="eba03-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="eba03-122">בחר **המרת נתונים**.</span><span class="sxs-lookup"><span data-stu-id="eba03-122">Select **Transform data**.</span></span> <span data-ttu-id="eba03-123">בשלב זה תוסיף ישויות למקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="eba03-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="eba03-124">ישויות הן מערכי נתונים.</span><span class="sxs-lookup"><span data-stu-id="eba03-124">Entities are datasets.</span></span> <span data-ttu-id="eba03-125">אם ברשותך מסד נתונים הכולל ערכות נתונים מרובות, כל ערכת נתונים היא ישות בפני עצמה.</span><span class="sxs-lookup"><span data-stu-id="eba03-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="eba03-126">תיבת הדו-שיח **Power Query - ערוך שאילתות** מאפשרת לך לסקור ולחדד את הנתונים.</span><span class="sxs-lookup"><span data-stu-id="eba03-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="eba03-127">הישויות שהמערכות זיהו במקור הנתונים שבחרת מופיעות בחלונית הימנית.</span><span class="sxs-lookup"><span data-stu-id="eba03-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="eba03-128">![תיבת דו-שיח של עריכת שאילתות](media/data-manager-configure-edit-queries.png "תיבת דו-שיח של עריכת שאילתות")</span><span class="sxs-lookup"><span data-stu-id="eba03-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="eba03-129">באפשרותך גם לשנות את הנתונים שלך.</span><span class="sxs-lookup"><span data-stu-id="eba03-129">You can also transform your data.</span></span> <span data-ttu-id="eba03-130">בחר ישות לעריכה או להמרה.</span><span class="sxs-lookup"><span data-stu-id="eba03-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="eba03-131">השתמש באפשרויות בחלון Power Query כדי להחיל טרנספורמציות.</span><span class="sxs-lookup"><span data-stu-id="eba03-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="eba03-132">כל טרנספורמציה מופיעה בחלק **צעדים שבוצעו**.</span><span class="sxs-lookup"><span data-stu-id="eba03-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="eba03-133">Power Query מספק מספר אפשרויות טרנספורמציה שנבנו מראש.</span><span class="sxs-lookup"><span data-stu-id="eba03-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="eba03-134">לקבלת מידע נוסף, ראה [טרנספורמציות ב- Power Query](/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="eba03-134">For more information, see [Power Query Transformations](/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="eba03-135">באפשרותך להוסיף ישויות נוספות למקור הנתונים על-ידי בחירה באפשרות **קבל נתונים** בתיבת הדו-שיח **עריכת שאילתות**.</span><span class="sxs-lookup"><span data-stu-id="eba03-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="eba03-136">המרות אלה מומלצות מאוד:</span><span class="sxs-lookup"><span data-stu-id="eba03-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="eba03-137">אם אתה קולט נתונים מקובץ CSV, השורה הראשונה מכילה לעיתים קרובות כותרות.</span><span class="sxs-lookup"><span data-stu-id="eba03-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="eba03-138">עבור אל **טרנספורמציה של טבלה** ובחר **השתמש בכותרות כשורה ראשונה**.</span><span class="sxs-lookup"><span data-stu-id="eba03-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="eba03-139">ודא שסוג הנתונים מוגדר כראוי.</span><span class="sxs-lookup"><span data-stu-id="eba03-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="eba03-140">בחר **שמור** בחלק התחתון של חלון Power Query כדי לשמור את הטרנספורמציות.</span><span class="sxs-lookup"><span data-stu-id="eba03-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="eba03-141">לאחר השמירה, תמצא את מקור הנתונים בחלק **נתונים** > **מקורות מידע**.</span><span class="sxs-lookup"><span data-stu-id="eba03-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="eba03-142">בדף **מקורות מידע** תראה שמקור הנתונים החדש נמצא במצב **רענון**.</span><span class="sxs-lookup"><span data-stu-id="eba03-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="eba03-143">מקורות נתונים זמינים של Power Query</span><span class="sxs-lookup"><span data-stu-id="eba03-143">Available Power Query data sources</span></span>

<span data-ttu-id="eba03-144">ראה את [הפניה למחבר Power Query](/power-query/connectors/) לקבלת רשימה עדכנית של מחברים שתוכל לבחור לייבא נתונים ל- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="eba03-144">See the [Power Query connector reference](/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="eba03-145">מחברים עם סימן ביקורת בעמודה **Customer Insights (זרימות נתונים)** זמינים ליצירת מקורות נתונים חדשים המבוססים על Power Query.</span><span class="sxs-lookup"><span data-stu-id="eba03-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="eba03-146">עיין בתיעוד של מחבר ספציפי כדי ללמוד עוד על התנאים המוקדמים שלו, המגבלות ופרטים אחרים.</span><span class="sxs-lookup"><span data-stu-id="eba03-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="eba03-147">ערוך מקורות נתונים זמינים של Power Query</span><span class="sxs-lookup"><span data-stu-id="eba03-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="eba03-148">ייתכן שאין אפשרות לבצע שינויים במקורות נתונים הנמצאים כעת בשימוש באחד מתהליכי היישום (*פילוח*, *התאמה* או *מיזוג*, לדוגמה).</span><span class="sxs-lookup"><span data-stu-id="eba03-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="eba03-149">בדף **הגדרות**, באפשרותך לעקוב אחר ההתקדמות של כל אחד מהתהליכים הפעילים.</span><span class="sxs-lookup"><span data-stu-id="eba03-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="eba03-150">כאשר תהליך הושלם, באפשרותך לחזור לדף **מקורות הנתונים** ולבצע את השינויים.</span><span class="sxs-lookup"><span data-stu-id="eba03-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="eba03-151">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="eba03-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="eba03-152">בחר את שלוש הנקודות האנכיות לצד מקור נתונים שברצונך לשנות ובחר **עריכה** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="eba03-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the dropdown menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="eba03-153">![ערוך אפשרות](media/edit-option-data-sources.png "ערוך אפשרות")</span><span class="sxs-lookup"><span data-stu-id="eba03-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="eba03-154">החל את השינויים והטרנספורמציות שלך בדו-שיח **Power Query - ערוך שאילתות** כפי שמתואר בסעיף [צור מקור נתונים חדש](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="eba03-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="eba03-155">בחר **שמור** ב- Power Query לאחר השלמת העריכות כדי לשמור את השינויים שעשית.</span><span class="sxs-lookup"><span data-stu-id="eba03-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]