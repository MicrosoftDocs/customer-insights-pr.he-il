---
title: קשרים בין ישויות ונתיבי ישויות
description: צור ונהל קשרים בין ישויות ממקורות נתונים מרובים.
ms.date: 04/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: c25bfcb8e2a8223498dd1a5e8cfb3712a40ab85e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595213"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="dcdfc-103">קשרים בין ישויות</span><span class="sxs-lookup"><span data-stu-id="dcdfc-103">Relationships between entities</span></span>

<span data-ttu-id="dcdfc-104">קשרי גומלין עוזרים לך לחבר ישויות וליצור גרף מהנתונים כאשר לישויות יש מזהה משותף (מפתח זר) שאפשר להפנות מגורם אחד למשנהו.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="dcdfc-105">ישויות מחוברות מאפשרות לך להגדיר פלחים ומדידות על בסיס מקורות נתונים מרובים.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="dcdfc-106">קיימים שני סוגים של קשרי גומלין.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-106">There are two types of relationships.</span></span> <span data-ttu-id="dcdfc-107">קשרי מערכת שאינם ניתנים לעריכה, אשר נוצרים באופן אוטומטי, וקשרים מותאמים אישית שנוצרים ומוגדרים על ידי משתמשים.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="dcdfc-108">במהלך תהליכי ההתאמה והמיזוג, מערכת קשרים נוצרת מאחורי הקלעים על בסיס התאמה חכמה.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="dcdfc-109">קשרים אלה עוזרים לקשר בין רשומות פרופיל הלקוח לבין רשומות של ישויות מתאימות אחרות.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="dcdfc-110">התרשים הבא ממחיש את היצירה של שלוש מערכות קשרים כאשר ישות הלקוח מתאימה לישויות נוספות כדי ליצור את הישות הסופית של פרופיל הלקוח.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dcdfc-111">![‏‏יצירת קשר](media/relationships-entities-merge.png "‏‏יצירת קשר")</span><span class="sxs-lookup"><span data-stu-id="dcdfc-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="dcdfc-112">**קשר מסוג *CustomerToContact*** נוצר בין ישות הלקוח לבין ישות איש קשר.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="dcdfc-113">ישות הלקוח מקבלת את שדה המפתח **Contact_contactId** כדי להתייחס לשדה מפתח ישות איש קשר **contactId**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="dcdfc-114">**קשר מסוג *CustomerToAccount*** נוצר בין ישות הלקוח לבין ישות תיק הלקוח.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="dcdfc-115">ישות הלקוח מקבלת את שדה המפתח **Account_accountId** כדי להתייחס לשדה מפתח ישות תיק הלקוח **accountId**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="dcdfc-116">**קשר מסוג *CustomerToWebAccount*** נוצר בין ישות הלקוח לבין הישות WebAccount.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="dcdfc-117">ישות הלקוח מקבלת את שדה המפתח **WebAccount_webaccountId** כדי להתייחס לשדה מפתח ישות תיק הלקוח **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="dcdfc-118">יצירת קשר</span><span class="sxs-lookup"><span data-stu-id="dcdfc-118">Create a relationship</span></span>

<span data-ttu-id="dcdfc-119">הגדר קשרים מותאם אישית בדף **קשרים**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="dcdfc-120">כל קשר מורכב מישות מקור (הישות שמחזיקה במפתח הזר) ומישות יעד (הישות שאליה מצביע המפתח הזר של ישות המקור).</span><span class="sxs-lookup"><span data-stu-id="dcdfc-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="dcdfc-121">ב- Audience Insights, עבור אל **נתונים** > **קשרים**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="dcdfc-122">בחר **קשר חדש**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="dcdfc-123">בחלונית **הוסף קשר**, ספק את הפרטים הבאים:</span><span class="sxs-lookup"><span data-stu-id="dcdfc-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dcdfc-124">![הזן פרטי קשר](media/relationships-add.png "הזן פרטי קשר")</span><span class="sxs-lookup"><span data-stu-id="dcdfc-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="dcdfc-125">**שם הקשר** : שם שמשקף את מטרת הקשר (לדוגמה, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="dcdfc-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="dcdfc-126">**תיאור**: תיאור של הקשר.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="dcdfc-127">**ישות המקור** : בחר את הישות שמשמשת כמקור בקשר (לדוגמה, WebLog).</span><span class="sxs-lookup"><span data-stu-id="dcdfc-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="dcdfc-128">**מספר מונה** : בחר את הקרדינליות, המספר המונה של רשומות ישויות המקור.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="dcdfc-129">לדוגמה, "רבים" פירושו שרשומות Weblog מרובות קשורות לחשבון WebAccount אחד.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="dcdfc-130">**שדה מפתח מקור** : שדה זה מייצג את שדה המפתח הזר בישות המקור.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="dcdfc-131">לדוגמה, ל- WebLog יש את שדה המפתח הזר **accountId‎**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="dcdfc-132">**ישות היעד** : בחר את הישות שמשמשת כיעד בקשר (לדוגמה, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="dcdfc-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="dcdfc-133">**מספר מונה של היעד** : בחר את הקרדינליות, המספר המונה של רשומות ישויות היעד.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="dcdfc-134">לדוגמה, "אחד" פירושו שרשומות Weblog מרובות קשורות לחשבון WebAccount אחד.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="dcdfc-135">**שדה מפתח יעד**: שדה זה מייצג את שדה המפתח של ישות היעד.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="dcdfc-136">לדוגמה, ל- WebAccount יש את שדה המפתח **accountId‎**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="dcdfc-137">רק קשרים מסוג רבים-לאחד ואחד-אחד נתמכים.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="dcdfc-138">ניתן ליצור קשרים מסוג רבים-לרבים באמצעות שני קשרים של רבים-לאחד וישות קישור (ישות המשמשת לחיבור ישות המקור לישות היעד).</span><span class="sxs-lookup"><span data-stu-id="dcdfc-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="dcdfc-139">‏‏מחק קשר</span><span class="sxs-lookup"><span data-stu-id="dcdfc-139">Delete a relationship</span></span>

1. <span data-ttu-id="dcdfc-140">ב- Audience Insights, עבור אל **נתונים** > **קשרים**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="dcdfc-141">בחר תיבות סימון עבור הקשר שברצונך למחוק.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="dcdfc-142">בחר **מחק** בחלק העליון של הטבלה **קשרים**.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="dcdfc-143">אשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="dcdfc-144">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="dcdfc-144">Next step</span></span>

<span data-ttu-id="dcdfc-145">קשרי מערכת וקשרים מותאמים אישית משמשים ליצירת פלחים המבוססים על מקורות נתונים מרובים שכבר אינם נפרדים.</span><span class="sxs-lookup"><span data-stu-id="dcdfc-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="dcdfc-146">לקבלת מידע נוסף, ראה [פלחים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="dcdfc-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]