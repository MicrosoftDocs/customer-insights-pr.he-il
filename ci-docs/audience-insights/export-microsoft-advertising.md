---
title: ייצוא נתוני Customer Insights אל Microsoft Advertising
description: למד כיצד להגדיר את החיבור ולייצא אל Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124495"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="97ee9-103">ייצוא פלחים אל Microsoft Advertising‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="97ee9-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="97ee9-104">יצא פלחים של Customer Insights אל ‏Microsoft Advertising כדי ליצור קהלים של Customer Match.</span><span class="sxs-lookup"><span data-stu-id="97ee9-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="97ee9-105">השתמש בקהלים אלה עבור הקמפיינים הפרסומיים שלך.</span><span class="sxs-lookup"><span data-stu-id="97ee9-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="97ee9-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="97ee9-106">Prerequisites</span></span>

-   <span data-ttu-id="97ee9-107">[חשבון Microsoft Advertising](https://ads.microsoft.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="97ee9-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="97ee9-108">אישרת את תנאי השימוש של Customer Match.</span><span class="sxs-lookup"><span data-stu-id="97ee9-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="97ee9-109">[פלחים מוגדרים](segments.md) בתובנות לגבי קהלים.</span><span class="sxs-lookup"><span data-stu-id="97ee9-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="97ee9-110">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה עם כתובת דואר אלקטרוני.</span><span class="sxs-lookup"><span data-stu-id="97ee9-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="97ee9-111">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="97ee9-111">Known limitations</span></span>

- <span data-ttu-id="97ee9-112">באפשרותך לייצא עד 500,000 פרופילים כדי לייצא אל Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="97ee9-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="97ee9-113">הייצוא אל Microsoft Advertising מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="97ee9-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="97ee9-114">ייצוא של עד 500,000 פרופילים ל- Microsoft Advertising יכול להימשך עד 10 דקות.</span><span class="sxs-lookup"><span data-stu-id="97ee9-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="97ee9-115">הגדרת החיבור אל Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="97ee9-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="97ee9-116">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="97ee9-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="97ee9-117">בחר **הוסף חיבור** ובחר **Microsoft Advertising** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="97ee9-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="97ee9-118">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="97ee9-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="97ee9-119">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="97ee9-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="97ee9-120">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="97ee9-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="97ee9-121">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="97ee9-121">Choose who can use this connection.</span></span> <span data-ttu-id="97ee9-122">ברירת המחדל היא מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="97ee9-122">The default is administrators.</span></span> <span data-ttu-id="97ee9-123">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="97ee9-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="97ee9-124">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="97ee9-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="97ee9-125">בחר **התחבר** כדי לאתחל את החיבור אל Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="97ee9-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="97ee9-126">בחר **בצע אימות באמצעות Microsoft Advertising** וספק את אישורי מנהל המערכת שלך עבור Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="97ee9-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="97ee9-127">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="97ee9-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="97ee9-128">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="97ee9-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="97ee9-129">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="97ee9-129">Configure an export</span></span>

<span data-ttu-id="97ee9-130">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="97ee9-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="97ee9-131">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="97ee9-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="97ee9-132">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="97ee9-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="97ee9-133">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="97ee9-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="97ee9-134">בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="97ee9-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="97ee9-135">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="97ee9-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="97ee9-136">בחר פלחים לייצוא.</span><span class="sxs-lookup"><span data-stu-id="97ee9-136">Select the segments to export.</span></span> <span data-ttu-id="97ee9-137">הקהלים של Customer Match ב- Microsoft Advertising נוצרים באופן אוטומטי עם שם הפלחים שנבחרו לייצוא.</span><span class="sxs-lookup"><span data-stu-id="97ee9-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="97ee9-138">לכל מקטע ייווצר קהל נפרד של Customer Match.</span><span class="sxs-lookup"><span data-stu-id="97ee9-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="97ee9-139">הזן את **מזהה הלקוח ומזהה החשבון של Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="97ee9-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="97ee9-140">באפשרותך לאתר את מזהה הלקוח (`cid`) ומזהה החשבון (`aid`) בפרמטרים של כתובת ה- URL כשאתה מחובר ל- Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="97ee9-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="97ee9-141">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח עם כתובת הדואר האלקטרוני של הלקוח.</span><span class="sxs-lookup"><span data-stu-id="97ee9-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="97ee9-142">יש לייצא פלחים אל Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="97ee9-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="97ee9-143">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="97ee9-143">Select **Save**.</span></span>

<span data-ttu-id="97ee9-144">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="97ee9-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="97ee9-145">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="97ee9-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="97ee9-146">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="97ee9-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="97ee9-147">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="97ee9-147">Data privacy and compliance</span></span>

<span data-ttu-id="97ee9-148">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Microsoft Advertising, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="97ee9-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="97ee9-149">Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- Microsoft Advertising עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="97ee9-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="97ee9-150">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="97ee9-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="97ee9-151">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="97ee9-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
