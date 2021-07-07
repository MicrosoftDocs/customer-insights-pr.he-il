---
title: התאמת ישויות לאיחוד נתונים
description: התאם ישויות ליצירת פרופילי לקוח מאוחדים.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50b11e7d6f62d7a25eb25a0f2b1c4ad7d859def1
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306029"
---
# <a name="match-entities"></a><span data-ttu-id="6fe73-103">התאמת ישויות</span><span class="sxs-lookup"><span data-stu-id="6fe73-103">Match entities</span></span>

<span data-ttu-id="6fe73-104">שלב ההתאמה מציין כיצד לשלב את ערכות הנתונים שלך בערכת נתונים של פרופיל לקוח אחיד.</span><span class="sxs-lookup"><span data-stu-id="6fe73-104">The match phase specifies how to combine your datasets into a unified customer profile dataset.</span></span> <span data-ttu-id="6fe73-105">לאחר השלמת [צעד המפה](map-entities.md) בתהליך איחוד הנתונים, אתה מוכן להתאמת הישויות שלך.</span><span class="sxs-lookup"><span data-stu-id="6fe73-105">After completing the [map step](map-entities.md) in the data unification process, you're ready to match your entities.</span></span> <span data-ttu-id="6fe73-106">שלב ההתאמה דורש לפחות שתי ישויות ממופות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-106">The match phase requires at least two mapped entities.</span></span>

<span data-ttu-id="6fe73-107">דף ההתאמה מורכב משלושה חלקים:</span><span class="sxs-lookup"><span data-stu-id="6fe73-107">The match page consists of three sections:</span></span> 
- <span data-ttu-id="6fe73-108">מדדים עיקריים המסכמים את מספר הרשומות המותאמות</span><span class="sxs-lookup"><span data-stu-id="6fe73-108">Key metrics that summarize the number of matched records</span></span>
- <span data-ttu-id="6fe73-109">סדר ההתאמה והכללים עבור התאמה בין ישויות</span><span class="sxs-lookup"><span data-stu-id="6fe73-109">Match order and rules for cross-entity matching</span></span>
- <span data-ttu-id="6fe73-110">כללים לביטול כפילויות של ישויות התאמה</span><span class="sxs-lookup"><span data-stu-id="6fe73-110">Rules for deduplication of match entities</span></span>

## <a name="specify-the-match-order"></a><span data-ttu-id="6fe73-111">ציין את סדר ההתאמה</span><span class="sxs-lookup"><span data-stu-id="6fe73-111">Specify the match order</span></span>

<span data-ttu-id="6fe73-112">עבור אל **נתחנים** > **אחד** > **התאם** ובחר **הגדר סדר** כדי להתחיל בשלב ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-112">Go to **Data** > **Unify** > **Match** and select **Set order** to start the match phase.</span></span>

<span data-ttu-id="6fe73-113">כל התאמה מאחדת שתי ישויות או יותר לישות אחת מאוחדת.</span><span class="sxs-lookup"><span data-stu-id="6fe73-113">Each match unifies two or more entities into a single, consolidated entity.</span></span> <span data-ttu-id="6fe73-114">בו-זמנית, היא שומרת על רשומות הלקוח הייחודיות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-114">At the same time, it keeps the unique customer records.</span></span> <span data-ttu-id="6fe73-115">לדוגמה, בחרנו שתי ישויות: **eCommerce:eCommerceContacts** כישות הראשית ו- **LoyaltyScheme:loyCustomers** כישות השנייה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-115">For example, we selected two entities: **eCommerce:eCommerceContacts** as the primary entity and **LoyaltyScheme:loyCustomers** as second entity.</span></span> <span data-ttu-id="6fe73-116">סדר הישויות מציין באיזה סדר המערכת תנסה להתאים את הרשומות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-116">The order of the entities specifies in which order the system will try to match the records.</span></span>

:::image type="content" source="media/match-page.png" alt-text="צילום מסך של דף ההתאמה באזור Unify של תהליך איחוד הנתונים.":::
  
<span data-ttu-id="6fe73-118">הישות הראשית *eCommerce:eCommerceContacts* מותאמת לישות הבאה *LoyaltyScheme:loyCustomers*.</span><span class="sxs-lookup"><span data-stu-id="6fe73-118">The primary entity *eCommerce:eCommerceContacts* is matched with the next entity *LoyaltyScheme:loyCustomers*.</span></span> <span data-ttu-id="6fe73-119">ערכת הנתונים המתקבלת משלב ההתאמה הראשון מותאמת לישות הבאה, אם יש לך יותר משתי ישויות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-119">The dataset that results from the first match step is matched with the following entity if you have more than two entities.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6fe73-120">הישות שאתה בוחר בתור הישות הראשית שלך תשמש כבסיס לערכת הנתונים של הפרופילים המאוחדים שלך.</span><span class="sxs-lookup"><span data-stu-id="6fe73-120">The entity that you choose as your primary entity will serve as the basis for your unified profiles dataset.</span></span> <span data-ttu-id="6fe73-121">ישויות נוספות שנבחרות במהלך שלב ההתאמה יתווספו לישות זו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-121">Additional entities that are selected during the match phase will be added to this entity.</span></span> <span data-ttu-id="6fe73-122">אין פירושו של דבר שהישות המאוחדת תכלול את *כל* הנתונים הכלולים בישות זו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-122">This doesn't mean that the unified entity will include *all* of the data included in this entity.</span></span>
>
> <span data-ttu-id="6fe73-123">קיימים שני שיקולים שיכולים לסייע לך לבחור את ההירארכיה של היישויות:</span><span class="sxs-lookup"><span data-stu-id="6fe73-123">There are two considerations that can help you choose the hierarchy of your entities:</span></span>
>
> - <span data-ttu-id="6fe73-124">בחר את הישות עם נתוני הפרופיל המלאים והאמינים ביותר אודות לקוחותיך כישות ראשית.</span><span class="sxs-lookup"><span data-stu-id="6fe73-124">Choose the entity with the most complete and reliable profile data about your customers as primary entity.</span></span>
> - <span data-ttu-id="6fe73-125">בחר את הישות שיש לה מספר תכונות משותפות עם ישויות אחרות (למשל, שם, מספר טלפון או כתובת דואר) כישות ראשית.</span><span class="sxs-lookup"><span data-stu-id="6fe73-125">Choose the entity that hast several attributes in common with other entities (for example, name, phone number, or email address) as primary entity.</span></span>

