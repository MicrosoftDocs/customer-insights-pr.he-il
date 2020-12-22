---
title: מחבר Power Automate | Microsoft Docs
description: צור זרימות ב- Microsoft Power Automate מ- Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405864"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="f7d96-103">מחבר Power Automate (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="f7d96-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="f7d96-104">הפעל אירועים ספציפיים כך שיתרחשו באופן אוטומטי כאשר הנתונים שלך ישתנו ונהל זרימות מורכבות יותר ישירות ב- [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="f7d96-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="f7d96-105">גורמים מפעילים של Power Automate</span><span class="sxs-lookup"><span data-stu-id="f7d96-105">Power Automate triggers</span></span>

<span data-ttu-id="f7d96-106">אתה יכול להשתמש במגוון גורמים מפעילים המאפשרים לך ליצור זרימות לאוטומציה של משימות חוזרות, כגון התראות או פעולות מתקדמות יותר.</span><span class="sxs-lookup"><span data-stu-id="f7d96-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="f7d96-107">הפעל כאשר רענון מקור נתונים נכשל.</span><span class="sxs-lookup"><span data-stu-id="f7d96-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="f7d96-108">הפעל כאשר רענון מקור נתונים מצליח.</span><span class="sxs-lookup"><span data-stu-id="f7d96-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="f7d96-109">הפעל כאשר סף כלשהו נחצה במקטע.</span><span class="sxs-lookup"><span data-stu-id="f7d96-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="f7d96-110">הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.</span><span class="sxs-lookup"><span data-stu-id="f7d96-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="f7d96-111">הפעל כאשר סף כלשהו נחצה במדד עסקי.</span><span class="sxs-lookup"><span data-stu-id="f7d96-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="f7d96-112">הגורם המפעיל מוגבל לחצייה של סף כלפי מעלה.</span><span class="sxs-lookup"><span data-stu-id="f7d96-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="f7d96-113">הפעל כאשר רענון מלא של (מקורות נתונים, פלחים, מדידות,...) הושלם.</span><span class="sxs-lookup"><span data-stu-id="f7d96-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="f7d96-114">הפעל לאחר השלמת רענון של תהליך האיחוד (מפה, התאמה, מיזוג).</span><span class="sxs-lookup"><span data-stu-id="f7d96-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="f7d96-115">[הגדר את הגורמים המפעילים ב- Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="f7d96-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="f7d96-116">פעולות Power Automate</span><span class="sxs-lookup"><span data-stu-id="f7d96-116">Power Automate actions</span></span>
<span data-ttu-id="f7d96-117">מחבר Power Automate מספק פעולות אחרות לגורמים המפעילים הזמינים.</span><span class="sxs-lookup"><span data-stu-id="f7d96-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="f7d96-118">לקבלת מידע נוסף, ראה [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="f7d96-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="f7d96-119">צור זרימת Power Automate ב- Audience Insights</span><span class="sxs-lookup"><span data-stu-id="f7d96-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="f7d96-120">ב- audience insights, עבור אל **ניהול** > **מערכת**.</span><span class="sxs-lookup"><span data-stu-id="f7d96-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="f7d96-121">בדף **מערכת**, בחר בכרטיסיה **מצב**.</span><span class="sxs-lookup"><span data-stu-id="f7d96-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="f7d96-122">במקטע **מקורות נתונים**, בחר **זרימות** ובחר **צור זרימה** מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="f7d96-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f7d96-123">![מחבר Power Automate מראה פעולה של יצירת זרימה](media/power-automate-connector-create-flow.png "מחבר Power Automate מראה פעולה של יצירת זרימה")</span><span class="sxs-lookup"><span data-stu-id="f7d96-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="f7d96-124">ב- Power Automate, בחר אחד מהגורמים המפעילים הזמינים ליצירת הזרימה המועדפת שלך.</span><span class="sxs-lookup"><span data-stu-id="f7d96-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="f7d96-125">אם אתה יוצר את הזרימה הראשונה שלך, ראשית יהיה עליך לאמת עם מחבר Power Automate.</span><span class="sxs-lookup"><span data-stu-id="f7d96-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
