---
title: ייצוא נתוני Customer Insights אל Google Ads
description: למד כיצד להגדיר את החיבור ולייצא אל Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759694"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="ab5c0-103">ייצוא פלחים אל Google Ads‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="ab5c0-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="ab5c0-104">יצא פלחים של פרופילי לקוחות מאוחדים אל רשימת קהלים של Google Ads והשתמש בהם כדי לפרסם ב- Google Search‏, Gmail, YouTube, ו- Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="ab5c0-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="ab5c0-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="ab5c0-106">יש לך [חשבון Google Ads](https://ads.google.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ab5c0-107">יש לך [אסימון מפתח Google Ads מאושר](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="ab5c0-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="ab5c0-108">אתה מקיים את הדרישות של [מדיניות התאמת הלקוח](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="ab5c0-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="ab5c0-109">אתה מקיים את הדרישות של [גדלי רשימת שיווק מחדש](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="ab5c0-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="ab5c0-110">קיימים קהלים ב- Google Ads ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="ab5c0-111">למידע נוסף, ראה [קהלי Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="ab5c0-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="ab5c0-112">יש לך [פלחים מוגדרים](segments.md)</span><span class="sxs-lookup"><span data-stu-id="ab5c0-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="ab5c0-113">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדות המייצגים כתובת דוא"ל, שם פרטי ושם משפחה</span><span class="sxs-lookup"><span data-stu-id="ab5c0-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ab5c0-114">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="ab5c0-114">Known limitations</span></span>

- <span data-ttu-id="ab5c0-115">עד מיליון פרופילים לייצוא ל- Google Ads.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="ab5c0-116">הייצוא ל- Google Ads מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="ab5c0-117">ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד חמש דקות בשל מגבלות בצד הספק.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="ab5c0-118">ההתאמה ב- Google Ads יכולה להימשך עד 48 שעות.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="ab5c0-119">הגדרת חיבור אל Google Ads</span><span class="sxs-lookup"><span data-stu-id="ab5c0-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="ab5c0-120">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ab5c0-121">בחר **הוסף חיבור** ובחר **Google Ads** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="ab5c0-122">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ab5c0-123">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ab5c0-124">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ab5c0-125">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-125">Choose who can use this connection.</span></span> <span data-ttu-id="ab5c0-126">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ab5c0-127">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ab5c0-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ab5c0-128">הזן את **[מזהה הלקוח של Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="ab5c0-129">הזן את **[אסימון המפתח המאושר של Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="ab5c0-130">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ab5c0-131">בחר **בצע אימות באמצעות Google Ads** וספק את אישורי Google Ads שלך.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="ab5c0-132">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ab5c0-133">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ab5c0-134">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="ab5c0-134">Configure an export</span></span>

<span data-ttu-id="ab5c0-135">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ab5c0-136">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ab5c0-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ab5c0-137">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ab5c0-138">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ab5c0-139">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Google Ads.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="ab5c0-140">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ab5c0-141">הזן את **[מזהה קהל Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ובחר **התחבר** כדי לאתחל את החיבור אל Google Ads.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="ab5c0-142">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ab5c0-143">חזור על אותם שלבים עבור השדות **שם פרטי** ו **שם משפחה**.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="ab5c0-144">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-144">Select the segments you want to export.</span></span> <span data-ttu-id="ab5c0-145">באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Google Ads.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="ab5c0-146">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ab5c0-147">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ab5c0-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ab5c0-148">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ab5c0-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ab5c0-149">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="ab5c0-149">Data privacy and compliance</span></span>

<span data-ttu-id="ab5c0-150">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Google Ads, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ab5c0-151">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Google Ads עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ab5c0-152">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ab5c0-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ab5c0-153">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="ab5c0-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
