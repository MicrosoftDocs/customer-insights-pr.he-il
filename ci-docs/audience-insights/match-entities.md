---
title: התאמת ישויות לאיחוד נתונים
description: התאם ישויות ליצירת פרופילי לקוח מאוחדים.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405905"
---
# <a name="match-entities"></a><span data-ttu-id="3c072-103">התאמת ישויות</span><span class="sxs-lookup"><span data-stu-id="3c072-103">Match entities</span></span>

<span data-ttu-id="3c072-104">לאחר השלמת שלב המפה, אתה מוכן להתאים את היישויות שלך.</span><span class="sxs-lookup"><span data-stu-id="3c072-104">After completing the map phase, you're ready to match your entities.</span></span> <span data-ttu-id="3c072-105">שלב ההתאמה מציין כיצד לשלב את ערכות הנתונים שלך בערכת נתונים של פרופיל לקוח אחיד.</span><span class="sxs-lookup"><span data-stu-id="3c072-105">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="3c072-106">שלב ההתאמה דורש לפחות [שתי ישויות ממופות](map-entities.md).</span><span class="sxs-lookup"><span data-stu-id="3c072-106">The match phase requires at least [two mapped entities](map-entities.md).</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="3c072-107">ציין את סדר ההתאמה</span><span class="sxs-lookup"><span data-stu-id="3c072-107">Specify the match order</span></span>

<span data-ttu-id="3c072-108">עבור אל **איחוד** > **התאמה** ובחר **הגדר סדר** כדי להתחיל את שלב ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-108">Go to **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="3c072-109">כל התאמה מאחדת שתי ישויות או יותר ליישות אחת, תוך הקפדה על כל רשומת לקוח ייחודית.</span><span class="sxs-lookup"><span data-stu-id="3c072-109">Each match unifies two or more entities into a single entity, while persisting each unique customer record.</span></span> <span data-ttu-id="3c072-110">בדוגמה הבאה, בחרנו שלוש ישויות: **ContactCSV: TestData** בתור הישות **הראשית**, **WebAccountCSV: TestData** בתור **ישות 2**, ו- **CallRecordSmall: TestData** בתור **ישות 3**.</span><span class="sxs-lookup"><span data-stu-id="3c072-110">In the following example, we selected three entities: **ContactCSV: TestData** as the **Primary** entity, **WebAccountCSV: TestData** as **Entity 2**, and **CallRecordSmall: TestData** as **Entity 3**.</span></span> <span data-ttu-id="3c072-111">הדיאגרמה שמעל לבחירות מתארת כיצד יבוצע סדר ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-111">The diagram above the selections illustrates how the match order will be executed.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3c072-112">![עריכת סדר התאמת הנתונים](media/configure-data-match-order-edit-page.png "עריכת סדר התאמת הנתונים")</span><span class="sxs-lookup"><span data-stu-id="3c072-112">![Edit the data match order](media/configure-data-match-order-edit-page.png "Edit the data match order")</span></span>
  
<span data-ttu-id="3c072-113">הישות **הראשית** מותאמת ל- **ישות 2**.</span><span class="sxs-lookup"><span data-stu-id="3c072-113">The **Primary** entity is matched with **Entity 2**.</span></span> <span data-ttu-id="3c072-114">ערכת הנתונים שנוצרת בעקבות מההתאמה הראשונה מתאימה **לישות 3**.</span><span class="sxs-lookup"><span data-stu-id="3c072-114">The dataset that results from the first match is matched with **Entity 3**.</span></span>
<span data-ttu-id="3c072-115">בדוגמה זו, בחרנו רק שתי התאמות, אך המערכת יכולה לתמוך ביותר.</span><span class="sxs-lookup"><span data-stu-id="3c072-115">In this example, we only selected two matches, but the system can support more.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3c072-116">הישות שאתה בוחר בתור הישות **הראשית** שלך תשמש כבסיס לערכת הנתונים הראשית האחידה.</span><span class="sxs-lookup"><span data-stu-id="3c072-116">The entity that you choose as your **Primary** entity will serve as the basis for your unified master dataset.</span></span> <span data-ttu-id="3c072-117">ישויות נוספות שנבחרות במהלך שלב ההתאמה יתווספו לישות זו.</span><span class="sxs-lookup"><span data-stu-id="3c072-117">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="3c072-118">יחד עם זאת, אין פירוש הדבר שהישות האחידה תכלול את *כל* הנתונים הכלולים בישות זו.</span><span class="sxs-lookup"><span data-stu-id="3c072-118">At the same time, this doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="3c072-119">קיימים שני שיקולים שיכולים לסייע לך לבחור את ההירארכיה של היישויות:</span><span class="sxs-lookup"><span data-stu-id="3c072-119">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="3c072-120">איזו ישות לדעתך היא בעלת המידע המלא והאמין ביותר לגבי הלקוחות שלך?</span><span class="sxs-lookup"><span data-stu-id="3c072-120">What entity do you consider having the most complete and reliable data about your customers?</span></span>
> - <span data-ttu-id="3c072-121">האם לישות שזיהית כרגע יש תכונות שמשותפות גם על-ידי ישויות אחרות (לדוגמה, שם, מספר טלפון או כתובת דואר אלקטרוני)?</span><span class="sxs-lookup"><span data-stu-id="3c072-121">Does the entity that you just identified have attributes that are also shared by other entities (for example, name, phone number, or email address)?</span></span> <span data-ttu-id="3c072-122">אם לא, בחר את הישות השנייה האמינה ביותר.</span><span class="sxs-lookup"><span data-stu-id="3c072-122">If not, choose your second most reliable entity.</span></span>

<span data-ttu-id="3c072-123">בחר באפשרות **בוצע** כדי לשמור את סדר ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-123">Select **Done** to save your match order.</span></span>

