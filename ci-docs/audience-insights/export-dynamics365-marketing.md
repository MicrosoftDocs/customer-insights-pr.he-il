---
title: ייצוא נתוני Customer Insights אל Dynamics 365 Marketing
description: למדו כיצד להגדיר את החיבור אל Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269055"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="a9987-103">מחבר עבור Dynamics 365 Marketing (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="a9987-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a9987-104">השתמש ב[פלחים](segments.md) כדי ליצור קמפיינים וליצור קשר עם קבוצות ספציפיות של לקוחות באמצעות Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a9987-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="a9987-105">למידע נוסף ראה [השתמש בקטעים מ- Dynamics 365 Customer Insights עם Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="a9987-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="a9987-106">דרישה מוקדמת</span><span class="sxs-lookup"><span data-stu-id="a9987-106">Prerequisite</span></span>

- <span data-ttu-id="a9987-107">רשומות אנשי קשר מוכרחות להיות קיימות ב- Dynamics 365 Marketing לפני שתוכל לייצא פלח מ- Customer Insights אל Marketing.</span><span class="sxs-lookup"><span data-stu-id="a9987-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="a9987-108">המשך לקרוא על אופן הקליטה של אנשי קשר ב- [Dynamics 365 Marketing באמצעות Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="a9987-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="a9987-109">ייצוא פלחים מ- audience insights אל Marketing לא ייצור רשומות אנשי קשר חדשות במופעי Marketing.</span><span class="sxs-lookup"><span data-stu-id="a9987-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="a9987-110">יש לקלוט את רשומות אנשי הקשר מ- Marketing ב- audience insights ולהשתמש בהן כמקור נתונים.</span><span class="sxs-lookup"><span data-stu-id="a9987-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="a9987-111">יש גם לכלול אותן בישות 'לקוח' המאוחדת כדי למפות מזהי לקוחות למזהי אנשי קשר לפני ייצוא הפלחים.</span><span class="sxs-lookup"><span data-stu-id="a9987-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="a9987-112">קביעת תצורת המחבר עבור Marketing</span><span class="sxs-lookup"><span data-stu-id="a9987-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="a9987-113">ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="a9987-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="a9987-114">תחת **Dynamics 365 Marketing**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="a9987-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="a9987-115">תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="a9987-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="a9987-116">הזן את כתובת ה- URL של Marketing של הארגון שלך בשדה **כתובת שרת**.</span><span class="sxs-lookup"><span data-stu-id="a9987-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="a9987-117">במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="a9987-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="a9987-118">מפה שדה של מזהה לקוח למזהה איש הקשר של Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="a9987-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="a9987-119">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="a9987-119">Select **Next**.</span></span>

1. <span data-ttu-id="a9987-120">בחר קטע אחד או יותר.</span><span class="sxs-lookup"><span data-stu-id="a9987-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="a9987-121">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="a9987-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="a9987-122">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="a9987-122">Export the data</span></span>

<span data-ttu-id="a9987-123">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="a9987-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="a9987-124">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a9987-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]