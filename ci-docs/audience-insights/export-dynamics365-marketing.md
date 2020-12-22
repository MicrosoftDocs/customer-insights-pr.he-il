---
title: ייצוא נתוני Customer Insights אל Dynamics 365 Marketing
description: למדו כיצד להגדיר את החיבור אל Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643774"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="cabcd-103">מחבר עבור Dynamics 365 Marketing (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="cabcd-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="cabcd-104">השתמש ב[פלחים](segments.md) כדי ליצור קמפיינים וליצור קשר עם קבוצות ספציפיות של לקוחות באמצעות Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="cabcd-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="cabcd-105">למידע נוסף ראה [השתמש בקטעים מ- Dynamics 365 Customer Insights עם Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="cabcd-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="cabcd-106">דרישה מוקדמת</span><span class="sxs-lookup"><span data-stu-id="cabcd-106">Prerequisite</span></span>

<span data-ttu-id="cabcd-107">רשומות איש קשר [מ- Dynamics 365 Marketing עיבדו את Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="cabcd-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="cabcd-108">קביעת תצורת המחבר עבור Marketing</span><span class="sxs-lookup"><span data-stu-id="cabcd-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="cabcd-109">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="cabcd-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cabcd-110">תחת **Dynamics 365 Marketing**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="cabcd-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="cabcd-111">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="cabcd-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="cabcd-112">הזן את כתובת ה- URL של Marketing של הארגון שלך בשדה **כתובת שרת**.</span><span class="sxs-lookup"><span data-stu-id="cabcd-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="cabcd-113">במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="cabcd-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="cabcd-114">מפה שדה של מזהה לקוח למזהה איש הקשר של Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="cabcd-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="cabcd-115">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="cabcd-115">Select **Next**.</span></span>

1. <span data-ttu-id="cabcd-116">בחר קטע אחד או יותר.</span><span class="sxs-lookup"><span data-stu-id="cabcd-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="cabcd-117">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="cabcd-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cabcd-118">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="cabcd-118">Export the data</span></span>

<span data-ttu-id="cabcd-119">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cabcd-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cabcd-120">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cabcd-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
