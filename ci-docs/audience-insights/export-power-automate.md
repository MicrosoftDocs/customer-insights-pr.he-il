---
title: מחבר Power Automate | Microsoft Docs
description: צור זרימות ב- Microsoft Power Automate מתוך Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976089"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="e5942-103">מחבר Power Automate (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="e5942-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="e5942-104">הפעל אירועים ספציפיים כך שיתרחשו באופן אוטומטי כאשר הנתונים שלך ישתנו ונהל זרימות מורכבות יותר ישירות ב- [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="e5942-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="e5942-105">גורמים מפעילים של Power Automate</span><span class="sxs-lookup"><span data-stu-id="e5942-105">Power Automate triggers</span></span>

<span data-ttu-id="e5942-106">השתמש בגורמים מפעילים כדי ליצור זרמי ענן ולהפוך משימות חוזרות לאוטומטיות, כגון הודעות או פעולות מתקדמות יותר.</span><span class="sxs-lookup"><span data-stu-id="e5942-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="e5942-107">הפעל כאשר רענון מקור נתונים נכשל.</span><span class="sxs-lookup"><span data-stu-id="e5942-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="e5942-108">הפעל כאשר רענון מקור נתונים מצליח.</span><span class="sxs-lookup"><span data-stu-id="e5942-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="e5942-109">הפעל כאשר סף כלשהו נחצה במקטע.</span><span class="sxs-lookup"><span data-stu-id="e5942-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="e5942-110">הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.</span><span class="sxs-lookup"><span data-stu-id="e5942-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="e5942-111">הפעל כאשר סף כלשהו נחצה במדד עסקי.</span><span class="sxs-lookup"><span data-stu-id="e5942-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="e5942-112">רק מדידות עסקיות ללא ממד נתמכות.</span><span class="sxs-lookup"><span data-stu-id="e5942-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="e5942-113">הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.</span><span class="sxs-lookup"><span data-stu-id="e5942-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="e5942-114">הפעל כאשר רענון מלא של (מקורות נתונים, פלחים, מדידות,...) הושלם.</span><span class="sxs-lookup"><span data-stu-id="e5942-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="e5942-115">הפעל לאחר השלמת רענון של תהליך האיחוד (מפה, התאמה, מיזוג).</span><span class="sxs-lookup"><span data-stu-id="e5942-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="e5942-116">[הגדר את הגורמים המפעילים ב- Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="e5942-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="e5942-117">פעולות Power Automate</span><span class="sxs-lookup"><span data-stu-id="e5942-117">Power Automate actions</span></span>
<span data-ttu-id="e5942-118">מחבר Power Automate מספק פעולות אחרות לגורמים המפעילים הזמינים.</span><span class="sxs-lookup"><span data-stu-id="e5942-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="e5942-119">לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="e5942-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="e5942-120">צור זרימת Power Automate</span><span class="sxs-lookup"><span data-stu-id="e5942-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="e5942-121">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="e5942-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e5942-122">באריח **Power Automate**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="e5942-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="e5942-123">מחבר Customer Insights‏ (preview) ב- Power Automate נפתח.</span><span class="sxs-lookup"><span data-stu-id="e5942-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="e5942-124">**כניסה** אל Power Automate.</span><span class="sxs-lookup"><span data-stu-id="e5942-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="e5942-125">בחר אחד מהגורמים המפעילים הזמינים והוסף שלבים נוספים לזרימה החדשה שלך.</span><span class="sxs-lookup"><span data-stu-id="e5942-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="e5942-126">למידע נוסף, ראה [צור זרימת ענן ב- Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="e5942-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="e5942-127">דוגמאות לשימוש בזרימות:</span><span class="sxs-lookup"><span data-stu-id="e5942-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="e5942-128">פרסם הודעה בערוץ Microsoft Teams אם רענון מקור נתונים נכשל.</span><span class="sxs-lookup"><span data-stu-id="e5942-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="e5942-129">שלח דואר לבעלי הנתונים בעת חציית ערך סף בפלח.</span><span class="sxs-lookup"><span data-stu-id="e5942-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
