---
title: העשרה באמצעות Experian העשרה של צד שלישי
description: מידע כללי על העשרת צד שלישי של Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309821"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="be340-103">העשר פרופילי לקוחות באמצעות נתונים דמוגרפיים מ- Experian ‏(Preview)</span><span class="sxs-lookup"><span data-stu-id="be340-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="be340-104">Experian הינה מובילה עולמית בתחום שירותי דיווח ושיווק של אשראי צרכני ועסקי.</span><span class="sxs-lookup"><span data-stu-id="be340-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="be340-105">באמצעות שירותי העשרת הנתונים של Experian, תוכל לבנות הבנה עמוקה יותר של הלקוחות שלך על-ידי העשרת פרופילי הלקוחות בנתונים דמוגרפיים כמו גודל משק בית, הכנסה ועוד.</span><span class="sxs-lookup"><span data-stu-id="be340-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="be340-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="be340-106">Prerequisites</span></span>

<span data-ttu-id="be340-107">כדי לקבוע את תצורת Experian, יש לקיים את הדרישות המוקדמות הבאות:</span><span class="sxs-lookup"><span data-stu-id="be340-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="be340-108">צריך להיות לך מינוי Experian פעיל.</span><span class="sxs-lookup"><span data-stu-id="be340-108">You have an active Experian subscription.</span></span> <span data-ttu-id="be340-109">כדי לקבל מינוי, [פנה ישירות ל- Experian](https://www.experian.com/marketing-services/contact).</span><span class="sxs-lookup"><span data-stu-id="be340-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="be340-110">[קבל מידע נוסף על Experian העשרת נתונים](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="be340-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="be340-111">חיבור Experian כבר הוגדר על-ידי מנהל מערכת *או* שיש לך הרשאות [מנהל מערכת](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="be340-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="be340-112">אתה צריך גם מזהה משתמש, מזהה צד ומספר מודל עבור חשבון Secure Transport‏ (ST) התומך ב- SSH ש- Experian יצרה עבורך.</span><span class="sxs-lookup"><span data-stu-id="be340-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="be340-113">מדינות/אזורים נתמכים</span><span class="sxs-lookup"><span data-stu-id="be340-113">Supported countries/regions</span></span>

<span data-ttu-id="be340-114">נכון לעכשיו אנחנו תומכים בהעשרת פרופילי לקוחות בארצות הברית בלבד.</span><span class="sxs-lookup"><span data-stu-id="be340-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="be340-115">קביעת תצורת ההעשרה</span><span class="sxs-lookup"><span data-stu-id="be340-115">Configure the enrichment</span></span>

1. <span data-ttu-id="be340-116">עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.</span><span class="sxs-lookup"><span data-stu-id="be340-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="be340-117">בחר **העשר את הנתונים שלי** באריח Experian.</span><span class="sxs-lookup"><span data-stu-id="be340-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="be340-118">![Experianאחרי](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="be340-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="be340-119">בחר [חיבור](connections.md) מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="be340-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="be340-120">צור קשר עם מנהל מערכת אם אין חיבור זמין.</span><span class="sxs-lookup"><span data-stu-id="be340-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="be340-121">אם אתה מנהל מערכת, אתה יכול ליצור חיבור על ידי בחירת **הוסף חיבור** ובחירת Experian מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="be340-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="be340-122">בחר **התחבר ל- Experian** כדי לאשר את בחירת החיבור.</span><span class="sxs-lookup"><span data-stu-id="be340-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="be340-123">בחר **הבא** ובחר את **ערכת נתוני הלקוח** שברצונך להעשיר בנתונים דמוגרפיים מ- Experian.</span><span class="sxs-lookup"><span data-stu-id="be340-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="be340-124">באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.</span><span class="sxs-lookup"><span data-stu-id="be340-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. <span data-ttu-id="be340-126">בחר **הבא** והגדר באיזה סוג של שדות מהפרופילים המאוחדים שלך יש להשתמש לצורך חיפוש נתונים דמוגרפיים מתאימים מ- Experian.</span><span class="sxs-lookup"><span data-stu-id="be340-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="be340-127">לפחות אחד מהשדות **שם וכתובת**, **טלפון** או **דואר** נדרש.</span><span class="sxs-lookup"><span data-stu-id="be340-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="be340-128">לקבלת דיוק התאמה גבוה יותר, ניתן להוסיף עד שני שדות אחרים.</span><span class="sxs-lookup"><span data-stu-id="be340-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="be340-129">בחירה זו תשפיע על שדות המיפוי שאליהם יש לך גישה בשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="be340-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="be340-130">תכונות מזהות רבות יותר הנשלחות ל- Experian יניבו, ככל הנראה, שיעור התאמה גבוה יותר.</span><span class="sxs-lookup"><span data-stu-id="be340-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="be340-131">בחר **הבא** כדי להפעיל את מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="be340-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="be340-132">הגדר באיזה סוג של שדות מהפרופילים המאוחדים שלך יש להשתמש לצורך חיפוש נתונים דמוגרפיים מתאימים מ- Experian.</span><span class="sxs-lookup"><span data-stu-id="be340-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="be340-133">השדות הנדרשים מסומנים.</span><span class="sxs-lookup"><span data-stu-id="be340-133">Required fields are marked.</span></span>

1. <span data-ttu-id="be340-134">ספק שם עבור ההעשרה ושם עבור ישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="be340-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="be340-135">בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.</span><span class="sxs-lookup"><span data-stu-id="be340-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="be340-136">קבע את תצורת החיבור של Experian</span><span class="sxs-lookup"><span data-stu-id="be340-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="be340-137">עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים.</span><span class="sxs-lookup"><span data-stu-id="be340-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="be340-138">בחר **הוסף חיבור** בעת הגדרת העשרה *או* עבור אל **מנהל מערכת** > **חיבורים** ובחר **הגדר** באריח Experian.</span><span class="sxs-lookup"><span data-stu-id="be340-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="be340-139">בחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="be340-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="be340-140">הזן שם עבור החיבור בתיבה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="be340-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="be340-141">הזן מזהה משתמש, מזהה צד ומספר מודל חוקיים עבור חשבון Experian Secure Transport שלך.</span><span class="sxs-lookup"><span data-stu-id="be340-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="be340-142">סקור את **פרטיות ותאימות נתונים** ותן את הסכמתך על-ידי בחירת **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="be340-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="be340-143">בחר **אימות** כדי לאמת את התצורה.</span><span class="sxs-lookup"><span data-stu-id="be340-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="be340-144">לאחר השלמת האימות, בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="be340-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian חלונית תצורת החיבור.":::

## <a name="enrichment-results"></a><span data-ttu-id="be340-146">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="be340-146">Enrichment results</span></span>

<span data-ttu-id="be340-147">כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="be340-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="be340-148">ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="be340-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="be340-149">זמן העיבוד יהיה תלוי בגודל נתוני הלקוחות ובתהליכי ההעשרה שהוגדרו עבור חשבונך על-ידי Experian.</span><span class="sxs-lookup"><span data-stu-id="be340-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="be340-150">לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**.</span><span class="sxs-lookup"><span data-stu-id="be340-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="be340-151">בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="be340-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="be340-152">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="be340-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="be340-153">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="be340-153">Next steps</span></span>

<span data-ttu-id="be340-154">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="be340-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="be340-155">צור [פלחים](segments.md) ו[מדידות](measures.md), ואפילו [יצא את הנתונים](export-destinations.md) כדי להעניק ללקוחות שלך חוויות מותאמות אישית.</span><span class="sxs-lookup"><span data-stu-id="be340-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="be340-156">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="be340-156">Data privacy and compliance</span></span>

<span data-ttu-id="be340-157">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים ל- Experian, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעלולים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="be340-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="be340-158">Microsoft תעביר נתונים כאלה בהוראתך, אבל אתה אחראי להבטיח ש- Experian עומדת בכל התחייבויות הפרטיות והאבטחה שלך.</span><span class="sxs-lookup"><span data-stu-id="be340-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="be340-159">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="be340-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="be340-160">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="be340-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
