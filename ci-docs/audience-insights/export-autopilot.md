---
title: ייצוא נתוני Customer Insights אל Autopilot
description: למד כיצד לקבוע את תצורת החיבור אל Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596131"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="4ee6f-103">מחבר עבור Autopilot‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="4ee6f-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="4ee6f-104">יצא פלחים של פרופילי לקוחות מאוחדים ל- Autopilot והשתמש בהם עבור שיווק בדוא"ל ב- Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="4ee6f-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="4ee6f-105">Prerequisites</span></span>

-   <span data-ttu-id="4ee6f-106">יש לך [חשבון Autopilot](https://www.autopilothq.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4ee6f-107">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4ee6f-108">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="4ee6f-109">התחברות ל- AutoPilot</span><span class="sxs-lookup"><span data-stu-id="4ee6f-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="4ee6f-110">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="4ee6f-111">תחת **Autopilot**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="4ee6f-112">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="חלונית תצורה עבור חיבור Autopilot.":::

1. <span data-ttu-id="4ee6f-114">הזן את **מפתח API של Autopilot** [מפתח API של Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="4ee6f-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="4ee6f-115">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4ee6f-116">בחר **התחבר** כדי לאתחל את החיבור אל Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="4ee6f-117">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4ee6f-118">בחר **הבא** להגדרת התצורה של הייצוא.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="4ee6f-119">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="4ee6f-119">Configure the connector</span></span>

1. <span data-ttu-id="4ee6f-120">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4ee6f-121">חזור על אותם שלבים עבור שדות אופציונליים אחרים כגון **שם פרטי**, **שם משפחה**.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="4ee6f-122">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-122">Select the segments you want to export.</span></span> <span data-ttu-id="4ee6f-123">אנחנו **ממליצים בחום לא לייצא יותר מ- 100,000 פרופילי לקוחות בסך הכל** אל Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="4ee6f-124">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="4ee6f-125">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="4ee6f-125">Export the data</span></span>

<span data-ttu-id="4ee6f-126">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="4ee6f-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="4ee6f-127">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4ee6f-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4ee6f-128">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="4ee6f-128">Known limitations</span></span>

- <span data-ttu-id="4ee6f-129">באפשרותך לייצא עד 100,000 פרופילי לקוחות בסך הכל ל- Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="4ee6f-130">הייצוא ל- Autopilot מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="4ee6f-131">ייצוא של עד 100,000 פרופילים ל- Autopilot יכול להימשך עד מספר שעות.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="4ee6f-132">מספר הפרופילים שתוכל לייצא ל- Autopilot תלוי ומוגבל בחוזה שלך עם Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4ee6f-133">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="4ee6f-133">Data privacy and compliance</span></span>

<span data-ttu-id="4ee6f-134">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Autopilot, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4ee6f-135">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Autopilot עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="4ee6f-136">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4ee6f-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4ee6f-137">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="4ee6f-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]