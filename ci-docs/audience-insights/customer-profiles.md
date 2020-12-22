---
title: הצגת פרופילי לקוחות
description: קבל תצוגה משולבת של נתוני הלקוחות המאוחדים שלך.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 13308c2f40cda0d7e813b4d94ab47d53b5ce2115
ms.sourcegitcommit: a6e7df90d61450e00886753eb5db116f2f35bb6c
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 12/01/2020
ms.locfileid: "4653891"
---
# <a name="customer-profiles"></a><span data-ttu-id="1da22-103">פרופילי לקוחות</span><span class="sxs-lookup"><span data-stu-id="1da22-103">Customer profiles</span></span>

<span data-ttu-id="1da22-104">הדף **לקוחות** מציג תצוגה משולב של הלקוחות שלך, בהתבסס על נתוני פרופיל שנאספו מ[כל מקורות הנתונים](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="1da22-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="1da22-105">פרופילי לקוחות זמינים ברגע שאתה [יוצר את ישות הלקוח המאוחדת](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1da22-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="1da22-106">ודא שאתה מסיים את תהליך איחוד הנתונים כדי לקבל תצוגות עשירות יותר של הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="1da22-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="1da22-107">הדף מאפשר לך גם לחפש לקוחות.</span><span class="sxs-lookup"><span data-stu-id="1da22-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="1da22-108">הלקוחות יכולים להיות אנשים או ארגונים (תצוגה מקדימה).</span><span class="sxs-lookup"><span data-stu-id="1da22-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="1da22-109">כל פרופיל לקוח או ארגון מיוצג על ידי אריח.</span><span class="sxs-lookup"><span data-stu-id="1da22-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="1da22-110">בחר אריח כדי לראות מידע נוסף על אותו לקוח או ארגון ספציפי.</span><span class="sxs-lookup"><span data-stu-id="1da22-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="1da22-111">השתמש בפקדי העימוד בתחתית הדף כדי לראות רשומות נוספות.</span><span class="sxs-lookup"><span data-stu-id="1da22-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="1da22-112">![פרופיל לקוח B2C](media/profiles-customers.png "פרופיל לקוח B2C")</span><span class="sxs-lookup"><span data-stu-id="1da22-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="1da22-113">ארגונים (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="1da22-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="1da22-114">![פרופיל לקוח B2B](media/profile-customers-b2b.png "פרופיל לקוח B2B")</span><span class="sxs-lookup"><span data-stu-id="1da22-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="1da22-115">אם אינך יכול לראות את האריחים כאשר אתה בוחר **לקוחות** בניווט, מנהל המערכת שלך צריך [להגדיר לפחות תכונה אחת ניתנת לחיפוש](search-filter-index.md) ב **אינדקס חיפוש וסינון**.</span><span class="sxs-lookup"><span data-stu-id="1da22-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="1da22-116">חפש לקוחות</span><span class="sxs-lookup"><span data-stu-id="1da22-116">Search for customers</span></span>

<span data-ttu-id="1da22-117">חפש לקוחות על ידי הזנת שם או תכונה אחרת בתיבת החיפוש.</span><span class="sxs-lookup"><span data-stu-id="1da22-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="1da22-118">החיפוש פועל רק ביישות פרופיל הלקוח שנוצרה בתהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="1da22-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="1da22-119">כמנהל מערכת, אתה יכול להגדיר את התכונות הניתנות לחיפוש בדף **אינדקס חיפוש וסינון**.</span><span class="sxs-lookup"><span data-stu-id="1da22-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="1da22-120">לקבלת מידע נוסף, ראה [ניהול אינדקס חיפוש וסינון](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="1da22-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="1da22-121">סינון לקוחות</span><span class="sxs-lookup"><span data-stu-id="1da22-121">Filter customers</span></span>

<span data-ttu-id="1da22-122">ניתן לסנן לקוחות לפי שדות של ישות פרופיל הלקוח.</span><span class="sxs-lookup"><span data-stu-id="1da22-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="1da22-123">בדומה לחיפוש, מנהל המערכת יצטרך להגדיר תחילה את השדות לסינון בדף **אינדקס חיפוש וסינון**.</span><span class="sxs-lookup"><span data-stu-id="1da22-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="1da22-124">בחר **סנן** בדף **לקוחות**.</span><span class="sxs-lookup"><span data-stu-id="1da22-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="1da22-125">סמן את התיבות לצד התכונות שברצונך לסנן לקוחות לפיהן.</span><span class="sxs-lookup"><span data-stu-id="1da22-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="1da22-126">![פרופילי לקוחות](media/profiles-customers3.png "פרופילי לקוחות")</span><span class="sxs-lookup"><span data-stu-id="1da22-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="1da22-127">הסר את המסננים שלך על-ידי בחירת **נקה מסננים** בדף **לקוחות**.</span><span class="sxs-lookup"><span data-stu-id="1da22-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="1da22-128">דף פרטי לקוח</span><span class="sxs-lookup"><span data-stu-id="1da22-128">Customer details page</span></span>

<span data-ttu-id="1da22-129">בחר באחד מאריחי הלקוחות כדי לפתוח את **דף פרטי הלקוח**.</span><span class="sxs-lookup"><span data-stu-id="1da22-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="1da22-130">תצוגה זו מכילה מידע מאוחד עבור הלקוח שנבחר.</span><span class="sxs-lookup"><span data-stu-id="1da22-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="1da22-131">פרטי לקוח כוללים:</span><span class="sxs-lookup"><span data-stu-id="1da22-131">Customer details include:</span></span>

-   <span data-ttu-id="1da22-132">**אריח פרופיל לקוח:** אריח זה מציג את הערכים השונים מהישות המאוחדת של פרופיל הלקוח.</span><span class="sxs-lookup"><span data-stu-id="1da22-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="1da22-133">פרטים אלה יכולים לכלול כתובת דוא"ל, שם, עיר וכן הלאה.</span><span class="sxs-lookup"><span data-stu-id="1da22-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="1da22-134">**תחומי עניין פוטנציאליים, מותגים פוטנציאליים:** מציג אם הגדרת העשרה של צד ראשון.</span><span class="sxs-lookup"><span data-stu-id="1da22-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="1da22-135">זה מייצג תחומי עניין וקירבות פוטנציאליים עבור מותגים שעשויים להיות ללקוח עם פרופיל הדומה ללקוח זה.</span><span class="sxs-lookup"><span data-stu-id="1da22-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="1da22-136">למידע נוסף ראה [העשרת פרופילי לקוחות בקשרי מותגים ותחומי עניין](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="1da22-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="1da22-137">**מדידות:** מציג אם הגדרת מידה אחת או יותר מסוג ספציפי: מדידות תכונת לקוח.</span><span class="sxs-lookup"><span data-stu-id="1da22-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="1da22-138">הן כוללות מחווני KPI מחושבים בהתאם ללקוחות שלך ברמת הלקוח היחיד.</span><span class="sxs-lookup"><span data-stu-id="1da22-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="1da22-139">לקבלת מידע נוסף, ראה [הגדרה וניהול של מדידות](measures.md).</span><span class="sxs-lookup"><span data-stu-id="1da22-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="1da22-140">**ציר זמן של פעילות:** מציג אם יש לך פעילויות מוגדרות.</span><span class="sxs-lookup"><span data-stu-id="1da22-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="1da22-141">תצוגת ציר הזמן מכילה פעילויות הממוינות בסדר כרונולוגי של לקוח זה, החל מהפעילות העדכנית ביותר.</span><span class="sxs-lookup"><span data-stu-id="1da22-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="1da22-142">למידע נוסף ראה [פעילויות של לקוחות](activities.md).</span><span class="sxs-lookup"><span data-stu-id="1da22-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="1da22-143">בחר **חזור ללקוחות** כדי לחזור לדף החיפוש של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="1da22-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1da22-144">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="1da22-144">Next steps</span></span>

<span data-ttu-id="1da22-145">[הוסף מקורות נתונים נוספים](data-sources.md) או [צור פלחי לקוחות](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1da22-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>
