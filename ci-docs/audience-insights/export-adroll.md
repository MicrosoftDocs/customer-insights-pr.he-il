---
title: ייצוא נתוני Customer Insights אל AdRoll
description: למד כיצד לקבוע את תצורת החיבור אל AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697075"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="d2ee4-103">מחבר עבור AdRoll‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="d2ee4-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="d2ee4-104">יצא פלחים של פרופילי לקוח מאוחדים אל AdRoll והשתמש בהם עבור פרסום.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="d2ee4-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="d2ee4-105">Prerequisites</span></span>

-   <span data-ttu-id="d2ee4-106">יש לך [חשבון AdRoll](https://www.adroll.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d2ee4-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d2ee4-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="d2ee4-109">התחבר ל- AdRoll</span><span class="sxs-lookup"><span data-stu-id="d2ee4-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="d2ee4-110">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d2ee4-111">תחת **AdRoll**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="d2ee4-112">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="חלונית תצורה עבור חיבור AdRoll.":::

1. <span data-ttu-id="d2ee4-114">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d2ee4-115">בחר **התחבר** כדי לאתחל את החיבור אל AdRoll.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="d2ee4-116">בחר **בצע אימות באמצעות AdRoll** וספק את אישורי מנהל המערכת שלך עבור AdRoll.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="d2ee4-117">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d2ee4-118">הזן את **מזהה מפרסם AdRoll** [פריט ניתן לפרסום של AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="d2ee4-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="d2ee4-119">בחר **הבא** להגדרת התצורה של הייצוא.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="d2ee4-120">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="d2ee4-120">Configure the connector</span></span>

1. <span data-ttu-id="d2ee4-121">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d2ee4-122">ייצוא פלחים אל AdRoll הוא הכרחי.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="d2ee4-123">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-123">Select the segments you want to export.</span></span> <span data-ttu-id="d2ee4-124">בחר פלח עם 100 חברים לפחות.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="d2ee4-125">אין באפשרותך לייצא פלחים קטנים יותר.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-125">You can't export smaller segments.</span></span> <span data-ttu-id="d2ee4-126">בנוסף, הגודל המרבי של פלח לייצוא הוא 250,000 חברים לייצוא.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="d2ee4-127">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="d2ee4-128">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="d2ee4-128">Export the data</span></span>

<span data-ttu-id="d2ee4-129">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="d2ee4-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="d2ee4-130">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d2ee4-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d2ee4-131">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="d2ee4-131">Known limitations</span></span>

- <span data-ttu-id="d2ee4-132">באפשרותך לייצא עד 250,000 פרופילים לייצוא אל AdRoll.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="d2ee4-133">אין באפשרותך לייצא פלחים עם פחות מ- 100 פרופילים ל- AdRoll.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="d2ee4-134">הייצוא ל- AdRoll מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="d2ee4-135">ייצוא של עד 250,000 פרופילים ל- AdRoll יכול להימשך עד 10 דקות.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="d2ee4-136">מספר הפרופילים שתוכל לייצא ל- AdRoll תלוי ומוגבל בחוזה שלך עם AdRoll.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d2ee4-137">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="d2ee4-137">Data privacy and compliance</span></span>

<span data-ttu-id="d2ee4-138">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל AdRoll, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d2ee4-139">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- AdRoll עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d2ee4-140">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d2ee4-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d2ee4-141">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="d2ee4-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
