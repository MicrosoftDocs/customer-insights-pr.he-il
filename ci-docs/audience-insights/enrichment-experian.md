---
title: העשרה באמצעות Experian להעשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896374"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="9cd23-103">העשר פרופילי לקוחות בדמוגרפיה של Experian ‏(Preview)</span><span class="sxs-lookup"><span data-stu-id="9cd23-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="9cd23-104">Experian הינה מובילה עולמית בתחום שירותי דיווח ושיווק אשראי צרכני ועסקי.</span><span class="sxs-lookup"><span data-stu-id="9cd23-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="9cd23-105">באמצעות שירותי העשרת הנתונים של Experian, תוכל לגבש הבנה מעמיקה יותר של לקוחותיך על ידי העשרת פרופילי הלקוחות בנתונים דמוגרפיים כגון גודל משק הבית, הכנסה ועוד.</span><span class="sxs-lookup"><span data-stu-id="9cd23-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9cd23-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="9cd23-106">Prerequisites</span></span>

<span data-ttu-id="9cd23-107">לקביעת התצורה של Experian, יש לעמוד בדרישות המקדימות הבאות:</span><span class="sxs-lookup"><span data-stu-id="9cd23-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9cd23-108">יש לך מנוי פעיל ל-Experian.</span><span class="sxs-lookup"><span data-stu-id="9cd23-108">You have an active Experian subscription.</span></span> <span data-ttu-id="9cd23-109">כדי לקבל מנוי, [צור קשר עם Experian](https://www.experian.com/marketing-services/contact) בצורה ישירה.</span><span class="sxs-lookup"><span data-stu-id="9cd23-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="9cd23-110">[למידע נוסף על העשרת נתונים של Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="9cd23-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="9cd23-111">חיבור Experian כבר הוגדר על-ידי מנהל מערכת *או* שיש לך הרשאות [מנהל מערכת](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="9cd23-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="9cd23-112">אתה זקוק גם למזהה המשתמש, מזהה הצד ומספר הדגם עבור חשבון Secure Transport‏ (ST) המופעל על-ידי SSH שיצרה Experian עבורך.</span><span class="sxs-lookup"><span data-stu-id="9cd23-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="9cd23-113">קביעת תצורת ההעשרה</span><span class="sxs-lookup"><span data-stu-id="9cd23-113">Configure the enrichment</span></span>

1. <span data-ttu-id="9cd23-114">עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.</span><span class="sxs-lookup"><span data-stu-id="9cd23-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="9cd23-115">בחר **העשיר את הנתונים שלי** על אריח Experian.</span><span class="sxs-lookup"><span data-stu-id="9cd23-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9cd23-116">![אריח Experian](media/experian-tile.png "אריח Experian")</span><span class="sxs-lookup"><span data-stu-id="9cd23-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="9cd23-117">‏‏בחר [חיבור](connections.md) מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="9cd23-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="9cd23-118">צור קשר עם מנהל מערכת אם אין חיבור זמין.</span><span class="sxs-lookup"><span data-stu-id="9cd23-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="9cd23-119">אם אתה מנהל מערכת, באפשרותך ליצור חיבור על-ידי בחירת **הוסף חיבור** ובחירת Experian מתוך התפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="9cd23-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="9cd23-120">בחר **התחבר ל- Experian** כדי לאשר את בחירת החיבור.</span><span class="sxs-lookup"><span data-stu-id="9cd23-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="9cd23-121">בחר **הבא** ובחר את **ערכת הנתונים של הלקוח** שברצונך להעשיר בנתונים דמוגרפיים מתוך Experian.</span><span class="sxs-lookup"><span data-stu-id="9cd23-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="9cd23-122">באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.</span><span class="sxs-lookup"><span data-stu-id="9cd23-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. <span data-ttu-id="9cd23-124">בחר **הבא** והגדר איזה סוג של שדות מתוך הפרופילים המאוחדים שלך צריך לשמש כדי לחפש נתונים דמוגרפיים תואמים מ- Experian.</span><span class="sxs-lookup"><span data-stu-id="9cd23-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="9cd23-125">לפחות אחד מהשדות **שם וכתובת**, **טלפון** או **דואר** נדרש.</span><span class="sxs-lookup"><span data-stu-id="9cd23-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="9cd23-126">לקבלת דיוק התאמה גבוה יותר, ניתן להוסיף עד שני שדות אחרים.</span><span class="sxs-lookup"><span data-stu-id="9cd23-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="9cd23-127">בחירה זו תשפיע על שדות המיפוי שאליהם יש לך גישה בשלב הבא.</span><span class="sxs-lookup"><span data-stu-id="9cd23-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="9cd23-128">ככל שישלחו יותר תכונות מזהה מפתח ל-Experian כך גדל הסיכוי לשיעור התאמה גבוה יותר.</span><span class="sxs-lookup"><span data-stu-id="9cd23-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="9cd23-129">בחר **הבא** כדי להפעיל את מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="9cd23-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="9cd23-130">הגדר אילו שדות מהפרופילים המאוחדים שלך צריכים לשמש כדי לחפש נתונים דמוגרפיים תואמים מ- Experian.</span><span class="sxs-lookup"><span data-stu-id="9cd23-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="9cd23-131">השדות הנדרשים מסומנים.</span><span class="sxs-lookup"><span data-stu-id="9cd23-131">Required fields are marked.</span></span>

1. <span data-ttu-id="9cd23-132">ספק שם עבור ההעשרה ושם עבור ישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="9cd23-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="9cd23-133">בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.</span><span class="sxs-lookup"><span data-stu-id="9cd23-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="9cd23-134">קביעת תצורת החיבור עבור Experian</span><span class="sxs-lookup"><span data-stu-id="9cd23-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="9cd23-135">עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים.</span><span class="sxs-lookup"><span data-stu-id="9cd23-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="9cd23-136">בחר **הוסף חיבור** בעת קביעת תצורת העשרה *או* עבור אל **ניהול** > **חיבורים** ובחר **הגדר** באריח Experian.</span><span class="sxs-lookup"><span data-stu-id="9cd23-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="9cd23-137">בחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="9cd23-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="9cd23-138">הזן שם עבור החיבור בתיבה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="9cd23-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="9cd23-139">הזן מזהה משתמש, מזהה צד ומספר דגם חוקיים עבור חשבון Experian Secure Transport שלך.</span><span class="sxs-lookup"><span data-stu-id="9cd23-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="9cd23-140">סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**</span><span class="sxs-lookup"><span data-stu-id="9cd23-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="9cd23-141">בחר **אימות** כדי לאמת את התצורה.</span><span class="sxs-lookup"><span data-stu-id="9cd23-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="9cd23-142">לאחר השלמת האימות, בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="9cd23-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="חלונית תצורת החיבור של Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="9cd23-144">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="9cd23-144">Enrichment results</span></span>

<span data-ttu-id="9cd23-145">כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="9cd23-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="9cd23-146">ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9cd23-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9cd23-147">זמן העיבוד יהיה תלוי בגודל נתוני הלקוחות שלך ובתהליכי העשרה שהגדרו עבור חשבונך על ידי Experian.</span><span class="sxs-lookup"><span data-stu-id="9cd23-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="9cd23-148">לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**.</span><span class="sxs-lookup"><span data-stu-id="9cd23-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="9cd23-149">בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="9cd23-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="9cd23-150">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="9cd23-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9cd23-151">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="9cd23-151">Next steps</span></span>

<span data-ttu-id="9cd23-152">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="9cd23-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="9cd23-153">צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="9cd23-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9cd23-154">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="9cd23-154">Data privacy and compliance</span></span>

<span data-ttu-id="9cd23-155">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Experian, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="9cd23-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9cd23-156">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Experian עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="9cd23-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="9cd23-157">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9cd23-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9cd23-158">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="9cd23-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
