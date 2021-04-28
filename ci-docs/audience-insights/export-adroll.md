---
title: ייצוא נתוני Customer Insights אל AdRoll
description: למד כיצד להגדיר את החיבור ולייצא אל AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895960"
---
# <a name="export-segment-lists-to-adroll-preview"></a><span data-ttu-id="e9a7f-103">ייצוא רשימות פלחים אל AdRoll‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="e9a7f-103">Export segment lists to AdRoll (preview)</span></span>

<span data-ttu-id="e9a7f-104">יצא פלחים של פרופילי לקוח מאוחדים אל AdRoll והשתמש בהם עבור פרסום.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="e9a7f-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="e9a7f-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="e9a7f-106">יש לך [חשבון AdRoll](https://www.adroll.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e9a7f-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e9a7f-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e9a7f-109">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="e9a7f-109">Known limitations</span></span>

- <span data-ttu-id="e9a7f-110">באפשרותך לייצא עד 250,000 פרופילים לייצוא אל AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-110">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="e9a7f-111">אין באפשרותך לייצא פלחים עם פחות מ- 100 פרופילים ל- AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-111">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="e9a7f-112">הייצוא ל- AdRoll מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-112">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="e9a7f-113">ייצוא של עד 250,000 פרופילים ל- AdRoll יכול להימשך עד 10 דקות.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-113">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="e9a7f-114">מספר הפרופילים שתוכל לייצא ל- AdRoll תלוי ומוגבל בחוזה שלך עם AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-114">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="set-up-connection-to-adroll"></a><span data-ttu-id="e9a7f-115">הגדרת חיבור אל AdRoll</span><span class="sxs-lookup"><span data-stu-id="e9a7f-115">Set up connection to AdRoll</span></span>

1. <span data-ttu-id="e9a7f-116">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e9a7f-117">בחר **הוסף חיבור** ובחר **AdRoll** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-117">Select **Add connection** and choose **AdRoll** to configure the connection.</span></span>

1. <span data-ttu-id="e9a7f-118">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e9a7f-119">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e9a7f-120">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e9a7f-121">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-121">Choose who can use this connection.</span></span> <span data-ttu-id="e9a7f-122">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e9a7f-123">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e9a7f-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e9a7f-124">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e9a7f-125">בחר **התחבר** כדי לאתחל את החיבור אל AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-125">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="e9a7f-126">בחר **בצע אימות באמצעות AdRoll** וספק את אישורי מנהל המערכת שלך עבור AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-126">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="e9a7f-127">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e9a7f-128">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e9a7f-129">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="e9a7f-129">Configure an export</span></span>

<span data-ttu-id="e9a7f-130">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e9a7f-131">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e9a7f-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e9a7f-132">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e9a7f-133">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e9a7f-134">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע AdRoll.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-134">In the **Connection for export** field, choose a connection from the AdRoll section.</span></span> <span data-ttu-id="e9a7f-135">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e9a7f-136">הזן את **מזהה מפרסם AdRoll** לקבלת מידע נוסף, ראה [פרופילי מפרס AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="e9a7f-136">Enter your **AdRoll Advertiser ID** For more information, see [AdRoll Advertiser Profiles](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="e9a7f-137">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e9a7f-138">ייצוא פלחים אל AdRoll הוא הכרחי.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-138">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="e9a7f-139">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-139">Select the segments you want to export.</span></span> <span data-ttu-id="e9a7f-140">בחר פלח עם 100 חברים לפחות.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="e9a7f-141">אין באפשרותך לייצא פלחים קטנים יותר.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-141">You can't export smaller segments.</span></span> <span data-ttu-id="e9a7f-142">בנוסף, הגודל המרבי של פלח לייצוא הוא 250,000 חברים לייצוא.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="e9a7f-143">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-143">Select **Save**.</span></span>

<span data-ttu-id="e9a7f-144">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e9a7f-145">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e9a7f-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e9a7f-146">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e9a7f-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e9a7f-147">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="e9a7f-147">Data privacy and compliance</span></span>

<span data-ttu-id="e9a7f-148">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל AdRoll, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-148">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e9a7f-149">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- AdRoll עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e9a7f-150">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e9a7f-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e9a7f-151">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="e9a7f-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
