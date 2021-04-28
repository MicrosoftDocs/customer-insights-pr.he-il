---
title: העשרת פרופילי לקוחות עם נתונים מ- Microsoft
description: השתמש בנתונים קנייניים מ- Microsoft כדי להעשיר את נתוני הלקוחות שלך עם זיקה למותג ולתחום עניין.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6f19033236190547f68d2b91ec6b32074bf7912a
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896603"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="2b5bd-103">העשרת פרופילי לקוחות עם קירבות למוצג ותחום עניין (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="2b5bd-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="2b5bd-104">השתמש בנתונים קנייניים של Microsoft כדי להעשיר את נתוני הלקוחות שלך עם זיקה למותג ולתחום עניין.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="2b5bd-105">קשרים אלה נקבעים על סמך נתונים של אנשים עם דמוגרפיה דומה ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="2b5bd-106">מידע זה עוזר לך להבין טוב יותר ולפלח את הלקוחות שלך על סמך הזיקה שלהם למותגים ולתחומי עניין ספציפיים.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="2b5bd-107">ב- audience insights, עבור אל **נתונים** > **העשרה** כדי [לקבוע תצורה ולהציג העשרות](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="2b5bd-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="2b5bd-108">כדי להגדיר העשרת קשרים עם מותג, עבור אל הכרטיסיה **גלה** ובחר **העשר את הנתונים שלי** באריח **מותגים**.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="2b5bd-109">כדי להגדיר העשרת קשרים עם תחום עניין, עבור אל הכרטיסיה **גלה** ובחר **העשר את הנתונים שלי** באריח **תחומי עניין**.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2b5bd-110">![אריחים של מותגים ותחומי עניין](media/BrandsInterest-tile-Hub.png "אריחים של מותגים ותחומי עניין")</span><span class="sxs-lookup"><span data-stu-id="2b5bd-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="2b5bd-111">כיצד אנחנו קובעים זיקה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-111">How we determine affinities</span></span>

<span data-ttu-id="2b5bd-112">אנו משתמשים בנתוני החיפוש המקוון של Microsoft כדי למצוא זיקות עבור מותגים ותחומי עניין בפלחים דמוגפיים שונים (מוגדר על-ידי גיל, מגדר או מיקום).</span><span class="sxs-lookup"><span data-stu-id="2b5bd-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="2b5bd-113">נפח החיפוש המקוון עבור מותג או תחום עניין קובע את מידת הקירבה של פלח שוק דמוגרפי, בהשוואה לפלחי שוק אחרים, למותג או לתחום עניין זה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span> <span data-ttu-id="2b5bd-114">מותג או תחום עניין.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-114">brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="2b5bd-115">רמת קירבה וניקוד</span><span class="sxs-lookup"><span data-stu-id="2b5bd-115">Affinity level and score</span></span>

<span data-ttu-id="2b5bd-116">בכל פרופיל לקוח מועשר אנחנו מספקים שני ערכים קשורים - רמת קירבה וניקוד קירבה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-116">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="2b5bd-117">ערכים אלה עוזרים לך לקבוע כמה חזקה הקירבה עבור פלח דמוגרפי של פרופיל זה, עבור מותג או תחום עניין, בהשוואה לפלחים דמוגרפיים אחרים.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-117">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="2b5bd-118">*רמת קירבה* מורכבת מארבע רמות ו *ניקוד קירבה* מחושב בסולם של 100 נקודות הממופה לרמות הקירבה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-118">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="2b5bd-119">רמת קירבה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-119">Affinity level</span></span> |<span data-ttu-id="2b5bd-120">ניקוד קירבה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-120">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="2b5bd-121">גבוהה מאוד</span><span class="sxs-lookup"><span data-stu-id="2b5bd-121">Very high</span></span>     | <span data-ttu-id="2b5bd-122">85-100</span><span class="sxs-lookup"><span data-stu-id="2b5bd-122">85-100</span></span>       |
|<span data-ttu-id="2b5bd-123">גדול</span><span class="sxs-lookup"><span data-stu-id="2b5bd-123">High</span></span>     | <span data-ttu-id="2b5bd-124">70-84</span><span class="sxs-lookup"><span data-stu-id="2b5bd-124">70-84</span></span>        |
|<span data-ttu-id="2b5bd-125">בינוני</span><span class="sxs-lookup"><span data-stu-id="2b5bd-125">Medium</span></span>     | <span data-ttu-id="2b5bd-126">35-69</span><span class="sxs-lookup"><span data-stu-id="2b5bd-126">35-69</span></span>        |
|<span data-ttu-id="2b5bd-127">‏‫נמוך</span><span class="sxs-lookup"><span data-stu-id="2b5bd-127">Low</span></span>     | <span data-ttu-id="2b5bd-128">1-34</span><span class="sxs-lookup"><span data-stu-id="2b5bd-128">1-34</span></span>        |

<span data-ttu-id="2b5bd-129">בהתאם לרמת הפירוט הרצויה עבור מדידת הקירבה, באפשרותך להשתמש בכל אחד מניקודי הקירבה או מרמות הקירבה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-129">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="2b5bd-130">ניקוד קירבה נותן לך שליטה מדויקת יותר.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-130">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="2b5bd-131">מדינות/אזורים נתמכים</span><span class="sxs-lookup"><span data-stu-id="2b5bd-131">Supported countries/regions</span></span>

<span data-ttu-id="2b5bd-132">אנו תומכים כרגע באפשרויות של המדינות/האזורים הבאים: אוסטרליה, קנדה (אנגלית), צרפת, גרמניה, בריטניה, או ארצות הברית (אנגלית).</span><span class="sxs-lookup"><span data-stu-id="2b5bd-132">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="2b5bd-133">לבחירת מדינה, פתח את **העשרת מותגים** אוֹ **העשרת אינטרס** ובחר **שינוי** ליד **מדינה/אזור**.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-133">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="2b5bd-134">בתוך החלונית **הגדרות מדינה / אזור**, בחר אפשרות ובחר **החל**.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-134">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="2b5bd-135">השלכות הקשורות לבחירת מדינה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-135">Implications related to country selection</span></span>

- <span data-ttu-id="2b5bd-136">בעת [בחירת המותגים שלך](#define-your-brands-or-interests), המערכת מספקת הצעות המבוססות על המדינה או האזור שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-136">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="2b5bd-137">בעת [בחירת ענף](#define-your-brands-or-interests), תקבל את המותגים או תחומי העניין הרלוונטיים ביותר בהתבסס על המדינה או האזור שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-137">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="2b5bd-138">בעת [העשרת פרופילים](#refresh-enrichment), אנחנו נעשיר את כל פרופילי הלקוחות שעבורם אנחנו מקבלים נתונים עבור המותגים ותחומי העניין שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-138">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="2b5bd-139">כולל פרופילים שאינם במדינה או באזור שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-139">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="2b5bd-140">לדוגמה, אם בחרת בגרמניה, אנחנו נעשיר פרופילים הממוקמים בארצות הברית אם יש לנו נתונים זמינים עבור המותגים ותחומי עניין הנבחרים בארצות הברית.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-140">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="2b5bd-141">הגדר העשרה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-141">Configure Enrichment</span></span>

<span data-ttu-id="2b5bd-142">חוויה מודרכת מסייעת לך בקביעת התצורה של ההעשרות.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-142">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="2b5bd-143">הגדר את המותגים או תחומי העניין שלך</span><span class="sxs-lookup"><span data-stu-id="2b5bd-143">Define your brands or interests</span></span>

<span data-ttu-id="2b5bd-144">בחר באחת מהאפשרויות הבאות:</span><span class="sxs-lookup"><span data-stu-id="2b5bd-144">Select one of the following options:</span></span>

- <span data-ttu-id="2b5bd-145">**תעשיה**: המערכת מזהה את המותגים ותחומי העניין המובילים הרלוונטיים לתעשיה שלך ומעשירה את נתוני הלקוחות שלך איתם.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-145">**Industry**: The system identifies the top brands or interests relevant to your industry and enriches your customer data with them.</span></span>
- <span data-ttu-id="2b5bd-146">**בחר אפשרויות משלך**: בחר עד חמישה פריטים מתוך רשימת המותגים ותחומי העניין שהם הרלוונטיים ביותר לארגון שלך.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-146">**Choose your own**: Select up to five items from the list of brands or interests that are most relevant to your organization.</span></span>

<span data-ttu-id="2b5bd-147">כדי להוסיף מותג או תחום עניין, הזן אותו באזור הקלט כדי לקבל הצעות המבוססות על מונחים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-147">To add a brand or interest, enter it in the input area to get suggestions based on matching terms.</span></span> <span data-ttu-id="2b5bd-148">אם איננו מציגים מותג או תחום עניין שאתה מחפש, שלח לנו משוב באמצעות הקישור **הצע**.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-148">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="2b5bd-149">סקירת העדפות העשרה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-149">Review enrichment preferences</span></span>

<span data-ttu-id="2b5bd-150">סקור את העדפות ההעשרה של ברירת המחדל ועדכן אותן בהתאם לצורך.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-150">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="צילום מסך של חלון העדפות ההעשרה.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="2b5bd-152">בחירת ישות להעשרה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-152">Select entity to enrich</span></span>

<span data-ttu-id="2b5bd-153">בחר **ישות מועשרת** ובחר את ערכת הנתונים שברצונך להעשיר עם נתוני החברה מ- Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-153">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="2b5bd-154">באפשרותך לבחור את הישות 'לקוח' כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-154">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="2b5bd-155">מיפוי השדות שלך</span><span class="sxs-lookup"><span data-stu-id="2b5bd-155">Map your fields</span></span>

<span data-ttu-id="2b5bd-156">מפה שדות מישות הלקוח המאוחדת שלך כדי להגדיר את הפלח הדמוגרפי שברצונך שהמערכת תשתמש בו לצורך העשרת נתוני הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-156">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="2b5bd-157">מפה מדינה/אזור ותכונות 'תאריך לידה' או 'מגדר' לפחות.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-157">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="2b5bd-158">בנוסף, עליך למפות לפחות אחת מהתכונות 'עיר' (ו'מחוז') או 'מיקוד'.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-158">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="2b5bd-159">בחר **ערוך** להגדרת מיפוי השדות ובחר **החל** לסיום.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-159">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="2b5bd-160">בחר **שמור** כדי להשלים את מיפוי השדות.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-160">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="2b5bd-161">הפורמטים והערכים הבאים נתמכים, הערכים אינם תלויי רישיות:</span><span class="sxs-lookup"><span data-stu-id="2b5bd-161">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="2b5bd-162">**תאריך לידה**: אנו ממליצים שתאריך הלידה יומר לסוג DateTime במהלך קליטת נתונים.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-162">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="2b5bd-163">לחלופין, זה יכול להיות מחרוזת במבנה [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) ‏"yyyy-MM-dd" או "yyyy-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="2b5bd-163">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="2b5bd-164">**מגדר**: זכר, נקבה, לא ידוע</span><span class="sxs-lookup"><span data-stu-id="2b5bd-164">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="2b5bd-165">**מיקוד**: מיקוד בן חמש ספרות לארה"ב, מיקוד סטנדרטי בכל מקום אחר</span><span class="sxs-lookup"><span data-stu-id="2b5bd-165">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="2b5bd-166">**עִיר**: שם העיר באנגלית</span><span class="sxs-lookup"><span data-stu-id="2b5bd-166">**City**: City name in English</span></span>
- <span data-ttu-id="2b5bd-167">**מדינה/מחוז**: קיצור בן שתי אותיות לארה"ב ולקנדה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-167">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="2b5bd-168">קיצור בן שתיים או שלוש אותיות לאוסטרליה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-168">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="2b5bd-169">לא חל על צרפת, גרמניה או בריטניה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-169">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="2b5bd-170">**מדינה/אזור**:</span><span class="sxs-lookup"><span data-stu-id="2b5bd-170">**Country/Region**:</span></span>

  - <span data-ttu-id="2b5bd-171">ארה"ב: ארצות הברית של אמריקה, ארצות הברית, ארה"ב, ארה"ב, אמריקה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-171">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="2b5bd-172">CA: קנדה, CA</span><span class="sxs-lookup"><span data-stu-id="2b5bd-172">CA: Canada, CA</span></span>
  - <span data-ttu-id="2b5bd-173">GB: הממלכה המאוחדת, בריטניה, UK, GB, בריטניה הגדולה וצפון אירלנד, הממלכה המאוחדת של בריטניה הגדולה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-173">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="2b5bd-174">AU: אוסטרליה, AU, חבר העמים של אוסטרליה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-174">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="2b5bd-175">FR: צרפת, הרפובליקה הצרפתית</span><span class="sxs-lookup"><span data-stu-id="2b5bd-175">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="2b5bd-176">DE: גרמניה, גרמניה, Deutschland, Allemagne, DE, הרפובליקה הפדרלית של גרמניה, הרפובליקה של גרמניה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-176">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="2b5bd-177">סקירת ההעשרה ומתן שם להעשרה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-177">Review and name the enrichment</span></span>

<span data-ttu-id="2b5bd-178">לבסוף, אתה יכול לסקור את המידע ולספק שם עבור ההעשרה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-178">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="סקירת תחומי עניין ודף מתן שמות.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="2b5bd-180">רענן העשרה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-180">Refresh enrichment</span></span>

<span data-ttu-id="2b5bd-181">הפעל את ההעשרה לאחר קביעת התצורה של מותגים, תחומי עניין ומיפוי השדות עבור דמוגרפיה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-181">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="2b5bd-182">כדי להתחיל בתהליך, בחר **הפעל** בדף התצורה של המותג או תחום העניין.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-182">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="2b5bd-183">בנוסף, אתה יכול לאפשר למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מרענון מתוזמן.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-183">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="2b5bd-184">בהתאם לגודל נתוני הלקוחות שלך, ייתכן שיידרשו מספר דקות עד להשלמת הפעלת העשרה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-184">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="2b5bd-185">קיימים [שישה סוגים של מצבים](system.md#status-types) עבור משימות/תהליכים.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-185">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="2b5bd-186">בנוסף, רוב התהליכים [תלויים בתהליכים אחרים במורד הזרם](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="2b5bd-186">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="2b5bd-187">באפשרותך לבחור את מצב התהליך כדי לראות פרטים על ההתקדמות של המשימה השלמה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-187">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="2b5bd-188">לאחר בחירה באפשרות **ראה פרטים** עבור אחת מהמשימות תמצא מידע נוסף: זמן העיבוד, תאריך העיבוד האחרון וכל השגיאות והאזהרות הקשורות למשימה.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-188">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="2b5bd-189">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="2b5bd-189">Enrichment results</span></span>

<span data-ttu-id="2b5bd-190">לאחר הפעלת תהליך ההעשרה, עבור אל **ההעשרות שלי** כדי לסקור את המספר הכולל של לקוחות מועשרים ופירוט של מותגים ותחומי עניין בפרופילי הלקוחות המועשרים.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-190">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="תצוגה מקדימה של תוצאות לאחר הפעלת תהליך העשרה":::

<span data-ttu-id="2b5bd-192">סקור את הנתונים המועשרים על-ידי בחירת **הצג נתונים מועשרים** בתרשים.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-192">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="2b5bd-193">נתונים מועשרים עבור מותגים מגיעים לישות **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-193">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="2b5bd-194">נתונים עבור תחומי עניין נמצאים בישות **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-194">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="2b5bd-195">תוכל למצוא ישויות אלה שרשומות בקבוצה **העשרה** גם ב- **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-195">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="2b5bd-196">ראה נתוני העשרה בכרטיס הלקוח</span><span class="sxs-lookup"><span data-stu-id="2b5bd-196">See enrichment data on the customer card</span></span>

<span data-ttu-id="2b5bd-197">ניתן להציג קשרי מותגים ותחומי עניין גם בכרטיסי לקוח פרטיים.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-197">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="2b5bd-198">עבור אל **לקוחות** ובחר פרופיל לקוח.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-198">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="2b5bd-199">בכרטיס הלקוח תמצא תרשימים עבור המותגים או תחומי העניין שלאנשים בפרופיל הדמוגרפי של אותו לקוח יש זיקה אליהם.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-199">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="כרטיס לקוח עם נתונים מועשרים":::

## <a name="next-steps"></a><span data-ttu-id="2b5bd-201">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="2b5bd-201">Next steps</span></span>

<span data-ttu-id="2b5bd-202">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-202">Build on top of your enriched customer data.</span></span> <span data-ttu-id="2b5bd-203">צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="2b5bd-203">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
