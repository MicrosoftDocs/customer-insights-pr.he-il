---
title: ‏‎מחבר ‎LiveRamp‏‏‏‏
description: למד כיצד להגדיר את החיבור ואת הייצוא אל LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760328"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="b3a7b-103">ייצוא פלחים אל LiveRamp&reg;‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="b3a7b-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="b3a7b-104">הפעל את הנתונים שלך ב- LiveRamp כדי להתחבר ליותר מ- 500 פלטפורמות בעולם הדיגיטלי, החברתי ובעולם הטלוויזיות.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="b3a7b-105">עבוד עם הנתונים שלך ב- LiveRamp כדי להתמקד, להשמיט ולהתאים אישית קמפיינים פרסומיים.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b3a7b-106">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="b3a7b-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="b3a7b-107">כדי להשתמש במחבר זה אתה זקוק למנוי LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="b3a7b-108">כדי לקבל מנוי, [צור קשר ישירות עם LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="b3a7b-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="b3a7b-109">[קבל מידע נוסף אודות LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="b3a7b-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="b3a7b-110">הגדרת חיבור אל LiveRamp</span><span class="sxs-lookup"><span data-stu-id="b3a7b-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="b3a7b-111">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b3a7b-112">בחר **הוסף חיבור** ובחר **LiveRamp** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="b3a7b-113">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b3a7b-114">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b3a7b-115">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b3a7b-116">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-116">Choose who can use this connection.</span></span> <span data-ttu-id="b3a7b-117">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b3a7b-118">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b3a7b-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b3a7b-119">ספק **שם משתמש** וכן **סיסמה** עבור חשבון LiveRamp Secure FTP‏ (SFTP) שלך.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="b3a7b-120">אישורים אלה עשויים להיות שונים מאישור LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="b3a7b-121">בחר **אמת** כדי לבדוק את החיבור ל- LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="b3a7b-122">לאחר אימות מוצלח, ספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="b3a7b-123">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b3a7b-124">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="b3a7b-124">Configure an export</span></span>

<span data-ttu-id="b3a7b-125">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b3a7b-126">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b3a7b-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b3a7b-127">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b3a7b-128">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b3a7b-129">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="b3a7b-130">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b3a7b-131">בשדה **בחר את מזהה המפתח שלך**, בחר **דואר אלקטרוני**, **שם וכתובת** או **טלפון** כדי לשלוח ל- LiveRamp עבור פענוח זהות.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b3a7b-132">![מחבר LiveRamp עם מיפוי תכונות](media/export-liveramp-segments.png "מחבר LiveRamp עם מיפוי תכונות")</span><span class="sxs-lookup"><span data-stu-id="b3a7b-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="b3a7b-133">מפה את התכונות המתאימות מישות הלקוח המאוחד שלך עבור מזהה המפתח שנבחר.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="b3a7b-134">בחר **הוסף תכונה** כדי למפות תכונות נוספות לשליחה אל LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="b3a7b-135">שליחת תכונות מזהה מפתח נוספות ל- LiveRamp עשויה להשיג לך שיעור התאמה גבוה יותר.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="b3a7b-136">בחר את הפלחים שברצונך לייצא ל- LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="b3a7b-137">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-137">Select **Save**.</span></span>

<span data-ttu-id="b3a7b-138">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b3a7b-139">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b3a7b-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b3a7b-140">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b3a7b-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b3a7b-141">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="b3a7b-141">Data privacy and compliance</span></span>

<span data-ttu-id="b3a7b-142">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Liveramp, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b3a7b-143">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Liveramp עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b3a7b-144">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b3a7b-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b3a7b-145">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="b3a7b-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
