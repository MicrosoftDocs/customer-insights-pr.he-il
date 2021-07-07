---
title: העשרת פרופילי לקוחות מאוחדים
description: השתמש ביכולות כדי להעשיר את נתוני הלקוחות שלך.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: c35e73b366fcd5db2ba5a757295ddda6db30efa0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305249"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="33fd7-103">העשרה לפרופילי לקוחות (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="33fd7-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="33fd7-104">השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="33fd7-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="דף מרכז ההעשרה":::

<span data-ttu-id="33fd7-106">ב- audience insights, עבור אל **נתונים** > **העשרה** כדי לעבוד עם אפשרויות העשרה.</span><span class="sxs-lookup"><span data-stu-id="33fd7-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>  

<span data-ttu-id="33fd7-107">עליך להיות בעל הרשאות משתתף או מנהל מערכת כדי ליצור או לערוך העשרה.</span><span class="sxs-lookup"><span data-stu-id="33fd7-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="33fd7-108">לקבלת מידע נוסף, ראה [הרשאות](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="33fd7-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="33fd7-109">בכרטיסיה **גלה**, תוכל למצוא את ההעשרה הבאה:</span><span class="sxs-lookup"><span data-stu-id="33fd7-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="33fd7-110">[מותגים](enrichment-microsoft.md) שסופקו על-ידי Microsoft</span><span class="sxs-lookup"><span data-stu-id="33fd7-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="33fd7-111">[תחומי עניין](enrichment-microsoft.md) שסופקו על-ידי Microsoft</span><span class="sxs-lookup"><span data-stu-id="33fd7-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="33fd7-112">[כתובות משופרות](enrichment-enhanced-addresses.md) מסופקות על-ידי Microsoft</span><span class="sxs-lookup"><span data-stu-id="33fd7-112">[Enhanced addresses](enrichment-enhanced-addresses.md) provided by Microsoft</span></span>
- <span data-ttu-id="33fd7-113">[נתוני החברה](enrichment-leadspace.md) מסופקים על-ידי Leadspace</span><span class="sxs-lookup"><span data-stu-id="33fd7-113">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="33fd7-114">[נתונים דמוגרפיים](enrichment-experian.md) המסופקים על-ידי Experian</span><span class="sxs-lookup"><span data-stu-id="33fd7-114">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="33fd7-115">[נתוני מיקום](enrichment-here.md) מסופקים על-ידי HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="33fd7-115">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="33fd7-116">[נתונים מותאמים אישית](enrichment-SFTP-custom-import.md) דרך Secure File Transfer Protocol‏ (SFTP)</span><span class="sxs-lookup"><span data-stu-id="33fd7-116">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="33fd7-117">בכרטיסיה **ההעשרות שלי**, תוכל לראות את ההעשרות שהגדרת ולערוך את המאפיינים שלהן.</span><span class="sxs-lookup"><span data-stu-id="33fd7-117">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="33fd7-118">ניהול העשרות קיימות</span><span class="sxs-lookup"><span data-stu-id="33fd7-118">Manage existing enrichments</span></span>

<span data-ttu-id="33fd7-119">עבור אל הכרטיסיה **ההעשרות שלי** כדי לראות את כל ההעשרות שהוגדרו.</span><span class="sxs-lookup"><span data-stu-id="33fd7-119">Go to the **My enrichments** tab to see all configured enrichments.</span></span> <span data-ttu-id="33fd7-120">כל העשרה מיוצגת כשורה הכוללת מידע נוסף על ההעשרה.</span><span class="sxs-lookup"><span data-stu-id="33fd7-120">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="33fd7-121">בחר העשרה כדי לראות את האפשרויות הזמינות.</span><span class="sxs-lookup"><span data-stu-id="33fd7-121">Select an enrichment to see the available options.</span></span> <span data-ttu-id="33fd7-122">באפשרותך גם לבחור את שלוש הנקודות (...) בפריט רשימה כדי לראות את האפשרויות.</span><span class="sxs-lookup"><span data-stu-id="33fd7-122">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="אפשרויות לניהול ההעשרות ברשימת ההעשרות":::

