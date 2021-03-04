---
title: העשרת פרופילי החברה באמצעות Leadspace העשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269423"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="ccb25-103">העשרה של פרופילי חברות באמצעות Leadspace (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="ccb25-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="ccb25-104">Leadspace היא חברה למדעי נתונים המספקת פלטפורמת נתוני לקוחות B2B.</span><span class="sxs-lookup"><span data-stu-id="ccb25-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="ccb25-105">היא מאפשרת ללקוחות עם פרופילי לקוחות אחידים לחברות להעשיר את הנתונים שלהם.</span><span class="sxs-lookup"><span data-stu-id="ccb25-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="ccb25-106">העשרות כוללות תכונות נוספות כגון גודל חברה, מיקום, ענף ועוד.</span><span class="sxs-lookup"><span data-stu-id="ccb25-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ccb25-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="ccb25-107">Prerequisites</span></span>

<span data-ttu-id="ccb25-108">כדי להגדיר את Leadspace, הדרישות המוקדמות הבאות צריכות להתקיים:</span><span class="sxs-lookup"><span data-stu-id="ccb25-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ccb25-109">יש לך רישיון Leadspace פעיל ו"מפתח קבוע" (מכונה **אסימון Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="ccb25-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="ccb25-110">צור קשר ישירות עם [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) לקבלת פרטים על המוצר שלהם.</span><span class="sxs-lookup"><span data-stu-id="ccb25-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="ccb25-111">יש לך הרשאות [מנהל מערכת](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="ccb25-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="ccb25-112">יש לך [פרופילי לקוחות מאוחדים](customer-profiles.md) עבור חברות.</span><span class="sxs-lookup"><span data-stu-id="ccb25-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="ccb25-113">תצורה</span><span class="sxs-lookup"><span data-stu-id="ccb25-113">Configuration</span></span>

1. <span data-ttu-id="ccb25-114">ב- audience insights, עבור אל **נתונים** > **העשרה**.</span><span class="sxs-lookup"><span data-stu-id="ccb25-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="ccb25-115">בחר **העשר את הנתונים שלי** באריח Leadspace.</span><span class="sxs-lookup"><span data-stu-id="ccb25-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="צילום מסך של אריח Leadspace.":::

1. <span data-ttu-id="ccb25-117">בחר **תחילת העבודה** והזן **אסימון Leadspace** פעיל (מפתח קבוע).</span><span class="sxs-lookup"><span data-stu-id="ccb25-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="ccb25-118">סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="ccb25-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="ccb25-119">אשר את שני ערכי הקלט על-ידי בחירת **התחבר ל- Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="ccb25-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="ccb25-120">בחר **מפה נתונים** ובחר את ערכת הנתונים שברצונך להעשיר בנתוני החברה מתוך Leadspace.</span><span class="sxs-lookup"><span data-stu-id="ccb25-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="ccb25-121">באפשרותך לבחור את הישות *לקוח* כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.</span><span class="sxs-lookup"><span data-stu-id="ccb25-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="בחר בין פרופיל לקוח להעשרת פלח.":::

1. <span data-ttu-id="ccb25-123">לחץ על **הבא** והגדר באילו שדות מהפרופילים המאוחדים שלך יש להשתמש כדי לחפש נתוני חברה תואמים מ- Leadspace.</span><span class="sxs-lookup"><span data-stu-id="ccb25-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="ccb25-124">השדה **שם חברה** הוא נדרש.</span><span class="sxs-lookup"><span data-stu-id="ccb25-124">The **Name of company** field is required.</span></span> <span data-ttu-id="ccb25-125">לקבלת דיוק התאמות גבוה יותר, ניתן להוסיף עד שני שדות אחרים, **אתר אינטרנט של חברה** ו **מיקום חברה**.</span><span class="sxs-lookup"><span data-stu-id="ccb25-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="חלונית מיפוי שדה Leadspace.":::
   
1. <span data-ttu-id="ccb25-127">בחר **החל** להשלמת מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="ccb25-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="ccb25-128">בחר **הפעל** כדי להעשיר את פרופילי החברה.</span><span class="sxs-lookup"><span data-stu-id="ccb25-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="ccb25-129">משך הזמן הדרוש להעשרה תלוי במספר פרופילי הלקוחות המאוחדים.</span><span class="sxs-lookup"><span data-stu-id="ccb25-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ccb25-130">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="ccb25-130">Enrichment results</span></span>

<span data-ttu-id="ccb25-131">לאחר רענון ההעשרה תוכל לסקור את נתוני החברה שהועשרו לאחרונה מתחת ל[העשרות שלי](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="ccb25-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="ccb25-132">תוכל למצוא את זמן העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="ccb25-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ccb25-133">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="ccb25-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="ccb25-134">לקבלת מידע נוסף, ראה [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="ccb25-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ccb25-135">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="ccb25-135">Next steps</span></span>

<span data-ttu-id="ccb25-136">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="ccb25-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ccb25-137">צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="ccb25-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ccb25-138">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="ccb25-138">Data privacy and compliance</span></span>

<span data-ttu-id="ccb25-139">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Leadspace, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="ccb25-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ccb25-140">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Leadspace עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="ccb25-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ccb25-141">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ccb25-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ccb25-142">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="ccb25-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]