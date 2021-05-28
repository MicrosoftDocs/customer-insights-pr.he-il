---
title: ייצוא נתוני Customer Insights אל SendGrid
description: למד כיצד להגדיר את החיבור ולייצא אל SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d3d61d2b5b68079c7717e41dee5a2f698f2b62c
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976917"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="a0be9-103">ייצוא פלחים ל- SendGrid‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="a0be9-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="a0be9-104">יצא פלחים של פרופילי לקוחות מאוחדים לרשימות אנשי הקשר של SendGrid והשתמש בהם עבור קמפיינים ושיווק בדוא"ל ב- SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a0be9-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="a0be9-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="a0be9-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="a0be9-106">יש לך [חשבון SendGrid](https://sendgrid.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="a0be9-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="a0be9-107">יש רשימות אנשי קשר קיימות ב- SendGrid ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="a0be9-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="a0be9-108">למידע נוסף, ראה [SendGrid - ניהול אנשי קשר](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="a0be9-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="a0be9-109">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="a0be9-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="a0be9-110">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="a0be9-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="a0be9-111">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="a0be9-111">Known limitations</span></span>

- <span data-ttu-id="a0be9-112">עד 100,000 פרופילים בסך הכל ל- SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a0be9-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="a0be9-113">הייצוא ל- SendGrid מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="a0be9-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="a0be9-114">ייצוא של עד 100,000 פרופילים ל- SendGrid יכול להימשך עד מספר שעות.</span><span class="sxs-lookup"><span data-stu-id="a0be9-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="a0be9-115">מספר הפרופילים שתוכל לייצא ל- SendGrid תלוי ומוגבל בחוזה שלך עם SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a0be9-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="a0be9-116">הגדרת חיבור אל SendGrid</span><span class="sxs-lookup"><span data-stu-id="a0be9-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="a0be9-117">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="a0be9-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="a0be9-118">בחר **הוסף חיבור** ובחר **SendGrid** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="a0be9-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="a0be9-119">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="a0be9-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="a0be9-120">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="a0be9-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="a0be9-121">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="a0be9-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="a0be9-122">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="a0be9-122">Choose who can use this connection.</span></span> <span data-ttu-id="a0be9-123">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="a0be9-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="a0be9-124">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="a0be9-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="a0be9-125">הזן את **מפתח API של SendGrid** [מפתח API של SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="a0be9-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="a0be9-126">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="a0be9-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="a0be9-127">בחר **התחבר** כדי לאתחל את החיבור אל SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a0be9-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="a0be9-128">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="a0be9-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="a0be9-129">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="a0be9-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="a0be9-130">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="a0be9-130">Configure an export</span></span>

<span data-ttu-id="a0be9-131">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="a0be9-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="a0be9-132">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="a0be9-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="a0be9-133">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="a0be9-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="a0be9-134">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="a0be9-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="a0be9-135">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a0be9-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="a0be9-136">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="a0be9-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="a0be9-137">הזן את **[מזהה רשימת SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="a0be9-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="a0be9-138">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="a0be9-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="a0be9-139">חזור על אותם שלבים עבור שדות אופציונליים אחרים כגון **שם פרטי**, **שם משפחה**, **מדינה/אזור**, **מחוז**, **עיר** ו **מיקוד**.</span><span class="sxs-lookup"><span data-stu-id="a0be9-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="a0be9-140">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="a0be9-140">Select the segments you want to export.</span></span> <span data-ttu-id="a0be9-141">אנחנו **ממליצים בחום לא לייצא יותר מ- 100,000 פרופילי לקוחות בסך הכל** אל SendGrid.</span><span class="sxs-lookup"><span data-stu-id="a0be9-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="a0be9-142">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="a0be9-142">Select **Save**.</span></span>

<span data-ttu-id="a0be9-143">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="a0be9-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="a0be9-144">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a0be9-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="a0be9-145">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="a0be9-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="a0be9-146">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="a0be9-146">Data privacy and compliance</span></span>

<span data-ttu-id="a0be9-147">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל SendGrid, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="a0be9-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="a0be9-148">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- SendGrid עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="a0be9-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="a0be9-149">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="a0be9-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="a0be9-150">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="a0be9-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]