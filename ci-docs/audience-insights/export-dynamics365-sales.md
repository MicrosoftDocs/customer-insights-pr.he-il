---
title: ייצוא נתוני Customer Insights אל Dynamics 365 Sales
description: למדו כיצד להגדיר את החיבור אל Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269009"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="3d2ae-103">מחבר עבור Dynamics 365 Sales (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="3d2ae-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="3d2ae-104">השתמש בנתוני הלקוחות שלך כדי ליצור רשימות שיווק, להמשיך לטפל בזרימות עבודה ולשלוח מבצעים באמצעות Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="3d2ae-105">דרישה מוקדמת</span><span class="sxs-lookup"><span data-stu-id="3d2ae-105">Prerequisite</span></span>

1. <span data-ttu-id="3d2ae-106">רשומות אנשי קשר מוכרחות להיות קיימות ב- Dynamics 365 Sales לפני שתוכל לייצא פלח מ- Customer Insights אל Sales.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="3d2ae-107">המשך לקרוא על אופן הקליטה של אנשי קשר ב- [Dynamics 365 Sales באמצעות Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="3d2ae-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="3d2ae-108">ייצוא פלחים מ- audience insights אל Sales לא ייצור רשומות אנשי קשר חדשות במופעי Sales.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="3d2ae-109">יש לקלוט את רשומות אנשי הקשר מ- Sales ב- audience insights ולהשתמש בהן כמקור נתונים.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="3d2ae-110">יש גם לכלול אותן בישות 'לקוח' המאוחדת כדי למפות מזהי לקוחות למזהי אנשי קשר לפני ייצוא הפלחים.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="3d2ae-111">קביעת תצורת המחבר עבור Sales</span><span class="sxs-lookup"><span data-stu-id="3d2ae-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="3d2ae-112">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3d2ae-113">תחת **Dynamics 365 Sales**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="3d2ae-114">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3d2ae-115">הזן את כתובת ה- URL של Sales של הארגון שלך בשדה **כתובת שרת**.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="3d2ae-116">במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="3d2ae-117">מפה שדה של מזהה לקוח למזהה איש הקשר של Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="3d2ae-118">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-118">Select **Next**.</span></span>

1. <span data-ttu-id="3d2ae-119">בחר קטע אחד או יותר.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="3d2ae-120">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="3d2ae-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3d2ae-121">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="3d2ae-121">Export the data</span></span>

<span data-ttu-id="3d2ae-122">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3d2ae-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3d2ae-123">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3d2ae-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]