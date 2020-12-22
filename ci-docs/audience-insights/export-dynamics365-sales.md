---
title: ייצוא נתוני Customer Insights אל Dynamics 365 Sales
description: למדו כיצד להגדיר את החיבור אל Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643819"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="47778-103">מחבר עבור Dynamics 365 Sales (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="47778-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="47778-104">השתמש בנתוני הלקוחות שלך כדי ליצור רשימות שיווק, להמשיך לטפל בזרימות עבודה ולשלוח מבצעים באמצעות Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="47778-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="47778-105">דרישה מוקדמת</span><span class="sxs-lookup"><span data-stu-id="47778-105">Prerequisite</span></span>

<span data-ttu-id="47778-106">רשומות איש קשר [מ- Dynamics 365 Sales עובדו באמצעות Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="47778-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="47778-107">קביעת תצורת המחבר עבור Sales</span><span class="sxs-lookup"><span data-stu-id="47778-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="47778-108">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="47778-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="47778-109">תחת **Dynamics 365 Sales**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="47778-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="47778-110">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="47778-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="47778-111">הזן את כתובת ה- URL של Sales של הארגון שלך בשדה **כתובת שרת**.</span><span class="sxs-lookup"><span data-stu-id="47778-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="47778-112">במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="47778-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="47778-113">מפה שדה של מזהה לקוח למזהה איש הקשר של Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="47778-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="47778-114">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="47778-114">Select **Next**.</span></span>

1. <span data-ttu-id="47778-115">בחר קטע אחד או יותר.</span><span class="sxs-lookup"><span data-stu-id="47778-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="47778-116">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="47778-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="47778-117">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="47778-117">Export the data</span></span>

<span data-ttu-id="47778-118">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="47778-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="47778-119">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="47778-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
