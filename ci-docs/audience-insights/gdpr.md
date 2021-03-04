---
title: בקשות של של זכויות נושא נתונים (DSR) במסגרת GDPR | Microsoft Docs
description: הגב לבקשות נושא נתונים עבור יכולת Audience Insights של Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268687"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="2e7a8-103">בקשות של של זכויות נושא נתונים (DSR) במסגרת GDPR</span><span class="sxs-lookup"><span data-stu-id="2e7a8-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="2e7a8-104">תגובה לבקשות מחיקת נושא נתוניםש ל GDPR עבור יכולת Audience Insights של Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="2e7a8-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="2e7a8-105">"הזכות למחוק מידע" על ידי הסרת נתונים אישיים מנתוני לקוחות של ארגון הינה הגנה מרכזית בתקנה הכללית להגנה על נתונים (GDPR).</span><span class="sxs-lookup"><span data-stu-id="2e7a8-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="2e7a8-106">הסרת נתונים אישיים כוללת הסרת כל הנתונים האישיים והיומנים שנוצרו על ידי המערכת, למעט מידע ביומן ביקורת.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="2e7a8-107">נהל בקשות למחיקת נתונים</span><span class="sxs-lookup"><span data-stu-id="2e7a8-107">Manage data subject delete requests</span></span>

<span data-ttu-id="2e7a8-108">Audience Insights מציע את חוויות המוצר הבאות למחיקת נתונים אישיים עבור לקוח או משתמש ספציפיים:</span><span class="sxs-lookup"><span data-stu-id="2e7a8-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="2e7a8-109">**נהל בקשות מחיקה של נתוני לקוחות**: נתוני לקוחות ב- Customer Insights מעובדים ממקורות נתונים מקוריים וחיצוניים ל- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="2e7a8-110">יש לבצע את כל בקשות המחיקה של GDPR במקור הנתונים המקורי.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="2e7a8-111">**נהל בקשות מחיקה עבור נתוני משתמש Customer Insights**: הנתונים עבור משתמשים נוצרים על-ידי Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="2e7a8-112">יש לבצע את כל בקשות המחיקה של GDPR ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="2e7a8-113">נהל בקשות מחיקה של נתוני לקוחות</span><span class="sxs-lookup"><span data-stu-id="2e7a8-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="2e7a8-114">מנהל Customer Insights יכול לבצע את הצעדים הבאים להסרת נתוני לקוחות שנמחקו במקור הנתונים:</span><span class="sxs-lookup"><span data-stu-id="2e7a8-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="2e7a8-115">היכנס אל Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="2e7a8-116">ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**</span><span class="sxs-lookup"><span data-stu-id="2e7a8-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="2e7a8-117">עבור כל מקור נתונים ברשימה המכילה נתוני לקוחות שנמחקו:</span><span class="sxs-lookup"><span data-stu-id="2e7a8-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="2e7a8-118">בחר (...) ולאחר מכן בחר **רענן**.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="2e7a8-119">בדוק את המצב של מקור הנתונים תחת **מצב**.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="2e7a8-120">סימן וי פירושו שהרענון בוצע בהצלחה.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="2e7a8-121">משולש אזהרה פירושו שמשהו השתבש.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="2e7a8-122">אם מוצג משולש אזהרה, צור קשר עם D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e7a8-123">![טיפול בבקשות מחיקה של GDPR של נתוני לקוחות](media/gdpr-data-sources.png "טיפול בבקשות מחיקה של GDPR של נתוני לקוחות")</span><span class="sxs-lookup"><span data-stu-id="2e7a8-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="2e7a8-124">ניהול בקשות מחיקה עבור נתוני משתמשים</span><span class="sxs-lookup"><span data-stu-id="2e7a8-124">Manage delete requests for user data</span></span>

<span data-ttu-id="2e7a8-125">מנהל מערכת של Customer Insights יכול לבצע את הצעדים הבאים למחיקת נתוני לקוחות ב- Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="2e7a8-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="2e7a8-126">היכנס אל Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="2e7a8-127">ב- audience insights, עבור אל **ניהול** > **הרשאות**.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="2e7a8-128">בחר את תיבת הסימון עבור המשתמשים שברצונך למחוק.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="2e7a8-129">בחר **הסר**.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="2e7a8-130">![טיפול בבקשות מחיקה של GDPR עבור נתוני משתמשים](media/gdpr-permissions.png "טיפול בבקשות מחיקה של GDPR עבור נתוני משתמשים")</span><span class="sxs-lookup"><span data-stu-id="2e7a8-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="2e7a8-131">תגובה לבקשות לייצוא נתוני GDPR</span><span class="sxs-lookup"><span data-stu-id="2e7a8-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="2e7a8-132">כחלק מהמחויבות שלנו לעבוד יחד אתך במסע שלך עם התקנה הכללית להגנה על נתונים (GDPR), פיתחנו תיעוד שיעזור לך להתכונן.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="2e7a8-133">תיעוד זה מתאר שלבים שניתן לבצע עוד היום כדי לתמוך בתאימות ל- GDPR בעת השימוש ב- Audience Insights.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="2e7a8-134">נהל ייצוא וצפה בבקשות</span><span class="sxs-lookup"><span data-stu-id="2e7a8-134">Manage export and view requests</span></span>

<span data-ttu-id="2e7a8-135">הזכות לניידות נתונים מאפשרת לאדם שאותו הנתונים מתארים לבקש עותק של הנתונים האישיים שלו בתבנית אלקטרונית ("תבנית מובנית, נפוצה, קריאה על-ידי מכונה ומאפשרת פעולה הדדית") שניתנת להעברה לבקר נתונים אחר.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="2e7a8-136">ייצוא נתוני לקוחות (מנהל דייר)</span><span class="sxs-lookup"><span data-stu-id="2e7a8-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="2e7a8-137">מנהל דייר יכול לבצע את השלבים הבאים לייצוא נתונים:</span><span class="sxs-lookup"><span data-stu-id="2e7a8-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="2e7a8-138">לשלוח דואר אלקטרוני אל D365CI@microsoft.com עם ציון כתובת הדואר האלקטרוני של הלקוח בבקשה.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="2e7a8-139">צוות Customer Insights ישלח דואר לכתובת הדואר הרשומה של מנהל הדייר, עם בקשה לאשר ייצוא נתונים.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="2e7a8-140">יש לקבל את האישור לייצוא הנתונים עבור הלקוח המבוקש.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="2e7a8-141">קבל את הנתונים המיוצאים באמצעות כתובת הדואר של מנהל הדייר.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="2e7a8-142">ייצוא נתוני משתמשים (מנהל דייר)</span><span class="sxs-lookup"><span data-stu-id="2e7a8-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="2e7a8-143">שלח דואר אלקטרוני אל D365CI@microsoft.com עם ציון כתובת הדואר האלקטרוני של המשתמש בבקשה.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="2e7a8-144">צוות Customer Insights ישלח דואר לכתובת הדואר הרשומה של מנהל הדייר, עם בקשה לאשר ייצוא נתונים.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="2e7a8-145">יש לקבל את האישור לייצוא הנתונים עבור המשתמש המבוקש.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="2e7a8-146">קבל את הנתונים המיוצאים באמצעות כתובת הדואר של מנהל הדייר.</span><span class="sxs-lookup"><span data-stu-id="2e7a8-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]