---
title: שימוש במקורות נתונים לקליטת נתונים
description: למד כיצד לייבא נתונים ממקורות שונים.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304697"
---
# <a name="data-sources-overview"></a><span data-ttu-id="27112-103">מבט כולל על מקורות נתונים</span><span class="sxs-lookup"><span data-stu-id="27112-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="27112-104">יכולת תובנות הקהל ב- Dynamics 365 Customer Insights מתחברת לנתונים מערכת מקורות רחבה.</span><span class="sxs-lookup"><span data-stu-id="27112-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="27112-105">לעיתים קרובות מתייחסים לחיבור למקור נתונים כאל תהליך של *עיבוד נתונים*.</span><span class="sxs-lookup"><span data-stu-id="27112-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="27112-106">לאחר עיבוד הנתונים, ניתן [לאחד](data-unification.md) ולנקוט פעולה.</span><span class="sxs-lookup"><span data-stu-id="27112-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="27112-107">הוספה של מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="27112-107">Add a data source</span></span>

<span data-ttu-id="27112-108">עיין במאמרים המפורטים על איך להוסיף מקור נתונים, בהתאם לאפשרות שבה תבחר.</span><span class="sxs-lookup"><span data-stu-id="27112-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="27112-109">ניתן להוסיף מקור נתונים בשלוש דרכים עיקריות:</span><span class="sxs-lookup"><span data-stu-id="27112-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="27112-110">דרך עשרות מחברי Power Query</span><span class="sxs-lookup"><span data-stu-id="27112-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="27112-111">דרך תיקית Common Data Model</span><span class="sxs-lookup"><span data-stu-id="27112-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="27112-112">דרך אגם ה-Microsoft Dataverse שלך</span><span class="sxs-lookup"><span data-stu-id="27112-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="27112-113">הוספת נתונים ממקורות נתונים מקומיים</span><span class="sxs-lookup"><span data-stu-id="27112-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="27112-114">קליטת נתונים ממקורות נתונים מקומיים בתובנות לגבי קהלים נתמכת בהתבסס על זרימות הנתונים של Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="27112-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="27112-115">ניתן להפעיל זרימות נתונים ב- Customer Insights על-ידי [מתן כתובת ה- URL של סביבת Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) בעת הגדרת הסביבה.</span><span class="sxs-lookup"><span data-stu-id="27112-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="27112-116">מקורות נתונים שנוצרו לאחר שיוך סביבת Dataverse ל- Customer Insights ישתמשו ב[זרימות נתונים של Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) כברירת מחדל.</span><span class="sxs-lookup"><span data-stu-id="27112-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="27112-117">זרימות נתונים תומכות בקישוריות מקומית באמצעות שער הנתונים.</span><span class="sxs-lookup"><span data-stu-id="27112-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="27112-118">הסר וצור מחדש מקורות נתונים שהתקיימו לפני שסביבת Dataverse שויכה ל[שימוש בשערי הנתונים המקומיים](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="27112-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="27112-119">שערי נתונים מסביבת Power BI או Power Apps קיימת יהיו גלויים ותוכל להשתמש בהם מחדש ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="27112-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="27112-120">דף מקורות הנתונים מציג קישורים למעבר אל סביבת Microsoft Power Platform שבה תוכל להציג ולהגדיר את שערי הנתונים המקומיים.</span><span class="sxs-lookup"><span data-stu-id="27112-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="27112-121">סקירה של נתונים מעובדים</span><span class="sxs-lookup"><span data-stu-id="27112-121">Review ingested data</span></span>

<span data-ttu-id="27112-122">תראה את השם של כל מקור נתונים שעובד, את המצב שלו ואת הפעם האחרונה שבו הנתונים מאותו מקור רועננו.</span><span class="sxs-lookup"><span data-stu-id="27112-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="27112-123">ניתן למיין את רשימת מקורות הנתונים לפי כל עמודה.</span><span class="sxs-lookup"><span data-stu-id="27112-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="27112-124">![מקור נתונים נוסף](media/configure-data-datasource-added.png "מקור נתונים נוסף")</span><span class="sxs-lookup"><span data-stu-id="27112-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="27112-125">סטאטוס</span><span class="sxs-lookup"><span data-stu-id="27112-125">Status</span></span>  |<span data-ttu-id="27112-126">תיאור</span><span class="sxs-lookup"><span data-stu-id="27112-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="27112-127">הצליח</span><span class="sxs-lookup"><span data-stu-id="27112-127">Successful</span></span>   |<span data-ttu-id="27112-128">מקור נתונים נקלט בהצלחה אם מוזכרת שעה בעמודה **בוצע רענון**.</span><span class="sxs-lookup"><span data-stu-id="27112-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="27112-129">לא התחילה</span><span class="sxs-lookup"><span data-stu-id="27112-129">Not started</span></span>   |<span data-ttu-id="27112-130">למקור הנתונים אין נתונים שנקלטו עדיין או שהוא עדיין במצב טיוטה.</span><span class="sxs-lookup"><span data-stu-id="27112-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="27112-131">עובר רענון</span><span class="sxs-lookup"><span data-stu-id="27112-131">Refreshing</span></span>    |<span data-ttu-id="27112-132">עיבוד נתונים מתבצע.</span><span class="sxs-lookup"><span data-stu-id="27112-132">Data ingestion is in progress.</span></span> <span data-ttu-id="27112-133">באפשרותך לבטל פעולה זו על-ידי בחירה באפשרות **עצור רענון** בעמודה **פעולות**.</span><span class="sxs-lookup"><span data-stu-id="27112-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="27112-134">עצירת הרענון של מקור נתונים תחזיר אותו למצב האחרון שלו.</span><span class="sxs-lookup"><span data-stu-id="27112-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="27112-135">השליחה נכשלה</span><span class="sxs-lookup"><span data-stu-id="27112-135">Failed</span></span>     |<span data-ttu-id="27112-136">עיבוד הנתונים נתקל בשגיאות.</span><span class="sxs-lookup"><span data-stu-id="27112-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="27112-137">בחר את הערך בעמודה **מצב** של מקור נתונים כלשהו כדי לסקור פרטים נוספים.</span><span class="sxs-lookup"><span data-stu-id="27112-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="27112-138">בחלונית **פרטי התקדמות**, הרחב את **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="27112-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="27112-139">בחר **הצג פרטים** לקבלת מידע נוסף אודות מצב הרענון, לרבות פרטי שגיאה ועדכוני תהליך במורד הזרם.</span><span class="sxs-lookup"><span data-stu-id="27112-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="27112-140">טעינת נתונים עשויה להימשך זמן מה.</span><span class="sxs-lookup"><span data-stu-id="27112-140">Loading data can take time.</span></span> <span data-ttu-id="27112-141">לאחר רענון מוצלח, ניתן לסקור את הנתונים שעובדו בדף **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="27112-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="27112-142">לקבלת מידע נוסף, ראה [ישויות](entities.md).</span><span class="sxs-lookup"><span data-stu-id="27112-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="27112-143">רענון מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="27112-143">Refresh a data source</span></span>

<span data-ttu-id="27112-144">ניתן לרענן את מקורות הנתונים בלוח זמנים אוטומטי או לרענן אותם באופן ידני לפי דרישה.</span><span class="sxs-lookup"><span data-stu-id="27112-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="27112-145">עבור אל **ניהול** > **מערכת** > [**לוח זמנים**](system.md#schedule-tab) כדי לקבוע תצורה של רענונים מתוזמנים של כל מקורות הנתונים שקלטת.</span><span class="sxs-lookup"><span data-stu-id="27112-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="27112-146">כדי לרענן מקור נתונים לפי דרישה, בצע את השלבים הבאים:</span><span class="sxs-lookup"><span data-stu-id="27112-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="27112-147">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="27112-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="27112-148">בחר את שלוש הנקודות האנכיות לצד מקור נתונים שברצונך לרענן ובחר **רענון** מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="27112-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="27112-149">מקור הנתונים מופעל כעת עבור רענון ידני.</span><span class="sxs-lookup"><span data-stu-id="27112-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="27112-150">רענון מקור נתונים יעדכן הן את סכימת הישות והן את הנתונים עבור כל הישויות שצוינו במקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="27112-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="27112-151">בחר **הפסק רענון** אם ברצונך לבטל רענון קיים ומקור הנתונים יחזור למצב הרענון האחרון שלו.</span><span class="sxs-lookup"><span data-stu-id="27112-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="27112-152">מחק מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="27112-152">Delete a data source</span></span>

1. <span data-ttu-id="27112-153">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="27112-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="27112-154">בחר את שלוש הנקודות האנכיות לצד מקור נתונים שברצונך להסיר ובחר **מחיקה** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="27112-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="27112-155">אשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="27112-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