## <a name="define-rules-for-your-first-match-pair"></a><span data-ttu-id="3c072-124">הגדרת כללים עבור זוג ההתאמה הראשון שלך</span><span class="sxs-lookup"><span data-stu-id="3c072-124">Define rules for your first match pair</span></span>

<span data-ttu-id="3c072-125">לאחר ציון סדר ההתאמה, תראה את ההתאמות המוגדרות בדף **התאמה**.</span><span class="sxs-lookup"><span data-stu-id="3c072-125">After specifying the match order, you'll see the defined matches on the **Match** page.</span></span> <span data-ttu-id="3c072-126">האריחים בחלק העליון של המסך יהיו ריקים עד שתפעיל את סדר ההתאמה שלך.</span><span class="sxs-lookup"><span data-stu-id="3c072-126">The tiles at the top of the screen will be empty until you run your match order.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3c072-127">![הגדרת כללים](media/configure-data-match-need-rules.png "הגדרת כללים")</span><span class="sxs-lookup"><span data-stu-id="3c072-127">![Define rules](media/configure-data-match-need-rules.png "Define rules")</span></span>

<span data-ttu-id="3c072-128">האזהרה **דרושים כללים** מרמזת על כך שלא מוגדר כלל התאמה עבור זוג התאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-128">The **Needs Rules** warning suggests that no match rule is defined for a match pair.</span></span> <span data-ttu-id="3c072-129">כללי התאמה מציינים את הלוגיקה שלפיה יותאמו זוג ישויות מסוים.</span><span class="sxs-lookup"><span data-stu-id="3c072-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

1. <span data-ttu-id="3c072-130">כדי להגדיר את הכלל הראשון, פתח את החלונית **הגדרת כלל** כל ידי בחירה בשורת ההתאמה הרלוונטית בטבלת ההתאמות (1) ובחירה באפשרות **צור כלל חדש** (2).</span><span class="sxs-lookup"><span data-stu-id="3c072-130">To define your first rule, open the **Rule Definition** pane by selecting the corresponding match row in the matches table (1) and then selecting **Create new rule** (2).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c072-131">![צור כלל חדש](media/configure-data-match-new-rule2.png "צור כלל חדש")</span><span class="sxs-lookup"><span data-stu-id="3c072-131">![Create new rule](media/configure-data-match-new-rule2.png "Create new rule")</span></span>

2. <span data-ttu-id="3c072-132">בחלונית **עריכת כלל**, הגדר את התנאים עבור כלל זה.</span><span class="sxs-lookup"><span data-stu-id="3c072-132">In the **Edit Rule** pane, configure the conditions for that rule.</span></span> <span data-ttu-id="3c072-133">כל תנאי מיוצג על-ידי שתי שורות הכוללות בחירות הכרחיות.</span><span class="sxs-lookup"><span data-stu-id="3c072-133">Each condition is represented by two rows that include mandatory selections.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c072-134">![חלונית כלל חדש](media/configure-data-match-new-rule-condition.png "חלונית כלל חדש")</span><span class="sxs-lookup"><span data-stu-id="3c072-134">![New rule pane](media/configure-data-match-new-rule-condition.png "New rule pane")</span></span>

   <span data-ttu-id="3c072-135">ישות/שדה (ראשון) - תכונה שתשמש להתאמה מהישות הראשונה של זוג ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-135">Entity/Field (first) - An attribute that will be used for matching from the first match pair entity.</span></span> <span data-ttu-id="3c072-136">דוגמאות יכולות לכלול מספר טלפון או כתובת דואר.</span><span class="sxs-lookup"><span data-stu-id="3c072-136">Examples could include a phone number or email address.</span></span> <span data-ttu-id="3c072-137">בחר תכונה שעשויה להיות ייחודית ללקוח.</span><span class="sxs-lookup"><span data-stu-id="3c072-137">Choose an attribute that is likely to be unique to the customer.</span></span>

   > [!TIP]
   > <span data-ttu-id="3c072-138">הימנע מהתאמה על בסיס תכונות מסוג פעילות.</span><span class="sxs-lookup"><span data-stu-id="3c072-138">Avoid matching on the basis of activity-type attributes.</span></span> <span data-ttu-id="3c072-139">במילים אחרות, אם תכונה נראית כפעילות, ייתכן שתהיה התאמה לקריטריונים באיכות נמוכה יותר.</span><span class="sxs-lookup"><span data-stu-id="3c072-139">In other words, if an attribute seems to be an activity, then it might be a poor criteria to match by.</span></span>  

   <span data-ttu-id="3c072-140">ישות/שדה (שני) - תכונה שתשמש להתאמה מהישות השנייה של זוג ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-140">Entity/Field (Second) - An attribute that will be used for matching from the second match pair entity.</span></span>

   <span data-ttu-id="3c072-141">נרמול - **שיטת נרמול**: אפשרויות נרמול שונות לתכונות שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="3c072-141">Normalize - **Normalization method**: Various normalization options are available for the selected attributes.</span></span> <span data-ttu-id="3c072-142">לדוגמה, הסרת פיסוק או הסרת רווחים</span><span class="sxs-lookup"><span data-stu-id="3c072-142">For example, removing punctuation or removing spaces</span></span>

   <span data-ttu-id="3c072-143">עבור נרמול שמות ארגוניים (תצוגה מקדימה), באפשרותך גם לבחור **סוג (טלפון, שם, ארגון)**</span><span class="sxs-lookup"><span data-stu-id="3c072-143">For Organization name normalization (Preview), you can also select **Type (Phone, Name, Organization)**</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c072-144">![נרמול-B2B](media/match-normalization-b2b.png "נרמול-B2B")</span><span class="sxs-lookup"><span data-stu-id="3c072-144">![Normalization-B2B](media/match-normalization-b2b.png "Normalization-B2B")</span></span>

   <span data-ttu-id="3c072-145">רמת דיוק - רמת הדיוק שתהיה בשימוש עבור מצב זה.</span><span class="sxs-lookup"><span data-stu-id="3c072-145">Precision level - The level of precision that will be used for this condition.</span></span> <span data-ttu-id="3c072-146">הגדרת רמת דיוק עבור תנאי התאמה יכולה להיות בעלת שני סוגים: **בסיסיים** או **מותאמים אישית**.</span><span class="sxs-lookup"><span data-stu-id="3c072-146">Setting a precision level for a match condition can have two types: **Basic** and **Custom**.</span></span>  
   - <span data-ttu-id="3c072-147">בסיסי: מספק ארבע אפשרויות לבחירה: נמוך, בינוני, גבוה ומדויק.</span><span class="sxs-lookup"><span data-stu-id="3c072-147">Basic: Provides you with four options to select from: Low, Medium, High, and Exact.</span></span> <span data-ttu-id="3c072-148">בחר **מדויק** כדי להתאים רק רשומות שתואמות ב- 100 אחוז.</span><span class="sxs-lookup"><span data-stu-id="3c072-148">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="3c072-149">בחר אחת מהרמות האחרות כדי להתאים רשומות שאינן זהות ב- 100 אחוז.</span><span class="sxs-lookup"><span data-stu-id="3c072-149">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
   - <span data-ttu-id="3c072-150">מותאם אישית: השתמש במחוון כדי להגדיר את האחוז המותאם אישית שהרשומות צריכות להתאים או הזן ערך בשדה **מותאם אישית**.</span><span class="sxs-lookup"><span data-stu-id="3c072-150">Custom: Use the slider to define the custom percentage that records need to match or enter a value in the **Custom** field.</span></span> <span data-ttu-id="3c072-151">המערכת תבצע התאמה רק לרשומות שעוברות את הסף הזה כזוגות תואמים.</span><span class="sxs-lookup"><span data-stu-id="3c072-151">The system will only match records passing this threshold as conflated match pairs.</span></span> <span data-ttu-id="3c072-152">הערכים במחוון הם בין 0 ל-1.</span><span class="sxs-lookup"><span data-stu-id="3c072-152">Values on the slider are between 0 and 1.</span></span> <span data-ttu-id="3c072-153">כלומר, 0.64 מייצג 64 אחוזים.</span><span class="sxs-lookup"><span data-stu-id="3c072-153">So 0.64 represents 64 percent.</span></span>

