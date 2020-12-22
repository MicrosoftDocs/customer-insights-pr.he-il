---
title: חפש וסנן פרופילי לקוחות
description: חפש במהירות מידע על פרופילי לקוחות מאוחדים וסנן עבור תכונות שצוינו.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405911"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="06dd9-103">פרופילי לקוחות: אינדקס חיפוש וסינון</span><span class="sxs-lookup"><span data-stu-id="06dd9-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="06dd9-104">תוצאת האיחוד של נתוני לקוחות היא ישות פרופיל לקוח המספקת תצוגה אחידה לבסיס הלקוחות הכולל.</span><span class="sxs-lookup"><span data-stu-id="06dd9-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="06dd9-105">כדי [למצוא במהירות מידע על לקוח מסוים או על קבוצת לקוחות מסוימת](customer-profiles.md), באפשרותך לקבוע את תצורת היכולות **חיפוש** ו **סינון** בדף **לקוחות**.</span><span class="sxs-lookup"><span data-stu-id="06dd9-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="06dd9-106">המשך לקרוא כדי ללמוד כיצד מנהלים יכולים לערוך את התכונות בדף **אינדקס חיפוש וסינון**, הזמינות למשתמשים לצורך חיפוש וסינון.</span><span class="sxs-lookup"><span data-stu-id="06dd9-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="06dd9-107">![חיפוש מסנן](media/search-filter.png "חיפוש מסנן")</span><span class="sxs-lookup"><span data-stu-id="06dd9-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="06dd9-108">הוספת שדות וציון תכונות</span><span class="sxs-lookup"><span data-stu-id="06dd9-108">Add fields and specify attributes</span></span>

<span data-ttu-id="06dd9-109">אם זו הפעם הראשונה שאתה מגדיר תכונות הניתנות לחיפוש כמנהל מערכת, תחילה עליך להגדיר שדות בעלי אינדקס.</span><span class="sxs-lookup"><span data-stu-id="06dd9-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="06dd9-110">אנו מציעים לך לבחור את כל התכונות שמשתמשים יכולים לחפש ולסנן את הלקוחות בדף **לקוחות**.</span><span class="sxs-lookup"><span data-stu-id="06dd9-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="06dd9-111">באפשרותך לציין רק תכונות שקיימות בישות 'פרופיל לקוח' שיצרת במהלך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="06dd9-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="06dd9-112">פתח את הדף **לקוחות** ובחר **אינדקס חיפוש וסינון**.</span><span class="sxs-lookup"><span data-stu-id="06dd9-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="06dd9-113">אנו יוצרים תצורת אינדקס חיפוש כברירת מחדל עבור התכונות הזמינות בישות הלקוח מהסוגים הסמנטיים הבאים כפי שמוגדר בדף המפה.</span><span class="sxs-lookup"><span data-stu-id="06dd9-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="06dd9-114">'שם פרטי', 'שם שני', 'שם משפחה', 'שם מלא'</span><span class="sxs-lookup"><span data-stu-id="06dd9-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="06dd9-115">שם ארגון</span><span class="sxs-lookup"><span data-stu-id="06dd9-115">Organization Name</span></span>
> - <span data-ttu-id="06dd9-116">כתובת דואר אלקטרוני</span><span class="sxs-lookup"><span data-stu-id="06dd9-116">Email address</span></span>
> - <span data-ttu-id="06dd9-117">מספר טלפון</span><span class="sxs-lookup"><span data-stu-id="06dd9-117">Phone number</span></span>
> - <span data-ttu-id="06dd9-118">פרטי המיקום</span><span class="sxs-lookup"><span data-stu-id="06dd9-118">Location information</span></span>

