---
title: ייצוא נתוני Customer Insights אל LinkedIn Ads
description: למד כיצד להגדיר את החיבור ולייצא אל LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124497"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="6c509-103">ייצוא פלחים אל LinkedIn Ads ‏(Preview)</span><span class="sxs-lookup"><span data-stu-id="6c509-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="6c509-104">ייצא פלחים של פרופילי לקוחות מאוחדים אל LinkedIn Ads כדי ליצור קהלים תואמים.</span><span class="sxs-lookup"><span data-stu-id="6c509-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="6c509-105">השתמש בקהלים תואמים ל- Company Targeting ול- Contact Targeting.</span><span class="sxs-lookup"><span data-stu-id="6c509-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6c509-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="6c509-106">Prerequisites</span></span>

-   <span data-ttu-id="6c509-107">יש לך [חשבון LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="6c509-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6c509-108">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="6c509-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6c509-109">פרופילי לקוח בפלחים המיוצאים מכילים שדה עם כתובת דואר אלקטרוני.</span><span class="sxs-lookup"><span data-stu-id="6c509-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6c509-110">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="6c509-110">Known limitations</span></span>

- <span data-ttu-id="6c509-111">באפשרותך לייצא עד 100,000 פרופילים לכל ייצוא אל LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="6c509-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="6c509-112">הייצוא אל LinkedIn Ads מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="6c509-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="6c509-113">ייצוא של עד 100,000 פרופילים אל LinkedIn Ads יכול להימשך עד 10 דקות.</span><span class="sxs-lookup"><span data-stu-id="6c509-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="6c509-114">הגדרת החיבור אל LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="6c509-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="6c509-115">בתובנות קהלים, עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="6c509-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6c509-116">בחר **הוסף חיבור** ובחר **LinkedIn Ads** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="6c509-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="6c509-117">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="6c509-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6c509-118">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="6c509-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6c509-119">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="6c509-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6c509-120">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="6c509-120">Choose who can use this connection.</span></span> <span data-ttu-id="6c509-121">אם לא תנקוט שום פעולה, ברירת המחדל היא מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="6c509-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="6c509-122">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6c509-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6c509-123">ספק את [מזהה החשבון של LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="6c509-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="6c509-124">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="6c509-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6c509-125">בחר **התחבר** כדי לאתחל את החיבור ל- Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="6c509-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="6c509-126">בחר **בצע אימות באמצעות LinkedIn** וספק את אישורי מנהל המערכת שלך עבור LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="6c509-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="6c509-127">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="6c509-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6c509-128">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="6c509-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6c509-129">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="6c509-129">Configure an export</span></span>

<span data-ttu-id="6c509-130">באפשרותך לקבוע תצורה של ייצוא אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="6c509-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="6c509-131">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6c509-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6c509-132">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="6c509-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6c509-133">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="6c509-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6c509-134">בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="6c509-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="6c509-135">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="6c509-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6c509-136">בחר אם ברצונך לייצא נתונים לשימוש ב- [Contact Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) או ב- [Company Targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) ב- LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="6c509-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="6c509-137">במקטע **התאמת נתונים**, בחר את השדה בפרופיל הלקוח המאוחד שמייצג את כתובת הדואר האלקטרוני של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="6c509-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6c509-138">יש לייצא פלחים אל LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="6c509-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="6c509-139">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="6c509-139">Select the segments you want to export.</span></span> <span data-ttu-id="6c509-140">הקהלים התואמים ב- LinkedIn Campaign Manager ייווצרו באופן אוטומטי עם שם הפלחים שבחרת לייצא.</span><span class="sxs-lookup"><span data-stu-id="6c509-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="6c509-141">לכל מקטע ייווצר קהל תואם נפרד.</span><span class="sxs-lookup"><span data-stu-id="6c509-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="6c509-142">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="6c509-142">Select **Save**.</span></span>

<span data-ttu-id="6c509-143">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="6c509-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6c509-144">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6c509-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6c509-145">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6c509-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6c509-146">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="6c509-146">Data privacy and compliance</span></span>

<span data-ttu-id="6c509-147">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל LinkedIn Ads, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="6c509-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6c509-148">Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- LinkedIn Ads עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="6c509-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6c509-149">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6c509-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="6c509-150">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="6c509-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
