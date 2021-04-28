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
ms.openlocfilehash: 0fc13d3ac0a5176637b6fe481dabe0b2aec11649
ms.sourcegitcommit: d89b19b2a3497722b78362aeee688ae7e94915d9
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5887895"
---
# <a name="data-sources-overview"></a><span data-ttu-id="de1a0-103">מבט כולל על מקורות נתונים</span><span class="sxs-lookup"><span data-stu-id="de1a0-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="de1a0-104">יכולת תובנות הקהל ב- Dynamics 365 Customer Insights מתחברת לנתונים מערכת מקורות רחבה.</span><span class="sxs-lookup"><span data-stu-id="de1a0-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="de1a0-105">לעיתים קרובות מתייחסים לחיבור למקור נתונים כאל תהליך של *עיבוד נתונים*.</span><span class="sxs-lookup"><span data-stu-id="de1a0-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="de1a0-106">לאחר עיבוד הנתונים, ניתן [לאחד](data-unification.md) ולנקוט פעולה.</span><span class="sxs-lookup"><span data-stu-id="de1a0-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="de1a0-107">הוספה של מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="de1a0-107">Add a data source</span></span>

<span data-ttu-id="de1a0-108">עיין במאמרים המפורטים על איך להוסיף מקור נתונים, בהתאם לאפשרות שבה תבחר.</span><span class="sxs-lookup"><span data-stu-id="de1a0-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="de1a0-109">ניתן להוסיף מקור נתונים בשלוש דרכים עיקריות:</span><span class="sxs-lookup"><span data-stu-id="de1a0-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="de1a0-110">דרך עשרות מחברי Power Query</span><span class="sxs-lookup"><span data-stu-id="de1a0-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="de1a0-111">דרך תיקית Common Data Model</span><span class="sxs-lookup"><span data-stu-id="de1a0-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="de1a0-112">דרך אגם ה-Common Data Service שלך</span><span class="sxs-lookup"><span data-stu-id="de1a0-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="de1a0-113">הוספת נתונים ממקורות נתונים מקומיים</span><span class="sxs-lookup"><span data-stu-id="de1a0-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="de1a0-114">קליטת נתונים ממקורות נתונים מקומיים בתובנות קהלים נתמכת בהתבסס על זרימות הנתונים של Power Platform.</span><span class="sxs-lookup"><span data-stu-id="de1a0-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="de1a0-115">ניתן להפעיל זרימות נתונים ב- Customer Insights על-ידי [מתן כתובת ה- URL של סביבת Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) בעת הגדרת הסביבה.</span><span class="sxs-lookup"><span data-stu-id="de1a0-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="de1a0-116">מקורות נתונים שנוצרו לאחר שיוך סביבת Dataverse ל- Customer Insights ישתמשו ב[זרימות נתונים של Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) כברירת מחדל.</span><span class="sxs-lookup"><span data-stu-id="de1a0-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="de1a0-117">זרימות נתונים תומכות בקישוריות מקומית באמצעות שערי הנתונים.</span><span class="sxs-lookup"><span data-stu-id="de1a0-117">Dataflows support on-prem connectivity using the data gateways.</span></span> <span data-ttu-id="de1a0-118">הסר וצור מחדש מקורות נתונים שהתקיימות לפני שסביבת Dataverse שויכה לשימוש בשערי הנתונים המקומיים.</span><span class="sxs-lookup"><span data-stu-id="de1a0-118">Remove and recreate data sources that existed before a Dataverse environment was associated to use the on-premises data gateways.</span></span>

<span data-ttu-id="de1a0-119">שערי נתונים מסביבת Power BI או Power Apps קיימת יהיו גלויים ותוכל להשתמש בהם מחדש ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="de1a0-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="de1a0-120">דף מקורות הנתונים מציג קישורים למעבר אל סביבת Power Platform שבה באפשרותך להציג ולקבוע תצורה של שערי נתונים מקומיים.</span><span class="sxs-lookup"><span data-stu-id="de1a0-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

:::image type="content" source="media/data-sources-onpremises-gateways.png" alt-text="צילום מסך של דף מקורות הנתונים המציג קישורים המצביעים אל סביבת Power Platform.":::

## <a name="review-ingested-data"></a><span data-ttu-id="de1a0-122">סקירה של נתונים מעובדים</span><span class="sxs-lookup"><span data-stu-id="de1a0-122">Review ingested data</span></span>

