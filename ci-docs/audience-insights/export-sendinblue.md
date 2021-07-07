---
title: ייצוא נתוני Customer Insights ל- Sendinblue
description: למד כיצד להגדיר את החיבור ולייצא ל- Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314619"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="45c71-103">ייצוא פלחים ל- Sendinblue‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="45c71-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="45c71-104">ייצא פלחים של פרופילי לקוחות מאוחדים כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="45c71-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="45c71-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="45c71-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="45c71-106">יש לך [חשבון Sendinblue](https://www.sendinblue.com/) ואישורי מנהל מערכת תואמים.</span><span class="sxs-lookup"><span data-stu-id="45c71-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="45c71-107">יש רשימות קיימות ב- Sendinblue והמזהים המתאימים.</span><span class="sxs-lookup"><span data-stu-id="45c71-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="45c71-108">יש לך [פלחים מוגדרים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="45c71-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="45c71-109">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="45c71-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="45c71-110">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="45c71-110">Known limitations</span></span>

- <span data-ttu-id="45c71-111">עד מיליון פרופילים לכל ייצוא ל- Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="45c71-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="45c71-112">הייצוא ל- Sendinblue מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="45c71-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="45c71-113">ייצוא פלחים עם סך של מיליון פרופילים יכול להימשך עד 90 דקות.</span><span class="sxs-lookup"><span data-stu-id="45c71-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="45c71-114">מספר הפרופילים שתוכל לייצא ל- Sendinblue תלוי בחוזה שלך עם Sendinblue ומגבל על ידו.</span><span class="sxs-lookup"><span data-stu-id="45c71-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="45c71-115">הגדרת חיבור ל- Sendinblue</span><span class="sxs-lookup"><span data-stu-id="45c71-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="45c71-116">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="45c71-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="45c71-117">בחר **הוסף חיבור** ולאחר מכן בחר **Sendinblue** כדי להגדיר את החיבור.</span><span class="sxs-lookup"><span data-stu-id="45c71-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="45c71-118">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="45c71-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="45c71-119">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="45c71-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="45c71-120">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="45c71-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="45c71-121">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="45c71-121">Choose who can use this connection.</span></span> <span data-ttu-id="45c71-122">כברירת מחדל, רק מנהלי מערכת אפשריים.</span><span class="sxs-lookup"><span data-stu-id="45c71-122">By default it's only administrators.</span></span> <span data-ttu-id="45c71-123">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="45c71-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="45c71-124">הזן את **[מפתח ה- API של SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="45c71-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="45c71-125">בחר **אני מסכים** כדי לאשר את **פרטיות ותאימות נתונים** ובחר **חבר** כדי לאתחל את החיבור ל- Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="45c71-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="45c71-126">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="45c71-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="45c71-127">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="45c71-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="45c71-128">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="45c71-128">Configure an export</span></span>

<span data-ttu-id="45c71-129">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="45c71-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="45c71-130">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="45c71-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="45c71-131">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="45c71-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="45c71-132">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="45c71-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="45c71-133">בשדה **חיבור לייצוא**, בחר חיבור מהמקטע Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="45c71-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="45c71-134">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="45c71-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="45c71-135">הזן את **מזהה רשימת Sendinblue** שלך</span><span class="sxs-lookup"><span data-stu-id="45c71-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="45c71-136">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="45c71-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="45c71-137">לחלופין, אתה יכול לייצא **שם פרטי**, **שם משפחה** ו **טלפון** ליצירת הודעות דואר אלקטרוני מותאמות אישית יותר.</span><span class="sxs-lookup"><span data-stu-id="45c71-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="45c71-138">בחר **הוסף תכונה** כדי למפות שדות אלה.</span><span class="sxs-lookup"><span data-stu-id="45c71-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="45c71-139">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="45c71-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="45c71-140">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="45c71-140">Select **Save**.</span></span>

<span data-ttu-id="45c71-141">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="45c71-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="45c71-142">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="45c71-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="45c71-143">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="45c71-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="45c71-144">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="45c71-144">Data privacy and compliance</span></span>

<span data-ttu-id="45c71-145">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים ל- Sendinblue, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעלולים להיות רגישים, כגון נתונים אישיים.</span><span class="sxs-lookup"><span data-stu-id="45c71-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="45c71-146">Microsoft תעביר נתונים כאלה בהוראתך, אבל אתה אחראי להבטיח ש- Sendinblue עומד בכל התחייבויות הפרטיות והאבטחה שלך.</span><span class="sxs-lookup"><span data-stu-id="45c71-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="45c71-147">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="45c71-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="45c71-148">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="45c71-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
