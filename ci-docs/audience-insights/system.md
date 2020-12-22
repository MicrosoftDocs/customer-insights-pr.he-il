---
title: קביעת תצורת המערכת ב- Audience Insights
description: קבל מידע על הגדרות המערכת ביכולת Audience Insights של Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405908"
---
# <a name="system-configuration"></a><span data-ttu-id="eccc5-103">קביעת תצורת המערכת‫</span><span class="sxs-lookup"><span data-stu-id="eccc5-103">System configuration</span></span>

<span data-ttu-id="eccc5-104">הדף **מערכת** כולל ארבע כרטיסיות: **מצב**, **לוח זמנים**, **אודות** ו **כללי**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-104">The **System** page includes four tabs: **Status**, **Schedule**, **About**, and **General**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="eccc5-105">![עמוד מערכת](media/system-tabs.png "דף מערכת")</span><span class="sxs-lookup"><span data-stu-id="eccc5-105">![System page](media/system-tabs.png "System page")</span></span>

## <a name="status-tab"></a><span data-ttu-id="eccc5-106">כרטיסיית מצב</span><span class="sxs-lookup"><span data-stu-id="eccc5-106">Status tab</span></span>

<span data-ttu-id="eccc5-107">הכרטיסייה **מצב** מאפשרת לך לעקוב אחר ההתקדמות של קליטת נתונים, ייצוא נתונים ומספר תהליכים חשובים שקשורים למוצר.</span><span class="sxs-lookup"><span data-stu-id="eccc5-107">The **Status tab** lets you track the progress of data ingestion, data exports, and several important product processes.</span></span> <span data-ttu-id="eccc5-108">עיין במידע בכרטיסיה זו כדי להבטיח את השלמתם של תהליכים פעילים.</span><span class="sxs-lookup"><span data-stu-id="eccc5-108">Review the information on this tab to ensure the completeness of active processes.</span></span>

<span data-ttu-id="eccc5-109">כרטיסיה זו כוללת טבלאות מצב עבור **מקורות מידע**, **תהליכי מערכת**, ו **הכנת נתונים**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-109">This tab includes status tables for **Data sources**, **System processes**, and **Data preparation**.</span></span> <span data-ttu-id="eccc5-110">כל טבלה עוקבת אחר **שם** המשימה והישות המתאימה לה, **מצב** מההפעלה האחרונה שלו, ומתי היה **‏‫עדכון אחרון‬**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-110">Each table tracks the **Name** of the task and its corresponding entity, the **Status** of its most recent run, and when it was **Last updated**.</span></span>

<span data-ttu-id="eccc5-111">הצג את הפרטים של ההפעלות האחרונות על-ידי בחירת השם.</span><span class="sxs-lookup"><span data-stu-id="eccc5-111">View the details of the tasks' last several runs by selecting its name.</span></span>

### <a name="status-types"></a><span data-ttu-id="eccc5-112">סוגי מצב</span><span class="sxs-lookup"><span data-stu-id="eccc5-112">Status types</span></span>

<span data-ttu-id="eccc5-113">קיימים שישה סוגים של מצבים עבור משימות.</span><span class="sxs-lookup"><span data-stu-id="eccc5-113">There are six types of status for tasks.</span></span> <span data-ttu-id="eccc5-114">סוגי המצבים הבאים מוצגים גם בדפים *התאמה*, *מיזוג*, *מקורות נתונים*, *פלחים*, *מדידות*, *העשרה*, *פעילויות* וכן *חיזויים*:</span><span class="sxs-lookup"><span data-stu-id="eccc5-114">The following status types also show on the *Match*, *Merge*, *Data sources*, *Segments*, *Measures*, *Enrichment*, *Activities*, and *Predictions* pages:</span></span>

