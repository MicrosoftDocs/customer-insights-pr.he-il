---
title: ייצוא נתוני Customer Insights אל Mailchimp
description: למד כיצד לקבוע את תצורת החיבור אל Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405870"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="e23bf-103">מחבר עבור Mailchimp‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="e23bf-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="e23bf-104">יצא מקטעים של פרופיל לקוח מאוחדים אל Mailchimp כדי ליצור ידיעונים וקמפיינים בדוא"ל.</span><span class="sxs-lookup"><span data-stu-id="e23bf-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e23bf-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="e23bf-105">Prerequisites</span></span>

-   <span data-ttu-id="e23bf-106">יש לך [חשבון Mailchimp](https://mailchimp.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="e23bf-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e23bf-107">קיימים קהלים ב- Mailchimp ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="e23bf-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="e23bf-108">למידע נוסף, ראה [קהלי Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="e23bf-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="e23bf-109">יש לך [פלחים מוגדרים](segments.md)</span><span class="sxs-lookup"><span data-stu-id="e23bf-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="e23bf-110">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="e23bf-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="e23bf-111">התחבר ל- Mailchimp</span><span class="sxs-lookup"><span data-stu-id="e23bf-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="e23bf-112">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e23bf-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e23bf-113">תחת **Mailchimp**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="e23bf-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="e23bf-114">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="e23bf-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e23bf-115">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="e23bf-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e23bf-116">הזן את **[מזהה קהל Mailchimp](https://mailchimp.com/help/find-audience-id/)** ובחר **התחבר** כדי לאתחל את החיבור אל Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e23bf-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="e23bf-117">בחר **בצע אימות באמצעות Mailchimp** וספק את אישורי Mailchimp שלך.</span><span class="sxs-lookup"><span data-stu-id="e23bf-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="e23bf-118">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="e23bf-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="יצא צילום מסך עבור חיבור Mailchimp":::

1. <span data-ttu-id="e23bf-120">בחר **הבא** להגדרת התצורה של הייצוא.</span><span class="sxs-lookup"><span data-stu-id="e23bf-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e23bf-121">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="e23bf-121">Configure the connector</span></span>

1. <span data-ttu-id="e23bf-122">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="e23bf-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="e23bf-123">אם תרצה בכך, תוכל לייצא את **שם פרטי** ו **שם משפחה** כשדות נוספים כדי ליצור הודעות דוא"ל מותאמות אישית יותר.</span><span class="sxs-lookup"><span data-stu-id="e23bf-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="e23bf-124">בחר **הוסף תכונה** כדי למפות שדות אלה.</span><span class="sxs-lookup"><span data-stu-id="e23bf-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="e23bf-125">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="e23bf-125">Select the segments you want to export.</span></span> <span data-ttu-id="e23bf-126">באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e23bf-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="בחר שדות ופלחים לייצוא ל- Mailchimp":::

1. <span data-ttu-id="e23bf-128">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="e23bf-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e23bf-129">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="e23bf-129">Export the data</span></span>

<span data-ttu-id="e23bf-130">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e23bf-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e23bf-131">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e23bf-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e23bf-132">ב- Mailchimp, באפשרותך למצוא כעת את הפלחים שלך תחת [קהלי Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="e23bf-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e23bf-133">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="e23bf-133">Known limitations</span></span>

- <span data-ttu-id="e23bf-134">עד מיליון פרופילים לייצוא ל- Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e23bf-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="e23bf-135">הייצוא ל- Mailchimp מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="e23bf-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="e23bf-136">ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד שלוש שעות בשל מגבלות בצד הספק.</span><span class="sxs-lookup"><span data-stu-id="e23bf-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="e23bf-137">מספר הפרופילים שתוכל לייצא ל- Mailchimp תלוי ומוגבל בחוזה שלך עם Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="e23bf-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e23bf-138">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="e23bf-138">Data privacy and compliance</span></span>

<span data-ttu-id="e23bf-139">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Mailchimp, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="e23bf-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e23bf-140">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Mailchimp עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="e23bf-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="e23bf-141">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e23bf-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e23bf-142">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="e23bf-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
