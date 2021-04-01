---
title: העשרת פרופילי לקוחות באמצעות Microsoft Graph
description: השתמש בנתונים קנייניים מ- Microsoft Graph כדי להעשיר את נתוני הלקוחות שלך עם קירבות למותג ותחום עניין.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: aa46dac4f9c0d27881371877b14a92a6725710da
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596454"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="38600-103">העשרת פרופילי לקוחות עם קירבות למוצג ותחום עניין (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="38600-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="38600-104">השתמש בנתונים קנייניים מ- Microsoft Graph כדי להעשיר את נתוני הלקוחות שלך עם קירבות למותג ותחום עניין.</span><span class="sxs-lookup"><span data-stu-id="38600-104">Use proprietary data from the Microsoft Graph to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="38600-105">קשרים אלה נקבעים על סמך נתונים של אנשים עם דמוגרפיה דומה ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="38600-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="38600-106">מידע זה עוזר לך להבין טוב יותר ולפלח את הלקוחות שלך על סמך הזיקה שלהם למותגים ולתחומי עניין ספציפיים.</span><span class="sxs-lookup"><span data-stu-id="38600-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="38600-107">ב- audience insights, עבור אל **נתונים** > **העשרה** כדי [לקבוע תצורה ולהציג העשרות](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="38600-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="38600-108">כדי להגדיר העשרת קשרים עם מותג, עבור אל הכרטיסיה **גלה** ובחר **העשר את הנתונים שלי** באריח **מותגים**.</span><span class="sxs-lookup"><span data-stu-id="38600-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="38600-109">כדי להגדיר העשרת קשרים עם תחום עניין, עבור אל הכרטיסיה **גלה** ובחר **העשר את הנתונים שלי** באריח **תחומי עניין**.</span><span class="sxs-lookup"><span data-stu-id="38600-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="38600-110">![אריחים של מותגים ותחומי עניין](media/BrandsInterest-tile-Hub.png "אריחים של מותגים ותחומי עניין")</span><span class="sxs-lookup"><span data-stu-id="38600-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="about-microsoft-graph"></a><span data-ttu-id="38600-111">אודות Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="38600-111">About Microsoft Graph</span></span>

<span data-ttu-id="38600-112">אנו משתמשים בנתוני חיפוש מקוונים מ- Microsoft Graph כדי למצוא קירבות עבור מותגים ותחומי עניין בפלחי שוק דמוגרפיים שונים (מוגדרים לפי גיל, מגדר או מיקום).</span><span class="sxs-lookup"><span data-stu-id="38600-112">We use online search data from the Microsoft Graph to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="38600-113">נפח החיפוש המקוון עבור מותג או תחום עניין קובע את מידת הקירבה של פלח שוק דמוגרפי, בהשוואה לפלחי שוק אחרים, למותג או לתחום עניין זה.</span><span class="sxs-lookup"><span data-stu-id="38600-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

<span data-ttu-id="38600-114">[קבל מידע נוסף אודות Microsoft Graph](/graph/overview).</span><span class="sxs-lookup"><span data-stu-id="38600-114">[Learn more about Microsoft Graph](/graph/overview).</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="38600-115">רמת קירבה וניקוד</span><span class="sxs-lookup"><span data-stu-id="38600-115">Affinity level and score</span></span>

<span data-ttu-id="38600-116">בכל פרופיל לקוח מועשר אנחנו מספקים שני ערכים קשורים - רמת קירבה וניקוד קירבה.</span><span class="sxs-lookup"><span data-stu-id="38600-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="38600-117">ערכים אלה עוזרים לך לקבוע כמה חזקה הקירבה עבור פלח דמוגרפי של פרופיל זה, עבור מותג או תחום עניין, בהשוואה לפלחים דמוגרפיים אחרים.</span><span class="sxs-lookup"><span data-stu-id="38600-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="38600-118">*רמת קירבה* מורכבת מארבע רמות ו *ניקוד קירבה* מחושב בסולם של 100 נקודות הממופה לרמות הקירבה.</span><span class="sxs-lookup"><span data-stu-id="38600-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="38600-119">רמת קירבה</span><span class="sxs-lookup"><span data-stu-id="38600-119">Affinity level</span></span> |<span data-ttu-id="38600-120">ניקוד קירבה</span><span class="sxs-lookup"><span data-stu-id="38600-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="38600-121">גבוהה מאוד</span><span class="sxs-lookup"><span data-stu-id="38600-121">Very high</span></span>     | <span data-ttu-id="38600-122">85-100</span><span class="sxs-lookup"><span data-stu-id="38600-122">85-100</span></span>       |
|<span data-ttu-id="38600-123">גדול</span><span class="sxs-lookup"><span data-stu-id="38600-123">High</span></span>     | <span data-ttu-id="38600-124">70-84</span><span class="sxs-lookup"><span data-stu-id="38600-124">70-84</span></span>        |
|<span data-ttu-id="38600-125">בינוני</span><span class="sxs-lookup"><span data-stu-id="38600-125">Medium</span></span>     | <span data-ttu-id="38600-126">35-69</span><span class="sxs-lookup"><span data-stu-id="38600-126">35-69</span></span>        |
|<span data-ttu-id="38600-127">‏‫נמוך</span><span class="sxs-lookup"><span data-stu-id="38600-127">Low</span></span>     | <span data-ttu-id="38600-128">1-34</span><span class="sxs-lookup"><span data-stu-id="38600-128">1-34</span></span>        |

<span data-ttu-id="38600-129">בהתאם לרמת הפירוט הרצויה עבור מדידת הקירבה, באפשרותך להשתמש בכל אחד מניקודי הקירבה או מרמות הקירבה.</span><span class="sxs-lookup"><span data-stu-id="38600-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="38600-130">ניקוד קירבה נותן לך שליטה מדויקת יותר.</span><span class="sxs-lookup"><span data-stu-id="38600-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="38600-131">מדינות/אזורים נתמכים</span><span class="sxs-lookup"><span data-stu-id="38600-131">Supported countries/regions</span></span>

<span data-ttu-id="38600-132">אנו תומכים כרגע באפשרויות של המדינות/האזורים הבאים: אוסטרליה, קנדה (אנגלית), צרפת, גרמניה, בריטניה, או ארצות הברית (אנגלית).</span><span class="sxs-lookup"><span data-stu-id="38600-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="38600-133">לבחירת מדינה, פתח את **העשרת מותגים** אוֹ **העשרת אינטרס** ובחר **שינוי** ליד **מדינה/אזור**.</span><span class="sxs-lookup"><span data-stu-id="38600-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="38600-134">בתוך החלונית **הגדרות מדינה / אזור**, בחר אפשרות ובחר **החל**.</span><span class="sxs-lookup"><span data-stu-id="38600-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="38600-135">השלכות הקשורות לבחירת מדינה</span><span class="sxs-lookup"><span data-stu-id="38600-135">Implications related to country selection</span></span>

- <span data-ttu-id="38600-136">בעת [בחירת המותגים שלך](#define-your-brands-or-interests), המערכת מספקת הצעות המבוססות על המדינה או האזור שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="38600-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="38600-137">בעת [בחירת ענף](#define-your-brands-or-interests), תקבל את המותגים או תחומי העניין הרלוונטיים ביותר בהתבסס על המדינה או האזור שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="38600-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="38600-138">בעת [העשרת פרופילים](#refresh-enrichment), אנחנו נעשיר את כל פרופילי הלקוחות שעבורם אנחנו מקבלים נתונים עבור המותגים ותחומי העניין שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="38600-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="38600-139">כולל פרופילים שאינם במדינה או באזור שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="38600-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="38600-140">לדוגמה, אם בחרת בגרמניה, אנו נעשיר פרופילים שנמצאים בארצות הברית אם יש לנו נתוני Microsoft Graph זמינים עבור המותגים והאינטרסים שנבחרו בארה"ב.</span><span class="sxs-lookup"><span data-stu-id="38600-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have Microsoft Graph data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="38600-141">הגדר העשרה</span><span class="sxs-lookup"><span data-stu-id="38600-141">Configure Enrichment</span></span>

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="38600-142">הגדר את המותגים או תחומי העניין שלך</span><span class="sxs-lookup"><span data-stu-id="38600-142">Define your brands or interests</span></span>

<span data-ttu-id="38600-143">בחר באחת מהאפשרויות הבאות:</span><span class="sxs-lookup"><span data-stu-id="38600-143">Select one of the following options:</span></span>

- <span data-ttu-id="38600-144">**תעשיה**: המערכת מזהה את המותגים ותחומי העניין המובילים הרלוונטיים לתעשיה שלך ומעשירה את נתוני הלקוחות שלך איתם.</span><span class="sxs-lookup"><span data-stu-id="38600-144">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="38600-145">**בחר אפשרויות משלך**: בחר עד חמישה פריטים מתוך רשימת המותגים ותחומי העניין שהם הרלוונטיים ביותר לארגון שלך.</span><span class="sxs-lookup"><span data-stu-id="38600-145">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="38600-146">כדי להוסיף מותג או תחום עניין, הזן אותו באזור הקלט כדי לקבל הצעות המבוססות על מונחים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="38600-146">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="38600-147">אם איננו מציגים מותג או תחום עניין שאתה מחפש, שלח לנו משוב באמצעות הקישור **הצע**.</span><span class="sxs-lookup"><span data-stu-id="38600-147">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="38600-148">סקירת העדפות העשרה</span><span class="sxs-lookup"><span data-stu-id="38600-148">Review enrichment preferences</span></span>

<span data-ttu-id="38600-149">סקור את העדפות ההעשרה של ברירת המחדל ועדכן אותן בהתאם לצורך.</span><span class="sxs-lookup"><span data-stu-id="38600-149">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="צילום מסך של חלון העדפות ההעשרה.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="38600-151">בחירת ישות להעשרה</span><span class="sxs-lookup"><span data-stu-id="38600-151">Select entity to enrich</span></span>

<span data-ttu-id="38600-152">בחר **ישות מועשרת** ובחר את ערכת הנתונים שברצונך להעשיר בנתוני החברה מתוך Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="38600-152">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft Graph.</span></span> <span data-ttu-id="38600-153">באפשרותך לבחור את הישות 'לקוח' כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.</span><span class="sxs-lookup"><span data-stu-id="38600-153">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="38600-154">מיפוי השדות שלך</span><span class="sxs-lookup"><span data-stu-id="38600-154">Map your fields</span></span>

<span data-ttu-id="38600-155">מפה שדות מישות הלקוח המאוחדת שלך כדי להגדיר את הפלח הדמוגרפי שברצונך שהמערכת תשתמש בו לצורך העשרת נתוני הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="38600-155">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="38600-156">מפה מדינה/אזור ותכונות 'תאריך לידה' או 'מגדר' לפחות.</span><span class="sxs-lookup"><span data-stu-id="38600-156">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="38600-157">בנוסף, עליך למפות לפחות אחת מהתכונות 'עיר' (ו'מחוז') או 'מיקוד'.</span><span class="sxs-lookup"><span data-stu-id="38600-157">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="38600-158">בחר **ערוך** להגדרת מיפוי השדות ובחר **החל** לסיום.</span><span class="sxs-lookup"><span data-stu-id="38600-158">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="38600-159">בחר **שמור** כדי להשלים את מיפוי השדות.</span><span class="sxs-lookup"><span data-stu-id="38600-159">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="38600-160">הפורמטים והערכים הבאים נתמכים, הערכים אינם תלויי רישיות:</span><span class="sxs-lookup"><span data-stu-id="38600-160">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="38600-161">**תאריך לידה**: אנו ממליצים שתאריך הלידה יומר לסוג DateTime במהלך קליטת נתונים.</span><span class="sxs-lookup"><span data-stu-id="38600-161">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="38600-162">לחלופין, זה יכול להיות מחרוזת במבנה [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) ‏"yyyy-MM-dd" או "yyyy-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="38600-162">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="38600-163">**מגדר**: זכר, נקבה, לא ידוע</span><span class="sxs-lookup"><span data-stu-id="38600-163">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="38600-164">**מיקוד**: מיקוד בן חמש ספרות לארה"ב, מיקוד סטנדרטי בכל מקום אחר</span><span class="sxs-lookup"><span data-stu-id="38600-164">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="38600-165">**עִיר**: שם העיר באנגלית</span><span class="sxs-lookup"><span data-stu-id="38600-165">**City**: City name in English</span></span>
- <span data-ttu-id="38600-166">**מדינה/מחוז**: קיצור בן שתי אותיות לארה"ב ולקנדה.</span><span class="sxs-lookup"><span data-stu-id="38600-166">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="38600-167">קיצור בן שתיים או שלוש אותיות לאוסטרליה.</span><span class="sxs-lookup"><span data-stu-id="38600-167">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="38600-168">לא חל על צרפת, גרמניה או בריטניה.</span><span class="sxs-lookup"><span data-stu-id="38600-168">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="38600-169">**מדינה/אזור**:</span><span class="sxs-lookup"><span data-stu-id="38600-169">**Country/Region**:</span></span>

  - <span data-ttu-id="38600-170">ארה"ב: ארצות הברית של אמריקה, ארצות הברית, ארה"ב, ארה"ב, אמריקה</span><span class="sxs-lookup"><span data-stu-id="38600-170">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="38600-171">CA: קנדה, CA</span><span class="sxs-lookup"><span data-stu-id="38600-171">CA: Canada, CA</span></span>
  - <span data-ttu-id="38600-172">GB: הממלכה המאוחדת, בריטניה, UK, GB, בריטניה הגדולה וצפון אירלנד, הממלכה המאוחדת של בריטניה הגדולה</span><span class="sxs-lookup"><span data-stu-id="38600-172">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="38600-173">AU: אוסטרליה, AU, חבר העמים של אוסטרליה</span><span class="sxs-lookup"><span data-stu-id="38600-173">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="38600-174">FR: צרפת, הרפובליקה הצרפתית</span><span class="sxs-lookup"><span data-stu-id="38600-174">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="38600-175">DE: גרמניה, גרמניה, Deutschland, Allemagne, DE, הרפובליקה הפדרלית של גרמניה, הרפובליקה של גרמניה</span><span class="sxs-lookup"><span data-stu-id="38600-175">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="refresh-enrichment"></a><span data-ttu-id="38600-176">רענן העשרה</span><span class="sxs-lookup"><span data-stu-id="38600-176">Refresh enrichment</span></span>

<span data-ttu-id="38600-177">הפעל את ההעשרה לאחר קביעת התצורה של מותגים, תחומי עניין ומיפוי השדות עבור דמוגרפיה.</span><span class="sxs-lookup"><span data-stu-id="38600-177">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="38600-178">כדי להתחיל בתהליך, בחר **הפעל** בדף התצורה של המותג או תחום העניין.</span><span class="sxs-lookup"><span data-stu-id="38600-178">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="38600-179">בנוסף, אתה יכול לאפשר למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מרענון מתוזמן.</span><span class="sxs-lookup"><span data-stu-id="38600-179">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="38600-180">בהתאם לגודל נתוני הלקוחות שלך, ייתכן שיידרשו מספר דקות עד להשלמת הפעלת העשרה.</span><span class="sxs-lookup"><span data-stu-id="38600-180">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="38600-181">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="38600-181">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="38600-182">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="38600-182">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="38600-183">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="38600-183">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="38600-184">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="38600-184">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="38600-185">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="38600-185">Enrichment results</span></span>

<span data-ttu-id="38600-186">לאחר הפעלת תהליך ההעשרה, עבור אל **ההעשרות שלי** כדי לסקור את המספר הכולל של לקוחות מועשרים ופירוט של מותגים ותחומי עניין בפרופילי הלקוחות המועשרים.</span><span class="sxs-lookup"><span data-stu-id="38600-186">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="תצוגה מקדימה של תוצאות לאחר הפעלת תהליך העשרה":::

<span data-ttu-id="38600-188">סקור את הנתונים המועשרים על-ידי בחירת **הצג נתונים מועשרים** בתרשים.</span><span class="sxs-lookup"><span data-stu-id="38600-188">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="38600-189">נתונים מועשרים עבור מותגים מגיעים לישות **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="38600-189">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="38600-190">נתונים עבור תחומי עניין נמצאים בישות **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="38600-190">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="38600-191">תוכל למצוא ישויות אלה שרשומות בקבוצה **העשרה** גם ב- **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="38600-191">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="38600-192">ראה נתוני העשרה בכרטיס הלקוח</span><span class="sxs-lookup"><span data-stu-id="38600-192">See enrichment data on the customer card</span></span>

<span data-ttu-id="38600-193">ניתן להציג קשרי מותגים ותחומי עניין גם בכרטיסי לקוח פרטיים.</span><span class="sxs-lookup"><span data-stu-id="38600-193">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="38600-194">עבור אל **לקוחות** ובחר פרופיל לקוח.</span><span class="sxs-lookup"><span data-stu-id="38600-194">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="38600-195">בכרטיס הלקוח תמצא תרשימים עבור המותגים או תחומי העניין שלאנשים בפרופיל הדמוגרפי של אותו לקוח יש זיקה אליהם.</span><span class="sxs-lookup"><span data-stu-id="38600-195">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="כרטיס לקוח עם נתונים מועשרים":::

## <a name="next-steps"></a><span data-ttu-id="38600-197">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="38600-197">Next steps</span></span>

<span data-ttu-id="38600-198">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="38600-198">Build on top of your enriched customer data.</span></span> <span data-ttu-id="38600-199">צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="38600-199">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]