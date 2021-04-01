---
title: התקנה וקביעת תצורה של תוספת כרטיס הלקוח
description: התקן והגדר את תוספת כרטיס לקוח ל- Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f3c4a01f9ce7749eeee72f7901620dae7cb9b8d3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597328"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="a8218-103">תוספת כרטיס לקוח (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="a8218-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a8218-104">קבל תצוגה של 360 מעלות של הלקוחות שלך ישירות ביישומי Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a8218-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="a8218-105">הצג דמוגרפיה, תובנות וצירי זמן של פעילויות בעזרת תוספת כרטיס הלקוח.</span><span class="sxs-lookup"><span data-stu-id="a8218-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a8218-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="a8218-106">Prerequisites</span></span>

- <span data-ttu-id="a8218-107">יישום Dynamics 365 (כגון מרכז המכירות או מרכז שירות לקוחות), גרסה 9.0 ואילך עם הפעלת ממשק מאוחד.</span><span class="sxs-lookup"><span data-stu-id="a8218-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="a8218-108">פרופילי לקוחות [שנקלטו מיישום Dynamics 365 באמצעות Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a8218-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="a8218-109">יש [להוסיף כמשתמשים](permissions.md) את המשתמשים ב'תוספת כרטיס לקוח' ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="a8218-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="a8218-110">[יכולות חיפוש וסינון מוגדרות](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="a8218-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="a8218-111">שליטה דמוגרפית: שדות דמוגרפיים (כגון גיל או מגדר) זמינים בפרופיל הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="a8218-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="a8218-112">פקד העשרה: דורש [העשרות](enrichment-hub.md) פעילות שחלות על פרופילי לקוחות.</span><span class="sxs-lookup"><span data-stu-id="a8218-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="a8218-113">בקרת בינה: דורש נתונים שנוצרו באמצעות Azure Machine Learning ([חיזויים](predictions.md) או [מודלים מותאמים אישית](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="a8218-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="a8218-114">בקרת מדידה: דורש [מדידות מוגדרות](measures.md).</span><span class="sxs-lookup"><span data-stu-id="a8218-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="a8218-115">בקרת ציר הזמן: דורש [פעילויות מוגדרות](activities.md).</span><span class="sxs-lookup"><span data-stu-id="a8218-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="a8218-116">התקן את תוספת כרטיס הלקוח</span><span class="sxs-lookup"><span data-stu-id="a8218-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="a8218-117">התוספת של כרטיס הלקוחות היא פתרון ליישומי Customer Engagement ב- Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a8218-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="a8218-118">להתקנת הפתרון, עבור אל AppSource וחפש את **כרטיס לקוח של Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="a8218-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="a8218-119">בחר את [תוספת כרטיס הלקוח ב- AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ובחר **השג אותה כעת**.</span><span class="sxs-lookup"><span data-stu-id="a8218-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="a8218-120">יתכן שתצטרך להתחבר עם אישורי הניהול שלך ליישום Dynamics 365 כדי להתקין את הפתרון.</span><span class="sxs-lookup"><span data-stu-id="a8218-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="a8218-121">ייתכן שייקח זמן להתקין את הפתרון בסביבה שלך.</span><span class="sxs-lookup"><span data-stu-id="a8218-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="a8218-122">קביעת תהצורה של תוספת כרטיס הלקוח</span><span class="sxs-lookup"><span data-stu-id="a8218-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="a8218-123">כמנהל מערכת, עבור למקטע **הגדרות** ב- Dynamics 365 ובחר **פתרונות**.</span><span class="sxs-lookup"><span data-stu-id="a8218-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="a8218-124">בחר את הקישור **שם תצוגה** עבור הפתרון **תוספת כרטיס לקוח (תצוגה מקדימה) של Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="a8218-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a8218-125">![‏‏בחר שם תצוגה](media/select-display-name.png "‏‏בחר שם תצוגה")</span><span class="sxs-lookup"><span data-stu-id="a8218-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="a8218-126">בחר **היכנס** והזן את האישורים עבור חשבון המנהל שאתה משתמש בו כדי לקבוע את תצורת Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a8218-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="a8218-127">בדוק שחוסם הפריטים המוקפצים של הדפדפן אינו חוסם את חלון האימות בעת בחירת לחצן **היכנס**.</span><span class="sxs-lookup"><span data-stu-id="a8218-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="a8218-128">בחר את הסביבה שממנה ברצונך להביא נתונים.</span><span class="sxs-lookup"><span data-stu-id="a8218-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="a8218-129">הגדר את מיפוי השדה לרשומות ביישום Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a8218-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="a8218-130">למיפוי עם איש קשר, בחר את השדה בישות 'לקוח' התואם למזהה של ישות איש הקשר שלך.</span><span class="sxs-lookup"><span data-stu-id="a8218-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="a8218-131">למיפוי עם תיק לקוח, בחר את השדה בישות 'לקוח' התואם למזהה של ישות תיק הלקוח שלך.</span><span class="sxs-lookup"><span data-stu-id="a8218-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a8218-132">![שדה מזהה איש קשר](media/contact-id-field.png "שדה מזהה איש קשר")</span><span class="sxs-lookup"><span data-stu-id="a8218-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="a8218-133">בחר **שמור תצורה** כדי לשמור את ההגדרות.</span><span class="sxs-lookup"><span data-stu-id="a8218-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="a8218-134">בשלב הבא עליך להקצות תפקידי אבטחה ב- Dynamics 365 כדי שמשתמשים יוכלו להתאים אישית את כרטיס הלקוח ולראות אותו.</span><span class="sxs-lookup"><span data-stu-id="a8218-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="a8218-135">ב- Dynamics 365, עבור אל **הגדרות** > **אבטחה** > **משתמשים**.</span><span class="sxs-lookup"><span data-stu-id="a8218-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="a8218-136">בחר את המשתמשים כדי לערוך תפקידי משתמשים ובחר **ניהול תפקידים**.</span><span class="sxs-lookup"><span data-stu-id="a8218-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="a8218-137">הקצה את התפקיד **מבצע התאמה אישית של כרטיס Customer Insights** למשתמשים שיבצעו התאמה של התוכן המוצג בכרטיס לכל הארגון.</span><span class="sxs-lookup"><span data-stu-id="a8218-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="a8218-138">הוספת פקדי 'כרטיס לקוח' לטפסים</span><span class="sxs-lookup"><span data-stu-id="a8218-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="a8218-139">כדי להוסיף את פקדי כרטיס הלקוח לטופס יצירת הקשר שלך, עבור אל **הגדרות** > **התאמות אישיות** ב- Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a8218-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="a8218-140">בחר **התאמה אישית של המערכת**.</span><span class="sxs-lookup"><span data-stu-id="a8218-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="a8218-141">עבור אל הישות **איש קשר**, הרחב אותה ובחר **טפסים**.</span><span class="sxs-lookup"><span data-stu-id="a8218-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="a8218-142">בחר בטופס יצירת הקשר שאליו ברצונך להוסיף את הפקדים של כרטיס לקוח.</span><span class="sxs-lookup"><span data-stu-id="a8218-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="a8218-143">![בחירת טופס של איש קשר](media/contact-active-forms.png "בחירת טופס של איש קשר")</span><span class="sxs-lookup"><span data-stu-id="a8218-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="a8218-144">כדי להוסיף פקד, בעורך הטפסים, גרור שדה כלשהו מ **סייר השדות** אל המקום שבו ברצונך שהפקד יופיע.</span><span class="sxs-lookup"><span data-stu-id="a8218-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="a8218-145">בחר את השדה בטופס שהוספת זה עתה ובחר **שינוי מאפיינים**.</span><span class="sxs-lookup"><span data-stu-id="a8218-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="a8218-146">עבור אל הכרטיסיה **פקדים** ובחר **הוסף פקד**.</span><span class="sxs-lookup"><span data-stu-id="a8218-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="a8218-147">בחר אחד מהפקדים המותאמים אישית הזמינים ובחר **הוסף**.</span><span class="sxs-lookup"><span data-stu-id="a8218-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="a8218-148">בתיבת הדו **מאפייני שדה**, נקה את תיבת הסימון **הצג תווית בטופס**.</span><span class="sxs-lookup"><span data-stu-id="a8218-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="a8218-149">בחר באפשרות **אינטרנט** עבור הפקד.</span><span class="sxs-lookup"><span data-stu-id="a8218-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="a8218-150">לפקד העשרה, בחר את סוג ההעשרה שברצונך להציג על ידי הגדרת שדה **סוג העשרה**.</span><span class="sxs-lookup"><span data-stu-id="a8218-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="a8218-151">הוסף בקרת העשרה נפרדת לכל סוג העשרה.</span><span class="sxs-lookup"><span data-stu-id="a8218-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="a8218-152">בחר **שמור** ו **פרסם** כדי לפרסם את טופס יצירת הקשר המעודכן.</span><span class="sxs-lookup"><span data-stu-id="a8218-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="a8218-153">עבור אל טופס יצירת הקשר שפורסם.</span><span class="sxs-lookup"><span data-stu-id="a8218-153">Go to the published contact form.</span></span> <span data-ttu-id="a8218-154">תראה את הפקד החדש שהתווסף.</span><span class="sxs-lookup"><span data-stu-id="a8218-154">You'll see the newly added control.</span></span> <span data-ttu-id="a8218-155">ייתכן שיהיה עליך לבצע כניסה בפעם הראשונה שתשתמש בו.</span><span class="sxs-lookup"><span data-stu-id="a8218-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="a8218-156">כדי להתאים אישית את מה שברצונך להציג בפקד המותאם אישית, בחר את לחצן העריכה בפינה הימנית העליונה.</span><span class="sxs-lookup"><span data-stu-id="a8218-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="a8218-157">שדרוג של תוספת כרטיס לקוח</span><span class="sxs-lookup"><span data-stu-id="a8218-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="a8218-158">'תוספת כרטיס הלקוח' אינה משודרגת באופן אוטומטי.</span><span class="sxs-lookup"><span data-stu-id="a8218-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="a8218-159">כדי לשדרג לגירסה האחרונה, בצע הליך זה ביישום Dynamics 365 שמותקנת בו התוספת.</span><span class="sxs-lookup"><span data-stu-id="a8218-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="a8218-160">ביישום Dynamics 365, עבור אל **הגדרות** > **התאמה אישית** ובחר **פתרונות**.</span><span class="sxs-lookup"><span data-stu-id="a8218-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="a8218-161">בטבלת התוספות, חפש את **CustomerInsightsCustomerCard** ובחר את השורה.</span><span class="sxs-lookup"><span data-stu-id="a8218-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="a8218-162">בחר את **החל שדרוג פתרון** בסרגל הפעולות.</span><span class="sxs-lookup"><span data-stu-id="a8218-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="שדרג את הפתרון באזור ההתאמה האישית של יישומי Dynamics 365":::

1. <span data-ttu-id="a8218-164">לאחר הפעלת תהליך השדרוג, תראה מחוון טעינה עד לסיום השדרוג.</span><span class="sxs-lookup"><span data-stu-id="a8218-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="a8218-165">אם אין גרסה חדשה יותר, השדרוג יציג הודעת שגיאה.</span><span class="sxs-lookup"><span data-stu-id="a8218-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]