<span data-ttu-id="6fe73-126">לאחר ציון סדר ההתאמה, תראה את זוגות ההתאמה המוגדרים במקטע **פרטי רשומות תואמות** תחת **נתונים** > **איחוד** > **התאמה**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-126">After specifying the match order, you'll see the defined match pairs in the **Matched records details** section on **Data** > **Unify** > **Match**.</span></span> <span data-ttu-id="6fe73-127">המדדים העיקריים יהיו ריקים עד לסיום תהליך ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-127">The key metrics will be empty until the match process completes.</span></span>

## <a name="define-rules-for-match-pairs"></a><span data-ttu-id="6fe73-128">הגדרת כללים עבור זוגות התאמה</span><span class="sxs-lookup"><span data-stu-id="6fe73-128">Define rules for match pairs</span></span>

<span data-ttu-id="6fe73-129">כללי התאמה מציינים את הלוגיקה שלפיה יותאמו זוג ישויות מסוים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-129">Match rules specify the logic by which a specific pair of entities will be matched.</span></span>

<span data-ttu-id="6fe73-130">האזהרה **זקוק לכללים** לצד שם הישות מעידה על כך שלא הוגדר כלל התאמה עבור זוג התאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-130">The **Needs rules** warning next to an entity name suggests that no match rule is defined for a match pair.</span></span> 

:::image type="content" source="media/match-rule-add.png" alt-text="צילום מסך של המקטע 'פרטי רשומות תואמות' עם פקד להוספת כללים מודגש.":::

1. <span data-ttu-id="6fe73-132">בחר **הוסף כללים** תחת ישות במקטע **פרטי רשומות תואמות** להגדרת כללי התאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-132">Select **Add rules** under an entity in the **Matched records details** section to define match rules.</span></span>

1. <span data-ttu-id="6fe73-133">בחלונית **צור כלל**, קבע את תצורת התנאים עבור הכלל.</span><span class="sxs-lookup"><span data-stu-id="6fe73-133">In the **Create rule** pane, configure the conditions for the rule.</span></span>

   :::image type="content" source="media/match-rule-conditions.png" alt-text="צילום מסך של כלל התאמה שנפתח עם תנאים שנוספו.":::

   - <span data-ttu-id="6fe73-135">**ישות/שדה (שורה ראשונה)**: בחר ישות קשורה ותכונה כדי לציין מאפיין רשומה שעשוי להיות ייחודי ללקוח.</span><span class="sxs-lookup"><span data-stu-id="6fe73-135">**Entity/Field (first row)**: Choose a related entity and an attribute to specify a record property that is likely unique to a customer.</span></span> <span data-ttu-id="6fe73-136">לדוגמא, מספר טלפון או כתובת דואר.</span><span class="sxs-lookup"><span data-stu-id="6fe73-136">For example, a phone number or email address.</span></span> <span data-ttu-id="6fe73-137">הימנע מהתאמה לפי תכונות מסוג פעילות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-137">Avoid matching by activity-type attributes.</span></span> <span data-ttu-id="6fe73-138">לדוגמא, כנראה שלמזהה רכישה לא תהיה התאמה בסוגי רשומה אחרים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-138">For example, a purchase ID will likely find no match in other record types.</span></span>

   - <span data-ttu-id="6fe73-139">**ישות/שדה (שורה שנייה)**: בחר מאפיין המתייחס לתכונה של הישות שצוינה בשורה הראשונה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-139">**Entity/Field (second row)**: Choose an attribute that relates to the attribute of the entity specified in the first row.</span></span>

   - <span data-ttu-id="6fe73-140">**נרמל**: בחר מבין אפשרויות הנרמול הבאות עבור התכונות שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-140">**Normalize**: Select from following normalization options for the selected attributes.</span></span> 
     - <span data-ttu-id="6fe73-141">רווח לבן: מסיר את כל הרווחים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-141">Whitespace: Removes all spaces.</span></span> <span data-ttu-id="6fe73-142">*שלום   עולם* הופך להיות *שלוםעולם*.</span><span class="sxs-lookup"><span data-stu-id="6fe73-142">*Hello   World* becomes *HelloWorld*.</span></span>
     - <span data-ttu-id="6fe73-143">סמלים: מסיר את כל הסמלים והתווים המיוחדים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-143">Symbols: Removes all symbols and special characters.</span></span> <span data-ttu-id="6fe73-144">*ראש&כתף* הופך להיות *ראשכתף*.</span><span class="sxs-lookup"><span data-stu-id="6fe73-144">*Head&Shoulder* becomes *HeadShoulder*.</span></span>
     - <span data-ttu-id="6fe73-145">טקסט לאותיות קטנות: ממיר את כל התווים לאותיות קטנות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-145">Text to lower case: Converts all character to lower case.</span></span> <span data-ttu-id="6fe73-146">*ALL CAPS and Title Case* הופך להיות *all caps and title case*.</span><span class="sxs-lookup"><span data-stu-id="6fe73-146">*ALL CAPS and Title Case* becomes *all caps and title case*.</span></span>
     - <span data-ttu-id="6fe73-147">Unicode ל- ASCII: ממיר את סימון ה- Unicode לתווי ASCII.</span><span class="sxs-lookup"><span data-stu-id="6fe73-147">Unicode to ASCII: Converts unicode notation to ASCII characters.</span></span> <span data-ttu-id="6fe73-148">*/u00B2* הופך להיות *2*.</span><span class="sxs-lookup"><span data-stu-id="6fe73-148">*/u00B2* becomes *2*.</span></span>
     - <span data-ttu-id="6fe73-149">ספרות: ממיר מערכות ספרות אחרות, כגון ספרות רומיות, לספרות בערבית.</span><span class="sxs-lookup"><span data-stu-id="6fe73-149">Numerals: Converts other numeral systems, such as Roman numerals, to Arabic numerals.</span></span> <span data-ttu-id="6fe73-150">*VIII* הופך להיות *8*.</span><span class="sxs-lookup"><span data-stu-id="6fe73-150">*VIII* becomes *8*.</span></span>
     - <span data-ttu-id="6fe73-151">סוגים סמנטיים: מתקנן שמות, כותרות, מספרי טלפון, כתובות וכדומה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-151">Semantic types: Standardizes names, titles, phone numbers, addresses, etc.</span></span> 

   - <span data-ttu-id="6fe73-152">**דיוק**: מגדיר את רמת הדיוק להחלה עבור תנאי זה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-152">**Precision**: Set the level of precision to apply for this condition.</span></span> 
     - <span data-ttu-id="6fe73-153">**בסיסי**: בחר מבין *נמוך*, *בינוני*, *גבוה*, ו *מדויק*.</span><span class="sxs-lookup"><span data-stu-id="6fe73-153">**Basic**: Choose from *Low*, *Medium*, *High*, and *Exact*.</span></span> <span data-ttu-id="6fe73-154">בחר **מדויק** כדי להתאים רק רשומות שתואמות ב- 100 אחוז.</span><span class="sxs-lookup"><span data-stu-id="6fe73-154">Select **Exact** to only match records that that match 100 percent.</span></span> <span data-ttu-id="6fe73-155">בחר אחת מהרמות האחרות כדי להתאים רשומות שאינן זהות ב- 100 אחוז.</span><span class="sxs-lookup"><span data-stu-id="6fe73-155">Select one of the other levels to match records that aren't 100 percent identical.</span></span>
     - <span data-ttu-id="6fe73-156">**מותאם אישית**: הגדר אחוז התאמה רצוי עבור רשומות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-156">**Custom**: Set a percentage that records need to match.</span></span> <span data-ttu-id="6fe73-157">המערכת תתאים רק רשומות שעוברות ערך סף זה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-157">The system will only match records passing this threshold.</span></span>

