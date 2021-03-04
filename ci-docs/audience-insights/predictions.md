---
title: השלמת נתונים חלקיים באמצעות חיזויים
description: השתמש בחיזויים כדי למלא נתוני לקוחות לא שלמים.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 577232c7e901dfd54a195c3e9cfac5d1f0f866e6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268273"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="99a32-103">השלמת הנתונים החלקיים שלך באמצעות חיזויים</span><span class="sxs-lookup"><span data-stu-id="99a32-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="99a32-104">חיזויים מאפשרים לך ליצור בקלות ערכים חזויים שיכולים לשפר את ההבנה שלך את הלקוח.</span><span class="sxs-lookup"><span data-stu-id="99a32-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="99a32-105">בדף **בינה** > **חיזויים**, באפשרותך לבחור **החיזויים שלי** כדי לראות חיזויים שהגדרת בחלקים אחרים של Audience Insights, ולהתאים אותם אישית עוד יותר.</span><span class="sxs-lookup"><span data-stu-id="99a32-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="99a32-106">אינך יכול להשתמש בתכונה זו אם הסביבה שלך משתמשת באחסון Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="99a32-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="99a32-107">תכונת החיזויים משתמשת באמצעים אוטומטיים כדי להעריך נתונים ולבצע תחזיות על סמך נתונים אלה, ולכן יש לה את היכולת לשמש כשיטה ליצירת פרופיל, שכן מונח זה מוגדר על ידי התקנה הכללית להגנה על נתונים ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="99a32-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="99a32-108">השימוש של הלקוח בתכונה זו לעיבוד נתונים עשוי להיות כפוף ל- GDPR או לחוקים ותקנות אחרים.</span><span class="sxs-lookup"><span data-stu-id="99a32-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="99a32-109">אתה אחראי להבטיח שהשימוש שלך ב- Dynamics 365 Customer Insights, כולל חיזויים, תואם לכל החוקים והתקנות החלים, כולל חוקים הקשורים לפרטיות, נתונים אישיים, נתונים ביומטריים, הגנה על נתונים וסודיות תקשורת.</span><span class="sxs-lookup"><span data-stu-id="99a32-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="99a32-110">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="99a32-110">Prerequisites</span></span>

