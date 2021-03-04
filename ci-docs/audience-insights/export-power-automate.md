---
title: מחבר Power Automate | Microsoft Docs
description: צור זרימות ב- Microsoft Power Automate מ- Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268825"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="d0bf2-103">מחבר Power Automate (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="d0bf2-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="d0bf2-104">הפעל אירועים ספציפיים כך שיתרחשו באופן אוטומטי כאשר הנתונים שלך ישתנו ונהל זרימות מורכבות יותר ישירות ב- [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="d0bf2-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="d0bf2-105">גורמים מפעילים של Power Automate</span><span class="sxs-lookup"><span data-stu-id="d0bf2-105">Power Automate triggers</span></span>

<span data-ttu-id="d0bf2-106">השתמש בגורמים מפעילים כדי ליצור זרמי ענן ולהפוך משימות חוזרות לאוטומטיות, כגון הודעות או פעולות מתקדמות יותר.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="d0bf2-107">הפעל כאשר רענון מקור נתונים נכשל.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="d0bf2-108">הפעל כאשר רענון מקור נתונים מצליח.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="d0bf2-109">הפעל כאשר סף כלשהו נחצה במקטע.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="d0bf2-110">הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="d0bf2-111">הפעל כאשר סף כלשהו נחצה במדד עסקי.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="d0bf2-112">הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="d0bf2-113">הפעל כאשר רענון מלא של (מקורות נתונים, פלחים, מדידות,...) הושלם.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="d0bf2-114">הפעל לאחר השלמת רענון של תהליך האיחוד (מפה, התאמה, מיזוג).</span><span class="sxs-lookup"><span data-stu-id="d0bf2-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="d0bf2-115">[הגדר את הגורמים המפעילים ב- Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="d0bf2-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="d0bf2-116">פעולות Power Automate</span><span class="sxs-lookup"><span data-stu-id="d0bf2-116">Power Automate actions</span></span>
<span data-ttu-id="d0bf2-117">מחבר Power Automate מספק פעולות אחרות לגורמים המפעילים הזמינים.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="d0bf2-118">לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="d0bf2-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="d0bf2-119">צור זרימת Power Automate</span><span class="sxs-lookup"><span data-stu-id="d0bf2-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="d0bf2-120">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="d0bf2-121">באריח **Power Automate**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="d0bf2-122">מחבר Customer Insights‏ (preview) ב- Power Automate נפתח.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="d0bf2-123">**כניסה** אל Power Automate.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="d0bf2-124">בחר אחד מהגורמים המפעילים הזמינים והוסף שלבים נוספים לזרימה החדשה שלך.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="d0bf2-125">למידע נוסף, ראה [צור זרימת ענן ב- Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="d0bf2-125">For more information, see [Create a cloud flow in Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="d0bf2-126">דוגמאות לשימוש בזרימות:</span><span class="sxs-lookup"><span data-stu-id="d0bf2-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="d0bf2-127">פרסם הודעה בערוץ Microsoft Teams אם רענון מקור נתונים נכשל.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="d0bf2-128">שלח דואר לבעלי הנתונים בעת חציית ערך סף בפלח.</span><span class="sxs-lookup"><span data-stu-id="d0bf2-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]