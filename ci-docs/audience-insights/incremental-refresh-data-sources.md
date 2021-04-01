---
title: רענון מצטבר עבור מקורות נתונים מבוססי-Power Query
description: רענן נתונים חדשים ומעודכנים עבור מקורות נתונים גדולים המבוססים על Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 03f76bcfc7336d8430146e8a26ffa649c6a17db0
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596822"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="06c6e-103">רענון מצטבר עבור מקורות נתונים מבוססי Power Query</span><span class="sxs-lookup"><span data-stu-id="06c6e-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="06c6e-104">רענון מצטבר של מקורות נתונים מספק את היתרונות הבאים:</span><span class="sxs-lookup"><span data-stu-id="06c6e-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="06c6e-105">**רענון מהר יותר** - רק הנתונים שהשתנו מתרעננים.</span><span class="sxs-lookup"><span data-stu-id="06c6e-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="06c6e-106">לדוגמה, תוכל לרענן רק את חמשת הימים האחרונים של ערכת נתונים היסטוריים.</span><span class="sxs-lookup"><span data-stu-id="06c6e-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="06c6e-107">**אמינות מוגברת** - ברענון קטן יותר, אינך צריך לשמור על חיבורים למערכות מקור רגישות למשך זמן רב, מה שמקטין את הסיכון לבעיות בחיבור.</span><span class="sxs-lookup"><span data-stu-id="06c6e-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="06c6e-108">**צריכת משאבים מופחתת** - רענון של קבוצת משנה בלבד מכלל הנתונים מביא לשימוש יעיל יותר במשאבי המחשוב ומוריד את טביעת הרגל הסביבתית.</span><span class="sxs-lookup"><span data-stu-id="06c6e-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="06c6e-109">קביעת תצורה של רענון מצטבר</span><span class="sxs-lookup"><span data-stu-id="06c6e-109">Configure incremental refresh</span></span>

<span data-ttu-id="06c6e-110">Audience insights מאפשר רענון מצטבר עבור מקורות נתונים שיובאו דרך Power Query התומך בעיבוד מצטבר.</span><span class="sxs-lookup"><span data-stu-id="06c6e-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="06c6e-111">לדוגמה, מסדי נתונים של Azure SQL עם שדות תאריך ושעה, המציינים מתי עודכנו רשומות הנתונים לאחרונה.</span><span class="sxs-lookup"><span data-stu-id="06c6e-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="06c6e-112">[יצרת מקור נתונים חדש המבוסס על Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="06c6e-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="06c6e-113">הזן שם למקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="06c6e-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="06c6e-114">בחר מקור נתונים שתומך ברענון מצטבר, כגון מסד נתונים של Azure SQL.</span><span class="sxs-lookup"><span data-stu-id="06c6e-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="06c6e-115">בחר את הישויות או הטבלאות שיש לעבד.</span><span class="sxs-lookup"><span data-stu-id="06c6e-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="06c6e-116">השלם את שלבי השינוי ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="06c6e-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="06c6e-117">בתיבת הדו-שיח **הגדר רענון מצטבר**, בחר **הגדר** כדי לפתוח את **הגדרות רענון מצטברות**.</span><span class="sxs-lookup"><span data-stu-id="06c6e-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="06c6e-118">אם תבחר **דלג**, מקור נתונים ירענן את כל ערכת הנתונים.</span><span class="sxs-lookup"><span data-stu-id="06c6e-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="06c6e-119">ניתן גם להחיל רענון מצטבר מאוחר יותר על ידי עריכת מקור נתונים קיים.</span><span class="sxs-lookup"><span data-stu-id="06c6e-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="06c6e-120">באפשרות **הגדרות רענון מצטבר**, הגדר את הרענון המצטבר עבור כל הישויות שבחרת בעת יצירת מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="06c6e-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="06c6e-121">![הגדר ישויות במקור הנתונים לצורך רענון מצטבר](media/incremental-refresh-settings.png "הגדר ישויות במקור הנתונים לצורך רענון מצטבר")</span><span class="sxs-lookup"><span data-stu-id="06c6e-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="06c6e-122">בחר ישות וספק את הפרטים הבאים:</span><span class="sxs-lookup"><span data-stu-id="06c6e-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="06c6e-123">**הגדר את המפתח הראשי**: בחר מפתח ראשי עבור הישות או הטבלה.</span><span class="sxs-lookup"><span data-stu-id="06c6e-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="06c6e-124">**הגדר את השדה "עודכן לאחרונה"**: שדה זה יציג רק תכונות מסוג תאריך ושעה.</span><span class="sxs-lookup"><span data-stu-id="06c6e-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="06c6e-125">בחר תכונה שמציינת מתי עודכנו הרשומות לאחרונה.</span><span class="sxs-lookup"><span data-stu-id="06c6e-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="06c6e-126">היא תשמש לזיהוי הרשומות שנמצאות במסגרת הזמן של הרענון המצטבר.</span><span class="sxs-lookup"><span data-stu-id="06c6e-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="06c6e-127">**בדוק אם קיימים עדכונים כל** : ציין בכל כמה זמן תרצה שהרענון המצטבר יבוצע.</span><span class="sxs-lookup"><span data-stu-id="06c6e-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="06c6e-128">בחר **שמור** כדי להשלים את יצירת מקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="06c6e-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="06c6e-129">רענון הנתונים הראשוני יהיה רענון מלא.</span><span class="sxs-lookup"><span data-stu-id="06c6e-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="06c6e-130">לאחר מכן, רענון הנתונים המצטבר מתרחש כפי שהוגדר בשלב הקודם.</span><span class="sxs-lookup"><span data-stu-id="06c6e-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]