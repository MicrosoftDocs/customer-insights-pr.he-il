---
title: העשרה באמצעות Experian להעשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות Experian.
ms.date: 09/17/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 60fc49734e54740e83b47a7028be216a0eb81e49
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668813"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="aefc1-103">העשר פרופילי לקוחות בדמוגרפיה של Experian ‏(Preview)</span><span class="sxs-lookup"><span data-stu-id="aefc1-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="aefc1-104">Experian הינה מובילה עולמית בתחום שירותי דיווח ושיווק אשראי צרכני ועסקי.</span><span class="sxs-lookup"><span data-stu-id="aefc1-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="aefc1-105">באמצעות שירותי העשרת הנתונים של Experian, תוכל לגבש הבנה מעמיקה יותר של לקוחותיך על ידי העשרת פרופילי הלקוחות בנתונים דמוגרפיים כגון גודל משק הבית, הכנסה ועוד.</span><span class="sxs-lookup"><span data-stu-id="aefc1-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="aefc1-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="aefc1-106">Prerequisites</span></span>

<span data-ttu-id="aefc1-107">לקביעת התצורה של Experian, יש לעמוד בדרישות המקדימות הבאות:</span><span class="sxs-lookup"><span data-stu-id="aefc1-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="aefc1-108">יש לך מנוי פעיל ל-Experian.</span><span class="sxs-lookup"><span data-stu-id="aefc1-108">You have an active Experian subscription.</span></span> <span data-ttu-id="aefc1-109">כדי לקבל מנוי, [צור קשר עם Experian](https://www.experian.com/marketing-services/contact) בצורה ישירה.</span><span class="sxs-lookup"><span data-stu-id="aefc1-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="aefc1-110">[למידע נוסף על העשרת נתונים של Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="aefc1-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="aefc1-111">יש לך את מזהה משתמש, מזהה צד ומספר דגם עבור חשבון התעבורה המאובטחת (ST) התומך SSH שלך שיצר עבורך Experian.</span><span class="sxs-lookup"><span data-stu-id="aefc1-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="aefc1-112">יש לך הרשאות [מנהל מערכת](permissions.md#administrator) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="aefc1-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="aefc1-113">תצורה</span><span class="sxs-lookup"><span data-stu-id="aefc1-113">Configuration</span></span>

1. <span data-ttu-id="aefc1-114">עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.</span><span class="sxs-lookup"><span data-stu-id="aefc1-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="aefc1-115">בחר **העשיר את הנתונים שלי** על אריח Experian.</span><span class="sxs-lookup"><span data-stu-id="aefc1-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aefc1-116">![אריח Experian](media/experian-tile.png "אריח Experian")</span><span class="sxs-lookup"><span data-stu-id="aefc1-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="aefc1-117">בחר באפשרות **תחילת העבודה** והזן את מזהה המשתמש, מזהה הצד ומספר הדגם עבור חשבון התעבורה המאובטחת שלך.</span><span class="sxs-lookup"><span data-stu-id="aefc1-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="aefc1-118">סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="aefc1-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="aefc1-119">לאישור כל יחידות הקלט על ידי בחר **הגש**.</span><span class="sxs-lookup"><span data-stu-id="aefc1-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="aefc1-120">מיפוי השדות שלך</span><span class="sxs-lookup"><span data-stu-id="aefc1-120">Map your fields</span></span>

1. <span data-ttu-id="aefc1-121">בחר **הוסף נתונים** ובחר את מזהי המפתח שלך מ **שם וכתובת**, **דואר**, או **טלפון** לשלוח ל-Experian לרזולוצית זהות.</span><span class="sxs-lookup"><span data-stu-id="aefc1-121">Select **Add data** and choose your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="aefc1-122">ככל שישלחו יותר תכונות מזהה מפתח ל-Experian כך גדל הסיכוי לשיעור התאמה גבוה יותר.</span><span class="sxs-lookup"><span data-stu-id="aefc1-122">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="aefc1-123">בחר באפשרות **הבא** ומפה את התכונות התואמות מישות הלקוחות המאוחד שלך עבור שדות מזהה המפתח שנבחרו.</span><span class="sxs-lookup"><span data-stu-id="aefc1-123">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="aefc1-124">בחר **הוסף תכונה** כדי למפות תכונות נוספות שברצונך לשלוח ל-Experian.</span><span class="sxs-lookup"><span data-stu-id="aefc1-124">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="aefc1-125">בחר **שמור** כדי להשלים את מיפוי השדות.</span><span class="sxs-lookup"><span data-stu-id="aefc1-125">Select **Save** to complete the field mapping.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="aefc1-126">![מיפוי שדות של Experian](media/experian-field-mapping.png "מיפוי שדות של Experian")</span><span class="sxs-lookup"><span data-stu-id="aefc1-126">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="aefc1-127">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="aefc1-127">Enrichment results</span></span>

<span data-ttu-id="aefc1-128">כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="aefc1-128">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="aefc1-129">ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="aefc1-129">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="aefc1-130">זמן העיבוד יהיה תלוי בגודל נתוני הלקוחות שלך ובתהליכי העשרה שהגדרו עבור חשבונך על ידי Experian.</span><span class="sxs-lookup"><span data-stu-id="aefc1-130">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="aefc1-131">לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**.</span><span class="sxs-lookup"><span data-stu-id="aefc1-131">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="aefc1-132">בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="aefc1-132">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="aefc1-133">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="aefc1-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="aefc1-134">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="aefc1-134">Next steps</span></span>

<span data-ttu-id="aefc1-135">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="aefc1-135">Build on top of your enriched customer data.</span></span> <span data-ttu-id="aefc1-136">צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="aefc1-136">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="aefc1-137">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="aefc1-137">Data privacy and compliance</span></span>

<span data-ttu-id="aefc1-138">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Experian, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="aefc1-138">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="aefc1-139">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Experian עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="aefc1-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="aefc1-140">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="aefc1-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="aefc1-141">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="aefc1-141">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>
