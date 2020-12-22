---
title: מחבר Power BI
description: למד איך להשתמש במחבר Dynamics 365 Customer Insights ב- Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405869"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="8c461-103">Connector עבור Power BI (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="8c461-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="8c461-104">צור תצוגות חזותיות עבור הנתונים שלך עם Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="8c461-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="8c461-105">צור תובנות נוספות ובנה דוחות בעזרת נתוני הלקוח המאוחד שלך.</span><span class="sxs-lookup"><span data-stu-id="8c461-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8c461-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="8c461-106">Prerequisites</span></span>

- <span data-ttu-id="8c461-107">יש לך פרופילי לקוחות מאוחדים.</span><span class="sxs-lookup"><span data-stu-id="8c461-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="8c461-108">הגרסה האחרונה של [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) מותקנת במחשב שלך.</span><span class="sxs-lookup"><span data-stu-id="8c461-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="8c461-109">[למד עוד על Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="8c461-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="8c461-110">קביעת תצורת המחבר עבור Power BI</span><span class="sxs-lookup"><span data-stu-id="8c461-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="8c461-111">ב- Power BI Desktop, בחר **קובץ** > **קבל נתונים**.</span><span class="sxs-lookup"><span data-stu-id="8c461-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="8c461-112">בחר **הצג יותר** וחפש את **Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="8c461-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="8c461-113">בחר את התוצאה ובחר **התחבר**.</span><span class="sxs-lookup"><span data-stu-id="8c461-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="8c461-114">**התחבר** עם אותו חשבון ארגוני שבו אתה משתמש עבור Customer Insights ובחר **התחבר**.</span><span class="sxs-lookup"><span data-stu-id="8c461-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="8c461-115">החשבון שאתה מציין בשלב זה משמש לאיסוף נתונים מ-Customer Insights ואינו צריך להיות זהה לחשבון איתו נכנסת ל-Power BI.</span><span class="sxs-lookup"><span data-stu-id="8c461-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="8c461-116">כדי לאפס את החשבון המשמש להבאת נתונים, פתח את Power BI ועבור אל **קובץ** > **אפשרויות** > **הגדרות** > **הגדרות מקור נתונים**.</span><span class="sxs-lookup"><span data-stu-id="8c461-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="8c461-117">ברשימת מקורות הנתונים בחר **Dynamics 365 Customer Insights התחברות** ובחר **נקה הרשאות**.</span><span class="sxs-lookup"><span data-stu-id="8c461-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="8c461-118">בתיבת הדו-שיח **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="8c461-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="8c461-119">אתה רואה את רשימת הסביבות שיש לך גישה אליהן.</span><span class="sxs-lookup"><span data-stu-id="8c461-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="8c461-120">הרחב סביבה ופתח כל אחת מהתיקיות (ישויות, מדידות, פלחים, העשרות).</span><span class="sxs-lookup"><span data-stu-id="8c461-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="8c461-121">לדוגמה, פתח את התיקיה **ישויות** כדי לראות את כל הישויות שאתה יכול לייבא.</span><span class="sxs-lookup"><span data-stu-id="8c461-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="8c461-122">![נווט במחבר Power BI](media/power-bi-navigator.png "נווט במחבר Power BI")</span><span class="sxs-lookup"><span data-stu-id="8c461-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="8c461-123">בחר את תיבות הסימון לצד הישויות שיש לכלול ו **טען**.</span><span class="sxs-lookup"><span data-stu-id="8c461-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="8c461-124">באפשרותך לבחור ישויות מרובות מכמה סביבות.</span><span class="sxs-lookup"><span data-stu-id="8c461-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="8c461-125">תראה תיבת דו-שיח שנטענת בזמן שהישויות נטענות.</span><span class="sxs-lookup"><span data-stu-id="8c461-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="8c461-126">לאחר שכל הישויות שנבחרו נטענו, באפשרותך להשתמש ביכולות של Power BI כדי להציג את הנתונים באופן חזותי.</span><span class="sxs-lookup"><span data-stu-id="8c461-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="8c461-127">ערכות נתונים גדולות</span><span class="sxs-lookup"><span data-stu-id="8c461-127">Large data sets</span></span>

<span data-ttu-id="8c461-128">מחבר Customer Insights עבור Power BI נועד לעבוד עבור ערכות נתונים המכילות עד מיליון פרופילי לקוחות.</span><span class="sxs-lookup"><span data-stu-id="8c461-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="8c461-129">ייבוא של ערכות נתונים גדולות יותר עשוי לעבוד, אך זה לוקח זמן רב.</span><span class="sxs-lookup"><span data-stu-id="8c461-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="8c461-130">בנוסף, התהליך עלול להיקלע לפסק זמן בגלל מגבלות של Power BI.</span><span class="sxs-lookup"><span data-stu-id="8c461-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="8c461-131">למידע נוסף ראה [Power BI: המלצות לערכות נתונים גדולות](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="8c461-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="8c461-132">עבוד עם קבוצת משנה של נתונים</span><span class="sxs-lookup"><span data-stu-id="8c461-132">Work with a subset of data</span></span>

<span data-ttu-id="8c461-133">שקול לעבוד עם ערכת משנה של הנתונים שלך.</span><span class="sxs-lookup"><span data-stu-id="8c461-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="8c461-134">לדוגמה, באפשרותך ליצור [פלחים](segments.md) במקום לייצא את כל רשומות הלקוחות אל Power BI.</span><span class="sxs-lookup"><span data-stu-id="8c461-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
