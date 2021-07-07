---
title: העשרת פרופילי החברה באמצעות Leadspace העשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 0496d10c994cd077a778a6e745e3774e316765ae
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305203"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="d3fc9-103">העשרה של פרופילי חברות באמצעות Leadspace (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="d3fc9-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="d3fc9-104">Leadspace היא חברה למדעי נתונים המספקת פלטפורמת נתוני לקוחות B2B.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="d3fc9-105">היא מאפשרת ללקוחות עם פרופילי לקוחות אחידים לחברות להעשיר את הנתונים שלהם.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="d3fc9-106">העשרות כוללות תכונות נוספות כגון גודל חברה, מיקום, תעשייה ועוד.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3fc9-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="d3fc9-107">Prerequisites</span></span>

<span data-ttu-id="d3fc9-108">כדי להגדיר את Leadspace, הדרישות המוקדמות הבאות צריכות להתקיים:</span><span class="sxs-lookup"><span data-stu-id="d3fc9-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="d3fc9-109">יש לך רישיון Leadspace פעיל.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="d3fc9-110">יש לך [פרופילי לקוחות מאוחדים](customer-profiles.md) עבור חברות.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="d3fc9-111">חיבור Leadspace כבר הוגדר על-ידי מנהל מערכת או שיש לך הרשאות [מנהל מערכת](permissions.md#administrator) ואת ה"מפתח התמידי" (מכונה **אסימון Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="d3fc9-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="d3fc9-112">צור קשר ישירות עם [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) לקבלת פרטים על המוצר שלהם.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="d3fc9-113">קביעת תצורת ההעשרה</span><span class="sxs-lookup"><span data-stu-id="d3fc9-113">Configure the enrichment</span></span>

1. <span data-ttu-id="d3fc9-114">ב- audience insights, עבור אל **נתונים** > **העשרה**.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="d3fc9-115">בחר **העשר את הנתונים שלי** באריח Leadspace ובחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="צילום מסך של אריח Leadspace.":::

1. <span data-ttu-id="d3fc9-117">בחר [חיבור](connections.md) מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-117">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="d3fc9-118">צור קשר עם מנהל מערכת אם אין חיבור זמין.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="d3fc9-119">אם אתה מנהל מערכת, באפשרותך ליצור חיבור על-ידי בחירת **הוסף חיבור** ובחירת **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="d3fc9-120">בחר **התחבר ל- Leadspace** כדי לאשר את החיבור.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="d3fc9-121">בחר **הבא** ובחר את **ערכת הנתונים של הלקוח** שברצונך להעשיר בנתוני חברה מתוך Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="d3fc9-122">באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. <span data-ttu-id="d3fc9-124">בחר **הבא** והגדר אילו שדות מתוך הפרופילים המאוחדים של משמשים כדי לחפש נתוני חברה מתאימים מ- Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="d3fc9-125">השדה **שם חברה** הוא נדרש.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-125">The **Name of company** field is required.</span></span> <span data-ttu-id="d3fc9-126">לקבלת דיוק התאמות גבוה יותר, ניתן להוסיף עד שני שדות אחרים, **אתר אינטרנט של חברה** ו **מיקום חברה**.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="חלונית מיפוי שדה Leadspace.":::

1. <span data-ttu-id="d3fc9-128">בחר **הבא** כדי להשלים את מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="d3fc9-129">ספק שם עבור ההעשרה ובחר **שמור העשרה** לאחר סקירת האפשרויות שלך.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="d3fc9-130">קביעת תצורת החיבור עבור Leadspace</span><span class="sxs-lookup"><span data-stu-id="d3fc9-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="d3fc9-131">עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="d3fc9-132">בחר **הוסף חיבור** בעת קביעת תצורת העשרה *או* עבור אל **ניהול** > **חיבורים** ובחר **הגדר** באריח Leadspace.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="d3fc9-133">בחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-133">Select **Get Started**.</span></span> 

1. <span data-ttu-id="d3fc9-134">הזן שם עבור החיבור בתיבה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="d3fc9-135">ספק אסימון Leadspace חוקי.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="d3fc9-136">סקור את **פרטיות ותאימות נתונים** ותן את הסכמתך על-ידי בחירת **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-136">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="d3fc9-137">בחר **אימות** כדי לאמת את התצורה.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="d3fc9-138">לאחר השלמת האימות, בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="דף תצורת החיבור של Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="d3fc9-140">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="d3fc9-140">Enrichment results</span></span>

<span data-ttu-id="d3fc9-141">לאחר רענון ההעשרה תוכל לסקור את נתוני החברה שהועשרו לאחרונה מתחת ל[העשרות שלי](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="d3fc9-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="d3fc9-142">תוכל למצוא את זמן העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="d3fc9-143">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="d3fc9-144">לקבלת מידע נוסף, ראה [Leadspace API](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="d3fc9-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d3fc9-145">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="d3fc9-145">Next steps</span></span>

<span data-ttu-id="d3fc9-146">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="d3fc9-147">צור [פלחים](segments.md) ו[מדידות](measures.md), ואפילו [יצא את הנתונים](export-destinations.md) כדי להעניק ללקוחות שלך חוויות מותאמות אישית.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-147">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d3fc9-148">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="d3fc9-148">Data privacy and compliance</span></span>

<span data-ttu-id="d3fc9-149">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Leadspace, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d3fc9-150">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Leadspace עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d3fc9-151">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d3fc9-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d3fc9-152">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="d3fc9-152">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
