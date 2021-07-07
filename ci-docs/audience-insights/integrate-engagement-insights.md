---
title: שילוב נתוני אינטרנט מתובנות מעורבות עם Audience Insights
description: ספק מידע אינטרנט על לקוחות מתובנות מעורבות ל- Audience Insights.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305019"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a><span data-ttu-id="a8991-103">שילוב נתוני אינטרנט מתובנות מעורבות עם Audience Insights</span><span class="sxs-lookup"><span data-stu-id="a8991-103">Integrate web data from engagement insights with audience insights</span></span>

<span data-ttu-id="a8991-104">לקוחות מבצעים לעתים קרובות את העסקאות היומיומיות שלהם באופן מקוון באמצעות אתרי אינטרנט.</span><span class="sxs-lookup"><span data-stu-id="a8991-104">Customers often do their day-to-day transactions online using web sites.</span></span> <span data-ttu-id="a8991-105">יכולת התובנות לגבי מעורבות (Preview) ב- Dynamics 365 Customer Insights היא פיתרון שימושי לשילוב נתוני רשת כמקור.</span><span class="sxs-lookup"><span data-stu-id="a8991-105">The engagement insights (preview) capability in Dynamics 365 Customer Insights is a handy solution to integrate web data as a source.</span></span> <span data-ttu-id="a8991-106">בנוסף לנתונים עסקיים, דמוגרפיים או התנהגותיים, ניתן לראות פעילויות באינטרנט בפרופילי הלקוחות המאוחדים.</span><span class="sxs-lookup"><span data-stu-id="a8991-106">In addition to transactional, demographic, or behavioral data we can see activities on the web in unified customer profiles.</span></span> <span data-ttu-id="a8991-107">אנחנו יכולים להשתמש בפרופילים אלה כדי להשיג תובנות נוספות כגון פלחים, ממדים או חיזויים להפעלת קהל.</span><span class="sxs-lookup"><span data-stu-id="a8991-107">We can use these profiles to gain additional insights like segments, measures, or predictions for audience activation.</span></span>

<span data-ttu-id="a8991-108">מאמר זה מתאר את השלבים להבאת נתוני הפעילות באינטרנט של לקוחותיך מתובנות מעורבות לסביבת Audience Insights הקיימת שלך.</span><span class="sxs-lookup"><span data-stu-id="a8991-108">This article describes the steps to bring your customers’ web activity data from engagement insights into your existing audience insights environment.</span></span>

<span data-ttu-id="a8991-109">בדוגמה זו, אנחנו מניחים סביבה המכילה פרופילי לקוחות מאוחדים.</span><span class="sxs-lookup"><span data-stu-id="a8991-109">In this example, we assume an environment that contains unified customer profiles.</span></span> <span data-ttu-id="a8991-110">הפרופילים אוחדו עם מקורות מסקרים, מכירות קמעונאיות ומערכת כרטיסים.</span><span class="sxs-lookup"><span data-stu-id="a8991-110">The profiles were unified with sources from surveys, retail sales, and a ticketing system.</span></span> <span data-ttu-id="a8991-111">הם מציגים גם את הפעילויות הקשורות של הלקוחות.</span><span class="sxs-lookup"><span data-stu-id="a8991-111">It also shows the related activities of the customers.</span></span> 

<span data-ttu-id="a8991-112">כעת אנחנו רוצים לדעת אם לקוח מבקר בנכסי האינטרנט שלנו ולהבין את הפעילויות שלו.</span><span class="sxs-lookup"><span data-stu-id="a8991-112">We now want to know if a customer visits our web properties and understand their activities.</span></span> <span data-ttu-id="a8991-113">הפעילויות כוללות, למשל, אתרים שביקרו בהם או דפי מוצר שהוצגו מקישור שהתקבל בדוא"ל.</span><span class="sxs-lookup"><span data-stu-id="a8991-113">Activities include, for example, visited websites or viewed product pages from a link received in an email.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8991-114">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="a8991-114">Prerequisites</span></span>

