---
title: ייצוא נתוני Customer Insights אל Autopilot
description: למד כיצד להגדיר את החיבור ולייצא אל Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760144"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="9d5b7-103">ייצוא פלחים ל- Autopilot‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="9d5b7-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="9d5b7-104">יצא פלחים של פרופילי לקוחות מאוחדים ל- Autopilot והשתמש בהם עבור שיווק בדוא"ל ב- Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="9d5b7-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="9d5b7-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="9d5b7-106">יש לך [חשבון Autopilot](https://www.autopilothq.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="9d5b7-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="9d5b7-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="9d5b7-109">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="9d5b7-109">Known limitations</span></span>

- <span data-ttu-id="9d5b7-110">באפשרותך לייצא עד 100,000 פרופילי לקוחות בסך הכל ל- Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="9d5b7-111">הייצוא ל- Autopilot מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="9d5b7-112">ייצוא של עד 100,000 פרופילים ל- Autopilot יכול להימשך עד מספר שעות.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="9d5b7-113">מספר הפרופילים שתוכל לייצא ל- Autopilot תלוי ומוגבל בחוזה שלך עם Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="9d5b7-114">הגדרת חיבור אל Autopilot</span><span class="sxs-lookup"><span data-stu-id="9d5b7-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="9d5b7-115">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="9d5b7-116">בחר **הוסף חיבור** ובחר **Autopilot** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="9d5b7-117">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="9d5b7-118">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="9d5b7-119">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="9d5b7-120">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-120">Choose who can use this connection.</span></span> <span data-ttu-id="9d5b7-121">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="9d5b7-122">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="9d5b7-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="9d5b7-123">הזן את [מפתח ה- API של Autopilot](https://autopilot.docs.apiary.io/#) שלך.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="9d5b7-124">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="9d5b7-125">בחר **התחבר** כדי לאתחל את החיבור אל Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="9d5b7-126">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="9d5b7-127">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="9d5b7-128">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="9d5b7-128">Configure an export</span></span>

<span data-ttu-id="9d5b7-129">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="9d5b7-130">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="9d5b7-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="9d5b7-131">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="9d5b7-132">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="9d5b7-133">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="9d5b7-134">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="9d5b7-135">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="9d5b7-136">חזור על אותם שלבים עבור שדות אופציונליים אחרים כגון **שם פרטי**, **שם משפחה**.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="9d5b7-137">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-137">Select the segments you want to export.</span></span> <span data-ttu-id="9d5b7-138">אנחנו **ממליצים בחום לא לייצא יותר מ- 100,000 פרופילי לקוחות בסך הכל** אל Autopilot.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="9d5b7-139">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-139">Select **Save**.</span></span>

<span data-ttu-id="9d5b7-140">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="9d5b7-141">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="9d5b7-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="9d5b7-142">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="9d5b7-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="9d5b7-143">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="9d5b7-143">Data privacy and compliance</span></span>

<span data-ttu-id="9d5b7-144">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Autopilot, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="9d5b7-145">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Autopilot עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="9d5b7-146">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="9d5b7-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="9d5b7-147">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="9d5b7-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