1. <span data-ttu-id="6fe73-158">ספק **שם** עבור הכלל.</span><span class="sxs-lookup"><span data-stu-id="6fe73-158">Provide a **Name** for the rule.</span></span>

1. <span data-ttu-id="6fe73-159">[הוסף תנאים נוספים](#add-conditions-to-a-rule) או בחר **בוצע** כדי לסיים את הכלל.</span><span class="sxs-lookup"><span data-stu-id="6fe73-159">[Add more conditions](#add-conditions-to-a-rule) or select **Done** to finalize the rule.</span></span>

1. <span data-ttu-id="6fe73-160">לבחירתך, [הוסף כללים נוספים](#add-rules-to-a-match-pair).</span><span class="sxs-lookup"><span data-stu-id="6fe73-160">Optionally, [add more rules](#add-rules-to-a-match-pair).</span></span>

1. <span data-ttu-id="6fe73-161">בחר **שמור** כדי להחיל את השינויים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-161">Select **Save** to apply your changes.</span></span>

### <a name="add-conditions-to-a-rule"></a><span data-ttu-id="6fe73-162">הוסף תנאים לכלל</span><span class="sxs-lookup"><span data-stu-id="6fe73-162">Add conditions to a rule</span></span>

<span data-ttu-id="6fe73-163">כדי להתאים ישויות רק אם תכונות עומדות בתנאים מרובים, הוסף תנאים נוספים לכלל התאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-163">To match entities only if attributes meet multiple conditions, add more conditions to a match rule.</span></span> <span data-ttu-id="6fe73-164">התנאים קשורים לאופרטור AND לוגי וכך הם מופעלים רק אם כל התנאים מתקיימים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-164">Conditions are connected with a logical AND operator and thus only executed if all conditions are met.</span></span>

1. <span data-ttu-id="6fe73-165">עבור אל **נתונים** > **איחוד** > **התאמה** ובחר **ערוך** בכלל שאליו ברצונך להוסיף תנאים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-165">Go to **Data** > **Unify** > **Match** and select **Edit** on the rule you want to add conditions to.</span></span>

1. <span data-ttu-id="6fe73-166">בחלונית **ערוך כלל**, בחר באפשרות **הוסף תנאי**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-166">In the **Edit rule** pane, select **Add condition**.</span></span>

1. <span data-ttu-id="6fe73-167">בחר **בוצע** כדי לשמור את הכלל.</span><span class="sxs-lookup"><span data-stu-id="6fe73-167">Select **Done** so save the rule.</span></span>

### <a name="add-rules-to-a-match-pair"></a><span data-ttu-id="6fe73-168">הוספת כללים לזוג התאמה</span><span class="sxs-lookup"><span data-stu-id="6fe73-168">Add rules to a match pair</span></span>

<span data-ttu-id="6fe73-169">כללי התאמה מייצגים קבוצות של תנאים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-169">Match rules represent sets of conditions.</span></span> <span data-ttu-id="6fe73-170">כדי להתאים ישויות לפי תנאים, בהתבסס על תכונות מרובות, הוסף כללים נוספים</span><span class="sxs-lookup"><span data-stu-id="6fe73-170">To match entities by conditions based on multiple attributes, add more rules</span></span>

1.  <span data-ttu-id="6fe73-171">עבור אל **נתונים** > **איחוד** > **התאמה** ובחר **הוסף כללי** בישות שאליה ברצונך להוסיף כללים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-171">Go to **Data** > **Unify** > **Match** and select **Add rule** on the entity you want to add rules to.</span></span>

2. <span data-ttu-id="6fe73-172">בצע את השלבים ב[הגדרת כללים עבור זוגות התאמה](#define-rules-for-match-pairs).</span><span class="sxs-lookup"><span data-stu-id="6fe73-172">Follow the steps in [Define rules for match pairs](#define-rules-for-match-pairs).</span></span>

> [!NOTE]
> <span data-ttu-id="6fe73-173">סדר הכללים חשוב.</span><span class="sxs-lookup"><span data-stu-id="6fe73-173">The order of rules matters.</span></span> <span data-ttu-id="6fe73-174">אלגוריתם ההתאמה מנסה להתאים על בסיס הכלל הראשון שלך וממשיך לכלל השני רק אם לא זוהו התאמות עם הכלל הראשון.</span><span class="sxs-lookup"><span data-stu-id="6fe73-174">The matching algorithm tries to match on the basis of your first rule and continues to the second rule only if no matches were identified with the first rule.</span></span>

### <a name="change-the-entity-order-in-match-rules"></a><span data-ttu-id="6fe73-175">שנה את סדר הישויות בכללי ההתאמה</span><span class="sxs-lookup"><span data-stu-id="6fe73-175">Change the entity order in match rules</span></span>

<span data-ttu-id="6fe73-176">באפשרותך לסדר מחדש את הישויות לפי כללי התאמה על מנת לשנות את הסדר שבו הן מעובדות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-176">You can reorder entities for match rules to change the order in which they are processed.</span></span> <span data-ttu-id="6fe73-177">כללים שמתנגשים בגלל סדר ששונה יוסרו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-177">Rules that are conflicting because of a changed order will be removed.</span></span> <span data-ttu-id="6fe73-178">עליך ליצור מחדש כללים שהוסרו בעזרת תצורה מעודכנת.</span><span class="sxs-lookup"><span data-stu-id="6fe73-178">You have to recreate removed rules with an updated configuration.</span></span>

1. <span data-ttu-id="6fe73-179">עבור אל **נתונים** > **איחוד** > **התאמה** ובחר **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-179">Go to **Data** > **Unify** > **Match** and select **Edit**.</span></span>

1. <span data-ttu-id="6fe73-180">בחלונית **ערוך כלל**, בחר בפקד **הזז למעלה/למטה** או גרור ושחרר ישויות לשינוי הסדר.</span><span class="sxs-lookup"><span data-stu-id="6fe73-180">In the **Edit rule** pane, select the **Move up/down** control or drag and drop entities to change the order.</span></span>

   :::image type="content" source="media/reorder-match-rules.png" alt-text="אפשרויות לשינוי שבהן ישויות הזמנת עבודה מעובדות בשלב ההתאמה.":::

1. <span data-ttu-id="6fe73-182">בחר **בוצע** כדי לשמור את הכלל.</span><span class="sxs-lookup"><span data-stu-id="6fe73-182">Select **Done** so save the rule.</span></span>

## <a name="define-deduplication-on-a-match-entity"></a><span data-ttu-id="6fe73-183">הגדרת ביטול כפילויות בישות מתאימה</span><span class="sxs-lookup"><span data-stu-id="6fe73-183">Define deduplication on a match entity</span></span>

<span data-ttu-id="6fe73-184">בנוסף ל[כללי התאמה בין ישויות](#define-rules-for-match-pairs), באפשרותך גם לציין כללי ביטול כפילויות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-184">In addition to [cross-entity match rules](#define-rules-for-match-pairs), you can also specify deduplications rules.</span></span> <span data-ttu-id="6fe73-185">*ביטול כפילויות* הוא תהליך נוסף בעת התאמת רשומות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-185">*Deduplication* is another process when matching records.</span></span> <span data-ttu-id="6fe73-186">הוא מזהה רשומות כפולות וממזג אותן לרשומה אחת.</span><span class="sxs-lookup"><span data-stu-id="6fe73-186">It identifies duplicate records and merges them into one record.</span></span> <span data-ttu-id="6fe73-187">רשומות המקור נקשרות לרשומה הממוזגת עם מזהים חלופיים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-187">Source records get linked to the merged record with alternate IDs.</span></span>

<span data-ttu-id="6fe73-188">רשומות שהכפילויות שלהן בוטלו ישמשו בתהליך ההתאמה בין ישויות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-188">Deduplicated records will be used in the cross-entity matching process.</span></span> <span data-ttu-id="6fe73-189">ביטול כפילויות מתרחש בישויות בודדות וניתן להגדיר אותו עבור כל ישות המשתמש בזוגות התאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-189">Deduplication happens on individual entities and can be configured every entity used in match pairs.</span></span>

<span data-ttu-id="6fe73-190">ציון כללי ביטול כפילויות אינו הכרחי.</span><span class="sxs-lookup"><span data-stu-id="6fe73-190">Specifying deduplication rules isn't mandatory.</span></span> <span data-ttu-id="6fe73-191">אם לא מוגדרים כללים כאלה, מוחלים הכללים המוגדרים על-ידי המערכת.</span><span class="sxs-lookup"><span data-stu-id="6fe73-191">If no such rules are configured, the system-defined rules are applied.</span></span> <span data-ttu-id="6fe73-192">הם משלבים את כל הרשומות לרשומה אחת לפני שהם מעבירים את נתוני הישות להתאמה בין ישויות עבור ביצועים משופרים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-192">They combine all records into a single record before passing the entity data to cross-entity matching for enhanced performance.</span></span>

### <a name="add-deduplication-rules"></a><span data-ttu-id="6fe73-193">הוספת כללים לביטול כפילויות</span><span class="sxs-lookup"><span data-stu-id="6fe73-193">Add deduplication rules</span></span>

1. <span data-ttu-id="6fe73-194">עבור אל **נתונים** > **איחוד** > **התאמה**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-194">Go to **Data** > **Unify** > **Match**.</span></span>

1. <span data-ttu-id="6fe73-195">במקטע **כפילויות ממוזגות**, בחר **הגדר ישויות**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-195">In the **Merged duplicates** section, select **Set entities**.</span></span> <span data-ttu-id="6fe73-196">במקרה שכבר נוצרו כללי ביטול כפילות, בחר **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-196">In case deduplication rules are already created, select **Edit**.</span></span>

1. <span data-ttu-id="6fe73-197">בחלונית **העדפות מיזוג**, בחר את הישויות שברצונך להפעיל בהן ביטול כפילויות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-197">In the **Merge preferences** pane, choose the entities you want to run deduplication on.</span></span>

1. <span data-ttu-id="6fe73-198">ציין כיצד יש לשלב את הרשומות הכפולות ובחר אחת מבין שלוש אפשרויות:</span><span class="sxs-lookup"><span data-stu-id="6fe73-198">Specify how to combine the duplicate records and choose one of three options:</span></span>
   - <span data-ttu-id="6fe73-199">**הכי הרבה אנשים מילאו**: מזהה את הרשומה עם הכי הרבה שדות תכונה מאוכלסים כרשומה המנצחת.</span><span class="sxs-lookup"><span data-stu-id="6fe73-199">**Most filled**: Identifies the record with most populated attribute fields as the winner record.</span></span> <span data-ttu-id="6fe73-200">זוהי אפשרות המיזוג של ברירת המחדל.</span><span class="sxs-lookup"><span data-stu-id="6fe73-200">It's the default merge option.</span></span>
   - <span data-ttu-id="6fe73-201">**החדשים ביותר**: מזהה את הרשומה המנצחת בהתבסס על העדכניות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-201">**Most recent**: Identifies the winner record based on the most recency.</span></span> <span data-ttu-id="6fe73-202">דורש תאריך או שדה מספרי להגדרת העדכניות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-202">Requires a date or a numeric field to define the recency.</span></span>
   - <span data-ttu-id="6fe73-203">**הישנים ביותר**: מזהה את הרשומה המנצחת בהתבסס על העדכניות הנמוכה ביותר.</span><span class="sxs-lookup"><span data-stu-id="6fe73-203">**Least recent**: Identifies the winner record based on the least recency.</span></span> <span data-ttu-id="6fe73-204">דורש תאריך או שדה מספרי להגדרת העדכניות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-204">Requires a date or a numeric field to define the recency.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6fe73-205">![כללים לביטול כפילויות שלב 1](media/match-selfconflation.png "כללים לביטול כפילויות שלב 1")</span><span class="sxs-lookup"><span data-stu-id="6fe73-205">![Deduplication rules step 1](media/match-selfconflation.png "Deduplication rules step 1")</span></span>
 
1. <span data-ttu-id="6fe73-206">כאשר הישויות נבחרות והעדפת המיזוג שלהן מוגדרת, בחר **צור כלל** כדי להגדיר את כללי ביטול הכפילויות ברמת ישות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-206">Once the entities are selected and their merge preference is set, select **Add rule** to define the deduplication rules at an entity level.</span></span>
   - <span data-ttu-id="6fe73-207">האפשרות **בחר שדה** מפרטת את כל השדות הזמינים מאותה ישות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-207">**Select field** lists all the available fields from that entity.</span></span> <span data-ttu-id="6fe73-208">בחר בשדה שברצונך לבדוק בו כפילויות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-208">Choose the field you want to check for duplicates.</span></span> <span data-ttu-id="6fe73-209">בחר שדות שעשויים להיות ייחודיים עבור כל לקוח יחיד.</span><span class="sxs-lookup"><span data-stu-id="6fe73-209">Choose fields that are likely unique for every single customer.</span></span> <span data-ttu-id="6fe73-210">לדוגמה, כתובת דואר, או השילוב של שם, עיר ומספר טלפון.</span><span class="sxs-lookup"><span data-stu-id="6fe73-210">For example, an email address, or the combination of name, city, and phone number.</span></span>
   - <span data-ttu-id="6fe73-211">ציין את הגדרות הנרמול והדיוק.</span><span class="sxs-lookup"><span data-stu-id="6fe73-211">Specify the normalization and precision settings.</span></span>
   - <span data-ttu-id="6fe73-212">הגדר תנאים נוספים על-ידי בחירת **הוסף תנאי**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-212">Define more conditions by selecting **Add condition**.</span></span>
 
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="6fe73-213">![כללים לביטול כפילויות שלב 2](media/match-selfconflation-rules.png "כללים לביטול כפילויות שלב 2")</span><span class="sxs-lookup"><span data-stu-id="6fe73-213">![Deduplication rules step 2](media/match-selfconflation-rules.png "Deduplication rules step 2")</span></span>

  <span data-ttu-id="6fe73-214">באפשרותך ליצור כללים מרובים לביטול כפילויות עבור ישות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-214">You can create multiple deduplication rules for an entity.</span></span> 

1. <span data-ttu-id="6fe73-215">הפעלת תהליך ההתאמה מקבץ כעת את הרשומות בהתבסס על התנאים המוגדרים בכללי ביטול הכפילויות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-215">Running the match process now groups the records based on the conditions defined in the deduplication rules.</span></span> <span data-ttu-id="6fe73-216">לאחר קיבוץ הרשומות, מדיניות המיזוג מיושמת כדי לזהות את הרשומה המנצחת.</span><span class="sxs-lookup"><span data-stu-id="6fe73-216">After grouping the records, the merge policy is applied to identify the winner record.</span></span>

1. <span data-ttu-id="6fe73-217">רשומה מנצחת זו עוברת לאחר מכן להתאמה חוצת-ישויות, ביחד עם הרשומות שאינן מנצחות (לדוגמה, מזהים חלופיים) כדי לשפר את איכות ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-217">This winner record is then passed on to the cross-entity matching, along with the non-winner records (for example, alternate IDs) to improve the matching quality.</span></span>

1. <span data-ttu-id="6fe73-218">כל כללי ההתאמה המותאמים אישית שהוגדרו מחליפים כללי ביטול כפילויות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-218">Any custom match rules defined overwrite deduplication rules.</span></span> <span data-ttu-id="6fe73-219">אם כלל ביטול כפילויות מזהה רשומות מתאימות, וכלל התאמה מותאם אישית מוגדר כדי לא להתאים אף פעם לרשומות אלה, שתי הרשומות הללו לא יותאמו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-219">If a deduplication rule identifies matching records, and a custom match rule is set to never match those records, then these two records won't be matched.</span></span>

1. <span data-ttu-id="6fe73-220">לאחר [הפעלת תהליך ההתאמה](#run-the-match-process), תראה את הנתונים הסטטיסטיים של ביטול הכפילויות באריחי המדדים העיקריים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-220">After [running the match process](#run-the-match-process), you will see the deduplication stats in the key metrics tiles.</span></span>

### <a name="deduplication-output-as-an-entity"></a><span data-ttu-id="6fe73-221">פלט ביטול כפילויות כישות</span><span class="sxs-lookup"><span data-stu-id="6fe73-221">Deduplication output as an entity</span></span>

<span data-ttu-id="6fe73-222">תהליך ביטול הכפילויות יוצר ישות חדשה לכל ישות מזוגות ההתאמה כדי לזהות את הרשומות שהכפילויות שלהן בוטלו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-222">The deduplication process creates a new entity for every entity from the match pairs to identify the deduplicated records.</span></span> <span data-ttu-id="6fe73-223">ניתן למצוא ישויות אלה ביחד עם **ConflationMatchPairs:CustomerInsights** במקטע **מערכת** בדף **ישויות** בשם **Deduplication_DataSource_Entity**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-223">These entities can be found along with the **ConflationMatchPairs:CustomerInsights** in the **System** section in the **Entities** page, with the name **Deduplication_DataSource_Entity**.</span></span>

<span data-ttu-id="6fe73-224">ישות של פלט ביטול כפילויות מכילה את המידע הבא:</span><span class="sxs-lookup"><span data-stu-id="6fe73-224">A deduplication output entity contains the following information:</span></span>
- <span data-ttu-id="6fe73-225">מזהים / מפתחות</span><span class="sxs-lookup"><span data-stu-id="6fe73-225">IDs / Keys</span></span>
  - <span data-ttu-id="6fe73-226">שדה המפתח הראשי ושדה המזהים החלופיים שלו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-226">Primary key field and its alternate IDs field.</span></span> <span data-ttu-id="6fe73-227">שדה מזהים חלופיים מורכב מכל המזהים החלופיים שזוהו עבור רשומה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-227">Alternate IDs field consists of all the alternate IDs identified for a record.</span></span>
  - <span data-ttu-id="6fe73-228">השדה Deduplication_GroupId מציג את הקבוצה או האשכול המזוהים בתוך ישות המקבצת את כל הרשומות הדומות בהתבסס על שדות ביטול הכפילויות שצוינו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-228">Deduplication_GroupId field shows the group or cluster identified within an entity that groups all the similar records based on the specified deduplication fields.</span></span> <span data-ttu-id="6fe73-229">הוא משמש למטרות עיבוד מערכת.</span><span class="sxs-lookup"><span data-stu-id="6fe73-229">It's used for system processing purposes.</span></span> <span data-ttu-id="6fe73-230">אם לא צוינו כללי ביטול כפילויות ידניים וכללי ביטול כפילויות שהוגדרו על-ידי המערכת חלים, ייתכן שלא תמצא שדה זה בישות פלט ביטול הכפילויות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-230">If there are no manual deduplication rules specified and system defined deduplication rules apply, you may not find this field in the deduplication output entity.</span></span>
  - <span data-ttu-id="6fe73-231">Deduplication_WinnerId: שדה זה מכיל את המזהה המנצח מהקבוצות או האשכולות שזוהו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-231">Deduplication_WinnerId: This field contains the winner ID from the identified groups or clusters.</span></span> <span data-ttu-id="6fe73-232">אם Deduplication_WinnerId זהה לערך המפתח הראשי עבור רשומה, המשמעות היא שהרשומה היא הרשומה המנצחת.</span><span class="sxs-lookup"><span data-stu-id="6fe73-232">If the Deduplication_WinnerId is same as the Primary key value for a record, it means that the record is the winner record.</span></span>
- <span data-ttu-id="6fe73-233">שדות המשמשים להגדרה של כללי ביטול הכפילויות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-233">Fields used to define the deduplication rules.</span></span>
- <span data-ttu-id="6fe73-234">השדות 'כלל' ו'ניקוד' כדי לציין אילו כללי ביטול כפילויות הוחלו והניקוד הוחזר על-ידי אלגוריתם ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-234">Rule and Score fields to denote which of the deduplication rules got applied and the score returned by the matching algorithm.</span></span>
   
## <a name="run-the-match-process"></a><span data-ttu-id="6fe73-235">הפעל את תהליך ההתאמה</span><span class="sxs-lookup"><span data-stu-id="6fe73-235">Run the match process</span></span>

<span data-ttu-id="6fe73-236">עם כללי התאמה מוגדרים, כולל כללי התאמה בין ישויות וביטול כפילות, ניתן להפעיל את תהליך ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-236">With configured match rules, including cross-entity matching and deduplication rules, you can run the match process.</span></span> 

<span data-ttu-id="6fe73-237">עבור אל **נתונים** > **איחוד** > **התאמה** ובחר **הפעל** כדי להתחיל בתהליך.</span><span class="sxs-lookup"><span data-stu-id="6fe73-237">Go to **Data** > **Unify** > **Match** and select **Run** to start the process.</span></span> <span data-ttu-id="6fe73-238">לאלגוריתם ההתאמה נדרש זמן מה כדי להסתיים ואין באפשרותך לשנות את התצורה עד להשלמתו.</span><span class="sxs-lookup"><span data-stu-id="6fe73-238">The matching algorithm takes some time to complete and you can't change the configuration until it completes.</span></span> <span data-ttu-id="6fe73-239">כדי לבצע שינויים, באפשרותך לבטל את ההפעלה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-239">To make changes, you can cancel the run.</span></span> <span data-ttu-id="6fe73-240">בחר את מצב המשימה ובחר **בטל משימה** בחלונית **פרטי התקדמות**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-240">Select the status of the job and select **Cancel job** on the **Progress details** pane.</span></span>

<span data-ttu-id="6fe73-241">בדף **ישויות** תוכל למצוא את התוצאה של הפעלה מוצלחת ואת ישות פרופיל הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="6fe73-241">You'll find the result of a successful run, the unified customer profile entity, on the **Entities** page.</span></span> <span data-ttu-id="6fe73-242">ישות הלקוח המאוחד שלך נקראת **לקוחות** במקטע **פרופילים**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-242">Your unified customer entity is called **Customers** in the **Profiles** section.</span></span> <span data-ttu-id="6fe73-243">הפעלת ההתאמה המוצלחת הראשונה יוצרת את הישות *לקוח* המאוחדת.</span><span class="sxs-lookup"><span data-stu-id="6fe73-243">The first successful match run creates the unified *Customer* entity.</span></span> <span data-ttu-id="6fe73-244">כל הפעלות ההתאמה הבאות מרחיבות את אותה ישות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-244">All subsequent match runs expand that entity.</span></span>

> [!TIP]
> <span data-ttu-id="6fe73-245">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-245">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="6fe73-246">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="6fe73-246">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="6fe73-247">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-247">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="6fe73-248">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-248">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="review-and-validate-your-matches"></a><span data-ttu-id="6fe73-249">בדוק ואמת את ההתאמות שלך</span><span class="sxs-lookup"><span data-stu-id="6fe73-249">Review and validate your matches</span></span>

<span data-ttu-id="6fe73-250">עבור אל **נתונים** > **איחוד** > **התאמה** כדי להעריך את איכות זוגות ההתאמה שלך ולמקד אותם במידת הצורך.</span><span class="sxs-lookup"><span data-stu-id="6fe73-250">Go to **Data** > **Unify** > **Match** to evaluate the quality of your match pairs and refine them if necessary.</span></span>

<span data-ttu-id="6fe73-251">האריחים בראש הדף מציגים מדדים עיקריים, המסכמים את מספר הרשומות והכפילויות המותאמות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-251">The tiles on top of the page show key metrics, summarizing the number of matched records and duplicates.</span></span>

:::image type="content" source="media/match-KPIs.png" alt-text="צילום מסך חתוך של מדדים עיקריים בדף 'התאמה' עם מספרים ופרטים.":::

- <span data-ttu-id="6fe73-253">האפשרות **רשומות מקור ייחודיות** מציגה את מספר רשומות המקור הבודדות שעובדו בהפעלת ההתאמה האחרונה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-253">**Unique source records** shows the number of individual source records that were processed in last match run.</span></span>
- <span data-ttu-id="6fe73-254">האפשרות **רשומות תואמות ולא תואמות** מדגישה כמה רשומות ייחודיות נותרו לאחר עיבוד כללי ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-254">**Matched and non-matched records** highlights how many unique records remain after processing the match rules.</span></span>
- <span data-ttu-id="6fe73-255">האפשרות **רשומות תואמות בלבד** מציגה את מספר ההתאמות בכל זוגות ההתאמה שלך.</span><span class="sxs-lookup"><span data-stu-id="6fe73-255">**Matched records only** shows the number of matches across all of your match pairs.</span></span>

<span data-ttu-id="6fe73-256">באפשרותך להעריך את התוצאות של כל זוג התאמה ואת הכללים שלו בטבלה **פרטי רשומות תואמות**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-256">You can assess the results of each match pair and its rules in the **Matched records details** table.</span></span> <span data-ttu-id="6fe73-257">השווה את מספר הרשומות שהגיעו מזוג התאמה לאחוז הרשומות שהותאמו בהצלחה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-257">Compare the number of records that came from a match pair against the percentage of successfully matched records.</span></span>

<span data-ttu-id="6fe73-258">סקור את הכללים של זוג התאמה כדי לראות את אחוז הרשומות שהותאמו בהצלחה ברמת הכלל.</span><span class="sxs-lookup"><span data-stu-id="6fe73-258">Review the rules of a match pair to see the percentage of successfully matched records at the rule level.</span></span> <span data-ttu-id="6fe73-259">בחר את שלוש הנקודות (...) ולאחר מכן בחר **תצוגה מקדימה של התאמה** כדי להציג את כל הרשומות הללו ברמת הכלל.</span><span class="sxs-lookup"><span data-stu-id="6fe73-259">Select the ellipsis (...) and then select **Match preview** to view all these records on the rule level.</span></span> <span data-ttu-id="6fe73-260">מומלץ לבחון חלק מהרשומות כדי לאמת שהן הותאמו כהלכה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-260">We recommend that you take a look at some records to validate that they were matched correctly.</span></span>

<span data-ttu-id="6fe73-261">נסה ערכי סף שונים של דיוק בתנאים כדי למצוא את הערך המיטבי.</span><span class="sxs-lookup"><span data-stu-id="6fe73-261">Try different precision thresholds on conditions to find the optimal value.</span></span>

  1. <span data-ttu-id="6fe73-262">בחר את שלוש הנקודות (...) עבור הכלל שברצונך להתנסות בו ובחר **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-262">Select the ellipsis (...) for the rule that you want to experiment with and select **Edit**.</span></span>

  2. <span data-ttu-id="6fe73-263">שנה את ערכי הדיוק בתנאים שברצונך לתקן.</span><span class="sxs-lookup"><span data-stu-id="6fe73-263">Change the precisions values in the conditions you want to revise.</span></span>

  3. <span data-ttu-id="6fe73-264">בחר **תצוגה מקדימה** כדי לראות את מספר הרשומות התואמות והלא תואמות עבור התנאי שנבחר.</span><span class="sxs-lookup"><span data-stu-id="6fe73-264">Select **Preview** so see the number of matched and unmatched records for the selected condition.</span></span>

## <a name="manage-match-rules"></a><span data-ttu-id="6fe73-265">ניהול כללי התאמה</span><span class="sxs-lookup"><span data-stu-id="6fe73-265">Manage match rules</span></span>

<span data-ttu-id="6fe73-266">באפשרותך להגדיר מחדש ולכוונן את רוב פרמטרי ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-266">You can reconfigure and fine-tune most of the match parameters.</span></span>

:::image type="content" source="media/match-rules-management.png" alt-text="צילום מסך של התפריט הנפתח עם אפשרויות לכלל התאמה.":::

- <span data-ttu-id="6fe73-268">**שנה את סדר הכללים** אם הגדרת מספר כללים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-268">**Change the order of your rules** if you defined multiple rules.</span></span> <span data-ttu-id="6fe73-269">באפשרותך לסדר מחדש את כללי ההתאמה על-ידי בחירת האפשרויות **הזז למעלה** ו **הזז למטה** או באמצעות גרירה ושחרור.</span><span class="sxs-lookup"><span data-stu-id="6fe73-269">You can reorder the match rules by selecting the **Move Up** and **Move Down** options or by drag and drop.</span></span>

- <span data-ttu-id="6fe73-270">**שנה את תנאי הכלל** על-ידי בחירת **ערוך** ובחר שדות שונים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-270">**Change rule conditions** by selecting **Edit** and choose different fields.</span></span>

- <span data-ttu-id="6fe73-271">**בטל כלל** כדי לשמור כלל התאמה תוך כדי אי הכללה שלו בתהליך ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-271">**Deactivate a rule** to retain a match rule while excluding it from the matching process.</span></span>

- <span data-ttu-id="6fe73-272">**שכפל את הכללים שלך** אם הגדרת כלל התאמה וברצונך ליצור כלל דומה עם שינויים, בחר **שכפל**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-272">**Duplicate your rules** if you've defined a match rule and would like to create a similar rule with modifications, select **Duplicate**.</span></span>

- <span data-ttu-id="6fe73-273">**מחק כלל** על-ידי בחירת הסמל **מחק**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-273">**Delete a rule** by selecting the **Delete** symbol.</span></span>

## <a name="specify-custom-match-conditions"></a><span data-ttu-id="6fe73-274">ציין תנאי התאמה מותאמים אישית</span><span class="sxs-lookup"><span data-stu-id="6fe73-274">Specify custom match conditions</span></span>

<span data-ttu-id="6fe73-275">ניתן לציין תנאים שרשומות מסוימות צריכות להתאים להם תמיד או אף פעם.</span><span class="sxs-lookup"><span data-stu-id="6fe73-275">You can specify conditions that certain records should always match or never match.</span></span> <span data-ttu-id="6fe73-276">ניתן להעלות כללים אלה כדי לעקוף את תהליך ההתאמה הסטנדרטי.</span><span class="sxs-lookup"><span data-stu-id="6fe73-276">These rules can be uploaded to override the standard match process.</span></span> <span data-ttu-id="6fe73-277">לדוגמה, אם ברשומות שלנו מופיעים John Doe I ו- John Doe II, המערכת עשויה להתאים אותם כאדם אחד.</span><span class="sxs-lookup"><span data-stu-id="6fe73-277">For example, if there are John Doe I and John Doe II in our records, the system might match them as one person.</span></span> <span data-ttu-id="6fe73-278">כללי התאמה מותאמים אישית מאפשרים לך לציין שהפרופילים שלהם מתייחסים לאנשים שונים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-278">Custom match rules let you specify that their profiles refer to different people.</span></span> 

1. <span data-ttu-id="6fe73-279">עבור אל **נתונים** > **איחוד** > **התאמה** ובחר **התאמה מותאמת אישית** במקטע **פרטי רשומות תואמות**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-279">Go to **Data** > **Unify** > **Match** and select **Custom match** in the **Matched records details** section.</span></span>

  :::image type="content" source="media/custom-match-create.png" alt-text="צילום מסך של המקטע 'כללי התאמה' עם פקד התאמה מותאמת אישית מודגש.":::

1. <span data-ttu-id="6fe73-281">אם לא הוגדרו כללי התאמה מותאמים אישית, תראה חלונית **התאמה מותאמת אישית** חדשה עם פרטים נוספים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-281">If you have no custom match rules set, you'll see a new **Custom match** pane with more details.</span></span>

1. <span data-ttu-id="6fe73-282">בחר **מלא את התבנית** כדי לקבל קובץ תבנית שיכול לציין אילו רשומות מאילו ישויות תמיד צריכות להתאים או לעולם לא להתאים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-282">Select **Fill in the template** to get a template file that can specify which records from which entities should always match or never match.</span></span> <span data-ttu-id="6fe73-283">יהיה עליך למלא בנפרד את הרשומות "תמיד להתאים" ו"אף פעם לא להתאים" בשני קבצים שונים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-283">You'll need to separately fill in the "always match" records and "never match" records in two different files.</span></span>

1. <span data-ttu-id="6fe73-284">התבנית מכילה שדות לציון הישות וערכי המפתח העיקריים של הישות שישמשו בהתאמה המותאמת אישית.</span><span class="sxs-lookup"><span data-stu-id="6fe73-284">The template contains fields to specify the entity and the entity primary key values to be used in the custom match.</span></span> <span data-ttu-id="6fe73-285">לדוגמה, אם ברצונך שהמפתח הראשי *12345* מהישות *מכירות* יתאים תמיד למפתח הראשי *34567* מהישות *איש קשר*, מלא את התבנית:</span><span class="sxs-lookup"><span data-stu-id="6fe73-285">For example, if you want primary key *12345* from *Sales* entity to always match with primary key *34567* from *Contact* entity, fill in the template:</span></span>
    - <span data-ttu-id="6fe73-286">ישות 1: מכירות</span><span class="sxs-lookup"><span data-stu-id="6fe73-286">Entity1: Sales</span></span>
    - <span data-ttu-id="6fe73-287">מפתח ישות 1: 12345</span><span class="sxs-lookup"><span data-stu-id="6fe73-287">Entity1Key: 12345</span></span>
    - <span data-ttu-id="6fe73-288">ישות 2: איש קשר</span><span class="sxs-lookup"><span data-stu-id="6fe73-288">Entity2: Contact</span></span>
    - <span data-ttu-id="6fe73-289">מפתח ישות 2: 34567</span><span class="sxs-lookup"><span data-stu-id="6fe73-289">Entity2Key: 34567</span></span>

   <span data-ttu-id="6fe73-290">אותו קובץ תבנית יכול לציין רשומות התאמה בהתאמה אישית מישויות מרובות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-290">The same template file can specify custom match records from multiple entities.</span></span>
   
   <span data-ttu-id="6fe73-291">אם ברצונך לציין התאמה מותאמת אישית עבור ביטול כפילויות בישות, ספק את אותה ישות הן כ- Entity1 והן כ- Entity2 והגדר את ערכי המפתח הראשי השונים.</span><span class="sxs-lookup"><span data-stu-id="6fe73-291">If you want to specify custom matching for deduplication on an entity, provide the same entity as both Entity1 and Entity2 and set the different primary key values.</span></span>

1. <span data-ttu-id="6fe73-292">לאחר הוספת כל הדרישות שברצונך להחיל, שמור את קובץ התבנית.</span><span class="sxs-lookup"><span data-stu-id="6fe73-292">After adding all the overrides you want to apply, save the template file.</span></span>

1. <span data-ttu-id="6fe73-293">עבור אל **נתונים** > **מקורות נתונים** וקלוט את קבצי התבנית כישויות חדשות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-293">Go to **Data** > **Data sources** and ingest the template files as new entities.</span></span> <span data-ttu-id="6fe73-294">לאחר השילוב תוכל להשתמש בהם כדי לציין את תצורת ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-294">Once ingested, you can use them to specify the Match configuration.</span></span>

1. <span data-ttu-id="6fe73-295">לאחר העלאת הישויות והקבצים הזמינים, בחר שוב **התאמה אישית**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-295">After uploading the files and entities are available, select the **Custom match** option again.</span></span> <span data-ttu-id="6fe73-296">תראה אפשרויות לציון הישויות שתרצה לכלול.</span><span class="sxs-lookup"><span data-stu-id="6fe73-296">You'll see options to specify the entities you want to include.</span></span> <span data-ttu-id="6fe73-297">בחר את הישויות הנדרשות מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="6fe73-297">Select the required entities from the dropdown menu.</span></span>

   :::image type="content" source="media/custom-match-overrides.png" alt-text="צילום מסך של תיבת הדו-שיח לבחירת עקיפות עבור תרחיש התאמה מותאם אישית.":::

1. <span data-ttu-id="6fe73-299">בחר את הישויות שבהן תרצה להשתמש עבור **תמיד התאם** או **לעולם אל תתאים**, בחר **בוצע**.</span><span class="sxs-lookup"><span data-stu-id="6fe73-299">Select the entities you want to use for **Always match** and **Never match**, select **Done**.</span></span>

1. <span data-ttu-id="6fe73-300">בחר **שמור** בדף **התאמה** כדי להחיל את תצורת ההתאמה המותאמת אישית.</span><span class="sxs-lookup"><span data-stu-id="6fe73-300">Select **Save** on the **Match** page to apply the custom match configuration.</span></span>

1. <span data-ttu-id="6fe73-301">בחר **הפעל** בדף **התאמה** כדי להתחיל בתהליך ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="6fe73-301">Select **Run** on the **Match** page to start the matching process.</span></span> <span data-ttu-id="6fe73-302">כללי התאמה אחרים שצוינו נעקפים על-ידי תצורת ההתאמה המותאמת אישית.</span><span class="sxs-lookup"><span data-stu-id="6fe73-302">Other specified match rules are overridden by the custom match configuration.</span></span>

> [!TIP]
> <span data-ttu-id="6fe73-303">עבור אל **נתונים** > **ישויות** וסקור את הישות **ConflationMatchPair** כדי לאשר את החלת העקיפות.</span><span class="sxs-lookup"><span data-stu-id="6fe73-303">Go to **Data** > **Entities** and review the **ConflationMatchPair** entity to confirm that the overrides are applied.</span></span>

## <a name="next-step"></a><span data-ttu-id="6fe73-304">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="6fe73-304">Next step</span></span>

<span data-ttu-id="6fe73-305">לאחר השלמת תהליך ההתאמה עבור זוג התאמה אחד לפחות, אתה יכול לפתור סתירות אפשריות בנתונים על ידי מעבר על הנושא [**מיזוג**](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="6fe73-305">After completing the match process for at least one match pair, you may resolve possible contradictions in your data by going through the [**Merge**](merge-entities.md) topic.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