<span data-ttu-id="a8991-115">כדי לשלב נתונים מתובנות לגבי מעורבות, מספר תנאים מוקדמים צריכים להתקיים:</span><span class="sxs-lookup"><span data-stu-id="a8991-115">To integrate data from engagement insights, a few prerequisites need to be met:</span></span> 

- <span data-ttu-id="a8991-116">שלב את ה- SDK של התובנות לגבי מעורבות עם אתר האינטרנט שלך.</span><span class="sxs-lookup"><span data-stu-id="a8991-116">Integrate the engagement insights SDK with your website.</span></span> <span data-ttu-id="a8991-117">לקבלת מידע נוסף, ראה [סקירה של משאבים למפתחים](../engagement-insights/developer-resources.md)‬‏‫.</span><span class="sxs-lookup"><span data-stu-id="a8991-117">For more information, see [Developer resources overview](../engagement-insights/developer-resources.md).</span></span>
- <span data-ttu-id="a8991-118">יצוא אירועים באינטרנט מתובנות לגבי מעורבות דורש גישה לחשבון Azure Data Lake Storage שישמש לקליטת נתונים מאירועים באינטרנט לתובנות לגבי קהלים.</span><span class="sxs-lookup"><span data-stu-id="a8991-118">Exporting web events from engagement insights requires access to an Azure Data Lake Storage account that will be used to ingest the web events data to audience insights.</span></span> <span data-ttu-id="a8991-119">לקבלת מידע נוסף, ראה [יצא אירועים](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="a8991-119">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="configure-refined-events-in-engagement-insights"></a><span data-ttu-id="a8991-120">קביעת תצורה של אירועים ממוקדים בתובנות לגבי מעורבות</span><span class="sxs-lookup"><span data-stu-id="a8991-120">Configure refined events in engagement insights</span></span>

<span data-ttu-id="a8991-121">לאחר שמנהל המערכת מבצע אינסטרומנטציה לאתר עם ה- SDK של תובנות לגבי מעורבות, נאספים *אירועי בסיס* כאשר משתמש צופה בדף אינטרנט או לוחץ על משהו.</span><span class="sxs-lookup"><span data-stu-id="a8991-121">After an administrator instruments a website with the engagement insights SDK, *base events* are gathered when a user views a webpage or clicks somewhere.</span></span> <span data-ttu-id="a8991-122">אירועי בסיס נוטים להכיל פרטים רבים.</span><span class="sxs-lookup"><span data-stu-id="a8991-122">Base events tend to contain numerous details.</span></span> <span data-ttu-id="a8991-123">בהתאם למקרה השימוש שלך, אתה זקוק רק לערכת משנה של הנתונים באירוע בסיס.</span><span class="sxs-lookup"><span data-stu-id="a8991-123">Depending on your use case, you only need a subset of the data in a base event.</span></span> <span data-ttu-id="a8991-124">תובנות לגבי מעורבות מאפשרות לך ליצור *אירועים ממוקדים* המכילים רק את המאפיינים של אירוע בסיס שאתה בוחר.</span><span class="sxs-lookup"><span data-stu-id="a8991-124">Engagement insights let you create *refined events* that contain only the properties of a base event that you select.</span></span>     

<span data-ttu-id="a8991-125">לקבלת מידע נוסף, ראה [יצירה ושינוי של אירועים ממוקדים](../engagement-insights/refined-events.md).</span><span class="sxs-lookup"><span data-stu-id="a8991-125">For more information, see [Create and modify refined events](../engagement-insights/refined-events.md).</span></span>

<span data-ttu-id="a8991-126">שיקולים בעת יצירת אירועים ממוקדים:</span><span class="sxs-lookup"><span data-stu-id="a8991-126">Considerations when creating refined events:</span></span> 

- <span data-ttu-id="a8991-127">ספק שם בעל משמעות לאירוע הממוקד.</span><span class="sxs-lookup"><span data-stu-id="a8991-127">Provide a meaningful name for the refined event.</span></span> <span data-ttu-id="a8991-128">הוא ישמש כשם פעילות בתובנות לגבי קהלים.</span><span class="sxs-lookup"><span data-stu-id="a8991-128">It will be used as an activity name in audience insights.</span></span>
- <span data-ttu-id="a8991-129">בחר לפחות את המאפיינים הבאים כדי ליצור פעילות ב- audience insights:</span><span class="sxs-lookup"><span data-stu-id="a8991-129">Select at least the following properties to create an activity in audience insights:</span></span> 
    - <span data-ttu-id="a8991-130">Signal.Action.Name – מציין את פרטי הפעילות.</span><span class="sxs-lookup"><span data-stu-id="a8991-130">Signal.Action.Name – indicates the activity details.</span></span>
    - <span data-ttu-id="a8991-131">Signal.User.Id – משמש למיפוי עם מזהה הלקוח.</span><span class="sxs-lookup"><span data-stu-id="a8991-131">Signal.User.Id – used to map with the customer ID.</span></span>
    - <span data-ttu-id="a8991-132">Signal.View.Uri – משמש ככתובת אינטרנט כבסיס לפלחים או מדדים.</span><span class="sxs-lookup"><span data-stu-id="a8991-132">Signal.View.Uri – used as a web address as a basis for segments or measures.</span></span>
    - <span data-ttu-id="a8991-133">Signal.Export.Id – משמש כמפתח ראשי לאירועים.</span><span class="sxs-lookup"><span data-stu-id="a8991-133">Signal.Export.Id – used as a primary key for events.</span></span>
    - <span data-ttu-id="a8991-134">Signal.Timestamp – קובע את התאריך והשעה עבור הפעילות.</span><span class="sxs-lookup"><span data-stu-id="a8991-134">Signal.Timestamp – determines the date and time for the activity.</span></span>

<span data-ttu-id="a8991-135">בחר את המסננים כדי להתמקד באירועים ובדפים החשובים עבור מקרה השימוש שלך.</span><span class="sxs-lookup"><span data-stu-id="a8991-135">Select the filters to focus on the events and pages that matter for your use case.</span></span> <span data-ttu-id="a8991-136">בדוגמה זו נשתמש בשם הפעולה "קידום דוא"ל".</span><span class="sxs-lookup"><span data-stu-id="a8991-136">In this example, we'll use the "Email promotion" action name.</span></span>

## <a name="export-the-refined-web-events"></a><span data-ttu-id="a8991-137">יצוא אירועי אינטרנט ממוקדים</span><span class="sxs-lookup"><span data-stu-id="a8991-137">Export the refined web events</span></span> 

<span data-ttu-id="a8991-138">לאחר הגדרת האירוע הממוקד, עליך להגדיר את יצוא נתוני האירוע אל Azure Data Lake Storage, שאותו ניתן להגדיר כמקור נתונים לעיבוד תובנות לגבי קהלים‬.</span><span class="sxs-lookup"><span data-stu-id="a8991-138">After defining the refined event, you have to configure the export of the event data to Azure Data Lake Storage, which can be set as a data source for ingestion in audience insights.</span></span> <span data-ttu-id="a8991-139">פעולות ייצוא מתרחשות ללא הרף כאשר האירועים זורמים מנכס האינטרנט.</span><span class="sxs-lookup"><span data-stu-id="a8991-139">Exports happen constantly as the events flow from the web property.</span></span>

<span data-ttu-id="a8991-140">לקבלת מידע נוסף, ראה [יצא אירועים](../engagement-insights/export-events.md).</span><span class="sxs-lookup"><span data-stu-id="a8991-140">For more information, see [Export events](../engagement-insights/export-events.md).</span></span>

## <a name="ingest-event-data-to-audience-insights"></a><span data-ttu-id="a8991-141">קליטת נתוני אירוע ל- audience insights</span><span class="sxs-lookup"><span data-stu-id="a8991-141">Ingest event data to audience insights</span></span>

<span data-ttu-id="a8991-142">כעת, לאחר שהגדרת את האירוע הממוקד וקבעת את תצורת הייצוא שלו, אנחנו עוברים לקליטת הנתונים ל- audience insights.</span><span class="sxs-lookup"><span data-stu-id="a8991-142">Now that you have defined the refined event and configured its export, we move on to ingesting the data to audience insights.</span></span> <span data-ttu-id="a8991-143">עליך ליצור מקור נתונים חדש המבוסס על תיקיית Common Data Model.</span><span class="sxs-lookup"><span data-stu-id="a8991-143">You need to create a new data source based on a Common Data Model folder.</span></span> <span data-ttu-id="a8991-144">הזן את הפרטים עבור חשבון האחסון שאליו אתה מייצא את האירועים.</span><span class="sxs-lookup"><span data-stu-id="a8991-144">Enter the details for the storage account you export the events to.</span></span> <span data-ttu-id="a8991-145">בקובץ *default.cdm.json*, בחר את האירוע הממוקד לקליטה וליצירה של הישות ב- audience insights.</span><span class="sxs-lookup"><span data-stu-id="a8991-145">In the *default.cdm.json* file, select the refined event to ingest and create the entity in audience insights.</span></span>

<span data-ttu-id="a8991-146">לקבלת מידע נוסף, ראה [התחברות לתיקיית Common Data Model באמצעות חשבון Azure Data Lake](connect-common-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="a8991-146">For more information, see [Connect to a Common Data Model folder using an Azure Data Lake account](connect-common-data-model.md).</span></span>


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a><span data-ttu-id="a8991-147">התייחסות לנתוני אירוע ממוקד כפעילות של פרופיל לקוח</span><span class="sxs-lookup"><span data-stu-id="a8991-147">Relate refined event data as an activity of a customer profile</span></span>

<span data-ttu-id="a8991-148">לאחר השלמת קליטת הישות, באפשרותך לקבוע את תצורת הפעילות עבור פרופיל הלקוח.</span><span class="sxs-lookup"><span data-stu-id="a8991-148">After completing the entity ingestion, you can configure the activity for the customer profile.</span></span>

<span data-ttu-id="a8991-149">למידע נוסף ראה [פעילויות של לקוחות](activities.md).</span><span class="sxs-lookup"><span data-stu-id="a8991-149">For more information, see [Customer activities](activities.md).</span></span>

:::image type="content" source="media/web-event-activity.png" alt-text="דף פעילויות עם חלונית 'ערוך פעילות' ושדות מלאים.":::

<span data-ttu-id="a8991-151">קבע את תצורת הפעילות החדשה עם המיפוי הבא:</span><span class="sxs-lookup"><span data-stu-id="a8991-151">Configure the new activity with the following mapping:</span></span> 

- <span data-ttu-id="a8991-152">**מפתח ראשי**: ‏Signal.Export.Id, מזהה ייחודי הזמין עבור כל רשומת אירוע בתובנות לגבי מעורבות.</span><span class="sxs-lookup"><span data-stu-id="a8991-152">**Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights.</span></span> <span data-ttu-id="a8991-153">מאפיין זה נוצר באופן אוטומטי.</span><span class="sxs-lookup"><span data-stu-id="a8991-153">This property is automatically generated.</span></span>

- <span data-ttu-id="a8991-154">**חותמת זמן**: ‏Signal.Timestamp במאפיין האירוע.</span><span class="sxs-lookup"><span data-stu-id="a8991-154">**Timestamp**: Signal.Timestamp in the event property.</span></span>

- <span data-ttu-id="a8991-155">**אירוע**: ‏Signal.Name, שם האירוע שברצונך לעקוב אחריו.</span><span class="sxs-lookup"><span data-stu-id="a8991-155">**Event**: Signal.Name, the event name that you want to track.</span></span>

- <span data-ttu-id="a8991-156">**כתובת אינטרנט**: ‏Signal.View.Uri מתייחס ל- URI של הדף שיצר את האירוע.</span><span class="sxs-lookup"><span data-stu-id="a8991-156">**Web address**: Signal.View.Uri referring to the URI of the page that created the event.</span></span>

- <span data-ttu-id="a8991-157">**פרטים**: ‏Signal.Action.Name לייצוג המידע שיש לשייך לאירוע.</span><span class="sxs-lookup"><span data-stu-id="a8991-157">**Details**: Signal.Action.Name to represent the information to associate with the event.</span></span> <span data-ttu-id="a8991-158">המאפיין שנבחר במקרה זה מציין שהאירוע נועד לקידום דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="a8991-158">The selected property in this case indicates that the event is for email promotion.</span></span>

- <span data-ttu-id="a8991-159">**סוג הפעילות**: בדוגמה זו, אנו בוחרים את סוג הפעילות הקיים WebLog.</span><span class="sxs-lookup"><span data-stu-id="a8991-159">**Activity type**: In this example, we choose the existing activity type WebLog.</span></span> <span data-ttu-id="a8991-160">בחירה זו היא אפשרות סינון שימושית להפעלת מודלי חיזוי או ליצירת פלחים המבוססים על סוג פעילות זה.</span><span class="sxs-lookup"><span data-stu-id="a8991-160">This selection is a useful filter option to run prediction models or create segments based on this activity type.</span></span>

- <span data-ttu-id="a8991-161">**הגדר קשר**: הגדרה חשובה זו קושרת את הפעילות לפרופילי לקוחות קיימים.</span><span class="sxs-lookup"><span data-stu-id="a8991-161">**Set up relationship**: This important setting ties the activity to existing customer profiles.</span></span> <span data-ttu-id="a8991-162">**Signal.User.Id** הוא המזהה המוגדר ב- SDK לאיסוף ואשר מתקשר למזהה המשתמש במקורות נתונים אחרים המוגדרים ב- audience insights.</span><span class="sxs-lookup"><span data-stu-id="a8991-162">**Signal.User.Id** is the identifier configured in the SDK to be collected and that relates to the user ID in other data sources that are configured in audience insights.</span></span> <span data-ttu-id="a8991-163">בדוגמה זו, אנו מגדירים את הקשר בין Signal.User.Id ו- RetailCustomers: CustomerRetailId, שהוא המפתח הראשי שזוהה בשלב המיפוי של תהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="a8991-163">In this example, we configure the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.</span></span>

<span data-ttu-id="a8991-164">לאחר עיבוד הפעילויות, תוכל לסקור את רשומות הלקוחות ולפתוח כרטיס לקוח כדי לראות פעילויות מתובנות לגבי מעורבות בציר הזמן.</span><span class="sxs-lookup"><span data-stu-id="a8991-164">After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline.</span></span> 

> [!TIP]
> <span data-ttu-id="a8991-165">כדי למצוא מזהה לקוח שיש לו פעילות תובנות לגבי מעורבות, עבור אל **ישויות** והצג בתצוגה מקדימה את הנתונים עבור הישות UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="a8991-165">To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity.</span></span> <span data-ttu-id="a8991-166">ActivityTypeDisplay = ‏WebLog מכיל את פעילות תובנות לגבי מעורבות שהוגדרה בדוגמה לעיל.</span><span class="sxs-lookup"><span data-stu-id="a8991-166">ActivityTypeDisplay = WebLog contains the engagement insights activity configured in the example above.</span></span> <span data-ttu-id="a8991-167">העתק את מזהה הלקוח עבור אחת מאותן רשומות ועבור מזהה זה בדף **לקוחות**.</span><span class="sxs-lookup"><span data-stu-id="a8991-167">Copy the customer ID for one of those records and for that ID on the **Customers** page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a8991-168">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="a8991-168">Next steps</span></span>

<span data-ttu-id="a8991-169">כעת באפשרותך ליצור [פלחים](segments.md), [מדדים](measures.md) ו[חיזויים](predictions.md) כדי ליצור קשר משמעותי עם הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="a8991-169">You can now create [segments](segments.md), [measures](measures.md), and [predictions](predictions.md) to make a meaningful connection with your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
