---
title: ייצוא נתוני Customer Insights אל Campaign Monitor
description: למד כיצד להגדיר את החיבור ולייצא אל Campaign Monitor.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124182"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="cc75e-103">ייצוא פלחים אל Campaign Monitor‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="cc75e-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="cc75e-104">יצא פלחים של פרופילי לקוחות מאוחדים אל Campaign Monitor והשתמש בהם עבור פעילויות שיווק.</span><span class="sxs-lookup"><span data-stu-id="cc75e-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="cc75e-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="cc75e-105">Prerequisites</span></span>

-   <span data-ttu-id="cc75e-106">יש לך [חשבון Campaign Monitor](https://www.campaignmonitor.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="cc75e-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cc75e-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="cc75e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="cc75e-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="cc75e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cc75e-109">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="cc75e-109">Known limitations</span></span>

- <span data-ttu-id="cc75e-110">באפשרותך לייצא עד מיליון פרופילים לכל ייצוא אל Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="cc75e-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="cc75e-111">הייצוא ל- Campaign Monitor מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="cc75e-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="cc75e-112">ייצוא של עד מיליון פרופילים ל- Campaign Monitor יכול להימשך עד 20 דקות.</span><span class="sxs-lookup"><span data-stu-id="cc75e-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="cc75e-113">מספר הפרופילים שבאפשרותך לייצא ל- Campaign Monitor תלוי ומוגבל בחוזה שלך עם Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="cc75e-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="cc75e-114">הגדרת חיבור ל- Campaign Monitor</span><span class="sxs-lookup"><span data-stu-id="cc75e-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="cc75e-115">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="cc75e-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="cc75e-116">בחר **הוסף חיבור** ובחר **Campaign Monitor** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="cc75e-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="cc75e-117">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="cc75e-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="cc75e-118">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="cc75e-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="cc75e-119">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="cc75e-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="cc75e-120">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="cc75e-120">Choose who can use this connection.</span></span> <span data-ttu-id="cc75e-121">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="cc75e-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="cc75e-122">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="cc75e-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="cc75e-123">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="cc75e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cc75e-124">בחר **התחבר** כדי לאתחל את החיבור ל- Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="cc75e-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="cc75e-125">בחר **בצע אימות מול Campaign Monitor** וספק את אישורי מנהל המערכת שלך עבור Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="cc75e-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="cc75e-126">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="cc75e-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cc75e-127">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="cc75e-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="cc75e-128">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="cc75e-128">Configure an export</span></span>

<span data-ttu-id="cc75e-129">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="cc75e-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="cc75e-130">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="cc75e-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="cc75e-131">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="cc75e-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="cc75e-132">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="cc75e-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="cc75e-133">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="cc75e-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="cc75e-134">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="cc75e-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="cc75e-135">הזן את [**מזהה רשימת Campaign Monitor**](https://www.campaignmonitor.com/api/getting-started/#your-list-id) שלך.</span><span class="sxs-lookup"><span data-stu-id="cc75e-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="cc75e-136">[צור את מפתח ה- API](https://www.campaignmonitor.com/api/getting-started/) דרך **הגדרות חשבון** ב- Campaign Monitor תחילה כדי להציג את מזהה רשימת ה- API.</span><span class="sxs-lookup"><span data-stu-id="cc75e-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="cc75e-137">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="cc75e-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="cc75e-138">יש לייצא פלחים אל Campaign Monitor.</span><span class="sxs-lookup"><span data-stu-id="cc75e-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="cc75e-139">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="cc75e-139">Select **Save**.</span></span>

<span data-ttu-id="cc75e-140">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="cc75e-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="cc75e-141">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cc75e-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="cc75e-142">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="cc75e-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cc75e-143">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="cc75e-143">Data privacy and compliance</span></span>

<span data-ttu-id="cc75e-144">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Campaign Monitor, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="cc75e-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cc75e-145">Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- Campaign Monitor עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="cc75e-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="cc75e-146">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cc75e-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="cc75e-147">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="cc75e-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
