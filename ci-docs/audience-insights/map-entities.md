---
title: מיפוי ישויות עבור איחוד נתונים
description: מפה נתונים כדי ליצור פרופילי לקוחות מאוחדים.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595994"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="c7fa6-103">מיפוי ישויות ותכונות</span><span class="sxs-lookup"><span data-stu-id="c7fa6-103">Map entities and attributes</span></span>

<span data-ttu-id="c7fa6-104">**מפה** הוא השלב הראשון בתהליך איחוד הנתונים של Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="c7fa6-105">המיפוי מורכב משלושה שלבים:</span><span class="sxs-lookup"><span data-stu-id="c7fa6-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="c7fa6-106">*בחירת ישויות*: זיהוי היישויות שניתן לשלב ושמובילות לערכת נתונים עם מידע מלא יותר אודות הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="c7fa6-107">*בחירת תכונות*: עבור כל ישות, זהה את העמודות שברצונך לשלב וליישב בשלבי *ההתאמה* *והמיזוג*.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="c7fa6-108">העמודות האלה נקראות *תכונות*.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="c7fa6-109">*בחירת מפתח ראשי וסוג סמנטי*: עבור כל ישות, זהה תכונה שברצונך להגדיר כמפתח העיקרי של הישות, ולכל תכונה זהה סוג סמנטי המתאר בצורה הטובה ביותר את התכונה הזו.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="c7fa6-110">לקבלת מידע נוסף אודות הזרימה הכללית של איחוד נתונים, ראה [איחוד](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa6-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="c7fa6-111">בחר את הישויות הראשונות</span><span class="sxs-lookup"><span data-stu-id="c7fa6-111">Select the first entities</span></span>

1. <span data-ttu-id="c7fa6-112">ב- audience insights, עבור אל **נתונים** > **אחד** > **מפה**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="c7fa6-113">הפעל את שלב המיפוי על-ידי בחירה באפשרות **בחר ישויות**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="c7fa6-114">בחר את הישויות והתכונות שבהן תרצה להשתמש בשלבים *התאמה* ו- *מיזוג*.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="c7fa6-115">באפשרותך לבחור את התכונות הנדרשות בנפרד מהישות או לכלול את כל התכונות מהישות על ידי בחירה בתיבת הסימון **כלול את כל השדות** ברמת הישות.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="c7fa6-116">אנו ממליצים לבחור לפחות שתי ישויות כדי ליהנות מהיתרון של תהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7fa6-117">![דוגמה של הוספת ישויות](media/data-manager-configure-map-add-entities-example.png "דוגמה של הוספת ישויות")</span><span class="sxs-lookup"><span data-stu-id="c7fa6-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="c7fa6-118">בדוגמה זו אנו מוסיפים את הישויות **eCommerceContacts** ו- **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="c7fa6-119">על ידי בחירה בישויות אלה, תוכל להפיק תובנות ולדעת מי מלקוחות העסק המקוונים חברים בתכנית נאמנות.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="c7fa6-120">ניתן לחפש במילות מפתח בכל המאפיינים והישויות כדי לבחור את התכונות הנדרשות שברצונך למפות.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7fa6-121">![דוגמה לשדות חיפוש](media/data-manager-configure-map-search-fields-example.png "דוגמה לשדות חיפוש")</span><span class="sxs-lookup"><span data-stu-id="c7fa6-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="c7fa6-122">בחר **החל** כדי לאשר את הבחירות שלך.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="c7fa6-123">בחר מפתח ראשי וסוג סמנטי לתכונות</span><span class="sxs-lookup"><span data-stu-id="c7fa6-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="c7fa6-124">לאחר בחירת הישויות, בדף **מפה** מופיעות הישויות שנבחרו לסקירה.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="c7fa6-125">הגדר את המפתח הראשי עבור ישות וזהה את הסוג הסמנטי של תכונה בישות.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="c7fa6-126">**מפתח ראשי**: בחר תכונה אחת כמפתח ראשי עבור כל אחת מהיישויות שלך.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="c7fa6-127">כדי שתכונה תהיה מפתח ראשי חוקי, היא לא יכולה לכלול ערכים כפולים, ערכים חסרים או ערכי null.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="c7fa6-128">תכונות סוגי נתונים מחרוזת, מספר שלם ו- GUID נתמכות כמפתחות ראשיים ויוצגו בשדה שמתוכו תוכל לבחור.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="c7fa6-129">**סוג סמנטי של תכונה**: קטגוריות של התכונות, כגון כתובת דואר אלקטרוני או שם.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="c7fa6-130">כדי להשתמש במודלים של AI עבור חיזויים חכמים של סמנטיקה, לחסוך זמן ולשפר את הדיוק, הגדר **מיפוי חכם** כ **פועל**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="c7fa6-131">מיפוי חכם מדגיש המלצות סמנטיות מבוססות AI בשדה **סוג**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="c7fa6-132">אם אתה מגדיר את מיפוי חכם ל **כבוי**, יוצגו לך המלצות המיפוי הרגילות שלנו.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="c7fa6-133">באפשרותך לבחור כל סוג סמנטי מרשימת האפשרויות הזמינות ולעקוף את הבחירה המוצעת.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c7fa6-134">![סוג תכונה וחיזוי סמנטי](media/data-manager-configure-map-add-attributes-semantic-prediction.png "סוג תכונה וחיזוי סמנטי")</span><span class="sxs-lookup"><span data-stu-id="c7fa6-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="c7fa6-135">ניתן גם להוסיף סוג סמנטי מותאם אישית.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="c7fa6-136">בחר את שדה הסוג עבור התכונה והקלד את שם הסוג הסמנטי המותאם אישית.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="c7fa6-137">בדרך זו, ניתן גם לשנות את סוגי התכונות שזוהו על-ידי המערכת.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="c7fa6-138">כל המאפיינים שעבורם מזוהה באופן אוטומטי סוג סמנטי מקובצים במקטע **סקור שדות ממופים**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="c7fa6-139">בדוק מאפיינים אלה ואת הסוג הסמנטי שלהם, מכיוון שהם ישמשו לשילוב הישויות בשלב המיזוג של איחוד נתונים.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="c7fa6-140">מאפיינים שאינם ממופים אוטומטית לסוג סמנטי מקובצים במקטע **הגדר את הנתונים בשדות הלא ממופים**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="c7fa6-141">בחר בשדה סוג סמנטי עבור התכונות הלא ממופות, או הזן את שם סוג התכונה המותאמת אישית שלך.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="c7fa6-142">![מפתח ראשי וסוג תכונה](media/data-manager-configure-map-add-attributes.png "מפתח ראשי וסוג תכונה")</span><span class="sxs-lookup"><span data-stu-id="c7fa6-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="c7fa6-143">שדה אחד צריך למפות את הסוג הסמנטי Person.FullName כדי לאכלס את שם הלקוח בכרטיס הלקוח.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="c7fa6-144">אחרת, כרטיסי הלקוח ייראו חסרי שם.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="c7fa6-145">הוסף והסר תכונות וישויות</span><span class="sxs-lookup"><span data-stu-id="c7fa6-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="c7fa6-146">באזור **איחוד** > **מפה**, בחר **ערוך שדות**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="c7fa6-147">בחלונית **ערוך שדות**, הוסף או הסר תכונות וישויות.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="c7fa6-148">השתמש בחיפוש או בגלול כדי למצוא ולבחור את התכונות והישויות המעניינות אותך.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="c7fa6-149">אינך יכול להסיר תכונה או ישות אם הם כבר תואמים.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c7fa6-150">![הוספה או הסרה של תכונות](media/configure-data-map-edit.png "הוספה או הסרה של תכונות")</span><span class="sxs-lookup"><span data-stu-id="c7fa6-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="c7fa6-151">בחר **החל**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="c7fa6-152">הוספת תמונות לפרופילים</span><span class="sxs-lookup"><span data-stu-id="c7fa6-152">Add images to profiles</span></span>