<span data-ttu-id="99a32-111">לפני שהארגון שלך יוכל להשתמש בתכונת החיזויים, ודא שמתקיימים התנאים המוקדמים הבאים:</span><span class="sxs-lookup"><span data-stu-id="99a32-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="99a32-112">לארגון שלך יש מופע [הגדרה ב- Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) והוא באותו ארגון כשל Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="99a32-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="99a32-113">הסביבה שלך קשורה למופע Common Data Service שלך.</span><span class="sxs-lookup"><span data-stu-id="99a32-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="99a32-114">אם אתה [יוצר סביבה חדשה](manage-environments.md), הגדר אותה בתיבת הדו-שיח **צור סביבה** ובחר **מתקדם**.</span><span class="sxs-lookup"><span data-stu-id="99a32-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="99a32-115">אם כבר יצרת סביבה, עבור להגדרות שלה ובחר **מתקדם**.</span><span class="sxs-lookup"><span data-stu-id="99a32-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="99a32-116">כך או כך, במקטע **השתמש בחיזויים**, הזן את כתובת ה- URL של מופע Common Data Service שאליו ברצונך לצרף את הסביבה שלך.</span><span class="sxs-lookup"><span data-stu-id="99a32-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="99a32-117">יצירת חיזוי בישות 'לקוח'</span><span class="sxs-lookup"><span data-stu-id="99a32-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="99a32-118">ב- audience insights, עבור אל **נתונים** > **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="99a32-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="99a32-119">בחר את הישות **לקוח**.</span><span class="sxs-lookup"><span data-stu-id="99a32-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="99a32-120">בישות **Customer: CustomerInsights** בחר בכרטיסיה **שדות**.</span><span class="sxs-lookup"><span data-stu-id="99a32-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="99a32-121">מצא את שם המאפיין שלגביו ברצונך לחזות ערכים, ובחר בסמל **סקירה כללית** בעמודה **סיכום**.</span><span class="sxs-lookup"><span data-stu-id="99a32-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99a32-122">![סמל סקירה כללית](media/intelligence-overviewicon.png "סמל סקירה כללית")</span><span class="sxs-lookup"><span data-stu-id="99a32-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="99a32-123">אם יש שיעור גבוה של ערכים חסרים בתכונה שלך, בחר **חזה ערכים חסרים** כדי להמשיך בחיזוי שלך.</span><span class="sxs-lookup"><span data-stu-id="99a32-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99a32-124">![מצב סקירה עם לחצן ערכים חסרים שמופיע](media/intelligence-overviewpredictmissingvalues.png "מצב סקירה עם לחצן ערכים חסרים שמופיע")</span><span class="sxs-lookup"><span data-stu-id="99a32-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="99a32-125">ספק **שם תצוגה** ו **שם ישות פלט** לתוצאות החיזוי.</span><span class="sxs-lookup"><span data-stu-id="99a32-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="99a32-126">רשימת אפשרויות מאוכלסת מראש תציג היכן ניתן למפות את הערכים לקטגוריה חזויה.</span><span class="sxs-lookup"><span data-stu-id="99a32-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="99a32-127">במקרה זה, אפשרויות הקטגוריה היחידות שלך יהיו 0 או 1 כאשר הן ממפות לערך true/false או בינארי של החיזוי.</span><span class="sxs-lookup"><span data-stu-id="99a32-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="99a32-128">בעמודה 'קטגוריה', מפה את ערכי השדות שתרצה לסווג כ- "0" בחיזוי הסופי ל- "0", ואת הפריטים שתרצה לסווג כ-"1" בחיזוי הסופי ל-"1".</span><span class="sxs-lookup"><span data-stu-id="99a32-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99a32-129">![דוגמה המציגה ערכי שדה ממופים לקטגוריות](media/intelligence-categorymapping.png "דוגמה המציגה ערכי שדה ממופים לקטגוריות")</span><span class="sxs-lookup"><span data-stu-id="99a32-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="99a32-130">בחר **בוצע** והחיזוי יעובד.</span><span class="sxs-lookup"><span data-stu-id="99a32-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="99a32-131">העיבוד ייקח זמן מה, תלוי בגודל ובמורכבות הנתונים.</span><span class="sxs-lookup"><span data-stu-id="99a32-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="99a32-132">התוצאות יהיו זמינות ביישות חדשה בהתבסס על **שם ישות פלט** של החיזוי שיצרת.</span><span class="sxs-lookup"><span data-stu-id="99a32-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="99a32-133">צור חיזוי תוך כדי יצירת פלח</span><span class="sxs-lookup"><span data-stu-id="99a32-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="99a32-134">חיזוי ערכים חסרים עבור תכונה ספציפית אפשרי גם בעת יצירת פלח.</span><span class="sxs-lookup"><span data-stu-id="99a32-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="99a32-135">באופן ספציפי, כשאתה יוצר במהירות פלח המבוסס על ישות הלקוח המאוחדת או על ישות Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="99a32-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="99a32-136">כחלק מהתהליך, תבחר תכונה ספציפית שתבסס עליה את הפלח, כגון שביעות רצון לקוחות או סכום רכישה.</span><span class="sxs-lookup"><span data-stu-id="99a32-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="99a32-137">עם יצירת הפלח, המערכת תציע שיטה לחיזוי הערכים החסרים עבור תכונה זו.</span><span class="sxs-lookup"><span data-stu-id="99a32-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="99a32-138">ב- Audience Insights, עבור לדף **פלחים** ובחר את האריח **פרופילים**.</span><span class="sxs-lookup"><span data-stu-id="99a32-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="99a32-139">בחר **שדה** כדי ליצור פלח לפיו ובחר **אופרטור** ואז בחר **סקירה**.</span><span class="sxs-lookup"><span data-stu-id="99a32-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="99a32-140">ספק **שם** ו **שם תצוגה** עבור הפלח.</span><span class="sxs-lookup"><span data-stu-id="99a32-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="99a32-141">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="99a32-141">Select **Save**.</span></span>

