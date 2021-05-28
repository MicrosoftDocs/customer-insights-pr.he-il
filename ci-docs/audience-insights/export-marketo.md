---
title: ייצוא נתוני Customer Insights אל Marketo
description: למד כיצד להגדיר את החיבור ולייצא אל Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b5a644e286bd44d4ebf7d1837255326c005b48d6
ms.sourcegitcommit: 74cd4fa9cbb784d9dff174c0eec7b4dcb408d66b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059317"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="adef3-103">ייצוא פלחים ל- Marketo‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="adef3-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="adef3-104">יצא פלחים של פרופילי לקוחות מאוחדים כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Marketo​.</span><span class="sxs-lookup"><span data-stu-id="adef3-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="adef3-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="adef3-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="adef3-106">יש לך [חשבון Marketo](https://login.marketo.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="adef3-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="adef3-107">יש רשימות קיימות ב- Marketo ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="adef3-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="adef3-108">לקבלת מידע נוסף, ראה [רשימות Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="adef3-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="adef3-109">יש לך [פלחים מוגדרים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="adef3-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="adef3-110">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="adef3-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="adef3-111">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="adef3-111">Known limitations</span></span>

- <span data-ttu-id="adef3-112">עד מיליון פרופילים לייצוא ל- Marketo.</span><span class="sxs-lookup"><span data-stu-id="adef3-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="adef3-113">הייצוא ל- Marketo מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="adef3-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="adef3-114">ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 3 שעות.</span><span class="sxs-lookup"><span data-stu-id="adef3-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="adef3-115">מספר הפרופילים שתוכל לייצא ל- Marketo תלוי ומוגבל בחוזה שלך עם Marketo.</span><span class="sxs-lookup"><span data-stu-id="adef3-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="adef3-116">הגדרת חיבור אל Marketo</span><span class="sxs-lookup"><span data-stu-id="adef3-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="adef3-117">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="adef3-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="adef3-118">בחר **הוסף חיבור** ובחר **Marketo** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="adef3-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="adef3-119">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="adef3-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="adef3-120">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="adef3-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="adef3-121">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="adef3-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="adef3-122">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="adef3-122">Choose who can use this connection.</span></span> <span data-ttu-id="adef3-123">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="adef3-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="adef3-124">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="adef3-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="adef3-125">הזן את **[מזהה הלקוח של Marketo, סוד הלקוח ושם מארח של נקודת קצה של REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="adef3-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span> <span data-ttu-id="adef3-126">שם המארח של נקודת הקצה REST הוא שם המארח בלבד, ללא `https://`.</span><span class="sxs-lookup"><span data-stu-id="adef3-126">The REST Endpoint Hostname is the hostname only, without `https://`.</span></span> <span data-ttu-id="adef3-127">דוגמה:`xyz-abc-123.mktorest.com`.</span><span class="sxs-lookup"><span data-stu-id="adef3-127">Example: `xyz-abc-123.mktorest.com`.</span></span> 

1. <span data-ttu-id="adef3-128">בחר **אני מסכים** כדי לאשר את **פרטיות ותאימות הנתונים** ובחר **התחבר** כדי לאתחל את החיבור אל Marketo.</span><span class="sxs-lookup"><span data-stu-id="adef3-128">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="adef3-129">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="adef3-129">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="adef3-130">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="adef3-130">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="adef3-131">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="adef3-131">Configure an export</span></span>

<span data-ttu-id="adef3-132">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="adef3-132">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="adef3-133">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="adef3-133">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="adef3-134">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="adef3-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="adef3-135">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="adef3-135">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="adef3-136">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Marketo.</span><span class="sxs-lookup"><span data-stu-id="adef3-136">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="adef3-137">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="adef3-137">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="adef3-138">הזן את **[מזהה רשימת Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span><span class="sxs-lookup"><span data-stu-id="adef3-138">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**.</span></span> <span data-ttu-id="adef3-139">מזהה הרשימה הוא ערך מספרי בלבד.</span><span class="sxs-lookup"><span data-stu-id="adef3-139">The list ID is a purely numerical value.</span></span> <span data-ttu-id="adef3-140">לדוגמה, אם מזהה רשימת Marketo שלך הוא ST12345A7, הסר את התו שמופיע לפני ואחרי הספרות והזן `12345`.</span><span class="sxs-lookup"><span data-stu-id="adef3-140">For example, if your Marketo list ID is ST12345A7, remove the character before and after the numerals and enter `12345`.</span></span> 

1. <span data-ttu-id="adef3-141">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="adef3-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="adef3-142">לחלופין, באפשרותך לייצא **שם פרטי**, **שם משפחה**, **עיר**, **ארץ** ו **מדינה/אזור** כדי ליצור הודעות דואר מותאמות אישית יותר.</span><span class="sxs-lookup"><span data-stu-id="adef3-142">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="adef3-143">בחר **הוסף תכונה** כדי למפות שדות אלה.</span><span class="sxs-lookup"><span data-stu-id="adef3-143">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="adef3-144">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="adef3-144">Select the segments you want to export.</span></span> <span data-ttu-id="adef3-145">באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Marketo.</span><span class="sxs-lookup"><span data-stu-id="adef3-145">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="adef3-146">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="adef3-146">Select **Save**.</span></span>

<span data-ttu-id="adef3-147">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="adef3-147">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="adef3-148">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="adef3-148">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="adef3-149">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="adef3-149">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="adef3-150">ב- Marketo, באפשרותך למצוא כעת את הפלחים שלך תחת [רשימות Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="adef3-150">In Marketo, you can now find your segments under [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="adef3-151">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="adef3-151">Data privacy and compliance</span></span>

<span data-ttu-id="adef3-152">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Marketo, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="adef3-152">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="adef3-153">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Marketo עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="adef3-153">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="adef3-154">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="adef3-154">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="adef3-155">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="adef3-155">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
