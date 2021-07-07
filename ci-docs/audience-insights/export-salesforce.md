---
title: ייצוא נתוני Customer Insights ל- Salesforce Marketing Cloud
description: למד כיצד להגדיר את החיבור ולייצא ל- Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314618"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="ccdf6-103">ייצוא פלחים ונתונים אחרים ל- Salesforce Marketing Cloud‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="ccdf6-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="ccdf6-104">השתמש בנתוני הלקוחות שלך ב- Salesforce Marketing Cloud על-ידי ייצוא שלהם באמצעות מיקום Secure File Transfer Protocol‏ (STFP).</span><span class="sxs-lookup"><span data-stu-id="ccdf6-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ccdf6-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="ccdf6-105">Prerequisites for connection</span></span>

- <span data-ttu-id="ccdf6-106">זמינות של מארח SFTP ואישורי מנהל מערכת תואמים.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="ccdf6-107">כיצד להגדיר מיקומי SFTP עבור Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="ccdf6-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="ccdf6-108">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="ccdf6-108">Known limitations</span></span>

- <span data-ttu-id="ccdf6-109">זמן הריצה של ייצוא תלוי בביצועי המערכת שלך.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="ccdf6-110">מומלץ שתי ליבות CPU וזיכרון של 1‎ GB כתצורה מינימלית עבור השרת שלך.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="ccdf6-111">ייצוא של ישויות עם עד 100 מיליון פרופילי לקוחות יכול להימשך 90 דקות בשימוש בתצורה המינימלית המומלצת.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="ccdf6-112">הגדרת החיבור ל- Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="ccdf6-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="ccdf6-113">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ccdf6-114">בחר **הוסף חיבור** ולאחר מכן בחר **Salesforce Marketing Cloud** כדי להגדיר את החיבור.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="ccdf6-115">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ccdf6-116">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ccdf6-117">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ccdf6-118">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-118">Choose who can use this connection.</span></span> <span data-ttu-id="ccdf6-119">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ccdf6-120">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ccdf6-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ccdf6-121">ספק **שם משתמש**, **סיסמה**, **שם מארח** ו **תיקיית ייצוא** עבור חשבון SFTP שלך.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="ccdf6-122">בחר **אימות** כדי לבדוק את החיבור.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="ccdf6-123">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ccdf6-124">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ccdf6-125">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="ccdf6-125">Configure an export</span></span>

<span data-ttu-id="ccdf6-126">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ccdf6-127">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ccdf6-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ccdf6-128">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ccdf6-129">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ccdf6-130">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע SFTP.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="ccdf6-131">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ccdf6-132">בחר אם ברצונך לייצא את הנתונים שלך **דחוסים ב- Gzip** או **לא דחוסים** ואת **מפריד השדה** עבור הקבצים המיוצאים.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="ccdf6-133">בחר את הישויות, לדוגמה פלחים, שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ccdf6-134">כל ישות שנבחרה תחולק לעד חמישה קבצי פלט בעת הייצוא.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="ccdf6-135">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-135">Select **Save**.</span></span>

<span data-ttu-id="ccdf6-136">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ccdf6-137">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ccdf6-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ccdf6-138">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ccdf6-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="ccdf6-139">ייבוא נתוני Customer Insights ממיקום SFTP ל- Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="ccdf6-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="ccdf6-140">צור [הרחבות נתונים ב- Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) כדי לייבא את קובץ הנתונים של Customer Insights ממיקום SFTP.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="ccdf6-141">[ייבא את הנתונים ממיקום SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) לתוך הרחבת הנתונים ב- Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="ccdf6-142">הגדר את האוטומציה לייבוא הנתונים אל הרחבות הנתונים.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="ccdf6-143">למידע נוסף על [אוטומציות file drop ואוטומציות מתוזמנות](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="ccdf6-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="ccdf6-144">הגדר [אוטומציה של file drop](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) או [אוטומציה מתוזמנת](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="ccdf6-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="ccdf6-145">הנה דוגמה ל[אוטומציה באמצעות SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="ccdf6-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ccdf6-146">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="ccdf6-146">Data privacy and compliance</span></span>

<span data-ttu-id="ccdf6-147">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים דרך SPTF, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ccdf6-148">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא שיעד הייצוא עומד בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ccdf6-149">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ccdf6-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ccdf6-150">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="ccdf6-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
