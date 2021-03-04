---
title: ייצוא נתוני Customer Insights אל Facebook Ads Manager
description: למד כיצד להגדיר את החיבור אל Facebook Ads Manager.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269975"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="dc773-103">מחבר ל- Facebook Ads Manager‏ (preview)</span><span class="sxs-lookup"><span data-stu-id="dc773-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="dc773-104">ייצא קטעים של פרופילי לקוחות מאוחדים אל Facebook Ads Manager ליצירת קמפיינים ב- Facebook ובאינסטגרם.</span><span class="sxs-lookup"><span data-stu-id="dc773-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dc773-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="dc773-105">Prerequisites</span></span>

- <span data-ttu-id="dc773-106">אתה צריך שיהיה לך [חשבון מודעות של **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) שכולל [חשבון עסקי של **Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="dc773-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="dc773-107">אתה צריך להיות מנהל מערכת ב [חשבון מודעות של **Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="dc773-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="dc773-108">התחבר אל Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="dc773-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="dc773-109">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="dc773-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="dc773-110">ב- **Facebook Ads Manager**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="dc773-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="dc773-111">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="dc773-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="dc773-112">בחר **המשך עם Facebook** כדי להיכנס לחשבון המודעות שלך ב- Facebook.</span><span class="sxs-lookup"><span data-stu-id="dc773-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="dc773-113">אפשר את הרשאת **ניהול מודעות** לאחר אימות עם Facebook.</span><span class="sxs-lookup"><span data-stu-id="dc773-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="dc773-114">בחר את **חשבון המודעות ב-Facebook** שברצונך לעבוד איתו.</span><span class="sxs-lookup"><span data-stu-id="dc773-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="dc773-115">בחר **קהל מותאם אישית קיים** מהרשימה הנפתחת או צור **קהל מותאם אישית חדש**.</span><span class="sxs-lookup"><span data-stu-id="dc773-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="dc773-116">למידע נוסף ראה [**קהלים ב- Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="dc773-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="dc773-117">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="dc773-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="dc773-118">בחר **הבא** להגדרת התצורה של הייצוא.</span><span class="sxs-lookup"><span data-stu-id="dc773-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="dc773-119">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="dc773-119">Configure the connector</span></span>

1. <span data-ttu-id="dc773-120">בתוך **בחר שדה מזהה מפתח**, בחר **דואר**, **שם וכתובת**, או **טלפון** כדי לשלוח אל Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="dc773-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="dc773-121">מפה את התכונות המתאימות מישות הלקוח המאוחד שלך עבור מזהה המפתח שנבחר.</span><span class="sxs-lookup"><span data-stu-id="dc773-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="dc773-122">[TIP] הסיכוי הטוב ביותר להתאמה הוא אם תבחר **דואר** כמזהה מפתח.</span><span class="sxs-lookup"><span data-stu-id="dc773-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="dc773-123">הוספת מזהים נוספים עשויה לשפר את ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="dc773-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="dc773-124">בחר **הוסף תכונה** כדי למפות תכונות נוספות שיש לשלוח אל Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="dc773-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="dc773-125">תכונות מ- Facebook Ads Manager ממופות לשמות המשתמש הבאים: **FN** = **שם פרטי**, **LN** = **שם משפחה**, **FI** = **ראשי תיבות**, **PHONE** = **טלפון**, **GEN** = **מין**, **DOB** = **תאריך לידה**, **ST** = **מדינה בארה"ב**, **CT** = **עיר**, **ZIP** = **מיקוד**, **COUNTRY** = **מדינה / אזור**</span><span class="sxs-lookup"><span data-stu-id="dc773-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="dc773-126">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="dc773-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="dc773-127">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="dc773-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="dc773-128">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="dc773-128">Export the data</span></span>

<span data-ttu-id="dc773-129">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="dc773-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="dc773-130">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dc773-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="dc773-131">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="dc773-131">Known limitations</span></span>

- <span data-ttu-id="dc773-132">עד 10 מיליון פרופילי לקוחות לכל ייצוא אל Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="dc773-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="dc773-133">הייצוא ל- Facebook Ads Manager מוגבל לפלחים</span><span class="sxs-lookup"><span data-stu-id="dc773-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="dc773-134">ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 90 דקות</span><span class="sxs-lookup"><span data-stu-id="dc773-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="dc773-135">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="dc773-135">Data privacy and compliance</span></span>

<span data-ttu-id="dc773-136">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Facebook Ads Manager, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="dc773-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="dc773-137">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Facebook Adsעומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="dc773-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="dc773-138">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="dc773-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="dc773-139">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="dc773-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]