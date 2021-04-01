---
title: שילוב נתוני אינטרנט מתובנות מעורבות עם Audience Insights
description: ספק מידע אינטרנט על לקוחות מתובנות מעורבות ל- Audience Insights.
ms.date: 12/17/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 14ebff30d3ec7fc52dca6f86136309a3f454fa27
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597466"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="f6d56-103">שילוב נתוני אינטרנט מתובנות מעורבות עם Audience Insights</span><span class="sxs-lookup"><span data-stu-id="f6d56-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="f6d56-104">לקוחות מבצעים לעתים קרובות את העסקאות היומיומיות שלהם באופן מקוון באמצעות אתרי אינטרנט.</span><span class="sxs-lookup"><span data-stu-id="f6d56-104">Customers often do their day to day transactions online using web sites.</span></span> <span data-ttu-id="f6d56-105">יכולת תובנות המעורבות ב- Dynamics 365 Customer Insights היא פתרון שימושי לשילוב נתוני אינטרנט כמקור.</span><span class="sxs-lookup"><span data-stu-id="f6d56-105">The engagement insights capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="f6d56-106">בנוסף לנתונים עסקיים, דמוגרפיים או התנהגותיים, ניתן לראות פעילויות באינטרנט בפרופילי הלקוחות המאוחדים.</span><span class="sxs-lookup"><span data-stu-id="f6d56-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="f6d56-107">אנחנו יכולים להשתמש בפרופיל זה כדי להשיג תובנות נוספות כגון פלחים, מדדים או חיזויים עבור הפעלת קהל.</span><span class="sxs-lookup"><span data-stu-id="f6d56-107">We can use this profile to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="f6d56-108">מאמר זה מתאר את השלבים להבאת נתוני הפעילות באינטרנט של לקוחותיך מתובנות מעורבות לסביבת Audience Insights הקיימת שלך.</span><span class="sxs-lookup"><span data-stu-id="f6d56-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="f6d56-109">בדוגמה זו, אנחנו מניחים סביבה המכילה פרופילי לקוחות מאוחדים.</span><span class="sxs-lookup"><span data-stu-id="f6d56-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="f6d56-110">הפרופילים אוחדו עם מקורות מסקרים, מכירות קמעונאיות ומערכת כרטיסים.</span><span class="sxs-lookup"><span data-stu-id="f6d56-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="f6d56-111">הם מציגים גם את הפעילויות הקשורות של הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="f6d56-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="f6d56-112">כעת אנחנו רוצים לדעת אם לקוח מבקר בנכסי האינטרנט שלנו ולהבין את הפעילויות שלו.</span><span class="sxs-lookup"><span data-stu-id="f6d56-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="f6d56-113">הפעילויות כוללות, למשל, אתרים שביקרו בהם או דפי מוצר שהוצגו מקישור שהתקבל בדוא"ל.</span><span class="sxs-lookup"><span data-stu-id="f6d56-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6d56-114">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="f6d56-114">Prerequisites</span></span>

