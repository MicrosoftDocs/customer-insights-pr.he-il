---
title: מצא לקוחות דומים עם AI
description: מצא פלחי לקוחות דומים עם בינה מלאכותית.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268871"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="1c65d-103">לקוחות דומים (Preview)</span><span class="sxs-lookup"><span data-stu-id="1c65d-103">Similar Customers (preview)</span></span>

<span data-ttu-id="1c65d-104">תכונה זו מאפשרת לך למצוא לקוחות דומים בבסיס הלקוחות שלך באמצעות בינה מלאכותית.</span><span class="sxs-lookup"><span data-stu-id="1c65d-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="1c65d-105">עליך ליצור לפחות פלח אחד כדי להשתמש בתכונה זו.</span><span class="sxs-lookup"><span data-stu-id="1c65d-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="1c65d-106">הרחבת הקריטריונים של פלח קיים עוזרת למצוא לקוחות הדומים לאותו פלח.</span><span class="sxs-lookup"><span data-stu-id="1c65d-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="1c65d-107">התכונה *מצא לקוחות דומים* משתמשת באמצעים אוטומטיים כדי להעריך נתונים ולבצע תחזיות על סמך נתונים אלה, ולכן יש לה את היכולת לשמש כשיטת פרופיל, כפי שמונח זה מוגדר על ידי התקנה הכללית להגנת נתונים ("GDPR").</span><span class="sxs-lookup"><span data-stu-id="1c65d-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="1c65d-108">השימוש של הלקוח בתכונה זו לעיבוד נתונים עשוי להיות כפוף ל- GDPR או לחוקים ותקנות אחרים.</span><span class="sxs-lookup"><span data-stu-id="1c65d-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="1c65d-109">אתה אחראי להבטיח שהשימוש שלך ב- Dynamics 365 Customer Insights, כולל חיזויים, תואם לכל החוקים והתקנות החלים, כולל חוקים הקשורים לפרטיות, נתונים אישיים, נתונים ביומטריים, הגנה על נתונים וסודיות תקשורת.</span><span class="sxs-lookup"><span data-stu-id="1c65d-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="1c65d-110">חיפוש לקוחות דומים</span><span class="sxs-lookup"><span data-stu-id="1c65d-110">Finding similar customers</span></span>

1. <span data-ttu-id="1c65d-111">ב- Audience Insights, עבור אל **פלחים** ובחר את הפלט שברצונך לבסס עליו את הפלח החדש.</span><span class="sxs-lookup"><span data-stu-id="1c65d-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="1c65d-112">זהו *פלח המקור*.</span><span class="sxs-lookup"><span data-stu-id="1c65d-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="1c65d-113">בסרגל הפעולות, בחר **חיפוש לקוחות דומים**.</span><span class="sxs-lookup"><span data-stu-id="1c65d-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="1c65d-114">סקור את השם המוצע עבור הפלח החדש ושנה אותו במידת הצורך.</span><span class="sxs-lookup"><span data-stu-id="1c65d-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="1c65d-115">סקור את השדות המגדירים את הפלח החדש.</span><span class="sxs-lookup"><span data-stu-id="1c65d-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="1c65d-116">שדות אלה מגדירים את הבסיס שעליו המערכת תנסה למצוא לקוחות שדומים לפלח המקור.</span><span class="sxs-lookup"><span data-stu-id="1c65d-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="1c65d-117">המערכת תבחר שדות מומלצים כברירת מחדל.</span><span class="sxs-lookup"><span data-stu-id="1c65d-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="1c65d-118">שדות שיכולים להפחית באופן משמעותי את ביצועי המודל אינם נכללים באופן אוטומטי:</span><span class="sxs-lookup"><span data-stu-id="1c65d-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="1c65d-119">שדות עם סוגי הנתונים הבאים: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="1c65d-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="1c65d-120">שדות עם קרדינליות (מספר האלמנטים בשדה) של פחות מ- 2 או יותר מ- 30</span><span class="sxs-lookup"><span data-stu-id="1c65d-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="1c65d-121">בחר אם ברצונך לכלול את **כל הלקוחות** או רק לקוחות בתוך **פלח קיים ספציפי** בפלח החדש שלך.</span><span class="sxs-lookup"><span data-stu-id="1c65d-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="1c65d-122">אל תכלול לקוחות בפלח המקור על ידי בחירה בתיבת סימון **אל תכלול את כולם בפלח המקור**.</span><span class="sxs-lookup"><span data-stu-id="1c65d-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="1c65d-123">כברירת מחדל, המערכת מציעה לכלול רק 20% מגודל קהל היעד בפלט שלך.</span><span class="sxs-lookup"><span data-stu-id="1c65d-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="1c65d-124">ערוך סף זה לפי הצורך.</span><span class="sxs-lookup"><span data-stu-id="1c65d-124">Edit this threshold as needed.</span></span> <span data-ttu-id="1c65d-125">הגדלת הסף תפחית את הדיוק.</span><span class="sxs-lookup"><span data-stu-id="1c65d-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="1c65d-126">בחר **הפעל** בתחתית הדף כדי להתחיל משימת סיווג בינארית (שיטה של למידת מכונה) המנתחת את ערכת נתונים.</span><span class="sxs-lookup"><span data-stu-id="1c65d-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="1c65d-127">צפה בפלח דומה</span><span class="sxs-lookup"><span data-stu-id="1c65d-127">View the similar segment</span></span>

