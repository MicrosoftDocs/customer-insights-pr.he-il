---
title: קשרים בין ישויות ונתיבי ישויות
description: צור ונהל קשרים בין ישויות ממקורות נתונים מרובים.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171165"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="4f0f5-103">קשרים בין ישויות</span><span class="sxs-lookup"><span data-stu-id="4f0f5-103">Relationships between entities</span></span>

<span data-ttu-id="4f0f5-104">קשרים מחברים בין ישויות ומגדירים גרף של הנתונים שלך כאשר ישויות משתפות מזהה משותף, מפתח זר.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="4f0f5-105">ניתן להפנות מפתח זר זה מישות אחת לאחרת.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="4f0f5-106">ישויות מחוברות מאפשרות להפעיל את ההגדרה של פלחים ומדידות בהתבסס על מקורות נתונים מרובים.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="4f0f5-107">ישנם שלושה סוגים של קשרים:</span><span class="sxs-lookup"><span data-stu-id="4f0f5-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="4f0f5-108">קשרי מערכת שאינם ניתנים לעריכה, נוצרים על-ידי המערכת כחלק מתהליך איחוד הנתונים</span><span class="sxs-lookup"><span data-stu-id="4f0f5-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="4f0f5-109">קשרים שהתקבלו בירושה ואינם ניתנים לעריכה, שנוצרים באופן אוטומטי מקליטת מקורות נתונים</span><span class="sxs-lookup"><span data-stu-id="4f0f5-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="4f0f5-110">קשרים מותאמים אישית הניתנים לעריכה, נוצרים ומוגדרים על-ידי משתמשים</span><span class="sxs-lookup"><span data-stu-id="4f0f5-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="4f0f5-111">קשרי מערכת שאינם ניתנים לעריכה</span><span class="sxs-lookup"><span data-stu-id="4f0f5-111">Non-editable system relationships</span></span>

<span data-ttu-id="4f0f5-112">במהלך איחוד הנתונים, קשרי מערכת נוצרים באופן אוטומטי בהתבסס על התאמה חכמה.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="4f0f5-113">קשרים אלה עוזרים לקשר בין רשומות פרופיל הלקוח לבין רשומות תואמות.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="4f0f5-114">הדיאגרמה הבאה ממחישה את היצירה של שלושת הקשרים מבוססי המערכת.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="4f0f5-115">ישות הלקוחות מותאמת לישויות אחרות כדי יצור את ישות *הלקוח* המאוחדת.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="דיאגרמה עם נתיבי קשרים עבור ישות הלקוחות עם שלושה קשרים מסוג 1-n.":::

- <span data-ttu-id="4f0f5-117">**קשר מסוג *CustomerToContact*** נוצר בין הישות *לקוח* לישות *איש קשר*.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="4f0f5-118">הישות *לקוח* מקבלת את שדה המפתח **Contact_contactId** כדי לקשר אותו לשדה מפתח הישות **contactId** של הישות *איש קשר*.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="4f0f5-119">**קשר מסוג *CustomerToAccount*** נוצר בין הישות *לקוח* לישות *תיק לקוח*.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="4f0f5-120">הישות *לקוח* מקבלת את שדה המפתח **Account_accountId** כדי לקשר אל שדה המפתח **accountId** של הישות *תיק הלקוח*.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="4f0f5-121">**קשר מסוג *CustomerToWebAccount*** נוצר בין הישות *לקוח* לישות *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="4f0f5-122">הישות *לקוח* מקבלת את שדה המפתח **WebAccount_webaccountId** כדי לקשר את שדה המפתח **webaccountId** של הישות *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="4f0f5-123">קשרים המתקבלים בירושה שאינם ניתנים לעריכה</span><span class="sxs-lookup"><span data-stu-id="4f0f5-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="4f0f5-124">בזמן תהליך קליטת הנתונים, המערכת בודקת את הקשרים הקיימים במקורות הנתונים.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="4f0f5-125">אם לא קיימים קשרים, המערכת יוצרת אותם באופן אוטומטי.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="4f0f5-126">קשרים אלה נמצאים גם בשימוש בתהליכים במורד הזרם.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="4f0f5-127">יצירת קשר מותאם אישית</span><span class="sxs-lookup"><span data-stu-id="4f0f5-127">Create a custom relationship</span></span>