<span data-ttu-id="c7fa6-153">אם ישות מכילה כתובות URL לתמונות או סמלים של פרופיל הזמין לציבור, באפשרותך להוסיף אותן לפרופיל הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="c7fa6-154">בחר את הישות ומצא את השדה שמכיל את כתובת ה- URL לתמונת הפרופיל.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="c7fa6-155">בשדה הקלט **סוג**, הזן ידנית את הערך הבא:</span><span class="sxs-lookup"><span data-stu-id="c7fa6-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="c7fa6-156">עבור אדם: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="c7fa6-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="c7fa6-157">עבור ארגון: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="c7fa6-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="c7fa6-158">המשך בשלבי האיחוד וודא שהתכונה המכילה את כתובת האתר של התמונה מתווספת גם בשלב [מיזוג](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="c7fa6-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="c7fa6-159">הגדרת תכונות עבור ארגונים</span><span class="sxs-lookup"><span data-stu-id="c7fa6-159">Set attributes for organizations</span></span>

<span data-ttu-id="c7fa6-160">עבור ארגונים (Preview), יש למפות את סוג התכונה ל"Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="c7fa6-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="c7fa6-161">![מפתח ראשי וסוג תכונה B2B](media/configure-data-map-edit-b2b.png "מפתח ראשי וסוג תכונה B2B")</span><span class="sxs-lookup"><span data-stu-id="c7fa6-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="c7fa6-162">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="c7fa6-162">Next step</span></span>

<span data-ttu-id="c7fa6-163">כחלק מתהליך איחוד הנתונים, עבור לדף **התאמה**.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="c7fa6-164">בקר ב- [**התאמה**](match-entities.md) כדי ללמוד על שלב זה.</span><span class="sxs-lookup"><span data-stu-id="c7fa6-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="c7fa6-165">בדוק את הווידאו הבא [: תחילת העבודה: יצירת פרופיל לקוח מאוחד](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="c7fa6-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]