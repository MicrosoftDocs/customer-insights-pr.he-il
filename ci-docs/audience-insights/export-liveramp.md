---
title: ‏‎מחבר ‎LiveRamp‏‏‏‏
description: למד כיצד לייצא נתונים אל LiveRamp.
ms.date: 12/02/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6ef4388b0e8ba8bc5866807765d8a872d41c9c14
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597558"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="7468d-103">מחבר LiveRamp&reg; (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="7468d-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="7468d-104">הפעל את הנתונים שלך ב- LiveRamp כדי להתחבר ליותר מ- 500 פלטפורמות במערכות אקולוגיות דיגיטליות, חברתיות ומערכות אקולוגיות של טלוויזיה.</span><span class="sxs-lookup"><span data-stu-id="7468d-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="7468d-105">עבוד עם הנתונים שלך ב- LiveRamp כדי להתמקד, להשמיט ולהתאים אישית קמפיינים פרסומיים.</span><span class="sxs-lookup"><span data-stu-id="7468d-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7468d-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="7468d-106">Prerequisites</span></span>

- <span data-ttu-id="7468d-107">כדי להשתמש במחבר זה אתה זקוק למנוי LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7468d-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="7468d-108">כדי לקבל מנוי, [צור קשר ישירות עם LiveRamp](https://liveramp.com/contact/).</span><span class="sxs-lookup"><span data-stu-id="7468d-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="7468d-109">[קבל מידע נוסף אודות LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="7468d-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="7468d-110">התחברות אל LiveRamp</span><span class="sxs-lookup"><span data-stu-id="7468d-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="7468d-111">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="7468d-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="7468d-112">באריח **LiveRamp**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="7468d-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="7468d-113">תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="7468d-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="7468d-114">ספק **שם משתמש** וכן **סיסמה** עבור חשבון LiveRamp Secure FTP‏ (SFTP) שלך.</span><span class="sxs-lookup"><span data-stu-id="7468d-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="7468d-115">אישורים אלה עשויים להיות שונים מאישור LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="7468d-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="7468d-116">בחר **אמת** כדי לבדוק את החיבור ל- LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7468d-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="7468d-117">לאחר אימות מוצלח, ספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="7468d-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="7468d-118">בחר **הבא** כדי להגדיר את מחבר LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7468d-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="7468d-119">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="7468d-119">Configure the connector</span></span>

1. <span data-ttu-id="7468d-120">בשדה **בחר את מזהה המפתח שלך**, בחר **דואר אלקטרוני**, **שם וכתובת** או **טלפון** כדי לשלוח ל- LiveRamp עבור פענוח זהות.</span><span class="sxs-lookup"><span data-stu-id="7468d-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="7468d-121">מפה את התכונות המתאימות מישות הלקוח המאוחד שלך עבור מזהה המפתח שנבחר.</span><span class="sxs-lookup"><span data-stu-id="7468d-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="7468d-122">בחר **הוסף תכונה** כדי למפות תכונות נוספות שיישלחו ל- LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7468d-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="7468d-123">שליחת תכונות מזהה מפתח נוספות ל- LiveRamp עשויה להשיג לך שיעור התאמה גבוה יותר.</span><span class="sxs-lookup"><span data-stu-id="7468d-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="7468d-124">בחר את הפלחים שברצונך לייצא ל- LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="7468d-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="7468d-125">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="7468d-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="7468d-126">![מחבר LiveRamp עם מיפוי תכונות](media/export-liveramp-segments.png "מחבר LiveRamp עם מיפוי תכונות")</span><span class="sxs-lookup"><span data-stu-id="7468d-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="7468d-127">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="7468d-127">Export the data</span></span>

<span data-ttu-id="7468d-128">הייצוא יתחיל בקרוב אם כל הדרישות המוקדמות עבור ייצוא יושלמו.</span><span class="sxs-lookup"><span data-stu-id="7468d-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="7468d-129">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7468d-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="7468d-130">לאחר השלמת הייצוא בהצלחה, תוכל להיכנס ל- LiveRamp Onboarding כדי להפעיל ולהפיץ את הנתונים שלך.</span><span class="sxs-lookup"><span data-stu-id="7468d-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="7468d-131">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="7468d-131">Data privacy and compliance</span></span>

<span data-ttu-id="7468d-132">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Liveramp, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="7468d-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="7468d-133">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Liveramp עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="7468d-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="7468d-134">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="7468d-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="7468d-135">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="7468d-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]