---
title: ייצוא נתוני Customer Insights אל SendGrid
description: למד כיצד לקבוע את תצורת החיבור אל SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268733"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="eb8b8-103">מחבר עבור SendGrid‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="eb8b8-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="eb8b8-104">יצא פלחים של פרופילי לקוחות מאוחדים לרשימות אנשי הקשר של SendGrid והשתמש בהם עבור קמפיינים ושיווק בדוא"ל ב- SendGrid.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="eb8b8-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="eb8b8-105">Prerequisites</span></span>

-   <span data-ttu-id="eb8b8-106">יש לך [חשבון SendGrid](https://sendgrid.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="eb8b8-107">יש רשימות אנשי קשר קיימות ב- SendGrid ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="eb8b8-108">למידע נוסף, ראה [SendGrid - ניהול אנשי קשר](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="eb8b8-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="eb8b8-109">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="eb8b8-110">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="eb8b8-111">התחבר ל- SendGrid</span><span class="sxs-lookup"><span data-stu-id="eb8b8-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="eb8b8-112">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="eb8b8-113">תחת **SendGrid**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="eb8b8-114">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="חלונית תצורת הייצוא של SendGrid.":::

1. <span data-ttu-id="eb8b8-116">הזן את **מפתח API של SendGrid** [מפתח API של SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="eb8b8-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="eb8b8-117">הזן את **[מזהה רשימת SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="eb8b8-118">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="eb8b8-119">בחר **התחבר** כדי לאתחל את החיבור אל SendGrid.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="eb8b8-120">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="eb8b8-121">בחר **הבא** להגדרת התצורה של הייצוא.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="eb8b8-122">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="eb8b8-122">Configure the connector</span></span>

1. <span data-ttu-id="eb8b8-123">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="eb8b8-124">חזור על אותם שלבים עבור שדות אופציונליים אחרים כגון **שם פרטי**, **שם משפחה**, **מדינה/אזור**, **מחוז**, **עיר** ו **מיקוד**.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="eb8b8-125">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-125">Select the segments you want to export.</span></span> <span data-ttu-id="eb8b8-126">אנחנו **ממליצים בחום לא לייצא יותר מ- 100,000 פרופילי לקוחות בסך הכל** אל SendGrid.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="eb8b8-127">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="eb8b8-128">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="eb8b8-128">Export the data</span></span>

<span data-ttu-id="eb8b8-129">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="eb8b8-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="eb8b8-130">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eb8b8-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="eb8b8-131">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="eb8b8-131">Known limitations</span></span>

- <span data-ttu-id="eb8b8-132">עד 100,000 פרופילים בסך הכל ל- SendGrid.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="eb8b8-133">הייצוא ל- SendGrid מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="eb8b8-134">ייצוא של עד 100,000 פרופילים ל- SendGrid יכול להימשך עד מספר שעות.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="eb8b8-135">מספר הפרופילים שתוכל לייצא ל- SendGrid תלוי ומוגבל בחוזה שלך עם SendGrid.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="eb8b8-136">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="eb8b8-136">Data privacy and compliance</span></span>

<span data-ttu-id="eb8b8-137">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל SendGrid, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="eb8b8-138">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- SendGrid עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="eb8b8-139">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="eb8b8-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="eb8b8-140">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="eb8b8-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]