<span data-ttu-id="1c65d-128">לאחר עיבוד הפלח הדומה, מצא את הפלח החדש בדף **פלחים**.</span><span class="sxs-lookup"><span data-stu-id="1c65d-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1c65d-129">![פלח לקוחות דומה](media/expanded-segment.png "פלח לקוחות דומה")</span><span class="sxs-lookup"><span data-stu-id="1c65d-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="1c65d-130">בחר **הצג** בסרגל הפעולות לפתיחת פרטי הפלח.</span><span class="sxs-lookup"><span data-stu-id="1c65d-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="1c65d-131">תצוגה זו מכילה מידע על חלוקת התוצאות של [ניקוד דמיון](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="1c65d-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="1c65d-132">תמצא גם את ערכי ניקוד הדמיון ב- **תצוגה מקדימה של חברי הפלח**.</span><span class="sxs-lookup"><span data-stu-id="1c65d-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="1c65d-133">השתמש בפלט של פלח דומה</span><span class="sxs-lookup"><span data-stu-id="1c65d-133">Use the output of a similar segment</span></span>

<span data-ttu-id="1c65d-134">אתה יכול [לעבוד עם הפלט של פלח דומה](segments.md) בדומה לפלחים אחרים.</span><span class="sxs-lookup"><span data-stu-id="1c65d-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="1c65d-135">לדוגמה, ייצא את הפלח או בנה מדד.</span><span class="sxs-lookup"><span data-stu-id="1c65d-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="1c65d-136">רענן וערוך פלח דומה</span><span class="sxs-lookup"><span data-stu-id="1c65d-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="1c65d-137">כדי לרענן פלח דומה, בחר אותו בדף **פלחים** ובחר **רענן** בסרגל הפעולות.</span><span class="sxs-lookup"><span data-stu-id="1c65d-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="1c65d-138">עריכת פלח דומה תעבד מחדש את הנתונים שלך.</span><span class="sxs-lookup"><span data-stu-id="1c65d-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="1c65d-139">הפלח שנוצר בעבר מתעדכן עם נתונים רעננים.</span><span class="sxs-lookup"><span data-stu-id="1c65d-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="1c65d-140">כדי לערוך פלח דומה, בחר אותו בדף **פלחים** ובחר **ערוך** בסרגל הפעולות.</span><span class="sxs-lookup"><span data-stu-id="1c65d-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="1c65d-141">החל את השינויים ובחר **הפעל** כדי להתחיל בעיבוד.</span><span class="sxs-lookup"><span data-stu-id="1c65d-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="1c65d-142">מחק פלח דומה</span><span class="sxs-lookup"><span data-stu-id="1c65d-142">Delete a similar segment</span></span>

<span data-ttu-id="1c65d-143">בחר את הפלח בדף **פלחים** ובחר **מחק** בסרגל הפעולות.</span><span class="sxs-lookup"><span data-stu-id="1c65d-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="1c65d-144">לאחר מכן אשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="1c65d-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="1c65d-145">ניקוד דמיון</span><span class="sxs-lookup"><span data-stu-id="1c65d-145">About similarity scores</span></span>

<span data-ttu-id="1c65d-146">מודל למידת מכונה של הסיווג הבינארי מסווג ניקוד ללקוחות בפלח הדומה.</span><span class="sxs-lookup"><span data-stu-id="1c65d-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="1c65d-147">הניקוד מבוסס על הדמיון ללקוחות בפלח המקור.</span><span class="sxs-lookup"><span data-stu-id="1c65d-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="1c65d-148">ניקודי דמיון מתחת ל- 0.55 מציינים לקוחות שהמערכת מסווגת *לא דומה* ללקוחות בפלח המקור</span><span class="sxs-lookup"><span data-stu-id="1c65d-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="1c65d-149">ניקודי דמיון בין 0.55 - 0.7 מסווגים *דומה במקצת*</span><span class="sxs-lookup"><span data-stu-id="1c65d-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="1c65d-150">ניקודי דמיון בין 0.7 - 0.85 מסווגים *דומה*</span><span class="sxs-lookup"><span data-stu-id="1c65d-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="1c65d-151">ניקודי דמיון בין 0.85 - 1 הם לקוחות שהמערכת מסווגת *דומה מאוד*</span><span class="sxs-lookup"><span data-stu-id="1c65d-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="1c65d-152">לקוחות עם ניקודי דמיון מתחת ל- 0.4 אינם נכללים בפלט המודל.</span><span class="sxs-lookup"><span data-stu-id="1c65d-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="1c65d-153">המערכת לא רואה אותם כדומים לפלח המקור.</span><span class="sxs-lookup"><span data-stu-id="1c65d-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]