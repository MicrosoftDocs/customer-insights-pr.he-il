---
title: מחבר Power Automate | Microsoft Docs
description: צור זרימות ב- Microsoft Power Automate מתוך Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597926"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="35853-103">מחבר Power Automate (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="35853-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="35853-104">הפעל אירועים ספציפיים כך שיתרחשו באופן אוטומטי כאשר הנתונים שלך ישתנו ונהל זרימות מורכבות יותר ישירות ב- [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="35853-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="35853-105">גורמים מפעילים של Power Automate</span><span class="sxs-lookup"><span data-stu-id="35853-105">Power Automate triggers</span></span>

<span data-ttu-id="35853-106">השתמש בגורמים מפעילים כדי ליצור זרמי ענן ולהפוך משימות חוזרות לאוטומטיות, כגון הודעות או פעולות מתקדמות יותר.</span><span class="sxs-lookup"><span data-stu-id="35853-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="35853-107">הפעל כאשר רענון מקור נתונים נכשל.</span><span class="sxs-lookup"><span data-stu-id="35853-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="35853-108">הפעל כאשר רענון מקור נתונים מצליח.</span><span class="sxs-lookup"><span data-stu-id="35853-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="35853-109">הפעל כאשר סף כלשהו נחצה במקטע.</span><span class="sxs-lookup"><span data-stu-id="35853-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="35853-110">הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.</span><span class="sxs-lookup"><span data-stu-id="35853-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="35853-111">הפעל כאשר סף כלשהו נחצה במדד עסקי.</span><span class="sxs-lookup"><span data-stu-id="35853-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="35853-112">הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.</span><span class="sxs-lookup"><span data-stu-id="35853-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="35853-113">הפעל כאשר רענון מלא של (מקורות נתונים, פלחים, מדידות,...) הושלם.</span><span class="sxs-lookup"><span data-stu-id="35853-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="35853-114">הפעל לאחר השלמת רענון של תהליך האיחוד (מפה, התאמה, מיזוג).</span><span class="sxs-lookup"><span data-stu-id="35853-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="35853-115">[הגדר את הגורמים המפעילים ב- Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="35853-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="35853-116">פעולות Power Automate</span><span class="sxs-lookup"><span data-stu-id="35853-116">Power Automate actions</span></span>
<span data-ttu-id="35853-117">מחבר Power Automate מספק פעולות אחרות לגורמים המפעילים הזמינים.</span><span class="sxs-lookup"><span data-stu-id="35853-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="35853-118">לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="35853-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="35853-119">צור זרימת Power Automate</span><span class="sxs-lookup"><span data-stu-id="35853-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="35853-120">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="35853-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="35853-121">באריח **Power Automate**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="35853-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="35853-122">מחבר Customer Insights‏ (preview) ב- Power Automate נפתח.</span><span class="sxs-lookup"><span data-stu-id="35853-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="35853-123">**כניסה** אל Power Automate.</span><span class="sxs-lookup"><span data-stu-id="35853-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="35853-124">בחר אחד מהגורמים המפעילים הזמינים והוסף שלבים נוספים לזרימה החדשה שלך.</span><span class="sxs-lookup"><span data-stu-id="35853-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="35853-125">למידע נוסף, ראה [צור זרימת ענן ב- Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="35853-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="35853-126">דוגמאות לשימוש בזרימות:</span><span class="sxs-lookup"><span data-stu-id="35853-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="35853-127">פרסם הודעה בערוץ Microsoft Teams אם רענון מקור נתונים נכשל.</span><span class="sxs-lookup"><span data-stu-id="35853-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="35853-128">שלח דואר לבעלי הנתונים בעת חציית ערך סף בפלח.</span><span class="sxs-lookup"><span data-stu-id="35853-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]