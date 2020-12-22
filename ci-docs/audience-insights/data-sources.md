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
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643954"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="6ee10-103">מבט כולל על מקורות נתונים</span><span class="sxs-lookup"><span data-stu-id="6ee10-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6ee10-104">יכולת תובנות הקהל ב- Dynamics 365 Customer Insights מתחברת לנתונים מערכת מקורות רחבה.</span><span class="sxs-lookup"><span data-stu-id="6ee10-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="6ee10-105">לעיתים קרובות מתייחסים לחיבור למקור נתונים כאל תהליך של *עיבוד נתונים*.</span><span class="sxs-lookup"><span data-stu-id="6ee10-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="6ee10-106">לאחר עיבוד הנתונים, ניתן [לאחד](data-unification.md) ולנקוט פעולה.</span><span class="sxs-lookup"><span data-stu-id="6ee10-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="6ee10-107">הוספה של מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="6ee10-107">Add a data source</span></span>

<span data-ttu-id="6ee10-108">עיין במאמרים המפורטים על איך להוסיף מקור נתונים, בהתאם לאפשרות שבה תבחר.</span><span class="sxs-lookup"><span data-stu-id="6ee10-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="6ee10-109">ניתן להוסיף מקור נתונים בשלוש דרכים עיקריות:</span><span class="sxs-lookup"><span data-stu-id="6ee10-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="6ee10-110">דרך עשרות מחברי Power Query</span><span class="sxs-lookup"><span data-stu-id="6ee10-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="6ee10-111">דרך תיקית Common Data Model</span><span class="sxs-lookup"><span data-stu-id="6ee10-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="6ee10-112">דרך אגם ה-Common Data Service שלך</span><span class="sxs-lookup"><span data-stu-id="6ee10-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="6ee10-113">עדיין לא ניתן להוסיף נתונים ממקורות נתונים מקומיות.</span><span class="sxs-lookup"><span data-stu-id="6ee10-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="6ee10-114">סקירה של נתונים מעובדים</span><span class="sxs-lookup"><span data-stu-id="6ee10-114">Review ingested data</span></span>

<span data-ttu-id="6ee10-115">תראה את השם של כל מקור נתונים שעובד, את המצב שלו ואת הפעם האחרונה שבו הנתונים מאותו מקור רועננו.</span><span class="sxs-lookup"><span data-stu-id="6ee10-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="6ee10-116">ניתן למיין את רשימת מקורות הנתונים לפי כל עמודה.</span><span class="sxs-lookup"><span data-stu-id="6ee10-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6ee10-117">![מקור נתונים נוסף](media/configure-data-datasource-added.png "מקור נתונים נוסף")</span><span class="sxs-lookup"><span data-stu-id="6ee10-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="6ee10-118">סטאטוס</span><span class="sxs-lookup"><span data-stu-id="6ee10-118">Status</span></span>  |<span data-ttu-id="6ee10-119">תיאור</span><span class="sxs-lookup"><span data-stu-id="6ee10-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="6ee10-120">הצליח</span><span class="sxs-lookup"><span data-stu-id="6ee10-120">Successful</span></span>   |<span data-ttu-id="6ee10-121">מקור נתונים נקלט בהצלחה אם מוזכרת שעה בעמודה **בוצע רענון**.</span><span class="sxs-lookup"><span data-stu-id="6ee10-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="6ee10-122">לא התחילה</span><span class="sxs-lookup"><span data-stu-id="6ee10-122">Not started</span></span>   |<span data-ttu-id="6ee10-123">למקור הנתונים אין נתונים שנקלטו עדיין או שהוא עדיין במצב טיוטה.</span><span class="sxs-lookup"><span data-stu-id="6ee10-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="6ee10-124">עובר רענון</span><span class="sxs-lookup"><span data-stu-id="6ee10-124">Refreshing</span></span>    |<span data-ttu-id="6ee10-125">עיבוד נתונים מתבצע.</span><span class="sxs-lookup"><span data-stu-id="6ee10-125">Data ingestion is in progress.</span></span> <span data-ttu-id="6ee10-126">באפשרותך לבטל פעולה זו על-ידי בחירה באפשרות **עצור רענון** בעמודה **פעולות**.</span><span class="sxs-lookup"><span data-stu-id="6ee10-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="6ee10-127">עצירת הרענון של מקור נתונים תחזיר אותו למצב האחרון שלו.</span><span class="sxs-lookup"><span data-stu-id="6ee10-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="6ee10-128">השליחה נכשלה</span><span class="sxs-lookup"><span data-stu-id="6ee10-128">Failed</span></span>     |<span data-ttu-id="6ee10-129">עיבוד הנתונים נתקל בשגיאות.</span><span class="sxs-lookup"><span data-stu-id="6ee10-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="6ee10-130">בחר **מצב רענון** כדי לסקור פרטים נוספים במצב הרענון, לרבות פרטי שגיאה ועדכוני תהליך במורד הזרם.</span><span class="sxs-lookup"><span data-stu-id="6ee10-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="6ee10-131">טעינת הנתונים עשויה להימשך זמן מה.</span><span class="sxs-lookup"><span data-stu-id="6ee10-131">Loading data can take some time.</span></span> <span data-ttu-id="6ee10-132">לאחר רענון מוצלח, ניתן לסקור את הנתונים שעובדו בדף **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="6ee10-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="6ee10-133">לקבלת מידע נוסף, ראה [ישויות](entities.md).</span><span class="sxs-lookup"><span data-stu-id="6ee10-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="6ee10-134">רענון מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="6ee10-134">Refresh a data source</span></span>

<span data-ttu-id="6ee10-135">ניתן לרענן את מקורות הנתונים בלוח זמנים אוטומטי או לרענן אותם באופן ידני לפי דרישה.</span><span class="sxs-lookup"><span data-stu-id="6ee10-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="6ee10-136">עבור אל **ניהול** > **מערכת** > [**לוח זמנים**](system.md#schedule-tab) כדי לקבוע תצורה של רענונים מתוזמנים של כל מקורות הנתונים שקלטת.</span><span class="sxs-lookup"><span data-stu-id="6ee10-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="6ee10-137">כדי לרענן מקור נתונים לפי דרישה, בצע את השלבים הבאים:</span><span class="sxs-lookup"><span data-stu-id="6ee10-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="6ee10-138">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**</span><span class="sxs-lookup"><span data-stu-id="6ee10-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="6ee10-139">בחר את שלוש הנקודות האנכיות לצד מקור הנתונים שברצונך לרענן ובחר **רענון** מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="6ee10-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="6ee10-140">מקור הנתונים מופעל כעת עבור רענון ידני.</span><span class="sxs-lookup"><span data-stu-id="6ee10-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="6ee10-141">רענון מקור נתונים יעדכן הן את סכימת הישות והן נתונים עבור כל הישויות שצוינו במקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="6ee10-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="6ee10-142">בחר **הפסק רענון** אם ברצונך לבטל רענון קיים ומקור הנתונים יחזור למצב הרענון האחרון שלו.</span><span class="sxs-lookup"><span data-stu-id="6ee10-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="6ee10-143">מחק מקור נתונים</span><span class="sxs-lookup"><span data-stu-id="6ee10-143">Delete a data source</span></span>

1. <span data-ttu-id="6ee10-144">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="6ee10-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="6ee10-145">בחר את שלוש הנקודות האנכיות לצד מקור הנתונים שברצונך להסיר ובחר **מחק** מהתפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="6ee10-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="6ee10-146">אשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="6ee10-146">Confirm your deletion.</span></span>
