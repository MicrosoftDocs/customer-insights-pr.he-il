---
title: ייצוא נתוני Customer Insights אל DotDigital
description: למד כיצד לקבוע את תצורת החיבור אל DotDigital.
ms.date: 11/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 51a28bdf0de34f0555d8ad7e3d13b2ef8911d417
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598018"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="137ce-103">מחבר עבור DotDigital‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="137ce-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="137ce-104">יצא פלחים של פרופילי לקוחות מאוחדים אל פנקסי הכתובות של DotDigital והשתמש בהם עבור קמפיינים, שיווק בדוא"ל ולבניית פלחי לקוחות עם DotDigital.</span><span class="sxs-lookup"><span data-stu-id="137ce-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="137ce-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="137ce-105">Prerequisites</span></span>

-   <span data-ttu-id="137ce-106">יש לך [חשבון DotDigital](https://dotdigital.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="137ce-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="137ce-107">קיימים פנקסי כתובות ב- DotDigital ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="137ce-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="137ce-108">ניתן למצוא את המזהה בכתובת ה- URL כאשר אתה בוחר ופותח פנקס כתובות.</span><span class="sxs-lookup"><span data-stu-id="137ce-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="137ce-109">לקבלת מידע נוסף, ראה [פנקסי כתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="137ce-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="137ce-110">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="137ce-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="137ce-111">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="137ce-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="137ce-112">התחבר ל- DotDigital</span><span class="sxs-lookup"><span data-stu-id="137ce-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="137ce-113">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="137ce-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="137ce-114">תחת **DotDigital**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="137ce-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="137ce-115">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="137ce-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="חלונית תצורה עבור ייצוא DotDigital.":::

1. <span data-ttu-id="137ce-117">הזן את **שם המשתמש והסיסמה של DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="137ce-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="137ce-118">הזן את **[מזהה פנקס הכתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="137ce-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="137ce-119">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="137ce-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="137ce-120">בחר **התחבר** כדי לאתחל את החיבור אל DotDigital.</span><span class="sxs-lookup"><span data-stu-id="137ce-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="137ce-121">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="137ce-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="137ce-122">בחר **הבא** להגדרת התצורה של הייצוא.</span><span class="sxs-lookup"><span data-stu-id="137ce-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="137ce-123">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="137ce-123">Configure the connector</span></span>

1. <span data-ttu-id="137ce-124">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="137ce-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="137ce-125">חזור על אותם שלבים עבור שדות אופציונליים אחרים כגון **שם פרטי**, **שם משפחה**, **שם מלא**, **מגדר**, ו **מיקוד**.</span><span class="sxs-lookup"><span data-stu-id="137ce-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="137ce-126">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="137ce-126">Select the segments you want to export.</span></span> <span data-ttu-id="137ce-127">באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- DotDigital.</span><span class="sxs-lookup"><span data-stu-id="137ce-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="137ce-128">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="137ce-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="137ce-129">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="137ce-129">Export the data</span></span>

<span data-ttu-id="137ce-130">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="137ce-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="137ce-131">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="137ce-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="137ce-132">ב- DotDigital, באפשרותך למצוא כעת את הפלחים שלך דרך [פנקסי כתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="137ce-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="137ce-133">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="137ce-133">Known limitations</span></span>

- <span data-ttu-id="137ce-134">עד מיליון פרופילים לייצוא ל- DotDigital.</span><span class="sxs-lookup"><span data-stu-id="137ce-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="137ce-135">הייצוא ל- DotDigital מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="137ce-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="137ce-136">ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 3 שעות בשל מגבלות בצד הספק.</span><span class="sxs-lookup"><span data-stu-id="137ce-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="137ce-137">מספר הפרופילים שתוכל לייצא ל- DotDigital תלוי ומוגבל בחוזה שלך עם DotDigital.</span><span class="sxs-lookup"><span data-stu-id="137ce-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="137ce-138">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="137ce-138">Data privacy and compliance</span></span>

<span data-ttu-id="137ce-139">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל DotDigital, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="137ce-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="137ce-140">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- DotDigital עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="137ce-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="137ce-141">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="137ce-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="137ce-142">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="137ce-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]