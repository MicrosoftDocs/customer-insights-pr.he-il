---
title: תוכנית Bot עבור Microsoft Teams
description: חפש פרופילי לקוחות מאוחדים ב- Microsoft Teams בעזרת תוכנית Bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267953"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="69731-103">תוכנית Bot של Teams עבור Dynamics 365 Customer Insights‎‏ (preview)</span><span class="sxs-lookup"><span data-stu-id="69731-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="69731-104">התחבר עם Microsoft Teams כדי לאפשר לתוכנית Bot לחפש פרופילי לקוחות מאוחדים בערוצי Teams.</span><span class="sxs-lookup"><span data-stu-id="69731-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="69731-105">![תוכנית Bot של Teams המציגה רשומת לקוח](media/teams-bot.png "תוכנית Bot של Teams המציגה רשומת לקוח")</span><span class="sxs-lookup"><span data-stu-id="69731-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69731-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="69731-106">Prerequisites</span></span>

<span data-ttu-id="69731-107">כדי להגדיר ולקבוע את התצורה של תוכנית ה- Bot, הדרישות המוקדמות הבאות מוכרחות להתקיים:</span><span class="sxs-lookup"><span data-stu-id="69731-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="69731-108">נוסף לפחות [מקור נתונים אחד](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="69731-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="69731-109">[תהליך האיחוד](data-unification.md) הושלם.</span><span class="sxs-lookup"><span data-stu-id="69731-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="69731-110">שדות מתווספים ל[אינדקס חיפוש וסינון ](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="69731-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="69731-111">Customer Insights ו- Teams נמצאים באותו ארגון.</span><span class="sxs-lookup"><span data-stu-id="69731-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="69731-112">קביעת התצורה של תוכנית ה- Bot</span><span class="sxs-lookup"><span data-stu-id="69731-112">Configure the bot</span></span>

1. <span data-ttu-id="69731-113">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="69731-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="69731-114">באריח Microsoft Teams, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="69731-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="69731-115">אתה מנותב מחדש אל האזור **יישומים** ב- Teams.</span><span class="sxs-lookup"><span data-stu-id="69731-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="69731-116">באפשרותך גם לפתוח את Teams ולבחור **יישומים** בפינה השמאלית התחתונה או [להשיג אותו דרך AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) ישירות.</span><span class="sxs-lookup"><span data-stu-id="69731-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="69731-117">חפש את **Customer Insights** ובחר את היישום.</span><span class="sxs-lookup"><span data-stu-id="69731-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="69731-118">בחר **הוסף**.</span><span class="sxs-lookup"><span data-stu-id="69731-118">Select **Add**.</span></span>
1. <span data-ttu-id="69731-119">לאחר הכניסה ל- Customer Insights ב- Teams, תראה הודעת קבלת פנים ותוכל להתחיל בעבודה.</span><span class="sxs-lookup"><span data-stu-id="69731-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="69731-120">דברים שניתן לעשות עם תוכנית ה- Bot</span><span class="sxs-lookup"><span data-stu-id="69731-120">Things you can do with the bot</span></span>

<span data-ttu-id="69731-121">תוכנית ה- Bot מספקת יכולות בדיקת מידע עבור פרופילי לקוחות מאוחדים.</span><span class="sxs-lookup"><span data-stu-id="69731-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="69731-122">הזן **חיפוש** ולאחר מכן שם, כתובת דוא"ל או כל שדה אחר בפרופיל הלקוח המאוחד המתווסף לאינדקס החיפוש והסינון.</span><span class="sxs-lookup"><span data-stu-id="69731-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="69731-123">תקבל כרטיס עם עד 15 שדות מפרופיל הלקוח המתקבל.</span><span class="sxs-lookup"><span data-stu-id="69731-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="69731-124">התאמות מרובות מחזירות רשימת תוצאות שבה תוכל לבחור פרופיל.</span><span class="sxs-lookup"><span data-stu-id="69731-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="69731-125">באפשרותך להוסיף את מונח החיפוש במרכאות כפולות כדי לחפש התאמה מדויקת.</span><span class="sxs-lookup"><span data-stu-id="69731-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="69731-126">אם הארגון שלך מתחזק מספר סביבות של Customer Insights באותו ארגון, באפשרותך להזין **switchinstance** כדי לבחור לאיזו סביבה ברצונך לחבר את תוכנית ה- Bot.</span><span class="sxs-lookup"><span data-stu-id="69731-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="69731-127">הזן **עזרה** כדי לראות רשימת פקודות זמינות עבור תוכנית ה- Bot.</span><span class="sxs-lookup"><span data-stu-id="69731-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]