<span data-ttu-id="4f0f5-128">קשר מורכב מ *ישות מקור* שמכילה את המפתח הזר ו *ישות יעד* שאליה מצביע המפתח הזר של ישות המקור.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="4f0f5-129">ב- Audience Insights, עבור אל **נתונים** > **קשרים**.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="4f0f5-130">בחר **קשר חדש**.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="4f0f5-131">בחלונית **קשר חדש**, ספק את הפרטים הבאים:</span><span class="sxs-lookup"><span data-stu-id="4f0f5-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="חלונית צדדית של קשר חדש עם שדות קלט ריקים.":::

   - <span data-ttu-id="4f0f5-133">**שם הקשר**: שם המשקף את מטרת הקשר.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="4f0f5-134">דוגמה: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="4f0f5-135">**תיאור**: תיאור של הקשר.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="4f0f5-136">**ישות מקור**: הישות המשמשת כמקור בקשר.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="4f0f5-137">דוגמה: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="4f0f5-138">**ישות יעד**: הישות המשמשת כיעד בקשר.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="4f0f5-139">דוגמא: לקוח.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-139">Example: Customer.</span></span>
   - <span data-ttu-id="4f0f5-140">**עוצמת המקור**: ציין את העוצמה של ישות המקור.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="4f0f5-141">עוצמה מתארת את מספר הרכיבים האפשריים בקבוצה.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="4f0f5-142">היא תמיד קשורה לעוצמת היעד.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="4f0f5-143">באפשרותך לבחור בין **אחד** ל **רבים**.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="4f0f5-144">רק קשרים מסוג רבים-לאחד ואחד-אחד נתמכים.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="4f0f5-145">רבים-לאחד: רשומות מקור מרובות יכולות להיות קשורות לרשומת יעד אחת.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="4f0f5-146">דוגמה: מקרי תמיכה מרובים מלקוח יחיד.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="4f0f5-147">אחד-לאחד: רשומת מקור יחידה קשורה לרשומת יעד אחת.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="4f0f5-148">דוגמה: מזהה נאמנות אחד עבור לקוח יחיד.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="4f0f5-149">ניתן ליצור קשרים מסוג רבים-לרבים באמצעות שני קשרים מסוג רבים-לאחד וישות מקשרת, המחברת בין ישות המקור לישות היעד.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="4f0f5-150">**מספר מונה של היעד** : בחר את הקרדינליות, המספר המונה של רשומות ישויות היעד.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="4f0f5-151">**שדה מפתח מקור** : שדה המפתח הזר בישות המקור.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="4f0f5-152">דוגמה: SupportCase יכול להשתמש ב- CaseID כשדה מפתח זר.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="4f0f5-153">**שדה מפתח יעד**: שדה המפתח של ישות היעד.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="4f0f5-154">לדוגמה, לקוח יכול להשתמש בשדה המפתח **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="4f0f5-155">בחר **שמור** כדי ליצור את הקשר המותאם אישית.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="4f0f5-156">הצגת קשרים</span><span class="sxs-lookup"><span data-stu-id="4f0f5-156">View relationships</span></span>

<span data-ttu-id="4f0f5-157">הדף 'קשרים' מפרט את כל הקשרים שנוצרו.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="4f0f5-158">כל שורה מייצגת קשר, וכוללת גם פרטים על ישות המקור, ישות היעד והעוצמה.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="רשימת הקשרים והאפשרויות בסרגל הפעולות של הדף 'קשרים'.":::

<span data-ttu-id="4f0f5-160">דף זה מציע קבוצה של אפשרויות עבור קשרים קיימים וחדשים:</span><span class="sxs-lookup"><span data-stu-id="4f0f5-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="4f0f5-161">**קשר חדש:** [יצירת קשר מותאם אישית](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="4f0f5-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="4f0f5-162">**רכיב המחשה**: [סקור את רכיב ההמחשה של הקשר](#explore-the-relationship-visualizer) כדי לראות דיאגרמת רשת של הקשרים הקיימים והעוצמה שלהם.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="4f0f5-163">**סנן לפי** : בחר את סוג הקשרים שיוצגו ברשימה.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="4f0f5-164">**חפש קשרים**: השתמש בחיפוש מבוסס טקסט במאפייני הקשרים.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="4f0f5-165">סקירת רכיב ההמחשה של קשרים</span><span class="sxs-lookup"><span data-stu-id="4f0f5-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="4f0f5-166">רכיב ההמחשה של הקשר מציג דיאגרמת רשת של הקשרים הקיימים בין ישויות מחוברות ואת העוצמה שלהם.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="4f0f5-167">כדי להתאים אישית את התצוגה, באפשרותך לשנות את מיקום התיבות על-ידי גרירתן על בד הציור.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="צילום מסך של דיאגרמת הרשת של רכיב ההמחשה של הקשר עם חיבורים בין ישויות קשורות.":::

<span data-ttu-id="4f0f5-169">האפשרויות הזמינות:</span><span class="sxs-lookup"><span data-stu-id="4f0f5-169">Available options:</span></span> 
- <span data-ttu-id="4f0f5-170">**יצא כתמונה**: שמור את התצוגה הנוכחית כקובץ תמונה.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="4f0f5-171">**שנה לפריסה אופקית/אנכית**: שנה את היישור של הישויות והקשרים.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="4f0f5-172">**עריכה**: עדכן מאפיינים של קשרים מותאמים אישית בחלונית העריכה ושמור שינויים.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="4f0f5-173">ניהול קשרים קיימים</span><span class="sxs-lookup"><span data-stu-id="4f0f5-173">Manage existing relationships</span></span> 

<span data-ttu-id="4f0f5-174">בדף 'קשרים', כל קשר מיוצג על-ידי שורה.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="4f0f5-175">בחר קשר ובחר אחת מהאפשרויות הבאות:</span><span class="sxs-lookup"><span data-stu-id="4f0f5-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="4f0f5-176">**עריכה**: עדכן מאפיינים של קשרים מותאמים אישית בחלונית העריכה ושמור שינויים.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="4f0f5-177">**מחק**: מחק קשרים מותאם אישית.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="4f0f5-178">**תצוגה**: הצג קשרים שנוצרו על-ידי המערכת והתקבלו בירושה.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="4f0f5-179">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="4f0f5-179">Next step</span></span>

<span data-ttu-id="4f0f5-180">קשרי מערכת וקשרים מותאמים אישית משמשים ל[יצירת פלחים](segments.md) המבוססים על מקורות נתונים מרובים שכבר אינם נפרדים.</span><span class="sxs-lookup"><span data-stu-id="4f0f5-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
