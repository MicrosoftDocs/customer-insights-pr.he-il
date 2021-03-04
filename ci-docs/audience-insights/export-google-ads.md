---
title: ייצוא נתוני Customer Insights אל Google Ads
description: למד כיצד לקבוע את תצורת החיבור אל Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268963"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="f6f8f-103">מחבר עבור Google Ads‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="f6f8f-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="f6f8f-104">יצא פלחים של פרופילי לקוחות מאוחדים אל רשימת קהלים של Google Ads והשתמש בהם כדי לפרסם ב- Google Search‏, Gmail, YouTube, ו- Google Display Network.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="f6f8f-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="f6f8f-105">Prerequisites</span></span>

-   <span data-ttu-id="f6f8f-106">יש לך [חשבון Google Ads](https://ads.google.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f6f8f-107">קיימים קהלים ב- Google Ads ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="f6f8f-108">למידע נוסף, ראה [קהלי Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="f6f8f-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="f6f8f-109">יש לך [פלחים מוגדרים](segments.md)</span><span class="sxs-lookup"><span data-stu-id="f6f8f-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="f6f8f-110">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדות המייצגים כתובת דוא"ל, שם פרטי ושם משפחה</span><span class="sxs-lookup"><span data-stu-id="f6f8f-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="f6f8f-111">התחבר ל- Google Ads</span><span class="sxs-lookup"><span data-stu-id="f6f8f-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="f6f8f-112">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f6f8f-113">תחת **Google Ads**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="f6f8f-114">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f6f8f-115">הזן את **[מזהה הלקוח של Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="f6f8f-116">הזן את **[אסימון המפתח המאושר של Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="f6f8f-117">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f6f8f-118">הזן את **[מזהה קהל Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** ובחר **התחבר** כדי לאתחל את החיבור אל Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="f6f8f-119">בחר **בצע אימות באמצעות Google Ads** וספק את אישורי Google Ads שלך.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="f6f8f-120">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="יצא צילום מסך עבור חיבור Google Ads":::

1. <span data-ttu-id="f6f8f-122">בחר **הבא** להגדרת התצורה של הייצוא.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f6f8f-123">קביעת תצורת המחבר</span><span class="sxs-lookup"><span data-stu-id="f6f8f-123">Configure the connector</span></span>

1. <span data-ttu-id="f6f8f-124">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f6f8f-125">חזור על אותם שלבים עבור השדות **שם פרטי** ו **שם משפחה**.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="f6f8f-126">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-126">Select the segments you want to export.</span></span> <span data-ttu-id="f6f8f-127">באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="f6f8f-128">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f6f8f-129">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="f6f8f-129">Export the data</span></span>

<span data-ttu-id="f6f8f-130">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f6f8f-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f6f8f-131">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f6f8f-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f6f8f-132">ב- Google Ads, באפשרותך למצוא כעת את הפלחים שלך תחת [קהלי Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="f6f8f-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f6f8f-133">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="f6f8f-133">Known limitations</span></span>

- <span data-ttu-id="f6f8f-134">עד מיליון פרופילים לייצוא ל- Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="f6f8f-135">הייצוא ל- Google Ads מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="f6f8f-136">ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד חמש דקות בשל מגבלות בצד הספק.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="f6f8f-137">ההתאמה ב- Google Ads יכולה להימשך עד 48 שעות.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f6f8f-138">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="f6f8f-138">Data privacy and compliance</span></span>

<span data-ttu-id="f6f8f-139">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל Google Ads, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f6f8f-140">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- Google Ads עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f6f8f-141">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f6f8f-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f6f8f-142">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="f6f8f-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]