5. <span data-ttu-id="99a32-142">אם לפלח שיצרת נתונים לא שלמים בשדה המקור, תוכל לבחור לחזות את הערכים החסרים.</span><span class="sxs-lookup"><span data-stu-id="99a32-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99a32-143">![לחצן חיזוי](media/segments-predictoption.png "לחצן חיזוי")</span><span class="sxs-lookup"><span data-stu-id="99a32-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="99a32-144">ספק **שם תצוגה** ו **שם ישות פלט** לתוצאות החיזוי.</span><span class="sxs-lookup"><span data-stu-id="99a32-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="99a32-145">בחר **סיום**.</span><span class="sxs-lookup"><span data-stu-id="99a32-145">Select **Done**.</span></span> <span data-ttu-id="99a32-146">החיזוי ייווצר בקרוב ביישות חדשה עם השם שסיפקת עבור **שם ישות פלט**.</span><span class="sxs-lookup"><span data-stu-id="99a32-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="99a32-147">הצג חיזוי</span><span class="sxs-lookup"><span data-stu-id="99a32-147">View a prediction</span></span>

1. <span data-ttu-id="99a32-148">ב- audience insights, עבור אל **בינה** > **חיזויים** > **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="99a32-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="99a32-149">בחר בחיזוי שברצונך לבדוק.</span><span class="sxs-lookup"><span data-stu-id="99a32-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="99a32-150">בחר בשלוש הנקודות בעמודה **פעולות** ובחר **הצג**.</span><span class="sxs-lookup"><span data-stu-id="99a32-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="99a32-151">תראה מספר נקודות נתונים בתצוגת החיזוי שלך.</span><span class="sxs-lookup"><span data-stu-id="99a32-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="99a32-152">![דף חיזויים](media/intelligence-predictionsviewpage.png "דף חיזויים")</span><span class="sxs-lookup"><span data-stu-id="99a32-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="99a32-153">**ערכים חזויים** מציג את המיפוי שיצרת בשלב שדה המיפוי של ערכי שדות לקטגוריה.</span><span class="sxs-lookup"><span data-stu-id="99a32-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="99a32-154">אלה הערכים בערכת הנתונים שמופו לקטגוריה ספציפית.</span><span class="sxs-lookup"><span data-stu-id="99a32-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="99a32-155">-**בעלי ההשפעה המובילים** הם גורמים בערכת הנתונים שככל הנראה השפיעו על מהימנות החיזוי של ערך השדות שמופו לקטגוריה מסוימת.</span><span class="sxs-lookup"><span data-stu-id="99a32-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="99a32-156">**ביצועים** מציין כיצד מתקבלים החיזויים.</span><span class="sxs-lookup"><span data-stu-id="99a32-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="99a32-157">למידע נוסף, בחר בקישור.</span><span class="sxs-lookup"><span data-stu-id="99a32-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="99a32-158">**תצוגה מקדימה** מראה דוגמאות של פלט ערכת נתונים מהחיזוי והסבירות, או המהימנות שלנו, לערך החזוי, כאשר 0 אינו בטוח, ו- 1 בטוח.</span><span class="sxs-lookup"><span data-stu-id="99a32-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="99a32-159">עדכן את החיזוי</span><span class="sxs-lookup"><span data-stu-id="99a32-159">Update a prediction</span></span>

1. <span data-ttu-id="99a32-160">ב- audience insights, עבור אל **בינה** > **חיזויים** > **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="99a32-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="99a32-161">בחר את החיזוי שברצונך לעדכן ובחר בסמל **עדכון**.</span><span class="sxs-lookup"><span data-stu-id="99a32-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="99a32-162">החיזוי יתוזמן לעיבוד.</span><span class="sxs-lookup"><span data-stu-id="99a32-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="99a32-163">אתה יכול לראות את השעה שבה הוא עודכן לאחרונה בעמודה **עודכן** בדף **חיזויים**.</span><span class="sxs-lookup"><span data-stu-id="99a32-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="99a32-164">ערוך חיזוי</span><span class="sxs-lookup"><span data-stu-id="99a32-164">Edit a prediction</span></span>