3. <span data-ttu-id="3c072-154">בחר **בוצע** כדי לשמור את הכלל.</span><span class="sxs-lookup"><span data-stu-id="3c072-154">Select **Done** to save the rule.</span></span>

### <a name="add-multiple-conditions"></a><span data-ttu-id="3c072-155">הוספת תנאים מרובים</span><span class="sxs-lookup"><span data-stu-id="3c072-155">Add multiple conditions</span></span>

<span data-ttu-id="3c072-156">כדי להתאים את הישויות רק אם מתקיימים תנאים מרובים, הוסף תנאים נוספים המקושרים באמצעות האופרטור AND.</span><span class="sxs-lookup"><span data-stu-id="3c072-156">To match your entities only if multiple conditions are met, add more conditions that are linked through an AND operator.</span></span>

1. <span data-ttu-id="3c072-157">בחלונית **ערוך כלל**, בחר באפשרות **הוסף תנאי**.</span><span class="sxs-lookup"><span data-stu-id="3c072-157">In the **Edit rule** pane, select **Add condition**.</span></span> <span data-ttu-id="3c072-158">באפשרותך גם למחוק תנאים על-ידי בחירה בלחצן הסר לצד תנאי קיים.</span><span class="sxs-lookup"><span data-stu-id="3c072-158">You can also delete conditions by selecting the remove button next to an existing condition.</span></span>

2. <span data-ttu-id="3c072-159">בחר **בוצע** כדי לשמור את הכלל.</span><span class="sxs-lookup"><span data-stu-id="3c072-159">Select **Done** so save the rule.</span></span>

## <a name="add-multiple-rules"></a><span data-ttu-id="3c072-160">הוספת כללים מרובים</span><span class="sxs-lookup"><span data-stu-id="3c072-160">Add multiple rules</span></span>

<span data-ttu-id="3c072-161">כל תנאי חל על זוג תכונות יחיד, בעוד שכללים מייצגים ערכות של תנאים.</span><span class="sxs-lookup"><span data-stu-id="3c072-161">Each condition applies to a single pair of attributes, while rules represent sets of conditions.</span></span> <span data-ttu-id="3c072-162">כדי שהישויות יותאמו באמצעות ערכות תכונות שונות, אפשר להוסיף כללים נוספים.</span><span class="sxs-lookup"><span data-stu-id="3c072-162">To have your entities matched by different sets of attributes, you can add more rules.</span></span>

1. <span data-ttu-id="3c072-163">ב- audience insights, עבור אל **נתונים** > **אחד** > **התאם**.</span><span class="sxs-lookup"><span data-stu-id="3c072-163">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

2. <span data-ttu-id="3c072-164">בחר את הישות שברצונך לעדכן ובחר **הוסף כללים**.</span><span class="sxs-lookup"><span data-stu-id="3c072-164">Select the entity you want to update and select **Add rules**.</span></span>