2. <span data-ttu-id="06dd9-119">בחר **+ הוסף** כדי לציין את השדות שיש להוסיף לאינדקס.</span><span class="sxs-lookup"><span data-stu-id="06dd9-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="06dd9-120">בחר את התכונות ברשימה שברצונך להוסיף כשדות הכלולים באינדקס.</span><span class="sxs-lookup"><span data-stu-id="06dd9-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="06dd9-121">תמיד תוכל להוסיף תכונות על-ידי בחירה באפשרות **הוסף**.</span><span class="sxs-lookup"><span data-stu-id="06dd9-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="06dd9-122">באפשרותך גם להסיר את כל התכונות שנבחרו על ידי בחירה בסמל **הסר**.</span><span class="sxs-lookup"><span data-stu-id="06dd9-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="06dd9-123">חקור את טבלת שדות הלקוחות הכלולים באינדקס</span><span class="sxs-lookup"><span data-stu-id="06dd9-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="06dd9-124">המידע הבא מופיע בטבלה.</span><span class="sxs-lookup"><span data-stu-id="06dd9-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="06dd9-125">**שם**: מייצג את שם התכונה כפי שמופיע בישות פרופיל הלקוח.</span><span class="sxs-lookup"><span data-stu-id="06dd9-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="06dd9-126">**סוג נתונים**: מציין אם סוג הנתונים הוא מחרוזת, מספר או תאריך.</span><span class="sxs-lookup"><span data-stu-id="06dd9-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="06dd9-127">**כלול בחיפוש**: מציין אם תכונה זו יכולה לשמש לחיפוש לקוחות בדף **לקוחות** באמצעות השדה **חיפוש**.</span><span class="sxs-lookup"><span data-stu-id="06dd9-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="06dd9-128">**הוסף מסנן**: פקד המגדיר כיצד ניתן להשתמש בתכונה זו לסינון בדף **לקוחות**.</span><span class="sxs-lookup"><span data-stu-id="06dd9-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="06dd9-129">עריכת אפשרויות סינון עבור תכונה נתונה</span><span class="sxs-lookup"><span data-stu-id="06dd9-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="06dd9-130">תפריט **מסנן** בדף **לקוחות** יכול לכלול מספר רמות של תכונות (לדוגמה, קבוצות גיל שונות כדי לסנן לקוחות לפיהן).</span><span class="sxs-lookup"><span data-stu-id="06dd9-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="06dd9-131">בחר באפשרות **הוסף מסנן** עבור תכונה נתונה בדף **אינדקס סינון וחיפוש**.</span><span class="sxs-lookup"><span data-stu-id="06dd9-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="06dd9-132">באפשרותך להגדיר את מספר התוצאות ואת הסדר שבו הן יופיעו.</span><span class="sxs-lookup"><span data-stu-id="06dd9-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="06dd9-133">בהתאם לסוג הנתונים של התכונה, מופיעה אחת מהחלוניות הבאות.</span><span class="sxs-lookup"><span data-stu-id="06dd9-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="06dd9-134">מאפיינים של סוג מחרוזת: ציין את מספר התוצאות הרצויות בלוח **אפשרויות סינון מחרוזות** ובמדיניות הסדר שלפיה הן יופיעו.</span><span class="sxs-lookup"><span data-stu-id="06dd9-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="06dd9-135">מאפיינים של סוג מספר: ציין את המרווחים בלוח **אפשרויות סינון מספרים** ובמדיניות הסדר שלפיה הן יופיעו.</span><span class="sxs-lookup"><span data-stu-id="06dd9-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="06dd9-136">מאפיינים של סוג תאריך: ציין את המרווחים הכלולים בלוח **אפשרויות סינון תאריכים** ובמדיניות הסדר שלפיה הן יופיעו.</span><span class="sxs-lookup"><span data-stu-id="06dd9-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="06dd9-137">בחר **שמור** כדי להחיל את השינויים.</span><span class="sxs-lookup"><span data-stu-id="06dd9-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="06dd9-138">בחר באפשרות **הפעלה** לאחר שתהיה מוכן להחיל את ההגדרות שלך.</span><span class="sxs-lookup"><span data-stu-id="06dd9-138">Select **Run** once you're ready to apply your settings.</span></span>
