---
title: ייצוא נתוני Customer Insights אל Facebook Ads Manager
description: למד כיצד להגדיר את החיבור ולייצא אל Facebook Ads Manager.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305111"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="2f8e4-103">ייצוא רשימת פלחים אל Facebook Ads Manager‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="2f8e4-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="2f8e4-104">ייצא קטעים של פרופילי לקוחות מאוחדים אל Facebook Ads Manager ליצירת קמפיינים ב- Facebook ובאינסטגרם.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="2f8e4-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="2f8e4-105">Prerequisites for connection</span></span>

- <span data-ttu-id="2f8e4-106">נדרש [**Facebook חשבון מודעות**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account)הכולל [**Facebook חשבון עסקי של**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="2f8e4-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="2f8e4-107">עליך להיות מנהל מערכת ב- [**Facebook חשבון מודעות**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="2f8e4-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2f8e4-108">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="2f8e4-108">Known limitations</span></span>

- <span data-ttu-id="2f8e4-109">עד 10 מיליון פריפילי לקוחות בכל ייצוא - Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="2f8e4-110">הייצוא ל- Facebook Ads Manager מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="2f8e4-111">צור או עדכן קהלים מותאמים אישית ב- Facebook מהסוג *רשימת לקוחות* בלבד.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="2f8e4-112">ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 90 דקות.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="2f8e4-113">הגדרת חיבור אל Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="2f8e4-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="2f8e4-114">לפני שמשתמשים יוכלו ליצור ייצוא, מנהל מערכת מוכרח להגדיר את החיבור לשירות ולאפשר למשתתפים להשתמש בחיבור.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="2f8e4-115">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2f8e4-116">בחר **הוסף חיבור** ובחר **Facebook Ads Manager** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="2f8e4-117">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2f8e4-118">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2f8e4-119">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2f8e4-120">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-120">Choose who can use this connection.</span></span> <span data-ttu-id="2f8e4-121">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2f8e4-122">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2f8e4-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2f8e4-123">אימות באמצעות Facebook Ads:</span><span class="sxs-lookup"><span data-stu-id="2f8e4-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="2f8e4-124">בחר **המשך עם Facebook** כדי להיכנס לחשבון Facebook Ads שלך.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="2f8e4-125">אפשר את הרשאת **ניהול מודעות** לאחר אימות עם Facebook.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="2f8e4-126">בחר את **חשבון המודעות ב-Facebook** שברצונך לעבוד איתו.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="2f8e4-127">בחר **קהל מותאם אישית קיים** מהרשימה הנפתחת או צור **קהל מותאם אישית חדש**.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="2f8e4-128">למידע נוסף ראה [**קהלים ב- Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="2f8e4-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="2f8e4-129">באפשרותך ליצור או לעדכן קהלים מותאמים אישית ב- Facebook מהסוג *רשימת לקוחות* עם ייצוא זה.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="2f8e4-130">במקרים מסוימים יופיעו קהלים מותאמים אישית מסוגים שונים ברשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="2f8e4-131">בחירת סוג שונה מ *רשימת לקוחות* תגרום לכשל בייצוא.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="2f8e4-132">סקור את **פרטיות ותאימות נתונים** ובחר **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="2f8e4-133">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2f8e4-134">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="2f8e4-134">Configure an export</span></span>

<span data-ttu-id="2f8e4-135">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2f8e4-136">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2f8e4-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2f8e4-137">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2f8e4-138">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="2f8e4-139">בשדה **חיבור לייצוא**, בחר חיבור מתוך המקטע **Facebook Ads Manager**.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="2f8e4-140">אם אינך רואה את שם הפלח הזה, אין קשרים זמינים עבורך מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="2f8e4-141">בתוך **בחר שדה מזהה מפתח**, בחר **דואר**, **שם וכתובת**, או **טלפון** כדי לשלוח אל Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="2f8e4-142">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2f8e4-143">מפה את התכונות המתאימות מישות הלקוח המאוחד שלך עבור מזהה המפתח שנבחר.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="2f8e4-144">הסיכוי הטוב ביותר להתאמה הוא אם תבחר **דואר** כמזהה מפתח.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="2f8e4-145">הוספת מזהים נוספים עשויה לשפר את ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="2f8e4-146">בחר **הוסף תכונה** כדי למפות תכונות נוספות לשליחה אל Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="2f8e4-147">תכונות מ- Facebook Ads Manager ממופות לשמות הידידותיים למשתמש הבאים: **FN** = **שם פרטי**, **LN** = **שם משפחה**, **FI** = **ראשי תיבות**, **PHONE** = **טלפון**, **GEN** = **מין**, **DOB** = **תאריך לידה**, **ST** = **מדינה בארה"ב**, **CT** = **עיר**, **ZIP** = **מיקוד**, **COUNTRY** = **מדינה / אזור**</span><span class="sxs-lookup"><span data-stu-id="2f8e4-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="2f8e4-148">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="2f8e4-149">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-149">Select **Save**.</span></span>

<span data-ttu-id="2f8e4-150">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2f8e4-151">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2f8e4-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="2f8e4-152">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2f8e4-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2f8e4-153">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="2f8e4-153">Data privacy and compliance</span></span>

<span data-ttu-id="2f8e4-154">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Facebook Ads Manager, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2f8e4-155">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Facebook Adsעומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="2f8e4-156">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2f8e4-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2f8e4-157">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="2f8e4-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
