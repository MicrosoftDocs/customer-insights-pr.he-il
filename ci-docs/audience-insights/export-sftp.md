---
title: ייצוא נתוני Customer Insights אל מארחי SPTF
description: למד כיצד להגדיר את החיבור ולייצא אל מיקום SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 96c6026aded315008439740646827ca910cead90
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760420"
---
# <a name="export-segment-lists-and-other-data-to-sftp-preview"></a><span data-ttu-id="6dd5e-103">ייצוא רשימות פלחים ונתונים אחרים אל SFTP‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="6dd5e-103">Export segment lists and other data to SFTP (preview)</span></span>

<span data-ttu-id="6dd5e-104">השתמש בנתוני הלקוחות שלך ביישומי צד שלישי על-ידי ייצוא שלהם למיקום Secure File Transfer Protocol‏ (SFTP).</span><span class="sxs-lookup"><span data-stu-id="6dd5e-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="6dd5e-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="6dd5e-105">Prerequisites for connection</span></span>

- <span data-ttu-id="6dd5e-106">זמינות של מארח SFTP ואישורים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6dd5e-107">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="6dd5e-107">Known limitations</span></span>

- <span data-ttu-id="6dd5e-108">זמן הריצה של ייצוא תלוי בביצועי המערכת שלך.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="6dd5e-109">מומלץ שתי ליבות CPU וזיכרון של 1‎ GB כתצורה מינימלית עבור השרת שלך.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="6dd5e-110">ייצוא ישויות עם עד 100 מיליון פרופילי לקוחות יכול להימשך 90 דקות בעת שימוש בתצורה המינימלית המומלצת של שתי ליבות CPU וזיכרון של 1‎ GB.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="6dd5e-111">הגדרת חיבור ל- SFTP</span><span class="sxs-lookup"><span data-stu-id="6dd5e-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="6dd5e-112">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6dd5e-113">בחר **הוסף חיבור** ובחר **SFTP** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="6dd5e-114">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6dd5e-115">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6dd5e-116">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6dd5e-117">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-117">Choose who can use this connection.</span></span> <span data-ttu-id="6dd5e-118">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6dd5e-119">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6dd5e-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6dd5e-120">ספק **שם משתמש**, **סיסמה**, **שם מארח** ו **תיקיית ייצוא** עבור חשבון SFTP שלך.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="6dd5e-121">בחר **אימות** כדי לבדוק את החיבור.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="6dd5e-122">בחר אם ברצונך לייצא את הנתונים שלך **דחוסים ב- Gzip** או **לא דחוסים** ואת **מפריד השדה** עבור הקבצים המיוצאים.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="6dd5e-123">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6dd5e-124">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="6dd5e-125">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="6dd5e-125">Configure an export</span></span>

<span data-ttu-id="6dd5e-126">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6dd5e-127">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6dd5e-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6dd5e-128">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6dd5e-129">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6dd5e-130">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע SFTP.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="6dd5e-131">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="6dd5e-132">בחר את הישויות, לדוגמה פלחים, שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="6dd5e-133">כל ישות שנבחרה תחולק לעד חמישה קבצי פלט בעת הייצוא.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="6dd5e-134">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-134">Select **Save**.</span></span>

<span data-ttu-id="6dd5e-135">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6dd5e-136">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6dd5e-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6dd5e-137">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6dd5e-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6dd5e-138">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="6dd5e-138">Data privacy and compliance</span></span>

<span data-ttu-id="6dd5e-139">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים דרך SPTF, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6dd5e-140">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא שיעד הייצוא עומד בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="6dd5e-141">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6dd5e-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6dd5e-142">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="6dd5e-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
