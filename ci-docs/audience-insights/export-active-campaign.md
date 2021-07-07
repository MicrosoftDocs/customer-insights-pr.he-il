---
title: ייצוא נתוני Customer Insights ל- ActiveCampaign
description: למד כיצד להגדיר את החיבור ולייצא ל- ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314620"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="e0b67-103">ייצוא פלחים ל- ActiveCampaign‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="e0b67-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="e0b67-104">ייצא פלחים של פרופילי לקוחות מאוחדים ל- ActiveCampaign והשתמש בהם לצורך פעילויות שיווק.</span><span class="sxs-lookup"><span data-stu-id="e0b67-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e0b67-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="e0b67-105">Prerequisites</span></span>

-   <span data-ttu-id="e0b67-106">יש לך [חשבון ActiveCampaign](https://www.activecampaign.com/) ואישורי מנהל מערכת תואמים.</span><span class="sxs-lookup"><span data-stu-id="e0b67-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e0b67-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="e0b67-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="e0b67-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה עם כתובת דואר אלקטרוני.</span><span class="sxs-lookup"><span data-stu-id="e0b67-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e0b67-109">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="e0b67-109">Known limitations</span></span>

- <span data-ttu-id="e0b67-110">ניתן לייצוא עם מיליון פרופילים בכל ייצוא ל- ActiveCampaign והפעולה יכולה להימשך עד 90 דקות.</span><span class="sxs-lookup"><span data-stu-id="e0b67-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="e0b67-111">הייצוא ל- ActiveCampaign מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="e0b67-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="e0b67-112">מספר הפרופילים שתוכל לייצא ל- ActiveCampaign תלוי בחוזה שלך עם ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="e0b67-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="e0b67-113">הגדר חיבור ל- ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="e0b67-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="e0b67-114">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="e0b67-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e0b67-115">בחר **הוסף חיבור** ולאחר מכן בחר **ActiveCampaign** כדי להגדיר את החיבור.</span><span class="sxs-lookup"><span data-stu-id="e0b67-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="e0b67-116">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="e0b67-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e0b67-117">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="e0b67-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e0b67-118">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="e0b67-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e0b67-119">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="e0b67-119">Choose who can use this connection.</span></span> <span data-ttu-id="e0b67-120">כברירת מחדל, רק מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="e0b67-120">By default, it's only administrators.</span></span> <span data-ttu-id="e0b67-121">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e0b67-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e0b67-122">הזן את [מפתח API של ActiveCampaign ואת שם המחשב המארח של נקודת הקצה של REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="e0b67-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="e0b67-123">שם המארח של נקודת הקצה REST הוא שם המארח בלבד, ללא https://.</span><span class="sxs-lookup"><span data-stu-id="e0b67-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="e0b67-124">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="e0b67-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e0b67-125">בחר **התחבר** כדי לאתחל את החיבור ל- ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="e0b67-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="e0b67-126">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="e0b67-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e0b67-127">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="e0b67-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="e0b67-128">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="e0b67-128">Configure an export</span></span>

<span data-ttu-id="e0b67-129">באפשרותך לקבוע תצורה של ייצוא אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="e0b67-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="e0b67-130">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e0b67-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e0b67-131">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e0b67-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="e0b67-132">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="e0b67-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e0b67-133">בשדה **חיבור לייצוא**, בחר חיבור מהמקטע ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="e0b67-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="e0b67-134">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="e0b67-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e0b67-135">הזן את [**מזהה רשימת ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign) שלך.</span><span class="sxs-lookup"><span data-stu-id="e0b67-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="e0b67-136">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="e0b67-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e0b67-137">זה נדרש כדי לייצא פלחים ל- ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="e0b67-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="e0b67-138">לחלופין, אתה יכול לייצא שם פרטי, שם משפחה, וטלפון ליצירת הודעות דואר אלקטרוני מותאמות אישית יותר.</span><span class="sxs-lookup"><span data-stu-id="e0b67-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="e0b67-139">בחר הוסף תכונה כדי למפות שדות אלה.</span><span class="sxs-lookup"><span data-stu-id="e0b67-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="e0b67-140">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="e0b67-140">Select **Save**.</span></span>

<span data-ttu-id="e0b67-141">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="e0b67-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e0b67-142">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e0b67-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e0b67-143">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e0b67-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e0b67-144">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="e0b67-144">Data privacy and compliance</span></span>

<span data-ttu-id="e0b67-145">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים ל- ActiveCampaign, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעלולים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="e0b67-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e0b67-146">Microsoft תעביר נתונים כאלה בהוראתך, אבל אתה אחראי להבטיח ש- ActiveCampaign עומדת בכל התחייבויות הפרטיות והאבטחה שלך.</span><span class="sxs-lookup"><span data-stu-id="e0b67-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e0b67-147">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e0b67-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="e0b67-148">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="e0b67-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
