---
title: העשרת שיפור כתובות
description: העשר ונרמל מידע על כתובות שמופיעות בפרופילי לקוחות באמצעות מודלים של Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305433"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="42625-103">העשרה של פרופילי לקוחות עם כתובות משופרות</span><span class="sxs-lookup"><span data-stu-id="42625-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="42625-104">כתובות בנתונים שלך יכולות להיות לא מובנות, לא שלמות או שגויות.</span><span class="sxs-lookup"><span data-stu-id="42625-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="42625-105">השתמש במודלים של Microsoft כדי לנרמל ולהעשיר את הכתובות שלך ב[תבנית Common Data Model](/common-data-model/schema/core/applicationcommon/address) ליתר דיוק ולהשגת תובנות טובות יותר.</span><span class="sxs-lookup"><span data-stu-id="42625-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="42625-106">כיצד אנו משפרים כתובות</span><span class="sxs-lookup"><span data-stu-id="42625-106">How we enhance addresses</span></span>

<span data-ttu-id="42625-107">המודל שלנו מבצע תהליך דו-שלבי לשיפור כתובת.</span><span class="sxs-lookup"><span data-stu-id="42625-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="42625-108">תחילה, הוא מנתח את הכתובת לזיהוי הרכיבים שלה ומציב אותם בתבנית מובנית.</span><span class="sxs-lookup"><span data-stu-id="42625-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="42625-109">לאחר מכן אנו משתמשים ב- AI כדי לתקן, להשלים ולתקנן את הערכים בכתובת.</span><span class="sxs-lookup"><span data-stu-id="42625-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="42625-110">דוגמה</span><span class="sxs-lookup"><span data-stu-id="42625-110">Example</span></span>

<span data-ttu-id="42625-111">פרטי הכתובת עשויים להיות בפורמט שאינו רגיל ולהכיל שגיאות כתיב.</span><span class="sxs-lookup"><span data-stu-id="42625-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="42625-112">המודל יכול לפתור את הבעיות הללו וליצור כתובות עקביות בפרופילי לקוחות מאוחדים.</span><span class="sxs-lookup"><span data-stu-id="42625-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="42625-113">מגבלות</span><span class="sxs-lookup"><span data-stu-id="42625-113">Limitations</span></span>

<span data-ttu-id="42625-114">כתובות משופרות פועלות רק עם הערכים שכבר קיימים בנתוני הכתובת שעובדה.</span><span class="sxs-lookup"><span data-stu-id="42625-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="42625-115">המודל אינו:</span><span class="sxs-lookup"><span data-stu-id="42625-115">The model doesn't:</span></span> 

1. <span data-ttu-id="42625-116">מאמת אם הכתובת היא כתובת חוקית.</span><span class="sxs-lookup"><span data-stu-id="42625-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="42625-117">מאמת אם אחד הערכים, כגון ערכי מיקוד או שמות של רחובות, הנו חוקי.</span><span class="sxs-lookup"><span data-stu-id="42625-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="42625-118">משנה ערכים שהוא אינו מזהה.</span><span class="sxs-lookup"><span data-stu-id="42625-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="42625-119">המודל משתמש בטכניקות מבוססות למידת מכונה כדי לשפר כתובות.</span><span class="sxs-lookup"><span data-stu-id="42625-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="42625-120">עם זאת שאנחנו מחילים רף מהימנות גבוה למועד שבו המודל ישנה ערך של קלט, כמו בכל מודל המבוסס על למידת מכונה, אי אפשר להבטיח דיוק של 100 אחוז.</span><span class="sxs-lookup"><span data-stu-id="42625-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="42625-121">מדינות או אזורים נתמכים</span><span class="sxs-lookup"><span data-stu-id="42625-121">Supported countries or regions</span></span>

<span data-ttu-id="42625-122">אנו תומכים כיום בכתובות מועשרות במדינות או באזורים הבאים:</span><span class="sxs-lookup"><span data-stu-id="42625-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="42625-123">אוסטרליה</span><span class="sxs-lookup"><span data-stu-id="42625-123">Australia</span></span>
- <span data-ttu-id="42625-124">קנדה</span><span class="sxs-lookup"><span data-stu-id="42625-124">Canada</span></span>
- <span data-ttu-id="42625-125">בריטניה</span><span class="sxs-lookup"><span data-stu-id="42625-125">United Kingdom</span></span>
- <span data-ttu-id="42625-126">ארצות הברית</span><span class="sxs-lookup"><span data-stu-id="42625-126">United States</span></span>

