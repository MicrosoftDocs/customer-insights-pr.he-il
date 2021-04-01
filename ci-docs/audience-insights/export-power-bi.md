---
title: מחבר Power BI
description: למד איך להשתמש במחבר Dynamics 365 Customer Insights ב- Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596040"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="b63cd-103">Connector עבור Power BI (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="b63cd-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="b63cd-104">צור תצוגות חזותיות עבור הנתונים שלך עם Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="b63cd-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="b63cd-105">צור תובנות נוספות ובנה דוחות בעזרת נתוני הלקוח המאוחד שלך.</span><span class="sxs-lookup"><span data-stu-id="b63cd-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b63cd-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="b63cd-106">Prerequisites</span></span>

- <span data-ttu-id="b63cd-107">יש לך פרופילי לקוחות מאוחדים.</span><span class="sxs-lookup"><span data-stu-id="b63cd-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="b63cd-108">הגירסה האחרונה של [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) מותקנת במחשב שלך.</span><span class="sxs-lookup"><span data-stu-id="b63cd-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="b63cd-109">[למד עוד על Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="b63cd-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="b63cd-110">קביעת תצורת המחבר עבור Power BI</span><span class="sxs-lookup"><span data-stu-id="b63cd-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="b63cd-111">ב- Power BI Desktop, בחר **קובץ** > **קבל נתונים**.</span><span class="sxs-lookup"><span data-stu-id="b63cd-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="b63cd-112">בחר **הצג יותר** וחפש את **Dynamics 365 Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="b63cd-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="b63cd-113">בחר **התחבר**.</span><span class="sxs-lookup"><span data-stu-id="b63cd-113">Select **Connect**.</span></span>

1. <span data-ttu-id="b63cd-114">**התחבר** עם אותו חשבון ארגוני שבו אתה משתמש עבור Customer Insights ובחר **התחבר**.</span><span class="sxs-lookup"><span data-stu-id="b63cd-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b63cd-115">החשבון שאתה מציין בשלב זה משמש לאיסוף נתונים מ-Customer Insights ואינו צריך להיות זהה לחשבון איתו נכנסת ל-Power BI.</span><span class="sxs-lookup"><span data-stu-id="b63cd-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="b63cd-116">כדי לאפס את החשבון המשמש להבאת נתונים, פתח את Power BI ועבור אל **קובץ** > **אפשרויות** > **הגדרות** > **הגדרות מקור נתונים**.</span><span class="sxs-lookup"><span data-stu-id="b63cd-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="b63cd-117">ברשימת מקורות הנתונים בחר **Dynamics 365 Customer Insights התחברות** ובחר **נקה הרשאות**.</span><span class="sxs-lookup"><span data-stu-id="b63cd-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="b63cd-118">בתיבת הדו-שיח **Navigator**.</span><span class="sxs-lookup"><span data-stu-id="b63cd-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="b63cd-119">אתה רואה את רשימת הסביבות שיש לך גישה אליהן.</span><span class="sxs-lookup"><span data-stu-id="b63cd-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="b63cd-120">הרחב סביבה ופתח כל אחת מהתיקיות (ישויות, מדידות, פלחים, העשרות).</span><span class="sxs-lookup"><span data-stu-id="b63cd-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="b63cd-121">לדוגמה, פתח את התיקיה **ישויות** כדי לראות את כל הישויות שאתה יכול לייבא.</span><span class="sxs-lookup"><span data-stu-id="b63cd-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="b63cd-122">![נווט במחבר Power BI](media/power-bi-navigator.png "נווט במחבר Power BI")</span><span class="sxs-lookup"><span data-stu-id="b63cd-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="b63cd-123">בחר את תיבות הסימון לצד הישויות שיש לכלול ו **טען**.</span><span class="sxs-lookup"><span data-stu-id="b63cd-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="b63cd-124">באפשרותך לבחור ישויות מרובות מכמה סביבות.</span><span class="sxs-lookup"><span data-stu-id="b63cd-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="b63cd-125">תראה תיבת דו-שיח שנטענת בזמן שהישויות נטענות.</span><span class="sxs-lookup"><span data-stu-id="b63cd-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="b63cd-126">לאחר שכל הישויות שנבחרו נטענו, באפשרותך להשתמש ביכולות של Power BI כדי להציג את הנתונים באופן חזותי.</span><span class="sxs-lookup"><span data-stu-id="b63cd-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="b63cd-127">ערכות נתונים גדולות</span><span class="sxs-lookup"><span data-stu-id="b63cd-127">Large data sets</span></span>

<span data-ttu-id="b63cd-128">מחבר Customer Insights עבור Power BI נועד לעבוד עבור ערכות נתונים המכילות עד מיליון פרופילי לקוחות.</span><span class="sxs-lookup"><span data-stu-id="b63cd-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="b63cd-129">ייבוא של ערכות נתונים גדולות יותר עשוי לעבוד, אך זה לוקח זמן רב.</span><span class="sxs-lookup"><span data-stu-id="b63cd-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="b63cd-130">בנוסף, התהליך עלול להיקלע לפסק זמן בגלל מגבלות של Power BI.</span><span class="sxs-lookup"><span data-stu-id="b63cd-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="b63cd-131">למידע נוסף ראה [Power BI: המלצות לערכות נתונים גדולות](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="b63cd-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="b63cd-132">עבוד עם קבוצת משנה של נתונים</span><span class="sxs-lookup"><span data-stu-id="b63cd-132">Work with a subset of data</span></span>

<span data-ttu-id="b63cd-133">שקול לעבוד עם ערכת משנה של הנתונים שלך.</span><span class="sxs-lookup"><span data-stu-id="b63cd-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="b63cd-134">לדוגמה, באפשרותך ליצור [פלחים](segments.md) במקום לייצא את כל רשומות הלקוחות אל Power BI.</span><span class="sxs-lookup"><span data-stu-id="b63cd-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="b63cd-135">פתרון בעיות</span><span class="sxs-lookup"><span data-stu-id="b63cd-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="b63cd-136">סביבת Customer Insights לא מוצגת ב- Power BI</span><span class="sxs-lookup"><span data-stu-id="b63cd-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="b63cd-137">סביבות שיש להן יותר מ[קשר](relationships.md) אחד מוגדר בין שתי ישויות זהות ב- audience insights לא יהיו זמינות במחבר Power BI.</span><span class="sxs-lookup"><span data-stu-id="b63cd-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="b63cd-138">באפשרותך לזהות ולהסיר את הקשרים הכפולים.</span><span class="sxs-lookup"><span data-stu-id="b63cd-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="b63cd-139">ב- audience insights, עבור אל **נתונים** > **קשרים** בסביבה שחסרה לך ב- Power BI.</span><span class="sxs-lookup"><span data-stu-id="b63cd-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="b63cd-140">זהה קשרים כפולים:</span><span class="sxs-lookup"><span data-stu-id="b63cd-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="b63cd-141">בדוק אם יש יותר מקשר אחד המוגדר בין אותן שתי ישויות.</span><span class="sxs-lookup"><span data-stu-id="b63cd-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="b63cd-142">בדוק אם נוצר קשר בין שתי ישויות שנכללות שתיהן בתהליך האיחוד.</span><span class="sxs-lookup"><span data-stu-id="b63cd-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="b63cd-143">יש קשר משתמע המוגדר בין כל הישויות הנכללות בתהליך האיחוד.</span><span class="sxs-lookup"><span data-stu-id="b63cd-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="b63cd-144">הסר כל קשר כפול שזוהה.</span><span class="sxs-lookup"><span data-stu-id="b63cd-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="b63cd-145">לאחר הסרת הקשרים הכפולים, נסה לקבוע שוב את תצורת מחבר Power BI.</span><span class="sxs-lookup"><span data-stu-id="b63cd-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="b63cd-146">הסביבה צריכה להיות זמינה כעת.</span><span class="sxs-lookup"><span data-stu-id="b63cd-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]