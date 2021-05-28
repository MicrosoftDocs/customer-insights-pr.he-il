---
title: תוספת כרטיס לקוח עבור יישומי Dynamics 365
description: הצג נתונים מתובנות לגבי קהלים ביישומי Dynamics 365 באמצעות תוספת זו.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059589"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="8d57d-103">תוספת כרטיס לקוח (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="8d57d-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="8d57d-104">קבל תצוגה של 360 מעלות של הלקוחות שלך ישירות ביישומי Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8d57d-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="8d57d-105">כאשר התוספת 'כרטיס לקוח' מותקנת ביישום נתמך של Dynamics 365, אתה יכול לבחור להציג נתונים דמוגרפיים, תובנות וצירי זמן של פעילויות.</span><span class="sxs-lookup"><span data-stu-id="8d57d-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="8d57d-106">התוספת תשלוף נתונים מ- Customer Insights מבלי להשפיע על הנתונים ביישום המחובר של Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8d57d-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="8d57d-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="8d57d-107">Prerequisites</span></span>

- <span data-ttu-id="8d57d-108">התוספת פועלת רק עם יישומים מונחי דגמים של Dynamics 365, כגון Sales או Customer Service, גירסה 9.0 ואילך.</span><span class="sxs-lookup"><span data-stu-id="8d57d-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="8d57d-109">על מנת שיתבצע מיפוי של נתוני Dynamics 365 לפרופילי הלקוח של תובנות לגבי קהלים, יש [לעבד אותם מיישום Dynamics 365 באמצעות המחבר Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="8d57d-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="8d57d-110">כל משתמשי Dynamics 365 של התוספת 'כרטיס לקוח' צריכים [להתווסף כמשתמשים](permissions.md) בתובנות לגבי קהלים כדי לראות את הנתונים.</span><span class="sxs-lookup"><span data-stu-id="8d57d-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="8d57d-111">[יכולות חיפוש וסינון מוגדרות](search-filter-index.md) בתובנות לגבי קהלים נדרשות על מנת שבדיקת המידע של נתונים תפעל.</span><span class="sxs-lookup"><span data-stu-id="8d57d-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="8d57d-112">כל בקרת תוספת מסתמכת על נתונים ספציפיים בתובנות לגבי קהלים:</span><span class="sxs-lookup"><span data-stu-id="8d57d-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="8d57d-113">בקרת מדידה: דורש [מדידות מוגדרות](measures.md).</span><span class="sxs-lookup"><span data-stu-id="8d57d-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="8d57d-114">בקרת בינה: מחייבת נתונים שנוצרו באמצעות [תחזיות](predictions.md) או [מודלים מותאמים אישית](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="8d57d-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="8d57d-115">שליטה דמוגרפית: שדות דמוגרפיים (כגון גיל או מגדר) זמינים בפרופיל הלקוח המאוחד.</span><span class="sxs-lookup"><span data-stu-id="8d57d-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="8d57d-116">פקד העשרה: דורש [העשרות](enrichment-hub.md) פעילות שחלות על פרופילי לקוחות.</span><span class="sxs-lookup"><span data-stu-id="8d57d-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="8d57d-117">בקרת ציר הזמן: דורש [פעילויות מוגדרות](activities.md).</span><span class="sxs-lookup"><span data-stu-id="8d57d-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="8d57d-118">התקן את תוספת כרטיס הלקוח</span><span class="sxs-lookup"><span data-stu-id="8d57d-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="8d57d-119">התוספת של כרטיס הלקוחות היא פתרון ליישומי Customer Engagement ב- Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8d57d-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="8d57d-120">להתקנת הפתרון, עבור אל AppSource וחפש את **כרטיס לקוח של Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="8d57d-121">בחר את [תוספת כרטיס הלקוח ב- AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) ובחר **השג אותה כעת**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="8d57d-122">יתכן שתצטרך להתחבר עם אישורי הניהול שלך ליישום Dynamics 365 כדי להתקין את הפתרון.</span><span class="sxs-lookup"><span data-stu-id="8d57d-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="8d57d-123">ייתכן שייקח זמן להתקין את הפתרון בסביבה שלך.</span><span class="sxs-lookup"><span data-stu-id="8d57d-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="8d57d-124">קביעת תהצורה של תוספת כרטיס הלקוח</span><span class="sxs-lookup"><span data-stu-id="8d57d-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="8d57d-125">כמנהל מערכת, עבור למקטע **הגדרות** ב- Dynamics 365 ובחר **פתרונות**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="8d57d-126">בחר את הקישור **שם תצוגה** עבור הפתרון **תוספת כרטיס לקוח (תצוגה מקדימה) של Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d57d-127">![‏‏בחר שם תצוגה](media/select-display-name.png "‏‏בחר שם תצוגה")</span><span class="sxs-lookup"><span data-stu-id="8d57d-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="8d57d-128">בחר **היכנס** והזן את האישורים עבור חשבון המנהל שאתה משתמש בו כדי לקבוע את תצורת Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8d57d-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8d57d-129">בדוק שחוסם הפריטים המוקפצים של הדפדפן אינו חוסם את חלון האימות בעת בחירת לחצן **היכנס**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="8d57d-130">בחר את הסביבה של Customer Insights שממנה ברצונך להביא נתונים.</span><span class="sxs-lookup"><span data-stu-id="8d57d-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="8d57d-131">הגדר את מיפוי השדות לרשומות ביישום Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8d57d-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="8d57d-132">בהתאם לנתונים שלך ב- Customer Insights תוכל לבחור למפות את האפשרויות הבאות:</span><span class="sxs-lookup"><span data-stu-id="8d57d-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="8d57d-133">למיפוי עם איש קשר, בחר את השדה בישות 'לקוח' התואם למזהה של ישות איש הקשר שלך.</span><span class="sxs-lookup"><span data-stu-id="8d57d-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="8d57d-134">למיפוי עם תיק לקוח, בחר את השדה בישות 'לקוח' התואם למזהה של ישות תיק הלקוח שלך.</span><span class="sxs-lookup"><span data-stu-id="8d57d-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8d57d-135">![שדה מזהה איש קשר](media/contact-id-field.png "שדה מזהה איש קשר")</span><span class="sxs-lookup"><span data-stu-id="8d57d-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="8d57d-136">בחר **שמור תצורה** כדי לשמור את ההגדרות.</span><span class="sxs-lookup"><span data-stu-id="8d57d-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="8d57d-137">בשלב הבא עליך להקצות תפקידי אבטחה ב- Dynamics 365 כדי שמשתמשים יוכלו להתאים אישית את כרטיס הלקוח ולראות אותו.</span><span class="sxs-lookup"><span data-stu-id="8d57d-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="8d57d-138">ב- Dynamics 365, עבור אל **הגדרות** > **אבטחה** > **משתמשים**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="8d57d-139">בחר את המשתמשים כדי לערוך תפקידי משתמשים ובחר **ניהול תפקידים**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="8d57d-140">הקצה את התפקיד **מבצע התאמה אישית של כרטיס Customer Insights** למשתמשים שיבצעו התאמה של התוכן המוצג בכרטיס לכל הארגון.</span><span class="sxs-lookup"><span data-stu-id="8d57d-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="8d57d-141">הוספת פקדי 'כרטיס לקוח' לטפסים</span><span class="sxs-lookup"><span data-stu-id="8d57d-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="8d57d-142">כדי להוסיף את פקדי כרטיס הלקוח לטופס יצירת הקשר שלך, עבור אל **הגדרות** > **התאמות אישיות** ב- Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="8d57d-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="8d57d-143">בחר **התאמה אישית של המערכת**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="8d57d-144">עבור אל הישות **איש קשר**, הרחב אותה ובחר **טפסים**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="8d57d-145">בחר בטופס יצירת הקשר שאליו ברצונך להוסיף את הפקדים של כרטיס לקוח.</span><span class="sxs-lookup"><span data-stu-id="8d57d-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="8d57d-146">![בחירת טופס של איש קשר](media/contact-active-forms.png "בחירת טופס של איש קשר")</span><span class="sxs-lookup"><span data-stu-id="8d57d-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="8d57d-147">כדי להוסיף פקד, בעורך הטפסים, גרור שדה כלשהו מ **סייר השדות** אל המקום שבו ברצונך שהפקד יופיע.</span><span class="sxs-lookup"><span data-stu-id="8d57d-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="8d57d-148">בחר את השדה בטופס שהוספת זה עתה ובחר **שינוי מאפיינים**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="8d57d-149">עבור אל הכרטיסיה **פקדים** ובחר **הוסף פקד**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="8d57d-150">בחר אחד מהפקדים המותאמים אישית הזמינים ובחר **הוסף**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="8d57d-151">בתיבת הדו **מאפייני שדה**, נקה את תיבת הסימון **הצג תווית בטופס**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="8d57d-152">בחר באפשרות **אינטרנט** עבור הפקד.</span><span class="sxs-lookup"><span data-stu-id="8d57d-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="8d57d-153">לפקד העשרה, בחר את סוג ההעשרה שברצונך להציג על ידי הגדרת שדה **סוג העשרה**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="8d57d-154">הוסף בקרת העשרה נפרדת לכל סוג העשרה.</span><span class="sxs-lookup"><span data-stu-id="8d57d-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="8d57d-155">בחר **שמור** ו **פרסם** כדי לפרסם את טופס יצירת הקשר המעודכן.</span><span class="sxs-lookup"><span data-stu-id="8d57d-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="8d57d-156">עבור אל טופס יצירת הקשר שפורסם.</span><span class="sxs-lookup"><span data-stu-id="8d57d-156">Go to the published contact form.</span></span> <span data-ttu-id="8d57d-157">תראה את הפקד החדש שהתווסף.</span><span class="sxs-lookup"><span data-stu-id="8d57d-157">You'll see the newly added control.</span></span> <span data-ttu-id="8d57d-158">ייתכן שיהיה עליך לבצע כניסה בפעם הראשונה שתשתמש בו.</span><span class="sxs-lookup"><span data-stu-id="8d57d-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="8d57d-159">כדי להתאים אישית את מה שברצונך להציג בפקד המותאם אישית, בחר את לחצן העריכה בפינה הימנית העליונה.</span><span class="sxs-lookup"><span data-stu-id="8d57d-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="8d57d-160">שדרוג של תוספת כרטיס לקוח</span><span class="sxs-lookup"><span data-stu-id="8d57d-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="8d57d-161">'תוספת כרטיס הלקוח' אינה משודרגת באופן אוטומטי.</span><span class="sxs-lookup"><span data-stu-id="8d57d-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="8d57d-162">כדי לשדרג לגירסה האחרונה, בצע הליך זה ביישום Dynamics 365 שמותקנת בו התוספת.</span><span class="sxs-lookup"><span data-stu-id="8d57d-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="8d57d-163">ביישום Dynamics 365, עבור אל **הגדרות** > **התאמה אישית** ובחר **פתרונות**.</span><span class="sxs-lookup"><span data-stu-id="8d57d-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="8d57d-164">בטבלת התוספות, חפש את **CustomerInsightsCustomerCard** ובחר את השורה.</span><span class="sxs-lookup"><span data-stu-id="8d57d-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="8d57d-165">בחר את **החל שדרוג פתרון** בסרגל הפעולות.</span><span class="sxs-lookup"><span data-stu-id="8d57d-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="שדרג את הפתרון באזור ההתאמה האישית של יישומי Dynamics 365":::

1. <span data-ttu-id="8d57d-167">לאחר הפעלת תהליך השדרוג, תראה מחוון טעינה עד לסיום השדרוג.</span><span class="sxs-lookup"><span data-stu-id="8d57d-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="8d57d-168">אם אין גרסה חדשה יותר, השדרוג יציג הודעת שגיאה.</span><span class="sxs-lookup"><span data-stu-id="8d57d-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