<span data-ttu-id="99a32-165">לאחר שיצרת חיזוי, תוכל להתאים אישית את הדגם ב- AI Builder כדי להגדיל את האפקטיביות של הדגם.</span><span class="sxs-lookup"><span data-stu-id="99a32-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="99a32-166">ב- audience insights, עבור אל **בינה** > **חיזויים** > **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="99a32-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="99a32-167">בחר את החיזוי שברצונך לערוך.</span><span class="sxs-lookup"><span data-stu-id="99a32-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="99a32-168">בחר בשלוש הנקודות בעמודה **פעולות** ובחר **הצג**.</span><span class="sxs-lookup"><span data-stu-id="99a32-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="99a32-169">בחר **התאם אישית ב- AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="99a32-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="99a32-170">עדכן את הדגם שלך ב- AI Builder.</span><span class="sxs-lookup"><span data-stu-id="99a32-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="99a32-171">[למידע נוסף על ניהול דגמים ב-AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="99a32-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="99a32-172">הריצה הבאה של החיזוי תשתמש בדגם המעודכן שיצרת.</span><span class="sxs-lookup"><span data-stu-id="99a32-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="99a32-173">מודלים חדשים שנוצרו ב- AI Builder לא יוצגו ב- Audience Insights, אלא אם כן המודל נוצר מהחוויות המפורטות לעיל.</span><span class="sxs-lookup"><span data-stu-id="99a32-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="99a32-174">הסר חיזוי</span><span class="sxs-lookup"><span data-stu-id="99a32-174">Remove a prediction</span></span>

1. <span data-ttu-id="99a32-175">ב- audience insights, עבור אל **בינה** > **חיזויים** > **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="99a32-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="99a32-176">בחר את החיזוי שברצונך למחוק.</span><span class="sxs-lookup"><span data-stu-id="99a32-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="99a32-177">בחר בשלוש הנקודות בעמודה **פעולות** ובחר **מחק**.</span><span class="sxs-lookup"><span data-stu-id="99a32-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="99a32-178">אשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="99a32-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="99a32-179">פתרון בעיות</span><span class="sxs-lookup"><span data-stu-id="99a32-179">Troubleshooting</span></span>

<span data-ttu-id="99a32-180">אם אינך יכול להשלים את תהליך צירוף Common Data Service עקב שגיאה, תוכל לנסות להשלים את התהליך ידנית.</span><span class="sxs-lookup"><span data-stu-id="99a32-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="99a32-181">קיימות שתי בעיות מוכרות שיכולול להופיע בתהליך הצירוף:</span><span class="sxs-lookup"><span data-stu-id="99a32-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="99a32-182">הפתרון 'תוספת כרטיס לקוח' אינו מותקן.</span><span class="sxs-lookup"><span data-stu-id="99a32-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="99a32-183">השלם את ההוראות עבור [התקנה וקביעת תצורה של הפתרון](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="99a32-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="99a32-184">הרשאות יישום אינן מוענקות.</span><span class="sxs-lookup"><span data-stu-id="99a32-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="99a32-185">עבור אל [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="99a32-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="99a32-186">בחר **סביבות**.</span><span class="sxs-lookup"><span data-stu-id="99a32-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="99a32-187">בחר את שלוש הנקודות לצד הסביבה שברצונך להוסיף את ההרשאה אליה ובחר **הגדרות**.</span><span class="sxs-lookup"><span data-stu-id="99a32-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="99a32-188">הרחב את **משתמשים + הרשאות** ובחר **משתמשים**.</span><span class="sxs-lookup"><span data-stu-id="99a32-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="99a32-189">בחר **+ חדש** ובחר **משתמש**.</span><span class="sxs-lookup"><span data-stu-id="99a32-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="99a32-190">בחר **משתמש ביישום** אם הוא עדיין לא נבחר והזן את המידע הבא:</span><span class="sxs-lookup"><span data-stu-id="99a32-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="99a32-191">**שם משתמש:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="99a32-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="99a32-192">**מזהה יישום:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="99a32-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="99a32-193">**שם פרטי:** Customer</span><span class="sxs-lookup"><span data-stu-id="99a32-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="99a32-194">**שם משפחה:** Insights</span><span class="sxs-lookup"><span data-stu-id="99a32-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="99a32-195">**כתובת דואר אלקטרוני ראשית:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="99a32-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="99a32-196">בחר **Save & Close**.</span><span class="sxs-lookup"><span data-stu-id="99a32-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="99a32-197">בחר במשתמש שיצרת זה עתה.</span><span class="sxs-lookup"><span data-stu-id="99a32-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="99a32-198">בחר **ניהול תפקידים** בשורת התפריטים העליונה.</span><span class="sxs-lookup"><span data-stu-id="99a32-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="99a32-199">בחר **מנהל מערכת** ולאחר מכן בחר **אישור**.</span><span class="sxs-lookup"><span data-stu-id="99a32-199">Select **System Administrator**, then select **OK**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]