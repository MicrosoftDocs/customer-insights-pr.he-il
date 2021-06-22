---
title: ייצוא נתוני Customer Insights אל Constant Contact
description: למד כיצד להגדיר את החיבור ולייצא אל Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124274"
---
# <a name="export-segments-to-constant-contact-preview"></a><span data-ttu-id="12ca9-103">ייצוא פלחים אל Constant Contact‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="12ca9-103">Export segments to Constant Contact (preview)</span></span>

<span data-ttu-id="12ca9-104">יצא פלחים של פרופילי לקוחות מאוחדים אל Constant Contact והשתמש בהם עבור פעילויות שיווק.</span><span class="sxs-lookup"><span data-stu-id="12ca9-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="12ca9-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="12ca9-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="12ca9-106">יש לך [חשבון Constant Contact](https://www.constantcontact.com/account-home) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="12ca9-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="12ca9-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="12ca9-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="12ca9-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="12ca9-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="12ca9-109">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="12ca9-109">Known limitations</span></span>

- <span data-ttu-id="12ca9-110">באפשרותך לייצא עד מיליון פרופילים לכל ייצוא אל Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="12ca9-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="12ca9-111">הייצוא אל Constant Contact מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="12ca9-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="12ca9-112">ייצוא של עד מיליון פרופילים ל- Constant Contact יכול להימשך עד שעה אחת.</span><span class="sxs-lookup"><span data-stu-id="12ca9-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="12ca9-113">מספר הפרופילים שבאפשרותך לייצא ל- Constant Contact תלוי ומוגבל בחוזה שלך עם Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="12ca9-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="12ca9-114">הגדרת חיבור ל- Constant Contact</span><span class="sxs-lookup"><span data-stu-id="12ca9-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="12ca9-115">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="12ca9-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="12ca9-116">בחר **הוסף חיבור** ובחר **Constant Contact** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="12ca9-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="12ca9-117">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="12ca9-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="12ca9-118">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="12ca9-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="12ca9-119">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="12ca9-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="12ca9-120">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="12ca9-120">Choose who can use this connection.</span></span> <span data-ttu-id="12ca9-121">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="12ca9-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="12ca9-122">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="12ca9-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="12ca9-123">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="12ca9-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="12ca9-124">בחר **התחבר** כדי לאתחל את החיבור ל- Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="12ca9-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="12ca9-125">בחר **אימות באמצעות AdRoll** וספק את אישורי מנהל המערכת שלך עבור Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="12ca9-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="12ca9-126">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="12ca9-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="12ca9-127">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="12ca9-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="12ca9-128">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="12ca9-128">Configure an export</span></span>

<span data-ttu-id="12ca9-129">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="12ca9-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="12ca9-130">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="12ca9-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="12ca9-131">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="12ca9-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="12ca9-132">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="12ca9-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="12ca9-133">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="12ca9-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="12ca9-134">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="12ca9-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="12ca9-135">הזן את [**מזהה הרשימה של Constant Contact שלך**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="12ca9-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="12ca9-136">פתח רשימה ב- Constant Contact כדי למצוא את מזהה הרשימה בכתובת ה- URL.</span><span class="sxs-lookup"><span data-stu-id="12ca9-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="12ca9-137">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="12ca9-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="12ca9-138">יש לייצא פלחים אל Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="12ca9-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="12ca9-139">אם תרצה בכך, תוכל לייצא את שם פרטי ושם משפחה כשדות נוספים כדי ליצור הודעות דוא"ל מותאמות אישית יותר.</span><span class="sxs-lookup"><span data-stu-id="12ca9-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="12ca9-140">בחר **הוסף תכונה** כדי למפות שדות אלה.</span><span class="sxs-lookup"><span data-stu-id="12ca9-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="12ca9-141">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="12ca9-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="12ca9-142">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="12ca9-142">Select **Save**.</span></span>

<span data-ttu-id="12ca9-143">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="12ca9-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="12ca9-144">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="12ca9-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="12ca9-145">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="12ca9-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="12ca9-146">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="12ca9-146">Data privacy and compliance</span></span>

<span data-ttu-id="12ca9-147">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Constant Contact, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, לרבות נתונים שעשויים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="12ca9-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="12ca9-148">Microsoft תעביר נתונים כאלה בהנחייתך, אך אתה אחראי להבטיח ש- Constant Contact עומד בכל מחויבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="12ca9-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="12ca9-149">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="12ca9-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="12ca9-150">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="12ca9-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
