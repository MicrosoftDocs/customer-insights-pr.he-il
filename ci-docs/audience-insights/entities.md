---
title: ישויות וערכות נתונים
description: הצג נתונים בדף 'ישויות'.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e71c69a6207147d8cd65363d51a5fa6bbf896151
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269377"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="42a44-103">ישויות ב- audience insights</span><span class="sxs-lookup"><span data-stu-id="42a44-103">Entities in audience insights</span></span>

<span data-ttu-id="42a44-104">לאחר [הגדרת מקורות הנתונים](data-sources.md), עבור אל **ישויות** כדי להעריך את איכות הנתונים המובאים.</span><span class="sxs-lookup"><span data-stu-id="42a44-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="42a44-105">ישויות נחשבות לערכות נתונים.</span><span class="sxs-lookup"><span data-stu-id="42a44-105">Entities are considered datasets.</span></span> <span data-ttu-id="42a44-106">יכולות מרובות של Dynamics 365 Customer Insights מבוססות על ישויות אלה.</span><span class="sxs-lookup"><span data-stu-id="42a44-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="42a44-107">עיון בהם מקרוב יכול לעזור לך לאמת את הפלט של יכולות אלה.</span><span class="sxs-lookup"><span data-stu-id="42a44-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="42a44-108">הדף **ישויות** מציג ישויות וכולל מספר עמודות:</span><span class="sxs-lookup"><span data-stu-id="42a44-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="42a44-109">**שם**: שם ישות הנתונים.</span><span class="sxs-lookup"><span data-stu-id="42a44-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="42a44-110">אם אתה רואה סמל אזהרה ליד שם ישות, פירוש הדבר שהנתונים עבור אותה ישות לא נטענו בהצלחה.</span><span class="sxs-lookup"><span data-stu-id="42a44-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="42a44-111">**מקור**: סוג מקור הנתונים ששולב בישות</span><span class="sxs-lookup"><span data-stu-id="42a44-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="42a44-112">**נוצר על ידי**: שם האדם שיצר את הישות</span><span class="sxs-lookup"><span data-stu-id="42a44-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="42a44-113">**נוצר**: תאריך ושעה של יצירת הישות</span><span class="sxs-lookup"><span data-stu-id="42a44-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="42a44-114">**עודכן על ידי**: שם האדם שעדכן את הישות</span><span class="sxs-lookup"><span data-stu-id="42a44-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="42a44-115">**עודכן לאחרונה**: תאריך ושעה של העדכון האחרון של הישות</span><span class="sxs-lookup"><span data-stu-id="42a44-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="42a44-116">**רענון אחרון**: תאריך ושעה של רענון הנתונים האחרון</span><span class="sxs-lookup"><span data-stu-id="42a44-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="42a44-117">בחינת נתוני ישות ספציפית</span><span class="sxs-lookup"><span data-stu-id="42a44-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="42a44-118">בחר ישות כדי לחקור את השדות והרשומות השונים הכלולים באותה ישות.</span><span class="sxs-lookup"><span data-stu-id="42a44-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42a44-119">![בחר ישות](media/data-manager-entities-data.png "בחר ישות")</span><span class="sxs-lookup"><span data-stu-id="42a44-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="42a44-120">הכרטיסיה **נתונים** נבחרת כברירת מחדל ומציגה טבלה עם פרטים על רשומות נפרדות של הישות.</span><span class="sxs-lookup"><span data-stu-id="42a44-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42a44-121">![טבלת שדות](media/data-manager-entities-fields.PNG "טבלת שדות")</span><span class="sxs-lookup"><span data-stu-id="42a44-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="42a44-122">הכרטיסיה **שדות** מציגה טבלה עם פרטי הישות שנבחרה, כגון שמות שדות, סוגי נתונים וסוגים.</span><span class="sxs-lookup"><span data-stu-id="42a44-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="42a44-123">העמודה **סוג** מציגה סוגים שקשורים ל- Common Data Model, שמזוהים באופן אוטומטי על ידי המערכת או באמצעות [מיפוי ידני](map-entities.md) על ידי משתמשים.</span><span class="sxs-lookup"><span data-stu-id="42a44-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="42a44-124">אלה הם סוגים סמנטיים שיכולים להיות שונים מסוגי הנתונים של המאפיינים - למשל, לשדה *דואר* בהמשך יש סוג נתונים *טקסט* אבל הסוג (הסמנטי) של Common Data Model שלו יכול להיות *דואר* או *כתובת דואר*.</span><span class="sxs-lookup"><span data-stu-id="42a44-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="42a44-125">בשתי הטבלאות מופיעה רק דגימה מנתוני היישות.</span><span class="sxs-lookup"><span data-stu-id="42a44-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="42a44-126">כדי להציג את ערכת הנתונים המלאה, עבור אל דף **מקורות נתונים**, בחר ישות ובחר באפשרות **עריכה**, ולאחר מכן הצג את נתוני הישות עם עורך Power Query כפי שמוסבר [במקורות נתונים](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="42a44-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="42a44-127">כדי ללמוד עוד על הנתונים שנמצאים בישות, עמודת **הסיכום** מספקת מאפיינים חשובים מסוימים של הנתונים, כגון ערכי null, ערכים חסרים, ערכים ייחודיים, ספירות והפצות, בהתאם לנתונים.</span><span class="sxs-lookup"><span data-stu-id="42a44-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="42a44-128">בחר את סמל התרשים כדי לראות את סיכום הנתונים.</span><span class="sxs-lookup"><span data-stu-id="42a44-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="42a44-129">![סמל סיכום](media/data-manager-entities-summary.png "טבלת סיכום הנתונים")</span><span class="sxs-lookup"><span data-stu-id="42a44-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="42a44-130">השלב הבא</span><span class="sxs-lookup"><span data-stu-id="42a44-130">Next step</span></span>

<span data-ttu-id="42a44-131">עיין בנושא [איחוד](data-unification.md) כדי ללמוד כיצד *למפות*, *להתאים*, *ולמזג* את הנתונים שעובדו.</span><span class="sxs-lookup"><span data-stu-id="42a44-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]