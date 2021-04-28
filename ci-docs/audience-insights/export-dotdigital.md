---
title: ייצוא נתוני Customer Insights אל DotDigital
description: למד כיצד להגדיר את החיבור ולייצא אל DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 235bcdfa4a7c4c1a382778bd4f66c1a9f5b7beb1
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759960"
---
# <a name="export-segment-lists-to-dotdigital-preview"></a><span data-ttu-id="43c13-103">ייצוא רשימות פלחים אל DotDigital‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="43c13-103">Export segment lists to DotDigital (preview)</span></span>

<span data-ttu-id="43c13-104">יצא פלחים של פרופילי לקוחות מאוחדים אל פנקסי הכתובות של DotDigital והשתמש בהם עבור קמפיינים, שיווק בדוא"ל ולבניית פלחי לקוחות עם DotDigital.</span><span class="sxs-lookup"><span data-stu-id="43c13-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="43c13-105">דרישות מוקדמות לחיבור</span><span class="sxs-lookup"><span data-stu-id="43c13-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="43c13-106">יש לך [חשבון DotDigital](https://dotdigital.com/) ואישורי מנהל מערכת מתאימים.</span><span class="sxs-lookup"><span data-stu-id="43c13-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="43c13-107">קיימים פנקסי כתובות ב- DotDigital ומזהים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="43c13-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="43c13-108">ניתן למצוא את המזהה בכתובת ה- URL כאשר אתה בוחר ופותח פנקס כתובות.</span><span class="sxs-lookup"><span data-stu-id="43c13-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="43c13-109">לקבלת מידע נוסף, ראה [פנקסי כתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="43c13-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="43c13-110">יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="43c13-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="43c13-111">פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.</span><span class="sxs-lookup"><span data-stu-id="43c13-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="43c13-112">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="43c13-112">Known limitations</span></span>

- <span data-ttu-id="43c13-113">עד מיליון פרופילים לייצוא ל- DotDigital.</span><span class="sxs-lookup"><span data-stu-id="43c13-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="43c13-114">הייצוא ל- DotDigital מוגבל לפלחים.</span><span class="sxs-lookup"><span data-stu-id="43c13-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="43c13-115">ייצוא פלחים עם מיליון פרופילים בסך הכל עשוי להימשך עד 3 שעות בשל מגבלות בצד הספק.</span><span class="sxs-lookup"><span data-stu-id="43c13-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="43c13-116">מספר הפרופילים שתוכל לייצא ל- DotDigital תלוי ומוגבל בחוזה שלך עם DotDigital.</span><span class="sxs-lookup"><span data-stu-id="43c13-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="43c13-117">הגדרת חיבור אל DotDigital</span><span class="sxs-lookup"><span data-stu-id="43c13-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="43c13-118">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="43c13-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="43c13-119">בחר **הוסף חיבור** ובחר **DotDigital** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="43c13-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="43c13-120">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="43c13-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="43c13-121">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="43c13-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="43c13-122">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="43c13-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="43c13-123">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="43c13-123">Choose who can use this connection.</span></span> <span data-ttu-id="43c13-124">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="43c13-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="43c13-125">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="43c13-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="43c13-126">הזן את **שם המשתמש והסיסמה של DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="43c13-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="43c13-127">הזן את **[מזהה פנקס הכתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="43c13-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="43c13-128">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="43c13-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="43c13-129">בחר **התחבר** כדי לאתחל את החיבור אל DotDigital.</span><span class="sxs-lookup"><span data-stu-id="43c13-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="43c13-130">בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="43c13-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="43c13-131">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="43c13-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="43c13-132">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="43c13-132">Configure an export</span></span>

<span data-ttu-id="43c13-133">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="43c13-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="43c13-134">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="43c13-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="43c13-135">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="43c13-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="43c13-136">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="43c13-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="43c13-137">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע DotDigital.</span><span class="sxs-lookup"><span data-stu-id="43c13-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="43c13-138">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="43c13-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="43c13-139">במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח.</span><span class="sxs-lookup"><span data-stu-id="43c13-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="43c13-140">חזור על אותם שלבים עבור שדות אופציונליים אחרים כגון **שם פרטי**, **שם משפחה**, **שם מלא**, **מגדר**, ו **מיקוד**.</span><span class="sxs-lookup"><span data-stu-id="43c13-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="43c13-141">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="43c13-141">Select the segments you want to export.</span></span> <span data-ttu-id="43c13-142">באפשרותך לייצא עד מיליון פרופילי לקוחות בסך הכל ל- DotDigital.</span><span class="sxs-lookup"><span data-stu-id="43c13-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="43c13-143">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="43c13-143">Select **Save**.</span></span>

<span data-ttu-id="43c13-144">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="43c13-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="43c13-145">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="43c13-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="43c13-146">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="43c13-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="43c13-147">ב- DotDigital, באפשרותך למצוא כעת את הפלחים שלך דרך [פנקסי כתובות של DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="43c13-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="43c13-148">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="43c13-148">Data privacy and compliance</span></span>

<span data-ttu-id="43c13-149">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל DotDigital, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="43c13-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="43c13-150">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- DotDigital עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="43c13-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="43c13-151">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="43c13-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="43c13-152">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="43c13-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
