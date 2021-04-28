---
title: ייצוא נתוני Customer Insights אל RollWorks
description: למד כיצד להגדיר את החיבור ולייצא אל RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760543"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="a1512-103">ייצוא רשימות פלחים אל RollWorks‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="a1512-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="a1512-104">יצא פלחים של פרופילי לקוחות מאוחדים אל RollWorks והשתמש בהם עבור פרסום.</span><span class="sxs-lookup"><span data-stu-id="a1512-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a1512-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="a1512-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a1512-106">יש לך [חשבון RollWorks](https://www.rollworks.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="a1512-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a1512-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="a1512-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a1512-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="a1512-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a1512-109">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="a1512-109">Known limitations</span></span>

- <span data-ttu-id="a1512-110">באפשרותך לייצא עד 250,000 פרופילים לכל ייצוא אל RollWorks.</span><span class="sxs-lookup"><span data-stu-id="a1512-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="a1512-111">אינך יכול לייצא פלחים עם פחות מ- 100 פרופילים אל RollWorks.</span><span class="sxs-lookup"><span data-stu-id="a1512-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="a1512-112">הייצוא אל RollWorks מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="a1512-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="a1512-113">ייצוא של עד 250,000 פרופילים ל- RollWorks יכול להימשך עד 10 דקות.</span><span class="sxs-lookup"><span data-stu-id="a1512-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="a1512-114">מספר הפרופילים שבאפשרותך לייצא ל- RollWorks תלוי ומוגבל בחוזה שלך עם RollWorks.</span><span class="sxs-lookup"><span data-stu-id="a1512-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="a1512-115">הגדרת חיבור אל RollWorks</span><span class="sxs-lookup"><span data-stu-id="a1512-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="a1512-116">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="a1512-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a1512-117">בחר **הוסף חיבור** ובחר **RollWorks** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="a1512-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="a1512-118">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="a1512-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a1512-119">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="a1512-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a1512-120">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="a1512-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a1512-121">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="a1512-121">Choose who can use this connection.</span></span> <span data-ttu-id="a1512-122">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="a1512-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a1512-123">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a1512-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a1512-124">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="a1512-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a1512-125">בחר **התחבר** כדי לאתחל את החיבור ל- RollWorks.</span><span class="sxs-lookup"><span data-stu-id="a1512-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="a1512-126">בחר **בצע אימות מול RollWorks** וספק את אישורי מנהל המערכת שלך עבור RollWorks.</span><span class="sxs-lookup"><span data-stu-id="a1512-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="a1512-127">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="a1512-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a1512-128">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="a1512-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a1512-129">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="a1512-129">Configure an export</span></span>

<span data-ttu-id="a1512-130">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="a1512-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a1512-131">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a1512-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a1512-132">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="a1512-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a1512-133">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="a1512-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a1512-134">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע RollWorks.</span><span class="sxs-lookup"><span data-stu-id="a1512-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="a1512-135">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="a1512-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a1512-136">הזן את **מזהה מפרסם RollWorks** [פריט ניתן לפרסום של RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="a1512-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="a1512-137">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="a1512-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a1512-138">יש לייצא פלחים אל RollWorks.</span><span class="sxs-lookup"><span data-stu-id="a1512-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="a1512-139">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="a1512-139">Select the segments you want to export.</span></span> <span data-ttu-id="a1512-140">בחר פלח עם 100 חברים לפחות.</span><span class="sxs-lookup"><span data-stu-id="a1512-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="a1512-141">אין באפשרותך לייצא פלחים קטנים יותר.</span><span class="sxs-lookup"><span data-stu-id="a1512-141">You can't export smaller segments.</span></span> <span data-ttu-id="a1512-142">בנוסף, הגודל המרבי של פלח לייצוא הוא 250,000 חברים לייצוא.</span><span class="sxs-lookup"><span data-stu-id="a1512-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="a1512-143">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="a1512-143">Select **Save**.</span></span>

<span data-ttu-id="a1512-144">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="a1512-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a1512-145">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a1512-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a1512-146">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a1512-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a1512-147">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="a1512-147">Data privacy and compliance</span></span>

<span data-ttu-id="a1512-148">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל RollWorks, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="a1512-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a1512-149">Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- RollWorks עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="a1512-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="a1512-150">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a1512-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="a1512-151">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="a1512-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