<span data-ttu-id="42625-127">הכתובות חייבות להכיל ערך מדינה/אזור.</span><span class="sxs-lookup"><span data-stu-id="42625-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="42625-128">אנו לא מעבדים כתובות עבור מדינות או אזורים שאינם נתמכים ועבור כתובות שאינן כוללות מדינה או אזור.</span><span class="sxs-lookup"><span data-stu-id="42625-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="42625-129">קביעת תצורת ההעשרה</span><span class="sxs-lookup"><span data-stu-id="42625-129">Configure the enrichment</span></span>

1. <span data-ttu-id="42625-130">עבור אל **נתונים** > **העשרה**.</span><span class="sxs-lookup"><span data-stu-id="42625-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="42625-131">בחר **העשר את הנתונים שלי‬** באריח **‏‫כתובות משופרות**.</span><span class="sxs-lookup"><span data-stu-id="42625-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="צילום מסך של האריח 'כתובות משופרות'.":::

1. <span data-ttu-id="42625-133">בחר **ערכת הנתונים של הלקוח** ובחר את הישות המכילה את הכתובות שברצונך להעשיר.</span><span class="sxs-lookup"><span data-stu-id="42625-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="42625-134">ניתן לבחור בישות *לקוח* להעשרת כתובות בכל פרופילי הלקוחות או לבחור ישות פלח שוק להעשרת כתובות רק בפרופילי לקוחות הכלולים בפלח זה.</span><span class="sxs-lookup"><span data-stu-id="42625-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="42625-135">בחר את התבנית של הכתובות בערכת הנתונים שלך.</span><span class="sxs-lookup"><span data-stu-id="42625-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="42625-136">בחר **כתובת בעלת תכונה יחידה** אם הכתובות בנתונים שלך משתמשות בשדה יחיד.</span><span class="sxs-lookup"><span data-stu-id="42625-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="42625-137">בחר **כתובת בעלת תכונות מרובות** אם הכתובות בנתונים שלך משתמשות ביותר משדה נתונים אחד.</span><span class="sxs-lookup"><span data-stu-id="42625-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="42625-138">מדינה / אזור נדרשים הן בכתובת בעלת תכונה יחידה והן בכתובת מרובת תכונות.</span><span class="sxs-lookup"><span data-stu-id="42625-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="42625-139">לא תתבצע העשרה של כתובות שאינן מכילות ערכים חוקיים או נתמכים של מדינה/אזור.</span><span class="sxs-lookup"><span data-stu-id="42625-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="42625-140">מפה את שדות הכתובת מישות הלקוח המאוחדת שלך.</span><span class="sxs-lookup"><span data-stu-id="42625-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="דף מיפוי שדה של כתובת משופרת.":::

1. <span data-ttu-id="42625-142">בחר **הבא** כדי להשלים את מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="42625-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="42625-143">ספק שם עבור ההעשרה ועבור ישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="42625-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="42625-144">בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.</span><span class="sxs-lookup"><span data-stu-id="42625-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="42625-145">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="42625-145">Enrichment results</span></span>

<span data-ttu-id="42625-146">כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="42625-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="42625-147">ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="42625-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="42625-148">זמן העיבוד תלוי בגודל נתוני הלקוח שלך.</span><span class="sxs-lookup"><span data-stu-id="42625-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="42625-149">לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**.</span><span class="sxs-lookup"><span data-stu-id="42625-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="42625-150">בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="42625-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="42625-151">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="42625-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="42625-152">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="42625-152">Next steps</span></span>

<span data-ttu-id="42625-153">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="42625-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="42625-154">צור [פלחים](segments.md) ו[מדידות](measures.md), ואפילו [יצא את הנתונים](export-destinations.md) כדי להעניק ללקוחות שלך חוויות מותאמות אישית.</span><span class="sxs-lookup"><span data-stu-id="42625-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