<span data-ttu-id="de1a0-123">תראה את השם של כל מקור נתונים שעובד, את המצב שלו ואת הפעם האחרונה שבו הנתונים מאותו מקור רועננו.</span><span class="sxs-lookup"><span data-stu-id="de1a0-123">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="de1a0-124">ניתן למיין את רשימת מקורות הנתונים לפי כל עמודה.</span><span class="sxs-lookup"><span data-stu-id="de1a0-124">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="de1a0-125">![מקור נתונים נוסף](media/configure-data-datasource-added.png "מקור נתונים נוסף")</span><span class="sxs-lookup"><span data-stu-id="de1a0-125">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="de1a0-126">סטאטוס</span><span class="sxs-lookup"><span data-stu-id="de1a0-126">Status</span></span>  |<span data-ttu-id="de1a0-127">תיאור</span><span class="sxs-lookup"><span data-stu-id="de1a0-127">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="de1a0-128">הצליח</span><span class="sxs-lookup"><span data-stu-id="de1a0-128">Successful</span></span>   |<span data-ttu-id="de1a0-129">מקור נתונים נקלט בהצלחה אם מוזכרת שעה בעמודה **בוצע רענון**.</span><span class="sxs-lookup"><span data-stu-id="de1a0-129">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="de1a0-130">לא התחילה</span><span class="sxs-lookup"><span data-stu-id="de1a0-130">Not started</span></span>   |<span data-ttu-id="de1a0-131">למקור הנתונים אין נתונים שנקלטו עדיין או שהוא עדיין במצב טיוטה.</span><span class="sxs-lookup"><span data-stu-id="de1a0-131">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="de1a0-132">עובר רענון</span><span class="sxs-lookup"><span data-stu-id="de1a0-132">Refreshing</span></span>    |<span data-ttu-id="de1a0-133">עיבוד נתונים מתבצע.</span><span class="sxs-lookup"><span data-stu-id="de1a0-133">Data ingestion is in progress.</span></span> <span data-ttu-id="de1a0-134">באפשרותך לבטל פעולה זו על-ידי בחירה באפשרות **עצור רענון** בעמודה **פעולות**.</span><span class="sxs-lookup"><span data-stu-id="de1a0-134">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="de1a0-135">עצירת הרענון של מקור נתונים תחזיר אותו למצב האחרון שלו.</span><span class="sxs-lookup"><span data-stu-id="de1a0-135">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="de1a0-136">השליחה נכשלה</span><span class="sxs-lookup"><span data-stu-id="de1a0-136">Failed</span></span>     |<span data-ttu-id="de1a0-137">עיבוד הנתונים נתקל בשגיאות.</span><span class="sxs-lookup"><span data-stu-id="de1a0-137">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="de1a0-138">בחר את הערך בעמודה **מצב** של מקור נתונים כלשהו כדי לסקור פרטים נוספים.</span><span class="sxs-lookup"><span data-stu-id="de1a0-138">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="de1a0-139">בחלונית **פרטי התקדמות**, הרחב את **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="de1a0-139">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="de1a0-140">בחר **הצג פרטים** לקבלת מידע נוסף אודות מצב הרענון, לרבות פרטי שגיאה ועדכוני תהליך במורד הזרם.</span><span class="sxs-lookup"><span data-stu-id="de1a0-140">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="de1a0-141">טעינת הנתונים עשויה להימשך זמן מה.</span><span class="sxs-lookup"><span data-stu-id="de1a0-141">Loading data can take some time.</span></span> <span data-ttu-id="de1a0-142">לאחר רענון מוצלח, ניתן לסקור את הנתונים שעובדו בדף **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="de1a0-142">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="de1a0-143">לקבלת מידע נוסף, ראה [ישויות](entities.md).</span><span class="sxs-lookup"><span data-stu-id="de1a0-143">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="de1a0-144">רענון מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="de1a0-144">Refresh a data source</span></span>

<span data-ttu-id="de1a0-145">ניתן לרענן את מקורות הנתונים בלוח זמנים אוטומטי או לרענן אותם באופן ידני לפי דרישה.</span><span class="sxs-lookup"><span data-stu-id="de1a0-145">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="de1a0-146">עבור אל **ניהול** > **מערכת** > [**לוח זמנים**](system.md#schedule-tab) כדי לקבוע תצורה של רענונים מתוזמנים של כל מקורות הנתונים שקלטת.</span><span class="sxs-lookup"><span data-stu-id="de1a0-146">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="de1a0-147">כדי לרענן מקור נתונים לפי דרישה, בצע את השלבים הבאים:</span><span class="sxs-lookup"><span data-stu-id="de1a0-147">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="de1a0-148">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**</span><span class="sxs-lookup"><span data-stu-id="de1a0-148">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="de1a0-149">בחר את שלוש הנקודות האנכיות לצד מקור הנתונים שברצונך לרענן ובחר **רענון** מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="de1a0-149">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="de1a0-150">מקור הנתונים מופעל כעת עבור רענון ידני.</span><span class="sxs-lookup"><span data-stu-id="de1a0-150">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="de1a0-151">רענון מקור נתונים יעדכן הן את סכימת הישות והן את הנתונים עבור כל הישויות שצוינו במקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="de1a0-151">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="de1a0-152">בחר **הפסק רענון** אם ברצונך לבטל רענון קיים ומקור הנתונים יחזור למצב הרענון האחרון שלו.</span><span class="sxs-lookup"><span data-stu-id="de1a0-152">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="de1a0-153">מחק מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="de1a0-153">Delete a data source</span></span>

1. <span data-ttu-id="de1a0-154">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="de1a0-154">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="de1a0-155">בחר את שלוש הנקודות האנכיות לצד מקור הנתונים שברצונך להסיר ובחר **מחק** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="de1a0-155">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="de1a0-156">אשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="de1a0-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
