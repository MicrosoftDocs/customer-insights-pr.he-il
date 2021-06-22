---
title: ייצוא נתונים של Customer Insights אל Omnisend
description: למד כיצד להגדיר את החיבור ולייצא אל Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124496"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="038ee-103">ייצוא פלחים ל- Omnisend ‏(Preview)</span><span class="sxs-lookup"><span data-stu-id="038ee-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="038ee-104">יצא פלחים של פרופילי לקוחות מאוחדים אל Omnisend והשתמש בהם עבור פעילויות שיווק.</span><span class="sxs-lookup"><span data-stu-id="038ee-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="038ee-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="038ee-105">Prerequisites</span></span>

-   <span data-ttu-id="038ee-106">יש לך [חשבון Omnisend](https://www.omnisend.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="038ee-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="038ee-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="038ee-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="038ee-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="038ee-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="038ee-109">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="038ee-109">Known limitations</span></span>

- <span data-ttu-id="038ee-110">ניתן לייצא עד מיליון פרופילים בכל פעולת ייצוא ל- Omnisend ופעולה זו יכולה להימשך עד 4 שעות.</span><span class="sxs-lookup"><span data-stu-id="038ee-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="038ee-111">הייצוא אל Omnisend מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="038ee-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="038ee-112">מספר הפרופילים שתוכל לייצא אל Omnisend תלוי בחוזה שלך עם Omnisend.</span><span class="sxs-lookup"><span data-stu-id="038ee-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="038ee-113">הגדרת חיבור אל Omnisend</span><span class="sxs-lookup"><span data-stu-id="038ee-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="038ee-114">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="038ee-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="038ee-115">בחר **הוסף חיבור** ובחר **Omnisend** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="038ee-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="038ee-116">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="038ee-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="038ee-117">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="038ee-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="038ee-118">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="038ee-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="038ee-119">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="038ee-119">Choose who can use this connection.</span></span> <span data-ttu-id="038ee-120">כברירת מחדל, רק מנהלי מערכת אפשריים.</span><span class="sxs-lookup"><span data-stu-id="038ee-120">By default it's only administrators.</span></span> <span data-ttu-id="038ee-121">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="038ee-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="038ee-122">הזן את [מפתח ה- API של Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key) שלך.</span><span class="sxs-lookup"><span data-stu-id="038ee-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="038ee-123">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="038ee-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="038ee-124">בחר **התחבר** כדי לאתחל את החיבור ל- Omnisend.</span><span class="sxs-lookup"><span data-stu-id="038ee-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="038ee-125">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="038ee-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="038ee-126">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="038ee-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="038ee-127">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="038ee-127">Configure an export</span></span>

<span data-ttu-id="038ee-128">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="038ee-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="038ee-129">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="038ee-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="038ee-130">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="038ee-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="038ee-131">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="038ee-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="038ee-132">בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע Omnisend.</span><span class="sxs-lookup"><span data-stu-id="038ee-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="038ee-133">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="038ee-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="038ee-134">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="038ee-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="038ee-135">יש לייצא פלחים אל Omnisend.</span><span class="sxs-lookup"><span data-stu-id="038ee-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="038ee-136">לחלופין, באפשרותך לייצא שם פרטי, שם משפחה, כתובת, ארץ/אזור, מדינה, עיר ומיקוד כדי ליצור הודעות דואר מותאמות אישית יותר.</span><span class="sxs-lookup"><span data-stu-id="038ee-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="038ee-137">בחר **הוסף תכונה** כדי למפות שדות אלה.</span><span class="sxs-lookup"><span data-stu-id="038ee-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="038ee-138">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="038ee-138">Select **Save**.</span></span>

<span data-ttu-id="038ee-139">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="038ee-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="038ee-140">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="038ee-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="038ee-141">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="038ee-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="038ee-142">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="038ee-142">Data privacy and compliance</span></span>

<span data-ttu-id="038ee-143">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Ommisend, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="038ee-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="038ee-144">Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- Ommisend עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="038ee-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="038ee-145">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="038ee-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="038ee-146">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="038ee-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
