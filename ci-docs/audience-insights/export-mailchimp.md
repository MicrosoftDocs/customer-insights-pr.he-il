---
title: ייצוא נתוני Customer Insights אל Mailchimp
description: למד כיצד להגדיר את החיבור ולייצא אל Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7922a6a69f863caae5401549ed6f88a61aa77d39
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124228"
---
# <a name="export-segments-to-mailchimp-preview"></a><span data-ttu-id="e66db-103">ייצוא פלחים אל Mailchimp‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="e66db-103">Export segments to Mailchimp (preview)</span></span>

<span data-ttu-id="e66db-104">יצא מקטעים של פרופיל לקוח מאוחדים אל Mailchimp כדי ליצור ידיעונים וקמפיינים בדוא"ל.</span><span class="sxs-lookup"><span data-stu-id="e66db-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="e66db-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="e66db-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="e66db-106">יש לך [חשבון Mailchimp](https://mailchimp.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="e66db-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e66db-107">קיימים קהלים ב- Mailchimp ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="e66db-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="e66db-108">למידע נוסף, ראה [קהלי Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="e66db-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="e66db-109">יש לך [פלחים מוגדרים](segments.md)</span><span class="sxs-lookup"><span data-stu-id="e66db-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="e66db-110">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="e66db-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e66db-111">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="e66db-111">Known limitations</span></span>

- <span data-ttu-id="e66db-112">עד מיליון פרופילים לייצוא ל- Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e66db-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="e66db-113">הייצוא ל- Mailchimp מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="e66db-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="e66db-114">ייצוא פלחים עם מיליון פרופילים יכול להימשך עד שלוש שעות.</span><span class="sxs-lookup"><span data-stu-id="e66db-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="e66db-115">מספר הפרופילים שתוכל לייצא ל- Mailchimp תלוי ומוגבל בחוזה שלך עם Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e66db-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="e66db-116">הגדרת חיבור אל Mailchimp</span><span class="sxs-lookup"><span data-stu-id="e66db-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="e66db-117">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="e66db-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="e66db-118">בחר **הוסף חיבור** ובחר **Autopilot** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="e66db-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="e66db-119">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="e66db-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="e66db-120">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="e66db-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="e66db-121">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="e66db-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="e66db-122">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="e66db-122">Choose who can use this connection.</span></span> <span data-ttu-id="e66db-123">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="e66db-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="e66db-124">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="e66db-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="e66db-125">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="e66db-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e66db-126">בחר **התחבר** כדי לאתחל את החיבור ל- Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e66db-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="e66db-127">בחר **בצע אימות באמצעות Mailchimp** וספק את אישורי Mailchimp שלך.</span><span class="sxs-lookup"><span data-stu-id="e66db-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="e66db-128">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="e66db-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="e66db-129">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="e66db-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="e66db-130">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="e66db-130">Configure the connector</span></span>

<span data-ttu-id="e66db-131">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="e66db-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="e66db-132">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="e66db-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="e66db-133">עבור אל **נתונים**> **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e66db-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="e66db-134">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="e66db-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="e66db-135">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e66db-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="e66db-136">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="e66db-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="e66db-137">הזן את **[מזהה קהל Mailchimp](https://mailchimp.com/help/find-audience-id/)** שלך</span><span class="sxs-lookup"><span data-stu-id="e66db-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="e66db-138">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="e66db-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e66db-139">לחלופין, באפשרותך לייצא **שם פרטי** ו **שם משפחה** כדי ליצור הודעות דואר מותאמות אישית יותר.</span><span class="sxs-lookup"><span data-stu-id="e66db-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="e66db-140">בחר **הוסף תכונה** כדי למפות שדות אלה.</span><span class="sxs-lookup"><span data-stu-id="e66db-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e66db-141">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="e66db-141">Select the segments you want to export.</span></span> <span data-ttu-id="e66db-142">באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e66db-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="e66db-143">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="e66db-143">Select **Save**.</span></span>

<span data-ttu-id="e66db-144">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="e66db-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="e66db-145">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e66db-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e66db-146">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e66db-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e66db-147">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="e66db-147">Data privacy and compliance</span></span>

<span data-ttu-id="e66db-148">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Mailchimp, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="e66db-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e66db-149">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Mailchimp עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="e66db-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e66db-150">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e66db-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e66db-151">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="e66db-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
