---
title: ייצוא נתוני Customer Insights אל Dynamics 365 Sales
description: למד כיצד להגדיר את החיבור ולייצא אל Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976227"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="4fd77-103">שימוש בפלחים ב- Dynamics 365 Sales‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="4fd77-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="4fd77-104">השתמש בנתוני הלקוחות שלך כדי ליצור רשימות שיווק, להמשיך לטפל בזרימות עבודה ולשלוח מבצעים באמצעות Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4fd77-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="4fd77-105">דרישה מוקדמת לחיבור</span><span class="sxs-lookup"><span data-stu-id="4fd77-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="4fd77-106">רשומות אנשי קשר מוכרחות להיות קיימות ב- Dynamics 365 Sales לפני שתוכל לייצא פלח מ- Customer Insights אל Sales.</span><span class="sxs-lookup"><span data-stu-id="4fd77-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="4fd77-107">המשך לקרוא על אופן הקליטה של אנשי קשר ב- [Dynamics 365 Sales באמצעות Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="4fd77-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="4fd77-108">ייצוא פלחים מ- audience insights אל Sales לא ייצור רשומות אנשי קשר חדשות במופעי Sales.</span><span class="sxs-lookup"><span data-stu-id="4fd77-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="4fd77-109">יש לקלוט את רשומות אנשי הקשר מ- Sales ב- audience insights ולהשתמש בהן כמקור נתונים.</span><span class="sxs-lookup"><span data-stu-id="4fd77-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="4fd77-110">יש גם לכלול אותן בישות 'לקוח' המאוחדת כדי למפות מזהי לקוחות למזהי אנשי קשר לפני ייצוא הפלחים.</span><span class="sxs-lookup"><span data-stu-id="4fd77-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="4fd77-111">הגדרת החיבור ל- Sales</span><span class="sxs-lookup"><span data-stu-id="4fd77-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="4fd77-112">עבור אל **ניהול** > **חיבורים**.</span><span class="sxs-lookup"><span data-stu-id="4fd77-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4fd77-113">בחר **הוסף חיבור** ובחר **Dynamics 365 Sales** כדי לקבוע את תצורת החיבור.</span><span class="sxs-lookup"><span data-stu-id="4fd77-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="4fd77-114">תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="4fd77-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4fd77-115">השם וסוג החיבור מתארים חיבור זה.</span><span class="sxs-lookup"><span data-stu-id="4fd77-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4fd77-116">מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.</span><span class="sxs-lookup"><span data-stu-id="4fd77-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4fd77-117">בחר מי יכול להשתמש בחיבור זה.</span><span class="sxs-lookup"><span data-stu-id="4fd77-117">Choose who can use this connection.</span></span> <span data-ttu-id="4fd77-118">אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת.</span><span class="sxs-lookup"><span data-stu-id="4fd77-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4fd77-119">לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4fd77-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="4fd77-120">הזן את כתובת ה- URL של Sales של הארגון שלך בשדה **כתובת שרת**.</span><span class="sxs-lookup"><span data-stu-id="4fd77-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="4fd77-121">במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4fd77-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="4fd77-122">מפה שדה של מזהה לקוח למזהה איש הקשר של Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="4fd77-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="4fd77-123">בחר **שמור** כדי להשלים את החיבור.</span><span class="sxs-lookup"><span data-stu-id="4fd77-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="4fd77-124">קביעת תצורה של ייצוא</span><span class="sxs-lookup"><span data-stu-id="4fd77-124">Configure an export</span></span>

<span data-ttu-id="4fd77-125">באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה.</span><span class="sxs-lookup"><span data-stu-id="4fd77-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4fd77-126">לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4fd77-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4fd77-127">עבור אל **נתונים** > **פעולות ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="4fd77-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4fd77-128">כדי ליצור ייצוא חדש, בחר **הוסף יעד**.</span><span class="sxs-lookup"><span data-stu-id="4fd77-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4fd77-129">בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="4fd77-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="4fd77-130">אם אינך רואה שם מקטע זה, אין חיבורים מסוג זה הזמינים עבורך.</span><span class="sxs-lookup"><span data-stu-id="4fd77-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="4fd77-131">בחר קטע אחד או יותר.</span><span class="sxs-lookup"><span data-stu-id="4fd77-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="4fd77-132">בחר **שמור**</span><span class="sxs-lookup"><span data-stu-id="4fd77-132">Select **Save**</span></span>

<span data-ttu-id="4fd77-133">שמירת ייצוא אינה מפעילה את הייצוא באופן מיידי.</span><span class="sxs-lookup"><span data-stu-id="4fd77-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4fd77-134">הייצוא פועל עם כל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4fd77-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4fd77-135">באפשרותך גם [לייצא נתונים לפי דרישה](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4fd77-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
