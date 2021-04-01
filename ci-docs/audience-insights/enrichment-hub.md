---
title: העשרת פרופילי לקוחות מאוחדים
description: השתמש ביכולות כדי להעשיר את נתוני הלקוחות שלך.
ms.date: 11/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 36e6f7f8fcd64fc2591e913910918b83bf27567b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597696"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="6a345-103">העשרה לפרופילי לקוחות (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="6a345-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="6a345-104">השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="6a345-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="דף מרכז ההעשרה":::

<span data-ttu-id="6a345-106">ב- audience insights, עבור אל **נתונים** > **העשרה** כדי לעבוד עם אפשרויות העשרה.</span><span class="sxs-lookup"><span data-stu-id="6a345-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="6a345-107">עליך להיות בעל הרשאות משתתף או מנהל מערכת כדי ליצור או לערוך העשרה.</span><span class="sxs-lookup"><span data-stu-id="6a345-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="6a345-108">לקבלת מידע נוסף, ראה [הרשאות](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="6a345-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="6a345-109">בכרטיסיה **גלה**, תוכל למצוא את ההעשרה הבאה:</span><span class="sxs-lookup"><span data-stu-id="6a345-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="6a345-110">[מותגים](enrichment-microsoft-graph.md) מסופקים על ידי Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="6a345-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="6a345-111">[תחומי עניין](enrichment-microsoft-graph.md) מסופקים על-ידי Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="6a345-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="6a345-112">[נתוני החברה](enrichment-leadspace.md) מסופקים על-ידי Leadspace</span><span class="sxs-lookup"><span data-stu-id="6a345-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="6a345-113">[נתונים דמוגרפיים](enrichment-experian.md) מסופקים על-ידי Experian</span><span class="sxs-lookup"><span data-stu-id="6a345-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="6a345-114">[נתוני מיקום](enrichment-here.md) מסופקים על-ידי HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="6a345-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="6a345-115">[נתונים מותאמים אישית](enrichment-SFTP-custom-import.md) דרך Secure File Transfer Protocol‏ (SFTP)</span><span class="sxs-lookup"><span data-stu-id="6a345-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="6a345-116">בכרטיסיה **ההעשרות שלי**, תוכל לראות את ההעשרות שהגדרת ולערוך את המאפיינים שלהן.</span><span class="sxs-lookup"><span data-stu-id="6a345-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="6a345-117">ניהול העשרות קיימות</span><span class="sxs-lookup"><span data-stu-id="6a345-117">Manage existing enrichments</span></span>

<span data-ttu-id="6a345-118">עבור אל **העשרה שלי** כדי לראות את כל ההעשרה המוגדרת.</span><span class="sxs-lookup"><span data-stu-id="6a345-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="6a345-119">כל העשרה מיוצגת כשורה הכוללת מידע נוסף על ההעשרה.</span><span class="sxs-lookup"><span data-stu-id="6a345-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="6a345-120">בחר העשרה כדי לראות את האפשרויות הזמינות.</span><span class="sxs-lookup"><span data-stu-id="6a345-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="6a345-121">לחלופין, ניתן לבחור בשלוש נקדות (...) בפריט של רשימה כדי לראות את האפשרויות.</span><span class="sxs-lookup"><span data-stu-id="6a345-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="אפשרויות לניהול ההעשרות ברשימת ההעשרות":::

- <span data-ttu-id="6a345-123">**הצג** פרטי העשרה עם המספר של פרופילי לקוחות המועשרים.</span><span class="sxs-lookup"><span data-stu-id="6a345-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="6a345-124">**ערוך** את תצורת ההעשרה.</span><span class="sxs-lookup"><span data-stu-id="6a345-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="6a345-125">**הפעל** את העשרה לעדכון את פרופילי הלקוחות בנתונים העדכניים ביותר.</span><span class="sxs-lookup"><span data-stu-id="6a345-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="6a345-126">**השבת** העשרה קיימת כדי למנוע ממנה רענון אוטומטי עם כל רענון מתוזמן.</span><span class="sxs-lookup"><span data-stu-id="6a345-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="6a345-127">נתונים מהרענון האחרון המוצלח ימשיכו להיות זמינים.</span><span class="sxs-lookup"><span data-stu-id="6a345-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="6a345-128">**להפעיל** העשרה לא פעילה להפעלה מחדש של רענון אוטומטי בכל רענון מתוזמן.</span><span class="sxs-lookup"><span data-stu-id="6a345-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="6a345-129">**מחק** העשרה.</span><span class="sxs-lookup"><span data-stu-id="6a345-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="6a345-130">באפשרותך להפעיל פעולות העשרה מרובות בבת אחת או לבטלן על ידי בחירתן מתוך רשימה.</span><span class="sxs-lookup"><span data-stu-id="6a345-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="6a345-131">אפשרויות תצוגה ועריכה אינן זמינות כפעולה בצובר והן פועלות רק עבור העשרה אחת בכל פעם.</span><span class="sxs-lookup"><span data-stu-id="6a345-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]