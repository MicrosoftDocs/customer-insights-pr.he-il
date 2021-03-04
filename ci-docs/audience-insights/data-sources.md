---
title: שימוש במקורות נתונים לקליטת נתונים
description: למד כיצד לייבא נתונים ממקורות שונים.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269699"
---
# <a name="data-sources-overview"></a><span data-ttu-id="22786-103">מבט כולל על מקורות נתונים</span><span class="sxs-lookup"><span data-stu-id="22786-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="22786-104">יכולת תובנות הקהל ב- Dynamics 365 Customer Insights מתחברת לנתונים מערכת מקורות רחבה.</span><span class="sxs-lookup"><span data-stu-id="22786-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="22786-105">לעיתים קרובות מתייחסים לחיבור למקור נתונים כאל תהליך של *עיבוד נתונים*.</span><span class="sxs-lookup"><span data-stu-id="22786-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="22786-106">לאחר עיבוד הנתונים, ניתן [לאחד](data-unification.md) ולנקוט פעולה.</span><span class="sxs-lookup"><span data-stu-id="22786-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="22786-107">הוספה של מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="22786-107">Add a data source</span></span>

<span data-ttu-id="22786-108">עיין במאמרים המפורטים על איך להוסיף מקור נתונים, בהתאם לאפשרות שבה תבחר.</span><span class="sxs-lookup"><span data-stu-id="22786-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="22786-109">ניתן להוסיף מקור נתונים בשלוש דרכים עיקריות:</span><span class="sxs-lookup"><span data-stu-id="22786-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="22786-110">דרך עשרות מחברי Power Query</span><span class="sxs-lookup"><span data-stu-id="22786-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="22786-111">דרך תיקית Common Data Model</span><span class="sxs-lookup"><span data-stu-id="22786-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="22786-112">דרך אגם ה-Common Data Service שלך</span><span class="sxs-lookup"><span data-stu-id="22786-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="22786-113">עדיין לא ניתן להוסיף נתונים ממקורות נתונים מקומיות.</span><span class="sxs-lookup"><span data-stu-id="22786-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="22786-114">סקירה של נתונים מעובדים</span><span class="sxs-lookup"><span data-stu-id="22786-114">Review ingested data</span></span>

<span data-ttu-id="22786-115">תראה את השם של כל מקור נתונים שעובד, את המצב שלו ואת הפעם האחרונה שבו הנתונים מאותו מקור רועננו.</span><span class="sxs-lookup"><span data-stu-id="22786-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="22786-116">ניתן למיין את רשימת מקורות הנתונים לפי כל עמודה.</span><span class="sxs-lookup"><span data-stu-id="22786-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="22786-117">![מקור נתונים נוסף](media/configure-data-datasource-added.png "מקור נתונים נוסף")</span><span class="sxs-lookup"><span data-stu-id="22786-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="22786-118">סטאטוס</span><span class="sxs-lookup"><span data-stu-id="22786-118">Status</span></span>  |<span data-ttu-id="22786-119">תיאור</span><span class="sxs-lookup"><span data-stu-id="22786-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="22786-120">הצליח</span><span class="sxs-lookup"><span data-stu-id="22786-120">Successful</span></span>   |<span data-ttu-id="22786-121">מקור נתונים נקלט בהצלחה אם מוזכרת שעה בעמודה **בוצע רענון**.</span><span class="sxs-lookup"><span data-stu-id="22786-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="22786-122">לא התחילה</span><span class="sxs-lookup"><span data-stu-id="22786-122">Not started</span></span>   |<span data-ttu-id="22786-123">למקור הנתונים אין נתונים שנקלטו עדיין או שהוא עדיין במצב טיוטה.</span><span class="sxs-lookup"><span data-stu-id="22786-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="22786-124">עובר רענון</span><span class="sxs-lookup"><span data-stu-id="22786-124">Refreshing</span></span>    |<span data-ttu-id="22786-125">עיבוד נתונים מתבצע.</span><span class="sxs-lookup"><span data-stu-id="22786-125">Data ingestion is in progress.</span></span> <span data-ttu-id="22786-126">באפשרותך לבטל פעולה זו על-ידי בחירה באפשרות **עצור רענון** בעמודה **פעולות**.</span><span class="sxs-lookup"><span data-stu-id="22786-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="22786-127">עצירת הרענון של מקור נתונים תחזיר אותו למצב האחרון שלו.</span><span class="sxs-lookup"><span data-stu-id="22786-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="22786-128">השליחה נכשלה</span><span class="sxs-lookup"><span data-stu-id="22786-128">Failed</span></span>     |<span data-ttu-id="22786-129">עיבוד הנתונים נתקל בשגיאות.</span><span class="sxs-lookup"><span data-stu-id="22786-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="22786-130">בחר את הערך בעמודה **מצב** של מקור נתונים כלשהו כדי לסקור פרטים נוספים.</span><span class="sxs-lookup"><span data-stu-id="22786-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="22786-131">בחלונית **פרטי התקדמות**, הרחב את **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="22786-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="22786-132">בחר **הצג פרטים** לקבלת מידע נוסף אודות מצב הרענון, לרבות פרטי שגיאה ועדכוני תהליך במורד הזרם.</span><span class="sxs-lookup"><span data-stu-id="22786-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="22786-133">טעינת הנתונים עשויה להימשך זמן מה.</span><span class="sxs-lookup"><span data-stu-id="22786-133">Loading data can take some time.</span></span> <span data-ttu-id="22786-134">לאחר רענון מוצלח, ניתן לסקור את הנתונים שעובדו בדף **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="22786-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="22786-135">לקבלת מידע נוסף, ראה [ישויות](entities.md).</span><span class="sxs-lookup"><span data-stu-id="22786-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="22786-136">רענון מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="22786-136">Refresh a data source</span></span>

<span data-ttu-id="22786-137">ניתן לרענן את מקורות הנתונים בלוח זמנים אוטומטי או לרענן אותם באופן ידני לפי דרישה.</span><span class="sxs-lookup"><span data-stu-id="22786-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="22786-138">עבור אל **ניהול** > **מערכת** > [**לוח זמנים**](system.md#schedule-tab) כדי לקבוע תצורה של רענונים מתוזמנים של כל מקורות הנתונים שקלטת.</span><span class="sxs-lookup"><span data-stu-id="22786-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="22786-139">כדי לרענן מקור נתונים לפי דרישה, בצע את השלבים הבאים:</span><span class="sxs-lookup"><span data-stu-id="22786-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="22786-140">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**</span><span class="sxs-lookup"><span data-stu-id="22786-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="22786-141">בחר את שלוש הנקודות האנכיות לצד מקור הנתונים שברצונך לרענן ובחר **רענון** מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="22786-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="22786-142">מקור הנתונים מופעל כעת עבור רענון ידני.</span><span class="sxs-lookup"><span data-stu-id="22786-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="22786-143">רענון מקור נתונים יעדכן הן את סכימת הישות והן נתונים עבור כל הישויות שצוינו במקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="22786-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="22786-144">בחר **הפסק רענון** אם ברצונך לבטל רענון קיים ומקור הנתונים יחזור למצב הרענון האחרון שלו.</span><span class="sxs-lookup"><span data-stu-id="22786-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="22786-145">מחק מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="22786-145">Delete a data source</span></span>

1. <span data-ttu-id="22786-146">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="22786-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="22786-147">בחר את שלוש הנקודות האנכיות לצד מקור הנתונים שברצונך להסיר ובחר **מחק** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="22786-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="22786-148">אשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="22786-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]