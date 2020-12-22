---
title: העשרת פרופילי החברה באמצעות Leadspace העשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668724"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="4cd44-103">העשרה של פרופילי חברות באמצעות Leadspace (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="4cd44-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="4cd44-104">Leadspace היא חברה למדעי נתונים המספקת פלטפורמת נתוני לקוחות B2B.</span><span class="sxs-lookup"><span data-stu-id="4cd44-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="4cd44-105">היא מאפשרת ללקוחות עם פרופילי לקוחות אחידים לחברות להעשיר את הנתונים שלהם.</span><span class="sxs-lookup"><span data-stu-id="4cd44-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="4cd44-106">העשרות כוללות תכונות נוספות כגון גודל חברה, מיקום, ענף ועוד.</span><span class="sxs-lookup"><span data-stu-id="4cd44-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4cd44-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="4cd44-107">Prerequisites</span></span>

<span data-ttu-id="4cd44-108">כדי להגדיר את Leadspace, הדרישות המוקדמות הבאות צריכות להתקיים:</span><span class="sxs-lookup"><span data-stu-id="4cd44-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4cd44-109">יש לך רישיון Leadspace פעיל ו"מפתח קבוע" (מכונה **אסימון Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="4cd44-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="4cd44-110">צור קשר ישירות עם [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) לקבלת פרטים על המוצר שלהם.</span><span class="sxs-lookup"><span data-stu-id="4cd44-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="4cd44-111">יש לך הרשאות [מנהל מערכת](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="4cd44-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="4cd44-112">יש לך [פרופילי לקוחות מאוחדים](customer-profiles.md) עבור חברות.</span><span class="sxs-lookup"><span data-stu-id="4cd44-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="4cd44-113">תצורה</span><span class="sxs-lookup"><span data-stu-id="4cd44-113">Configuration</span></span>

1. <span data-ttu-id="4cd44-114">ב- audience insights, עבור אל **נתונים** > **העשרה**.</span><span class="sxs-lookup"><span data-stu-id="4cd44-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="4cd44-115">בחר **העשר את הנתונים שלי** באריח Leadspace.</span><span class="sxs-lookup"><span data-stu-id="4cd44-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="צילום מסך של אריח Leadspace.":::

1. <span data-ttu-id="4cd44-117">בחר **תחילת העבודה** והזן **אסימון Leadspace** פעיל (מפתח קבוע).</span><span class="sxs-lookup"><span data-stu-id="4cd44-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="4cd44-118">סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="4cd44-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="4cd44-119">אשר את שני ערכי הקלט על-ידי בחירת **התחבר ל- Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="4cd44-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="4cd44-120">בחר **נתוני מפה** והגדר באילו שדות מהפרופילים המאוחדים שלך יש להשתמש כדי לחפש נתוני חברה תואמים מ- Leadspace.</span><span class="sxs-lookup"><span data-stu-id="4cd44-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="4cd44-121">השדה **שם חברה** הוא נדרש.</span><span class="sxs-lookup"><span data-stu-id="4cd44-121">The **Name of company** field is required.</span></span> <span data-ttu-id="4cd44-122">לקבלת דיוק התאמות גבוה יותר, ניתן להוסיף עד שני שדות אחרים, **אתר אינטרנט של חברה** ו **מיקום חברה**.</span><span class="sxs-lookup"><span data-stu-id="4cd44-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="חלונית מיפוי שדה Leadspace.":::
   
1. <span data-ttu-id="4cd44-124">בחר **החל** להשלמת מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="4cd44-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="4cd44-125">בחר **הפעל** כדי להעשיר את פרופילי החברה.</span><span class="sxs-lookup"><span data-stu-id="4cd44-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="4cd44-126">משך הזמן הדרוש להעשרה תלוי במספר פרופילי הלקוחות המאוחדים.</span><span class="sxs-lookup"><span data-stu-id="4cd44-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="4cd44-127">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="4cd44-127">Enrichment results</span></span>

<span data-ttu-id="4cd44-128">לאחר רענון ההעשרה תוכל לסקור את נתוני החברה שהועשרו לאחרונה מתחת ל[העשרות שלי](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="4cd44-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="4cd44-129">תוכל למצוא את זמן העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="4cd44-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4cd44-130">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="4cd44-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="4cd44-131">לקבלת מידע נוסף, ראה [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="4cd44-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4cd44-132">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="4cd44-132">Next steps</span></span>

<span data-ttu-id="4cd44-133">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="4cd44-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4cd44-134">צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="4cd44-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4cd44-135">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="4cd44-135">Data privacy and compliance</span></span>

<span data-ttu-id="4cd44-136">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Leadspace, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="4cd44-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4cd44-137">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Leadspace עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="4cd44-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4cd44-138">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4cd44-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4cd44-139">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="4cd44-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>