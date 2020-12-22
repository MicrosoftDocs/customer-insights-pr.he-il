---
title: ייצוא נתוני Customer Insights אל Marketo
description: למד כיצד לקבוע את תצורת החיבור אל Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570404"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="61c08-103">מחבר עבור Marketo‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="61c08-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="61c08-104">יצא פלחים של פרופילי לקוחות מאוחדים כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Marketo​.</span><span class="sxs-lookup"><span data-stu-id="61c08-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="61c08-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="61c08-105">Prerequisites</span></span>

-   <span data-ttu-id="61c08-106">יש לך [חשבון Marketo](https://login.marketo.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="61c08-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="61c08-107">יש רשימות קיימות ב- Marketo ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="61c08-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="61c08-108">לקבלת מידע נוסף, ראה [רשימות Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="61c08-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="61c08-109">יש לך [פלחים מוגדרים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="61c08-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="61c08-110">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="61c08-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="61c08-111">התחבר ל- Marketo</span><span class="sxs-lookup"><span data-stu-id="61c08-111">Connect to Marketo</span></span>

1. <span data-ttu-id="61c08-112">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="61c08-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="61c08-113">תחת **Marketo**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="61c08-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="61c08-114">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="61c08-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="61c08-115">הזן את **[מזהה הלקוח של Marketo, סוד הלקוח ושם מארח של נקודת קצה של REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="61c08-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="61c08-116">הזן את **[מזהה רשימת Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="61c08-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="61c08-117">בחר **אני מסכים** כדי לאשר את **פרטיות ותאימות הנתונים** ובחר **התחבר** כדי לאתחל את החיבור אל Marketo.</span><span class="sxs-lookup"><span data-stu-id="61c08-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="61c08-118">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="61c08-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="יצא צילום מסך עבור חיבור Marketo":::

1. <span data-ttu-id="61c08-120">בחר **הבא** להגדרת התצורה של הייצוא.</span><span class="sxs-lookup"><span data-stu-id="61c08-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="61c08-121">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="61c08-121">Configure the connector</span></span>

1. <span data-ttu-id="61c08-122">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="61c08-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="61c08-123">אם תרצה בכך, תוכל לייצא את **שם פרטי**, **שם משפחה**, **עיר**, **ארץ** ו **מדינה/אזור** כשדות נוספים ליצירת הודעות דוא"ל מותאמות אישית יותר.</span><span class="sxs-lookup"><span data-stu-id="61c08-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="61c08-124">בחר **הוסף תכונה** כדי למפות שדות אלה.</span><span class="sxs-lookup"><span data-stu-id="61c08-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="61c08-125">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="61c08-125">Select the segments you want to export.</span></span> <span data-ttu-id="61c08-126">באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Marketo.</span><span class="sxs-lookup"><span data-stu-id="61c08-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="בחר שדות ופלחים לייצוא ל- Marketo":::

1. <span data-ttu-id="61c08-128">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="61c08-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="61c08-129">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="61c08-129">Export the data</span></span>

<span data-ttu-id="61c08-130">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="61c08-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="61c08-131">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="61c08-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="61c08-132">ב- Marketo, באפשרותך למצוא כעת את הפלחים שלך תחת [רשימות Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="61c08-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="61c08-133">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="61c08-133">Known limitations</span></span>

- <span data-ttu-id="61c08-134">עד מיליון פרופילים לייצוא ל- Marketo.</span><span class="sxs-lookup"><span data-stu-id="61c08-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="61c08-135">הייצוא ל- Marketo מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="61c08-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="61c08-136">ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 3 שעות.</span><span class="sxs-lookup"><span data-stu-id="61c08-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="61c08-137">מספר הפרופילים שתוכל לייצא ל- Marketo תלוי ומוגבל בחוזה שלך עם Marketo.</span><span class="sxs-lookup"><span data-stu-id="61c08-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="61c08-138">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="61c08-138">Data privacy and compliance</span></span>

<span data-ttu-id="61c08-139">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Marketo, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="61c08-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="61c08-140">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Marketo עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="61c08-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="61c08-141">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="61c08-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="61c08-142">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="61c08-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