<span data-ttu-id="f6d56-115">כדי לשלב נתונים מתובנות לגבי מעורבות, מספר תנאים מוקדמים צריכים להתקיים:</span><span class="sxs-lookup"><span data-stu-id="f6d56-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="f6d56-116">שלב את ה- SDK של התובנות לגבי מעורבות עם אתר האינטרנט שלך.</span><span class="sxs-lookup"><span data-stu-id="f6d56-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="f6d56-117">לקבלת מידע נוסף, ראה [תחילת העבודה עם ה- SDK של האינטרנט](../engagement-insights/instrument-website.md).</span><span class="sxs-lookup"><span data-stu-id="f6d56-117">For more information, see [Get started with the web SDK](../engagement-insights/instrument-website.md).</span></span>
- <span data-ttu-id="f6d56-118">ייצוא אירועי אינטרנט מתובנות לגבי מעורבות דרוש גישה לחשבון אחסון ADLS Gen 2 שישמש לקליטת הנתונים של אירועי האינטרנט ל- audience insights.</span><span class="sxs-lookup"><span data-stu-id="f6d56-118">Exporting web events from engagement insights requires access to an ADLS Gen 2 storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="f6d56-119">לקבלת מידע נוסף, ראה [יצא אירועים](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="f6d56-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="f6d56-120">קביעת תצורה של אירועים ממוקדים בתובנות לגבי מעורבות</span><span class="sxs-lookup"><span data-stu-id="f6d56-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="f6d56-121">לאחר שמנהל מערכת יצר אתר אינטרנט עם ה- SDK של התובנות לגבי מעורבות, *אירועי בסיס* נאספים כאשר משתמש מציג דף אינטרנט או לוחץ במקום כלשהו.</span><span class="sxs-lookup"><span data-stu-id="f6d56-121">After an administrator instrumented a website with the engagement insights SDK, *base events* are gathered when a user views a web page or clicks somewhere.</span></span> <span data-ttu-id="f6d56-122">אירועי בסיס נוטים להכיל פרטים רבים.</span><span class="sxs-lookup"><span data-stu-id="f6d56-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="f6d56-123">בהתאם למקרה השימוש שלך, אתה זקוק רק לערכת משנה של הנתונים באירוע בסיס.</span><span class="sxs-lookup"><span data-stu-id="f6d56-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="f6d56-124">תובנות לגבי מעורבות מאפשרות לך ליצור *אירועים ממוקדים* המכילים רק את המאפיינים של אירוע בסיס שאתה בוחר.</span><span class="sxs-lookup"><span data-stu-id="f6d56-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="f6d56-125">לקבלת מידע נוסף, ראה [יצירה ושינוי של אירועים ממוקדים](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="f6d56-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="f6d56-126">שיקולים בעת יצירת אירועים ממוקדים:</span><span class="sxs-lookup"><span data-stu-id="f6d56-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="f6d56-127">ספק שם בעל משמעות לאירוע הממוקד.</span><span class="sxs-lookup"><span data-stu-id="f6d56-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="f6d56-128">הוא ישמש כשם פעילות ב- audience insights.</span><span class="sxs-lookup"><span data-stu-id="f6d56-128">It's be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="f6d56-129">בחר לפחות את המאפיינים הבאים כדי ליצור פעילות ב- audience insights:</span><span class="sxs-lookup"><span data-stu-id="f6d56-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="f6d56-130">Signal.Action.Name - מציין את פרטי הפעילות</span><span class="sxs-lookup"><span data-stu-id="f6d56-130">Signal.Action.Name - indicating the activity details</span></span>
    - <span data-ttu-id="f6d56-131">Signal.User.Id - משמש למיפוי עם מזהה הלקוח</span><span class="sxs-lookup"><span data-stu-id="f6d56-131">Signal.User.Id - used to map with the customer ID</span></span>
    - <span data-ttu-id="f6d56-132">Signal.View.Uri - משמש ככתובת אינטרנט כבסיס לפלחים או מדדים</span><span class="sxs-lookup"><span data-stu-id="f6d56-132">Signal.View.Uri - used as a web address as a basis for segments or measures</span></span>
    - <span data-ttu-id="f6d56-133">Signal.Export.Id - לשימוש כמפתח ראשי עבור אירועים</span><span class="sxs-lookup"><span data-stu-id="f6d56-133">Signal.Export.Id - to use as a primary key for events</span></span> <!-- system generated, do we need to list?-->
    - <span data-ttu-id="f6d56-134">Signal.Timestamp - לקביעת התאריך והשעה עבור הפעילות</span><span class="sxs-lookup"><span data-stu-id="f6d56-134">Signal.Timestamp - to determine the date and time for the activity</span></span>

<span data-ttu-id="f6d56-135">בחר את המסננים כדי להתמקד באירועים ובדפים החשובים עבור מקרה השימוש שלך.</span><span class="sxs-lookup"><span data-stu-id="f6d56-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="f6d56-136">בדוגמה זו נשתמש בשם הפעולה "קידום דוא"ל".</span><span class="sxs-lookup"><span data-stu-id="f6d56-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="f6d56-137">ייצוא אירועי האינטרנט הממוקדים</span><span class="sxs-lookup"><span data-stu-id="f6d56-137">Export the Refined Web Events</span></span> 

<span data-ttu-id="f6d56-138">לאחר הגדרת האירוע הממוקד, עליך לקבוע את תצורת הייצוא של נתוני האירוע ל- Azure Data Lake Storage, שניתן להגדרה כמקור נתונים עבור עיבוד ב- audience insights.</span><span class="sxs-lookup"><span data-stu-id="f6d56-138">After defining the refined event is defined, you have to configure the export of the event data to an Azure Data Lake Storage, that can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="f6d56-139">פעולות ייצוא מתרחשות ללא הרף כאשר האירועים זורמים מנכס האינטרנט.</span><span class="sxs-lookup"><span data-stu-id="f6d56-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="f6d56-140">לקבלת מידע נוסף, ראה [יצא אירועים](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="f6d56-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="f6d56-141">קליטת נתוני אירוע ל- audience insights</span><span class="sxs-lookup"><span data-stu-id="f6d56-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="f6d56-142">כעת, לאחר שהגדרת את האירוע הממוקד וקבעת את תצורת הייצוא שלו, אנחנו עוברים לקליטת הנתונים ל- audience insights.</span><span class="sxs-lookup"><span data-stu-id="f6d56-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="f6d56-143">עליך ליצור מקור נתונים חדש המבוסס על תיקיית Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="f6d56-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="f6d56-144">הזן את הפרטים עבור חשבון האחסון שאליו אתה מייצא את האירועים.</span><span class="sxs-lookup"><span data-stu-id="f6d56-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="f6d56-145">בקובץ *default.cdm.json*, בחר את האירוע הממוקד לקליטה וליצירה של הישות ב- audience insights.</span><span class="sxs-lookup"><span data-stu-id="f6d56-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="f6d56-146">לקבלת מידע נוסף, ראה [התחברות לתיקיית Common Data Model באמצעות חשבון Azure Data Lake](connect-common-data-model.md)</span><span class="sxs-lookup"><span data-stu-id="f6d56-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md)</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="f6d56-147">התייחסות לנתוני אירוע ממוקד כפעילות של פרופיל לקוח</span><span class="sxs-lookup"><span data-stu-id="f6d56-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="f6d56-148">לאחר השלמת קליטת הישות, באפשרותך לקבוע את תצורת הפעילות עבור פרופיל הלקוח.</span><span class="sxs-lookup"><span data-stu-id="f6d56-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="f6d56-149">למידע נוסף ראה [פעילויות של לקוחות](activities.md).</span><span class="sxs-lookup"><span data-stu-id="f6d56-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="דף פעילויות עם חלונית 'ערוך פעילות' ושדות מלאים.":::