- <span data-ttu-id="33fd7-124">**הצג** פרטי העשרה עם המספר של פרופילי לקוחות המועשרים.</span><span class="sxs-lookup"><span data-stu-id="33fd7-124">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="33fd7-125">**ערוך** את תצורת ההעשרה.</span><span class="sxs-lookup"><span data-stu-id="33fd7-125">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="33fd7-126">**הפעל** את העשרה לעדכון את פרופילי הלקוחות בנתונים העדכניים ביותר.</span><span class="sxs-lookup"><span data-stu-id="33fd7-126">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="33fd7-127">**השבת** העשרה קיימת כדי למנוע ממנה רענון אוטומטי עם כל רענון מתוזמן.</span><span class="sxs-lookup"><span data-stu-id="33fd7-127">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="33fd7-128">נתונים מהרענון האחרון המוצלח ימשיכו להיות זמינים.</span><span class="sxs-lookup"><span data-stu-id="33fd7-128">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="33fd7-129">**להפעיל** העשרה לא פעילה להפעלה מחדש של רענון אוטומטי בכל רענון מתוזמן.</span><span class="sxs-lookup"><span data-stu-id="33fd7-129">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="33fd7-130">**מחק** העשרה.</span><span class="sxs-lookup"><span data-stu-id="33fd7-130">**Delete** an enrichment.</span></span>

<span data-ttu-id="33fd7-131">באפשרותך להפעיל פעולות העשרה מרובות בבת אחת או לבטלן על ידי בחירתן מתוך רשימה.</span><span class="sxs-lookup"><span data-stu-id="33fd7-131">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="33fd7-132">אפשרויות תצוגה ועריכה אינן זמינות כפעולה בצובר והן פועלות רק עבור העשרה אחת בכל פעם.</span><span class="sxs-lookup"><span data-stu-id="33fd7-132">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="33fd7-133">העשרות וחיבורים</span><span class="sxs-lookup"><span data-stu-id="33fd7-133">Enrichments and connections</span></span>

<span data-ttu-id="33fd7-134">העשרות צד שלישי מוגדרות באמצעות [חיבורים](connections.md), אשר מנהל מערכת מגדיר עם אישורים ומספק הסכמה עבור העברות נתונים.</span><span class="sxs-lookup"><span data-stu-id="33fd7-134">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="33fd7-135">החיבור יכול לשמש את מנהלי המערכת והמשתתפים לקביעת תצורה של העשרות.</span><span class="sxs-lookup"><span data-stu-id="33fd7-135">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="33fd7-136">העשרות מרובות מאותו סוג</span><span class="sxs-lookup"><span data-stu-id="33fd7-136">Multiple enrichments of the same type</span></span>

<span data-ttu-id="33fd7-137">הישות שיש להעשיר מצוינת במהלך קביעת תצורת ההעשרה, אשר מאפשרת לך להעשיר רק ערכת משנה של הפרופילים שלך.</span><span class="sxs-lookup"><span data-stu-id="33fd7-137">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="33fd7-138">לדוגמה, העשרת נתונים רק עבור פלח ספציפי.</span><span class="sxs-lookup"><span data-stu-id="33fd7-138">For example, enrich data only for a specific segment.</span></span> <span data-ttu-id="33fd7-139">באפשרותך לקבוע תצורה של מספר העשרות מאותו סוג ולהשתמש מחדש באותו חיבור.</span><span class="sxs-lookup"><span data-stu-id="33fd7-139">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="33fd7-140">לחלק מההעשרות יהיו מגבלות על מספר ההעשרות מאותו הסוג שניתן ליצור.</span><span class="sxs-lookup"><span data-stu-id="33fd7-140">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="33fd7-141">ניתן לראות את המגבלות והשימוש הנוכחי בדף **העשרה**.</span><span class="sxs-lookup"><span data-stu-id="33fd7-141">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