- <span data-ttu-id="eccc5-115">המשימה **עיבוד:** מתבצעת.</span><span class="sxs-lookup"><span data-stu-id="eccc5-115">**Processing:** Task is in progress.</span></span> <span data-ttu-id="eccc5-116">המצב יכול להשתנות ל'הצליח' או 'כשל'.</span><span class="sxs-lookup"><span data-stu-id="eccc5-116">The status can change to Successful or Failure.</span></span>
- <span data-ttu-id="eccc5-117">**הצליח:** המשימה הושלמה בהצלחה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-117">**Successful:** Task completed successfully.</span></span>
- <span data-ttu-id="eccc5-118">**בוצע דילוג:** המערכת דילגה על המשימה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-118">**Skipped:** Task got skipped.</span></span> <span data-ttu-id="eccc5-119">אחד או יותר מהתהליכים במורד הזרם שהמשימה הזו תלויה בהם נכשלים או שהמערכת דילגה עליהם.</span><span class="sxs-lookup"><span data-stu-id="eccc5-119">One or more of the downstream processes this task depends on are failing or got skipped.</span></span>
- <span data-ttu-id="eccc5-120">**כשל:** עיבוד המשימה נכשל.</span><span class="sxs-lookup"><span data-stu-id="eccc5-120">**Failure:** Processing  of the task has failed.</span></span>
- <span data-ttu-id="eccc5-121">**בוטלה:** העיבוד בוטל על-ידי המשתמש לפני שהסתיים.</span><span class="sxs-lookup"><span data-stu-id="eccc5-121">**Canceled:** Processing was canceled by the user before it finished.</span></span>
- <span data-ttu-id="eccc5-122">**הוצב בתור:** העיבוד מוצב בתור ויתחיל כאשר כל המשימות במורד הזרם יושלמו.</span><span class="sxs-lookup"><span data-stu-id="eccc5-122">**Queued:** Processing is queued and will start once all the downstream tasks are completed.</span></span> <span data-ttu-id="eccc5-123">למידע נוסף, ראה [‏‫מדיניות רענון](#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="eccc5-123">For more information, see [Refresh policies](#refresh-policies).</span></span>

### <a name="refresh-policies"></a><span data-ttu-id="eccc5-124">מדיניות רענון</span><span class="sxs-lookup"><span data-stu-id="eccc5-124">Refresh policies</span></span>

<span data-ttu-id="eccc5-125">רשימה זו מציגה את מדיניות הרענון עבור כל אחד מהתהליכים העיקריים:</span><span class="sxs-lookup"><span data-stu-id="eccc5-125">This list shows the refresh policies for each of the main processes:</span></span>

- <span data-ttu-id="eccc5-126">**מקורות נתונים:** פועל בהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-126">**Data sources:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-127">לא תלוי בתהליך אחר.</span><span class="sxs-lookup"><span data-stu-id="eccc5-127">Doesn't depend on any other process.</span></span> <span data-ttu-id="eccc5-128">ההתאמה תלויה בסיום המוצלח של תהליך זה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-128">Match depends on the successful completion of this process.</span></span>
- <span data-ttu-id="eccc5-129">**התאמה:** פועל בהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-129">**Match:** Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-130">תלוי בעיבוד מקורות הנתונים המשמשים בהגדרת ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-130">Depends on the processing of the data sources used in the match definition.</span></span> <span data-ttu-id="eccc5-131">המיזוג תלוי בסיום המוצלח של תהליך זה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-131">Merge depends on the successful completion of this process.</span></span>
- <span data-ttu-id="eccc5-132">**מיזוג:** פועל בהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-132">**Merge**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-133">תלוי בהשלמת תהליך ההתאמה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-133">Depends on the completion of the match process.</span></span> <span data-ttu-id="eccc5-134">פלחים, מדידות, העשרה, חיפוש, פעילויות, חיזויים והכנת נתונים תלויים בהשלמה מוצלחת של תהליך זה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-134">Segments, measures, enrichment, search, activities, predictions, and data preparation depend on the successful completion of this process.</span></span>
- <span data-ttu-id="eccc5-135">**פלחים** : פועל ידנית (רענון חד פעמי) ובהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-135">**Segments**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-136">תלוי במיזוג.</span><span class="sxs-lookup"><span data-stu-id="eccc5-136">Depends on Merge.</span></span> <span data-ttu-id="eccc5-137">התובנות תלויות בעיבוד שלהן.</span><span class="sxs-lookup"><span data-stu-id="eccc5-137">Insights depend on its processing.</span></span>
- <span data-ttu-id="eccc5-138">**מדידות** : פועל ידנית (רענון חד פעמי) ובהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-138">**Measures**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-139">תלוי במיזוג.</span><span class="sxs-lookup"><span data-stu-id="eccc5-139">Depends on Merge.</span></span>
- <span data-ttu-id="eccc5-140">**פעילויות** : פועל ידנית (רענון חד פעמי) ובהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-140">**Activities**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-141">תלוי במיזוג.</span><span class="sxs-lookup"><span data-stu-id="eccc5-141">Depends on Merge.</span></span>
- <span data-ttu-id="eccc5-142">**העשרה** : פועל ידנית (רענון חד פעמי) ובהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-142">**Enrichment**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-143">תלוי במיזוג.</span><span class="sxs-lookup"><span data-stu-id="eccc5-143">Depends on Merge.</span></span>
- <span data-ttu-id="eccc5-144">**חיפוש** : פועל ידנית (רענון חד פעמי) ובהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-144">**Search**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-145">תלוי במיזוג.</span><span class="sxs-lookup"><span data-stu-id="eccc5-145">Depends on Merge.</span></span>
- <span data-ttu-id="eccc5-146">**הכנת נתונים:** פועל בהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-146">**Data preparation**: Runs according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-147">תלוי במיזוג.</span><span class="sxs-lookup"><span data-stu-id="eccc5-147">Depends on Merge.</span></span>
- <span data-ttu-id="eccc5-148">**תובנות** : פועל ידנית (רענון חד פעמי) ובהתאם ל[לוח זמנים מוגדר](#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="eccc5-148">**Insights**: Runs manually (single time refresh) and according to the [configured schedule](#schedule-tab).</span></span> <span data-ttu-id="eccc5-149">תלוי בפלחים.</span><span class="sxs-lookup"><span data-stu-id="eccc5-149">Depends on Segments.</span></span>

<span data-ttu-id="eccc5-150">בחר את מצב המשימה כדי לראות את פרטי ההתקדמות של המשימה השלמה שהיא הייתה חלק ממנה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-150">Select the status of a task to see the progress details of the entire job it was in.</span></span> <span data-ttu-id="eccc5-151">מדיניות הרענון לעיל יכולה לעזור להבין מה ניתן לעשות כדי לטפל במשימת **בוצע דילוג** או **ממתין בתור**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-151">The refresh policies above can help to understand what you can do to address a **Skipped** or **Queued** task.</span></span>

## <a name="schedule-tab"></a><span data-ttu-id="eccc5-152">כרטיסיית לוח זמנים</span><span class="sxs-lookup"><span data-stu-id="eccc5-152">Schedule tab</span></span>

<span data-ttu-id="eccc5-153">השתמש בכרטיסיה **לוח זמנים** כדי לתזמן רענונים אוטומטיים של כל [מקורות הנתונים שנקלטו](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="eccc5-153">Use the **Schedule** tab to schedule automatic refreshes of all your [ingested data sources](data-sources.md).</span></span> <span data-ttu-id="eccc5-154">רענונים אוטומטיים עוזרים להבטיח שעדכונים ממקורות הנתונים שלך ישתקפו בפרופילי הלקוחות המאוחדים שלך.</span><span class="sxs-lookup"><span data-stu-id="eccc5-154">Automatic refreshes help ensure that updates from your data sources are reflected in your unified customer profiles.</span></span>

1. <span data-ttu-id="eccc5-155">ב- Audience Insights, עבור אל **מנהל מערכת** > **מערכת** ובחר את הכרטיסיה **לוח זמנים**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-155">In audience insights, go to **Admin** > **System** and select the **Schedule** tab.</span></span>

2. <span data-ttu-id="eccc5-156">מצב ברירת המחדל עבור הרענון המתוזמן הוא **כבוי**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-156">The default state for the scheduled refresh is **Off**.</span></span> <span data-ttu-id="eccc5-157">כדי לאפשר רענון מתוזמן, שנה את המתח בחלק העליון של המסך ל **פועל**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-157">To enable scheduled refreshes, change the toggle at the top of the screen to **On**.</span></span>

3. <span data-ttu-id="eccc5-158">בחר בין רענון **שבועי** (ברירת מחדל) לבין **יומי**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-158">Choose between **Weekly** (default) and **Daily** refreshes.</span></span> <span data-ttu-id="eccc5-159">אם אתה מתכוון לתזמן רענונים שבועיים, בחר יום אחד או יותר שבו תרצה להפעיל את הרענון.</span><span class="sxs-lookup"><span data-stu-id="eccc5-159">If you intend to schedule weekly refreshes, select one or more days on which you want to run the refresh.</span></span>

4. <span data-ttu-id="eccc5-160">הגדר **אזור זמן** והשתמש בתפריט הנפתח **זמן** להגדרת תזמון הרענון שלך.</span><span class="sxs-lookup"><span data-stu-id="eccc5-160">Set your **Time zone**, then use the **Time** dropdown to set your refresh timing.</span></span> <span data-ttu-id="eccc5-161">לאחר שתסיים, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-161">When you're finished, select **Set**.</span></span> <span data-ttu-id="eccc5-162">אם תרצה לתזמן רענונים מרובים ביום אחד, בחר **הוסף עוד זמן**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-162">If you'd like to schedule multiple refreshes in a single day, select **Add another time**.</span></span>

5. <span data-ttu-id="eccc5-163">בחר **שמור** כדי להחיל את השינויים.</span><span class="sxs-lookup"><span data-stu-id="eccc5-163">Select **Save** to apply your changes.</span></span>

## <a name="about-tab"></a><span data-ttu-id="eccc5-164">כרטיסיית אודות</span><span class="sxs-lookup"><span data-stu-id="eccc5-164">About tab</span></span>

<span data-ttu-id="eccc5-165">הכרטיסיה **אודות** מכילה את נתוני הארגון **שם תצוגה**, **מזהה הסביבה** הפעילה, **אזור**, ו- **מזהה הפעלה**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-165">The **About** tab contains your organization's **Display name**, the active **Environment ID**, the **Region**, and your **Session ID**.</span></span> <span data-ttu-id="eccc5-166">אם יש לך יותר מסביבת עבודה אחת, עליך להעניק לכל אחת מהן שם תצוגה שניתן לזהות בקלות.</span><span class="sxs-lookup"><span data-stu-id="eccc5-166">If you have more than one work environment, you should give each an easily identifiable display name.</span></span>

## <a name="general-tab"></a><span data-ttu-id="eccc5-167">הכרטיסיה 'כללי'</span><span class="sxs-lookup"><span data-stu-id="eccc5-167">General tab</span></span>

<span data-ttu-id="eccc5-168">קיימות שתי אפשרויות בכרטיסיה **כללי**, **שפה** ו **תבנית מדינה/אזור**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-168">There are two options on the **General** tab, **Language** and **Country/Region format**.</span></span>

<span data-ttu-id="eccc5-169">האפליקציה [תומכת במספר שפות](supported-languages.md).</span><span class="sxs-lookup"><span data-stu-id="eccc5-169">The app [supports a number of languages](supported-languages.md).</span></span> <span data-ttu-id="eccc5-170">כדי לשנות את השפה המועדפת עליך, בחר **שפה** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="eccc5-170">To change your preferred language, choose a **Language** from the dropdown.</span></span>

<span data-ttu-id="eccc5-171">כדי לשנות את העיצוב המועדף עליך עבור תאריכים, שעה ומספרים, השתמש ברשימה הנפתחת **תבנית מדינה/אזור**.</span><span class="sxs-lookup"><span data-stu-id="eccc5-171">To change your preferred formatting for dates, time, and numbers, use the **Country/Region format** dropdown.</span></span> <span data-ttu-id="eccc5-172">תצוגה מקדימה של עיצוב מוצגת תחת שדה זה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-172">A formatting preview is displayed under this field.</span></span> <span data-ttu-id="eccc5-173">המערכת תציע באופן אוטומטי אפשרות בחירה כשתבחר שפה חדשה.</span><span class="sxs-lookup"><span data-stu-id="eccc5-173">The system will automatically suggest a selection when you choose a new language.</span></span>

<span data-ttu-id="eccc5-174">בחר **שמור** ואשר את הבחירות.</span><span class="sxs-lookup"><span data-stu-id="eccc5-174">Select **Save** to confirm your selections.</span></span>

## <a name="api-usage-tab"></a><span data-ttu-id="eccc5-175">כרטיסיית שימוש בממשק API</span><span class="sxs-lookup"><span data-stu-id="eccc5-175">API usage tab</span></span>

<span data-ttu-id="eccc5-176">מצא פרטים על השימוש בממשק ה- API בזמן אמת וראה אילו אירועים התרחשו בטווח זמן נתון.</span><span class="sxs-lookup"><span data-stu-id="eccc5-176">Find details about the real-time API usage and see which events happened in a given time range.</span></span> <span data-ttu-id="eccc5-177">למידע נוסף, ראה [קליטת נתונים בזמן אמת](real-time-data-ingestion.md).</span><span class="sxs-lookup"><span data-stu-id="eccc5-177">For more information, see [Real-time data ingestion](real-time-data-ingestion.md).</span></span>
