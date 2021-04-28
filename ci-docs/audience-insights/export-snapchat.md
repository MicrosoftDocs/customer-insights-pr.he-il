---
title: ייצוא נתוני Customer Insights אל Snapchat
description: למד כיצד להגדיר את החיבור ולייצא אל Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760540"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="da468-103">ייצוא רשימות פלחים אל Snapchat‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="da468-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="da468-104">יצא פלחים של פרופילי לקוחות מאוחדים אל Snapchat והשתמש בהם עבור פרסום.</span><span class="sxs-lookup"><span data-stu-id="da468-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="da468-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="da468-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="da468-106">יש לך [חשבון עסקי של Snapchat](https://business.snapchat.com/), [חשבון Snapchat Ads](https://ads.snapchat.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="da468-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="da468-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="da468-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="da468-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="da468-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="da468-109">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="da468-109">Known limitations</span></span>

- <span data-ttu-id="da468-110">הייצוא אל Snapchat מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="da468-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="da468-111">ייצוא של עד מיליון פרופילים ל- Snapchat יכול להימשך עד 15 דקות.</span><span class="sxs-lookup"><span data-stu-id="da468-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="da468-112">הגדרת חיבור אל Snapchat</span><span class="sxs-lookup"><span data-stu-id="da468-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="da468-113">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="da468-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="da468-114">בחר **הוסף חיבור** ובחר **Snapchat** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="da468-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="da468-115">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="da468-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="da468-116">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="da468-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="da468-117">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="da468-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="da468-118">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="da468-118">Choose who can use this connection.</span></span> <span data-ttu-id="da468-119">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="da468-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="da468-120">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="da468-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="da468-121">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="da468-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="da468-122">בחר **התחבר** כדי לאתחל את החיבור ל- Snapchat.</span><span class="sxs-lookup"><span data-stu-id="da468-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="da468-123">בחר **בצע אימות באמצעות Snapchat** וספק את אישורי מנהל המערכת שלך עבור Snapchat.</span><span class="sxs-lookup"><span data-stu-id="da468-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="da468-124">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="da468-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="da468-125">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="da468-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="da468-126">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="da468-126">Configure an export</span></span>

<span data-ttu-id="da468-127">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="da468-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="da468-128">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="da468-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="da468-129">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="da468-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="da468-130">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="da468-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="da468-131">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Snapchat.</span><span class="sxs-lookup"><span data-stu-id="da468-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="da468-132">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="da468-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="da468-133">הזן את [**מזהה הקהל של Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="da468-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="da468-134">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="da468-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="da468-135">יש לייצא פלחים אל Snapchat.</span><span class="sxs-lookup"><span data-stu-id="da468-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="da468-136">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="da468-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="da468-137">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="da468-137">Select **Save**.</span></span>

<span data-ttu-id="da468-138">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="da468-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="da468-139">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="da468-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="da468-140">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="da468-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="da468-141">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="da468-141">Data privacy and compliance</span></span>

<span data-ttu-id="da468-142">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Snapchat, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="da468-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="da468-143">Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- Snapchat עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="da468-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="da468-144">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="da468-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="da468-145">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="da468-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
