---
title: ייצוא נתוני Customer Insights אל Dynamics 365 Marketing
description: למד כיצד להגדיר את החיבור ולייצא אל Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759638"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="ece58-103">שימוש בפלחים ב- Dynamics 365 Marketing‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="ece58-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="ece58-104">השתמש ב[פלחים](segments.md) כדי ליצור קמפיינים וליצור קשר עם קבוצות ספציפיות של לקוחות באמצעות Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="ece58-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="ece58-105">למידע נוסף ראה [השתמש בקטעים מ- Dynamics 365 Customer Insights עם Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="ece58-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="ece58-106">דרישה מוקדמת לחיבור</span><span class="sxs-lookup"><span data-stu-id="ece58-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="ece58-107">רשומות אנשי קשר מוכרחות להיות קיימות ב- Dynamics 365 Marketing לפני שתוכל לייצא פלח מ- Customer Insights אל Marketing.</span><span class="sxs-lookup"><span data-stu-id="ece58-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="ece58-108">המשך לקרוא על אופן הקליטה של אנשי קשר ב- [Dynamics 365 Marketing באמצעות Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="ece58-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="ece58-109">ייצוא פלחים מ- audience insights אל Marketing לא ייצור רשומות אנשי קשר חדשות במופעי Marketing.</span><span class="sxs-lookup"><span data-stu-id="ece58-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="ece58-110">יש לקלוט את רשומות אנשי הקשר מ- Marketing ב- audience insights ולהשתמש בהן כמקור נתונים.</span><span class="sxs-lookup"><span data-stu-id="ece58-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="ece58-111">יש גם לכלול אותן בישות 'לקוח' המאוחדת כדי למפות מזהי לקוחות למזהי אנשי קשר לפני ייצוא הפלחים.</span><span class="sxs-lookup"><span data-stu-id="ece58-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="ece58-112">הגדרת חיבור אל Marketing</span><span class="sxs-lookup"><span data-stu-id="ece58-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="ece58-113">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="ece58-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ece58-114">בחר **הוסף חיבור** ובחר **Dynamics 365 Marketing** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="ece58-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="ece58-115">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="ece58-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ece58-116">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="ece58-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ece58-117">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="ece58-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ece58-118">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="ece58-118">Choose who can use this connection.</span></span> <span data-ttu-id="ece58-119">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="ece58-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ece58-120">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ece58-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ece58-121">הזן את כתובת ה- URL של Marketing של הארגון שלך בשדה **כתובת שרת**.</span><span class="sxs-lookup"><span data-stu-id="ece58-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="ece58-122">במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="ece58-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="ece58-123">מפה שדה של מזהה לקוח למזהה איש הקשר של Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="ece58-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="ece58-124">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="ece58-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="ece58-125">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="ece58-125">Configure an export</span></span>

<span data-ttu-id="ece58-126">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="ece58-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ece58-127">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ece58-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ece58-128">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="ece58-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ece58-129">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="ece58-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ece58-130">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="ece58-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="ece58-131">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="ece58-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ece58-132">בחר קטע אחד או יותר.</span><span class="sxs-lookup"><span data-stu-id="ece58-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="ece58-133">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="ece58-133">Select **Save**.</span></span>

<span data-ttu-id="ece58-134">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="ece58-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ece58-135">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ece58-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ece58-136">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ece58-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