3. <span data-ttu-id="3c072-165">בצע את ההליך כמתואר ב- [הגדרת כללים עבור זוג ההתאמה הראשון](#define-rules-for-your-first-match-pair).</span><span class="sxs-lookup"><span data-stu-id="3c072-165">Follow the procedure as outlined in [Define rules for your first match pair](#define-rules-for-your-first-match-pair).</span></span>

> [!NOTE]
> <span data-ttu-id="3c072-166">יש חשיבות לסדר הכללים.</span><span class="sxs-lookup"><span data-stu-id="3c072-166">The rule order matters.</span></span> <span data-ttu-id="3c072-167">אלגוריתם ההתאמה מנסה להתאים לפי הכלל הראשון וממשיך לכלל השני רק אם לא זוהו התאמות לפי הכלל הראשון.</span><span class="sxs-lookup"><span data-stu-id="3c072-167">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified under the first rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="3c072-168">הגדרת ביטול כפילויות בישות מתאימה</span><span class="sxs-lookup"><span data-stu-id="3c072-168">Define deduplication on a match entity</span></span>

<span data-ttu-id="3c072-169">לצד ציון כללי התאמה בין ישויות כמתואר בסעיפים לעיל, תוכל גם לציין כללי ביטול כפילויות.</span><span class="sxs-lookup"><span data-stu-id="3c072-169">Along with specifying cross entity matching rules as outlined in the above sections, you can also specify deduplications rules.</span></span> <span data-ttu-id="3c072-170">*ביטול כפילויות* הוא תהליך.</span><span class="sxs-lookup"><span data-stu-id="3c072-170">*Deduplication* is a process.</span></span> <span data-ttu-id="3c072-171">הוא מזהה רשומות כפולות, ממזג אותן לרשומה אחת ומקשר את כל רשומות המקור לרשומה ממוזגת זו עם מזהים חלופיים לרשומה הממוזגת.</span><span class="sxs-lookup"><span data-stu-id="3c072-171">It identifies duplicate records, merges them into one record, and links all the source records to this merged record with alternate IDs to the merged record.</span></span>

<span data-ttu-id="3c072-172">לאחר זיהוי רשומה שהכפילויות שלה בוטלו, רשומה זו תשמש בתהליך ההתאמה בין ישויות.</span><span class="sxs-lookup"><span data-stu-id="3c072-172">After a deduplicated record is identified, that record will be used in the cross-entity matching process.</span></span> <span data-ttu-id="3c072-173">ביטול כפילויות מיושם ברמת הישות וניתן להחיל אותו על כל ישות המשמשת בתהליך ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-173">Deduplication is implemented at the entity level and can be applied to every entity used in the Match process.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="3c072-174">הוספת כללים לביטול כפילויות</span><span class="sxs-lookup"><span data-stu-id="3c072-174">Add deduplication rules</span></span>

1. <span data-ttu-id="3c072-175">ב- audience insights, עבור אל **נתונים** > **אחד** > **התאם**.</span><span class="sxs-lookup"><span data-stu-id="3c072-175">In audience insights, go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="3c072-176">במקטע **כפילויות ממוזגות**, בחר **הגדר ישויות**.</span><span class="sxs-lookup"><span data-stu-id="3c072-176">In the **Merged duplicates** section, select **Set entities**.</span></span>

1. <span data-ttu-id="3c072-177">במקטע **העדפות מיזוג**, בחר את הישויות שברצונך להחיל עליהן ביטול כפילויות.</span><span class="sxs-lookup"><span data-stu-id="3c072-177">In the **Merge preferences** section, select the entities you want to apply deduplication to.</span></span>

1. <span data-ttu-id="3c072-178">ציין כיצד יש למזג את הרשומות הכפולות ובחר אחת מבין שלוש אפשרויות מיזוג:</span><span class="sxs-lookup"><span data-stu-id="3c072-178">Specify how to merge the duplicate records and choose one of three merge options:</span></span>
   - <span data-ttu-id="3c072-179">*הכי הרבה אנשים מילאו*: מזהה את הרשומה עם הכי הרבה תכונות מלאות כרשומה המנצחת.</span><span class="sxs-lookup"><span data-stu-id="3c072-179">*Most filled*: Identifies the record with most filled attributes as the winner record.</span></span> <span data-ttu-id="3c072-180">זוהי אפשרות המיזוג של ברירת המחדל.</span><span class="sxs-lookup"><span data-stu-id="3c072-180">This is the default merge option.</span></span>
   - <span data-ttu-id="3c072-181">*החדשים ביותר*: מזהה את הרשומה המנצחת בהתבסס על העדכניות.</span><span class="sxs-lookup"><span data-stu-id="3c072-181">*Most recent*: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="3c072-182">דורש תאריך או שדה מספרי להגדרת העדכניות.</span><span class="sxs-lookup"><span data-stu-id="3c072-182">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="3c072-183">*הישנים ביותר*: מזהה את הרשומה המנצחת בהתבסס על העדכניות הנמוכה ביותר.</span><span class="sxs-lookup"><span data-stu-id="3c072-183">*Least recent*: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="3c072-184">דורש תאריך או שדה מספרי להגדרת העדכניות.</span><span class="sxs-lookup"><span data-stu-id="3c072-184">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c072-185">![כללים לביטול כפילויות שלב 1](media/match-selfconflation.png "כללים לביטול כפילויות שלב 1")</span><span class="sxs-lookup"><span data-stu-id="3c072-185">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="3c072-186">כאשר הישויות נבחרות והעדפת המיזוג שלהן מוגדרת, בחר **צור כלל חדש** כדי להגדיר את כללי ביטול הכפילויות ברמת ישות.</span><span class="sxs-lookup"><span data-stu-id="3c072-186">Once the entities are selected and their merge preference is set, select **Create new rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="3c072-187">האפשרות **בחר שדה** מפרטת את כל השדות הזמינים מאותה ישות שבהם ברצונך לבטל את הכפילויות של נתוני המקור.</span><span class="sxs-lookup"><span data-stu-id="3c072-187">**Select field** lists all the available fields from that entity you want to deduplicate source data on.</span></span>
   - <span data-ttu-id="3c072-188">ציין את הגדרות הנרמול והדיוק באופן דומה, כפי שצוין בהתאמה בין ישויות.</span><span class="sxs-lookup"><span data-stu-id="3c072-188">Specify the normalization and precision settings in similar way as specified in the cross entity matching.</span></span>
   - <span data-ttu-id="3c072-189">באפשרותך להגדיר תנאים נוספים על-ידי בחירת **הוסף תנאי**.</span><span class="sxs-lookup"><span data-stu-id="3c072-189">You can define additional conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c072-190">![כללים לביטול כפילויות שלב 2](media/match-selfconflation-rules.png "כללים לביטול כפילויות שלב 2")</span><span class="sxs-lookup"><span data-stu-id="3c072-190">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="3c072-191">באפשרותך ליצור כללים מרובים לביטול כפילויות עבור ישות.</span><span class="sxs-lookup"><span data-stu-id="3c072-191">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="3c072-192">הפעלת תהליך ההתאמה מקבץ כעת את הרשומות בהתבסס על התנאים המוגדרים בכללי ביטול הכפילויות.</span><span class="sxs-lookup"><span data-stu-id="3c072-192">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="3c072-193">לאחר קיבוץ הרשומות, מדיניות המיזוג מיושמת כדי לזהות את הרשומה המנצחת.</span><span class="sxs-lookup"><span data-stu-id="3c072-193">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="3c072-194">רשומה מנצחת זו לאחר מכן מועברת להתאמה בין ישויות.</span><span class="sxs-lookup"><span data-stu-id="3c072-194">This winner record is then passed on to the cross-entity matching.</span></span>

1. <span data-ttu-id="3c072-195">כל כללי ההתאמה המותאמים אישית מוגדרים עבור כללי ביטול כפילויות של עקיפת התאמה תמיד והתאמה אף פעם.</span><span class="sxs-lookup"><span data-stu-id="3c072-195">Any custom match rules defined for always match and never match overrule deduplication rules.</span></span> <span data-ttu-id="3c072-196">אם כלל ביטול כפילויות מזהה רשומות מתאימות, וכלל התאמה מותאם אישית מוגדר כדי לא להתאים אף פעם לרשומות אלה, שתי הרשומות הללו לא יותאמו.</span><span class="sxs-lookup"><span data-stu-id="3c072-196">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="3c072-197">לאחר הפעלת תהליך ההתאמה, תראה את הנתונים הסטטיסטיים של ביטול הכפילויות.</span><span class="sxs-lookup"><span data-stu-id="3c072-197">After running the match process, you will see the deduplication stats.</span></span>
   
> [!NOTE]
> <span data-ttu-id="3c072-198">ציון כללי ביטול כפילויות אינו הכרחי.</span><span class="sxs-lookup"><span data-stu-id="3c072-198">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="3c072-199">אם לא מוגדרים כללים כאלה, מוחלים הכללים המוגדרים על-ידי המערכת.</span><span class="sxs-lookup"><span data-stu-id="3c072-199">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="3c072-200">הם מכווצים את כל הרשומות שחולקות את אותו שילוב ערכים (התאמה מדויקת) ממפתח ראשי ואת השדות בכללי ההתאמה לרשומה אחת לפני העברת נתוני הישות להתאמה בין ישויות עבור ביצועים משופרים ושפיות של מערכת.</span><span class="sxs-lookup"><span data-stu-id="3c072-200">They collapse all records that share the same value combination (exact match) from primary key and the fields in the matching rules into a single record before passing the entity data to cross-entity matching for enhanced performance and system sanity.</span></span>

## <a name="run-your-match-order"></a><span data-ttu-id="3c072-201">הפעל את סדר ההתאמה שלך</span><span class="sxs-lookup"><span data-stu-id="3c072-201">Run your match order</span></span>

<span data-ttu-id="3c072-202">לאחר הגדרת כללי ההתאמה, כולל כללי התאמה בין ישויות וביטול כפילות, ניתן להפעיל את סדר ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-202">After defining the match rules, including cross-entity matching and deduplication rules, you can run the match order.</span></span> <span data-ttu-id="3c072-203">בדף **התאמה** בחר **הפעל** כדי להתחיל בתהליך.</span><span class="sxs-lookup"><span data-stu-id="3c072-203">On the **Match** page, select **Run** to start the process.</span></span> <span data-ttu-id="3c072-204">ייתכן שאלגוריתם ההתאמה ייקח זמן להשלמת הפעולה.</span><span class="sxs-lookup"><span data-stu-id="3c072-204">The matching algorithm might take some time to complete.</span></span> <span data-ttu-id="3c072-205">אינך יכול לשנות מאפיינים בדף **התאמה** עד להשלמת תהליך ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-205">You can't change properties on the **Match** page until the match process completes.</span></span> <span data-ttu-id="3c072-206">תמצא את ישות פרופיל הלקוח המאוחד שנוצרה בדף **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="3c072-206">You'll find the unified customer profile entity that was created on the **Entities** page.</span></span> <span data-ttu-id="3c072-207">יישות הלקוח המאוחדת נקראת **ConflationMatchPairs : CustomerInsights**.</span><span class="sxs-lookup"><span data-stu-id="3c072-207">Your unified customer entity is called **ConflationMatchPairs:CustomerInsights**.</span></span>

<span data-ttu-id="3c072-208">כדי לבצע שינויים נוספים ולהפעיל מחדש את הצעד, באפשרותך לבטל התאמה מתבצעת.</span><span class="sxs-lookup"><span data-stu-id="3c072-208">To make additional changes and rerun the step, you can cancel a match in progress.</span></span> <span data-ttu-id="3c072-209">בחר את הטקסט **מרענן...** ובחר **בטל משימה** בתחתית החלונית הצדדית שמופיעה.</span><span class="sxs-lookup"><span data-stu-id="3c072-209">Select the **Refreshing ...** text and select **Cancel job** at the bottom of the side pane that appears.</span></span>

<span data-ttu-id="3c072-210">לאחר השלמת תהליך ההתאמה, הטקסט **מרענן...** ישתנה ל **בוצע בהצלחה** ותוכל להשתמש בכל הפונקציונליות של הדף שוב.</span><span class="sxs-lookup"><span data-stu-id="3c072-210">When the match process is complete, the **Refreshing ...** text will change to **Successful** and you can use all functionality of the page again.</span></span>

<span data-ttu-id="3c072-211">תהליך ההתאמה הראשון מביא ליצירת ישות אב מאוחדת.</span><span class="sxs-lookup"><span data-stu-id="3c072-211">The first match process results in the creation of a unified master entity.</span></span> <span data-ttu-id="3c072-212">כל ריצות ההתאמה שלאחר מכן גורמות להרחבה של אותה ישות.</span><span class="sxs-lookup"><span data-stu-id="3c072-212">All subsequent match runs result in the expansion of that entity.</span></span>

> [!TIP]
> <span data-ttu-id="3c072-213">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="3c072-213">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="3c072-214">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="3c072-214">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="3c072-215">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-215">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="3c072-216">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="3c072-216">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="3c072-217">בדוק ואמת את ההתאמות שלך</span><span class="sxs-lookup"><span data-stu-id="3c072-217">Review and validate your matches</span></span>

<span data-ttu-id="3c072-218">בצע הערכה של איכות זוגות ההתאמה:</span><span class="sxs-lookup"><span data-stu-id="3c072-218">Evaluate the quality of your match pairs and refine it:</span></span>

- <span data-ttu-id="3c072-219">בדף **התאמה**, תמצא שני אריחים המציגים תובנות ראשוניות לגבי הנתונים.</span><span class="sxs-lookup"><span data-stu-id="3c072-219">On the **Match** page, you'll find two tiles showing initial insights about your data.</span></span>

  - <span data-ttu-id="3c072-220">**לקוחות ייחודיים**: מציג את מספר הפרופילים הייחודיים שהמערכת זיהתה.</span><span class="sxs-lookup"><span data-stu-id="3c072-220">**Unique customers**: shows the number of unique profiles that the system identified.</span></span>
  - <span data-ttu-id="3c072-221">**רשומות תואמות**: מציג את מספר ההתאמות בכל צמדי ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-221">**Matched records**: shows the number of matches across all of your match pairs.</span></span>

- <span data-ttu-id="3c072-222">בטבלה **סדר התאמה**, באפשרותך להעריך את התוצאות של כל זוג-התאמה על ידי השוואה בין מספר הרשומות שהגיעו מישות זוג-התאמה זה לעומת אחוז הרשומות שהותאמו בהצלחה.</span><span class="sxs-lookup"><span data-stu-id="3c072-222">In the **Match order** table, you can assess the results of each match pair by comparing the number of records that came from this match-pair entity against the percentage of successfully matched records.</span></span>

- <span data-ttu-id="3c072-223">במקטע **כללים** של ישות בטבלה **סדר התאמה**, תוכל למצוא את אחוז הרשומות שהותאמו בהצלחה ברמת הכלל.</span><span class="sxs-lookup"><span data-stu-id="3c072-223">In the **Rules** section of an entity in the **Match order** table, you'll find the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="3c072-224">על ידי בחירת סמל הטבלה לצד כלל, תוכל להציג את כל הרשומות הללו ברמת הכלל.</span><span class="sxs-lookup"><span data-stu-id="3c072-224">By selecting the table symbol next to a rule, you can view all these records on the rule level.</span></span> <span data-ttu-id="3c072-225">אנו ממליצים לבדוק קבוצת משנה של הרשומות כדי לאמת שהם הותאמו נכון.</span><span class="sxs-lookup"><span data-stu-id="3c072-225">We recommend that you review a subset of the records to validate that they were matched correctly.</span></span>

- <span data-ttu-id="3c072-226">נסה ספי דיוק שונים עם התנאים שהגדרת כדי לזהות את הערך האופטימלי.</span><span class="sxs-lookup"><span data-stu-id="3c072-226">Experiment with different precision thresholds around your conditions to identify the optimal value.</span></span>

  1. <span data-ttu-id="3c072-227">בחר בשלוש הנקודות (...) עבור כלל זוג ההתאמה שאתה רוצה לשחק איתו ובחר **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="3c072-227">Select the ellipsis (...) for the match pair rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="3c072-228">בחר את התנאי שברצונך לבדוק.</span><span class="sxs-lookup"><span data-stu-id="3c072-228">Select the condition that you want to experiment with.</span></span> <span data-ttu-id="3c072-229">כל קריטריון מיוצג על ידי שורה אחת בחלונית **כלל התאמה**.</span><span class="sxs-lookup"><span data-stu-id="3c072-229">Each criterion is represented by one row in the **Match rule** pane.</span></span>

  3. <span data-ttu-id="3c072-230">מה שתראה בדף **תצוגה מקדימה של קריטריונים** תלוי ברמת הדיוק שבחרת לתנאי.</span><span class="sxs-lookup"><span data-stu-id="3c072-230">What you'll see on the **Criteria preview** page depends on the precision level you've selected for a condition.</span></span> <span data-ttu-id="3c072-231">מצא את מספר הרשומות המותאמות ואלה שלא הותאמו עבור התנאי שנבחר.</span><span class="sxs-lookup"><span data-stu-id="3c072-231">Find the number of matched and unmatched records for the selected condition.</span></span>

     <span data-ttu-id="3c072-232">הבן טוב יותר את ההשפעות של רמות סף שונות.</span><span class="sxs-lookup"><span data-stu-id="3c072-232">Get a rich understanding of the effects of different threshold levels.</span></span> <span data-ttu-id="3c072-233">אתה יכול להשוות כמה רשומות יותאמו בכל אחת מרמות הסף, ולהציג את הרשומות שבכל אפשרות.</span><span class="sxs-lookup"><span data-stu-id="3c072-233">You can compare how many records will be matched under each of the threshold levels, and view the records under each option.</span></span> <span data-ttu-id="3c072-234">בחר כל אחד מהאריחים ובדוק את הנתונים במקטע הטבלה.</span><span class="sxs-lookup"><span data-stu-id="3c072-234">Select each of the tiles and review the data in the table section.</span></span>

## <a name="optimize-your-matches"></a><span data-ttu-id="3c072-235">מטב את ההתאמות</span><span class="sxs-lookup"><span data-stu-id="3c072-235">Optimize your matches</span></span>

<span data-ttu-id="3c072-236">שפר את האיכות על ידי הגדרה מחדש של כמה מפרמטרי ההתאמה:</span><span class="sxs-lookup"><span data-stu-id="3c072-236">Increase the quality by reconfiguring some of your match parameters:</span></span>

- <span data-ttu-id="3c072-237">**שנה את סדר ההתאמה** על ידי בחירה באפשרות **ערוך** ושנה את שדות סדר ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-237">**Change the match order** by selecting **Edit** and change the match order fields.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="3c072-238">![עריכת סדר התאמת הנתונים](media/configure-data-match-order-edit.png "עריכת סדר התאמת הנתונים")</span><span class="sxs-lookup"><span data-stu-id="3c072-238">![Edit data match order](media/configure-data-match-order-edit.png "Edit data match order")</span></span>

- <span data-ttu-id="3c072-239">**שנה את סדר הכללים** אם הגדרת מספר כללים.</span><span class="sxs-lookup"><span data-stu-id="3c072-239">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="3c072-240">באפשרותך לסדר מחדש את כללי ההתאמה על ידי בחירה באפשרויות **הזז למעלה** או **הזז למטה** ברשת כללי ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-240">You can reorder the match rules by selecting the **Move Up** and **Move Down** options in the match rules grid.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="3c072-241">![שנה את סדר הכללים](media/configure-data-change-rule-order.png "שנה את סדר הכללים")</span><span class="sxs-lookup"><span data-stu-id="3c072-241">![Change rule order](media/configure-data-change-rule-order.png "Change rule order")</span></span>

- <span data-ttu-id="3c072-242">**שכפל את הכללים** אם הגדרת כלל התאמה וברצונך ליצור כלל דומה עם שינויים.</span><span class="sxs-lookup"><span data-stu-id="3c072-242">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications.</span></span> <span data-ttu-id="3c072-243">עשה זאת על ידי בחירה באפשרות **שכפל‬**.</span><span class="sxs-lookup"><span data-stu-id="3c072-243">Do so by selecting **Duplicate**.</span></span>

  > [!div class="mx-imgBorder"]
  > <span data-ttu-id="3c072-244">![שכפל כלל](media/configure-data-duplicate-rule.png "שכפל כלל")</span><span class="sxs-lookup"><span data-stu-id="3c072-244">![Duplicate a rule](media/configure-data-duplicate-rule.png "Duplicate a rule")</span></span>

- <span data-ttu-id="3c072-245">**ערוך את הכללים** על ידי בחירה בסמל **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="3c072-245">**Edit your rules** by selecting the **Edit** symbol.</span></span> <span data-ttu-id="3c072-246">באפשרותך לבצע את השינויים הבאים:</span><span class="sxs-lookup"><span data-stu-id="3c072-246">You can apply the following changes:</span></span>

  - <span data-ttu-id="3c072-247">שינוי תכונות עבור תנאי: בחר תכונות חדשות בשורת התנאים הספציפית.</span><span class="sxs-lookup"><span data-stu-id="3c072-247">Change attributes for a condition: Select new attributes within the specific condition row.</span></span>
  - <span data-ttu-id="3c072-248">שנה את סף התנאי: התאם את מחוון הדיוק.</span><span class="sxs-lookup"><span data-stu-id="3c072-248">Change the threshold for a condition: Adjust the precision slider.</span></span>
  - <span data-ttu-id="3c072-249">שנה את שיטת הנרמול של תנאי: עדכן את שיטת הנרמול.</span><span class="sxs-lookup"><span data-stu-id="3c072-249">Change the normalization method for a condition: Update the normalization method.</span></span>

## <a name="specify-your-custom-match-records"></a><span data-ttu-id="3c072-250">ציין את רשומות ההתאמה המותאמות אישית</span><span class="sxs-lookup"><span data-stu-id="3c072-250">Specify your custom match records</span></span>

<span data-ttu-id="3c072-251">ניתן לציין תנאים שרשומות מסוימות צריכות להתאים להם תמיד או אף פעם.</span><span class="sxs-lookup"><span data-stu-id="3c072-251">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="3c072-252">ניתן להעלות כללים אלה ביחד לתהליך ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-252">These rules can be uploaded in bulk to the match process.</span></span>

1. <span data-ttu-id="3c072-253">בחר באפשרות **התאמה אישית** במסך **סדר התאמה**.</span><span class="sxs-lookup"><span data-stu-id="3c072-253">Select the **Custom match** option on the **Match order** screen.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c072-254">![יצירת התאמה מותאמת אישית](media/custom-match-create.png "יצירת התאמה מותאמת אישית")</span><span class="sxs-lookup"><span data-stu-id="3c072-254">![Create a custom match](media/custom-match-create.png "Create a custom match")</span></span>

2. <span data-ttu-id="3c072-255">אם אין לך ישויות שהועלו, תראה תיבת דו-שיח חדשה של **התאמה אישית** המחייבת אותך למלא כמה פרטים.</span><span class="sxs-lookup"><span data-stu-id="3c072-255">If you have no uploaded entities, you'll see a new **Custom match** dialog box that requires you to fill in some details.</span></span> <span data-ttu-id="3c072-256">אם סיפקת את הפרטים האלה קודם לכן, דלג לשלב 8.</span><span class="sxs-lookup"><span data-stu-id="3c072-256">If you've provided these details earlier, skip to step 8.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c072-257">![תיבת דו-שיח חדשה של התאמה אישית](media/custom-match-new-dialog-box.png "תיבת דו-שיח חדשה של התאמה אישית")</span><span class="sxs-lookup"><span data-stu-id="3c072-257">![New custom match dialog box](media/custom-match-new-dialog-box.png "New custom match dialog box")</span></span>

3. <span data-ttu-id="3c072-258">בחר **מלא את התבנית** כדי לקבל קובץ תבנית שיכול לציין אילו רשומות מאילו ישויות תמיד צריכות להתאים או לעולם לא להתאים.</span><span class="sxs-lookup"><span data-stu-id="3c072-258">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="3c072-259">יהיה עליך למלא בנפרד את הרשומות "תמיד להתאים" ו"אף פעם לא להתאים" בשני קבצים שונים.</span><span class="sxs-lookup"><span data-stu-id="3c072-259">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

4. <span data-ttu-id="3c072-260">התבנית מכילה שדות לציון הישות וערכי המפתח העיקריים של הישות שישמשו בהתאמה המותאמת אישית.</span><span class="sxs-lookup"><span data-stu-id="3c072-260">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="3c072-261">לדוגמה, אם ברצונך שמפתח ראשי 12345 מישות מכירות יתאים תמיד למפתח הראשי 34567 מישות אנשי קשר, תצטרך לציין:</span><span class="sxs-lookup"><span data-stu-id="3c072-261">For example, if you want primary key 12345 from Sales entity to always match with primary key 34567 from Contact entity, you'll need to specify as follows:</span></span>
    - <span data-ttu-id="3c072-262">ישות 1: מכירות</span><span class="sxs-lookup"><span data-stu-id="3c072-262">Entity1: Sales</span></span>
    - <span data-ttu-id="3c072-263">מפתח ישות 1: 12345</span><span class="sxs-lookup"><span data-stu-id="3c072-263">Entity1Key: 12345</span></span>
    - <span data-ttu-id="3c072-264">ישות 2: איש קשר</span><span class="sxs-lookup"><span data-stu-id="3c072-264">Entity2: Contact</span></span>
    - <span data-ttu-id="3c072-265">מפתח ישות 2: 34567</span><span class="sxs-lookup"><span data-stu-id="3c072-265">Entity2Key: 34567</span></span>

   <span data-ttu-id="3c072-266">אותו קובץ תבנית יכול לציין רשומות התאמה בהתאמה אישית מישויות מרובות.</span><span class="sxs-lookup"><span data-stu-id="3c072-266">The same template file can specify custom match records from multiple entities.</span></span>

5. <span data-ttu-id="3c072-267">לאחר הוספת כל הדרישות שברצונך להחיל, שמור את קובץ התבנית.</span><span class="sxs-lookup"><span data-stu-id="3c072-267">After adding all the overrides you want to apply, save the template file.</span></span>

<span data-ttu-id="3c072-268">6.עבור אל **נתונים** > **מקורות נתונים** וקלוט את קבצי התבנית כישויות חדשות.</span><span class="sxs-lookup"><span data-stu-id="3c072-268">6.Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="3c072-269">לאחר השילוב תוכל להשתמש בהם כדי לציין את תצורת ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="3c072-269">Once ingested, you can use them to specify the Match configuration.</span></span>

7. <span data-ttu-id="3c072-270">לאחר העלאת הישויות והקבצים הזמינים, בחר שוב **התאמה אישית**.</span><span class="sxs-lookup"><span data-stu-id="3c072-270">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="3c072-271">תראה אפשרויות לציון הישויות שתרצה לכלול.</span><span class="sxs-lookup"><span data-stu-id="3c072-271">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="3c072-272">בחר את הישויות הרצויות מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="3c072-272">Select the required entities from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3c072-273">![עקיפות התאמה מותאמת אישית](media/custom-match-overrides.png "עקיפות התאמה מותאמת אישית")</span><span class="sxs-lookup"><span data-stu-id="3c072-273">![Custom match overrides](media/custom-match-overrides.png "Custom match overrides")</span></span>

8. <span data-ttu-id="3c072-274">בחר את הישויות שבהן תרצה להשתמש עבור **תמיד התאם** או **לעולם אל תתאים**, בחר **בוצע**.</span><span class="sxs-lookup"><span data-stu-id="3c072-274">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

9. <span data-ttu-id="3c072-275">בחר **שמור** בדף **התאמה** עבור תצורת ההתאמה האישית שהגדרת זה עתה.</span><span class="sxs-lookup"><span data-stu-id="3c072-275">Select **Save** on the **Match** page for the custom match configuration you just set up.</span></span>

10. <span data-ttu-id="3c072-276">בחר **הפעל** בדף **התאמה** כדי להתחיל בתהליך ההתאמה, ותצורת ההתאמה המותאמת אישית תיכנס לתוקף.</span><span class="sxs-lookup"><span data-stu-id="3c072-276">Select **Run** on the **Match** page to start the matching process, and the custom match configuration will be taken into effect.</span></span> <span data-ttu-id="3c072-277">הגדרת התצורה מקבלת עדיפות על פני כל כללי ההתאמה של המערכת.</span><span class="sxs-lookup"><span data-stu-id="3c072-277">Any system matched rules are overridden by the configuration set.</span></span>

11. <span data-ttu-id="3c072-278">לאחר השלמת ההתאמה, תוכל לאמת את הישות **ConflationMatchPair** כדי לאשר שההחלפות מיושמות בהתאמות ההתנגשויות.</span><span class="sxs-lookup"><span data-stu-id="3c072-278">Once the matching is complete, you can verify the **ConflationMatchPair** entity to confirm that the overrides are applied in the conflation matches.</span></span>

## <a name="next-step"></a><span data-ttu-id="3c072-279">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="3c072-279">Next step</span></span>

<span data-ttu-id="3c072-280">לאחר השלמת תהליך ההתאמה עבור זוג התאמה אחד לפחות, אתה יכול לפתור סתירות אפשריות בנתונים על ידי מעבר על הנושא [**מיזוג**](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="3c072-280">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>