<span data-ttu-id="f6d56-151">קבע את תצורת הפעילות החדשה עם המיפוי הבא:</span><span class="sxs-lookup"><span data-stu-id="f6d56-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="f6d56-152">**מפתח ראשי:** Signal.Export.Id, מזהה ייחודי הזמין עבור כל רשומת אירוע בתובנות לגבי מעורבות.</span><span class="sxs-lookup"><span data-stu-id="f6d56-152">**Primary Key:** Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="f6d56-153">מאפיין זה נוצר באופן אוטומטי.</span><span class="sxs-lookup"><span data-stu-id="f6d56-153">This property is automatically generated.</span></span>

- <span data-ttu-id="f6d56-154">**חותמת זמן:** Signal.Timestamp במאפיין האירוע.</span><span class="sxs-lookup"><span data-stu-id="f6d56-154">**Timestamp:** Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="f6d56-155">**אירוע:** Signal.Name, שם האירוע שברצונך לעקוב אחריו.</span><span class="sxs-lookup"><span data-stu-id="f6d56-155">**Event:** Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="f6d56-156">**כתובת אינטרנט:** Signal.View.Uri מתייחס ל- uri של הדף שיצר את האירוע.</span><span class="sxs-lookup"><span data-stu-id="f6d56-156">**Web address:** Signal.View.Uri referring to the uri of the page that created the event.</span></span>

- <span data-ttu-id="f6d56-157">**פרטים:** Signal.Action.Name לייצוג המידע שיש לשייך לאירוע.</span><span class="sxs-lookup"><span data-stu-id="f6d56-157">**Details:** Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="f6d56-158">המאפיין שנבחר במקרה זה מציין שהאירוע נועד לקידום דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="f6d56-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="f6d56-159">**סוג הפעילות:** בדוגמה זו, אנו בוחרים את סוג הפעילות הקיים WebLog.</span><span class="sxs-lookup"><span data-stu-id="f6d56-159">**Activity type:** In this example, we choose the exsting activity type WebLog.</span></span> <span data-ttu-id="f6d56-160">בחירה זו היא אפשרות סינון שימושית להפעלת מודלי חיזוי או ליצירת פלחים המבוססים על סוג פעילות זה.</span><span class="sxs-lookup"><span data-stu-id="f6d56-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="f6d56-161">**הגדר קשר:** הגדרה חשובה זו קושרת את הפעילות לפרופילי לקוחות קיימים.</span><span class="sxs-lookup"><span data-stu-id="f6d56-161">**Set up relationship:** This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="f6d56-162">**Signal.User.Id** הוא המזהה המוגדר ב- SDK לאיסוף ואשר מתקשר למזהה המשתמש במקורות נתונים אחרים המוגדרים ב- audience insights.</span><span class="sxs-lookup"><span data-stu-id="f6d56-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="f6d56-163">בדוגמה זו, אנחנו מגדירים את הקשר בין Signal.User.Id ו- RetailCustomers: CustomerRetailId, שהוא המפתח הראשי שהוגדר בשלב המיפוי של תהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="f6d56-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was deinfed in the map step of the data unification process.</span></span>


<span data-ttu-id="f6d56-164">לאחר עיבוד הפעילויות, תוכל לסקור את רשומות הלקוחות ולפתוח כרטיס לקוח כדי לראות פעילויות מתובנות לגבי מעורבות בציר הזמן.</span><span class="sxs-lookup"><span data-stu-id="f6d56-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="f6d56-165">כדי למצוא מזהה לקוח שיש לו פעילות תובנות לגבי מעורבות, עבור אל **ישויות** והצג בתצוגה מקדימה את הנתונים עבור הישות UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="f6d56-165">To find a customer id that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="f6d56-166">ActivityTypeDisplay‏ = WebLog המכיל את פעילות התובנות לגבי מעורבות שהוגדרה בדוגמה לעיל.</span><span class="sxs-lookup"><span data-stu-id="f6d56-166">ActivityTypeDisplay = WebLog contain the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="f6d56-167">העתק את מזהה הלקוח עבור אחת מאותן רשומות ועבור מזהה זה בדף **לקוחות**.</span><span class="sxs-lookup"><span data-stu-id="f6d56-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f6d56-168">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="f6d56-168">Next Steps</span></span>

<span data-ttu-id="f6d56-169">כעת באפשרותך ליצור [פלחים](segments.md), [מדדים](measures.md) ו[חיזויים](predictions.md) כדי ליצור קשר משמעותי עם הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="f6d56-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]