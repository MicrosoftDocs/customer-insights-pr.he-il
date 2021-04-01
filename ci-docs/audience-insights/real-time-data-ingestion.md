---
title: קליטת נתונים בזמן אמת ומגבלות
description: מידע כללי על יכולות בזמן אמת ב- Audience Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598570"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="80d87-103">קליטת נתונים בזמן אמת (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="80d87-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="80d87-104">הפונקציונליות של כמעט בזמן אמת מאפשרת לך לראות, תוך שניות, את האינטראקציות האחרונות שביצעו הלקוחות שלך עם המוצרים או השירותים שלך.</span><span class="sxs-lookup"><span data-stu-id="80d87-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="80d87-105">הכרטיסיה [רענונים מתוזמנים](system.md#schedule-tab) כוללת מספר רב של רשומות וכמה פעולות מורכבות.</span><span class="sxs-lookup"><span data-stu-id="80d87-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="80d87-106">ראשית, הנתונים נמשכים ממקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="80d87-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="80d87-107">בשלב הבא, הנתונים מאוחדים ולאחר מכן מועשרים בעזרת מידע נוסף.</span><span class="sxs-lookup"><span data-stu-id="80d87-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="80d87-108">כל הפעלה של תהליך זה עשויה לארוך דקות עד שעות.</span><span class="sxs-lookup"><span data-stu-id="80d87-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="80d87-109">הפונקציונליות בזמן אמת מספקת מיד נתונים לצריכה, עד שהרענון המתוזמן הבא ימשוך נתונים אלה ממקור הנתונים.</span><span class="sxs-lookup"><span data-stu-id="80d87-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="80d87-110">לעדכונים בזמן אמת יש זמן תפוגה שלאחריו הם כבר לא עוקפים את הערך ממקור הנתונים:</span><span class="sxs-lookup"><span data-stu-id="80d87-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="80d87-111">עדכוני הפרופיל יישמרו למשך 4 שעות</span><span class="sxs-lookup"><span data-stu-id="80d87-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="80d87-112">פעילויות יישמרו למשך 30 יום</span><span class="sxs-lookup"><span data-stu-id="80d87-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="80d87-113">ערכים אלה הם פרמטרים של קרית API שניתן לשנות.</span><span class="sxs-lookup"><span data-stu-id="80d87-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="80d87-114">הם שואפים להבטיח שנתוני המקור שלך יישארו מקור האמת שלך.</span><span class="sxs-lookup"><span data-stu-id="80d87-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="80d87-115">אם ברצונך לכלול עדכונים בזמן אמת לזמן ארוך יותר, עליך להוסיף אותם למקור נתונים כדי שימשכו אותם במהלך הרענון המתוזמן הבא.</span><span class="sxs-lookup"><span data-stu-id="80d87-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="80d87-116">עדכון בזמן אמת של שדות פרופיל של הלקוח המאוחד</span><span class="sxs-lookup"><span data-stu-id="80d87-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="80d87-117">פרופילים מעודכנים יופיעו בתצוגת כרטיס הלקוח, או בכל תצוגה חזותית אחרת, תוך שניות ספורות.</span><span class="sxs-lookup"><span data-stu-id="80d87-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="80d87-118">משום שפעולות בזמן אמת מתרחשות לאחר שאיחוד הנתונים התרחש, הן חלות רק על פרופילי הלקוחות המאוחדים.</span><span class="sxs-lookup"><span data-stu-id="80d87-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="80d87-119">כתוצאה מכך, שינויים בפרופיל בזמן אמת לא יעדכנו מדדים, חברות בפלח או העשרות.</span><span class="sxs-lookup"><span data-stu-id="80d87-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="80d87-120">מגבלות</span><span class="sxs-lookup"><span data-stu-id="80d87-120">Limitations</span></span>

- <span data-ttu-id="80d87-121">ניתן לעדכן פרופילי לקוחות, אך לא ליצור או למחוק אותם.</span><span class="sxs-lookup"><span data-stu-id="80d87-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="80d87-122">ייצוא עדכונים בזמן אמת למערכות חיצוניות, כגון Power BI, אינו אפשרי כרגע.</span><span class="sxs-lookup"><span data-stu-id="80d87-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="80d87-123">יצירת פעילויות בזמן אמת</span><span class="sxs-lookup"><span data-stu-id="80d87-123">Real-time creation of activities</span></span>

<span data-ttu-id="80d87-124">ממשק ה- API בזמן אמת מאפשר לך לפרסם פעילות חדשה ממערכת המקור שלך (רשומת מקור בודדת) לפרופיל לקוח מאוחד.</span><span class="sxs-lookup"><span data-stu-id="80d87-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="80d87-125">הפעילות החדשה תהיה זמינה כפעילות מאוחדת בציר הזמן של פרופיל הלקוח המאוחד תוך שניות.</span><span class="sxs-lookup"><span data-stu-id="80d87-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="80d87-126">באפשרותך לראות את ציר הזמן בתצוגת כרטיס הלקוח או כל שילוב אחר של ציר הזמן שהגדרת.</span><span class="sxs-lookup"><span data-stu-id="80d87-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="80d87-127">הפעילויות אינן ניתנות לשינוי.</span><span class="sxs-lookup"><span data-stu-id="80d87-127">Activities are immutable.</span></span> <span data-ttu-id="80d87-128">הן לא משתנות לאחר שנוצרו.</span><span class="sxs-lookup"><span data-stu-id="80d87-128">They don't change once created.</span></span>
> - <span data-ttu-id="80d87-129">לעת עתה, פלחי שוק ומדדים לא יתעדכנו על סמך הפעילות החדשה.</span><span class="sxs-lookup"><span data-stu-id="80d87-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="80d87-130">פעילויות שנוספו רק דרך ממשק ה- API בזמן אמת אינן חלק מפעולות הייצוא ולא יופיעו ב- PowerBI.</span><span class="sxs-lookup"><span data-stu-id="80d87-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="80d87-131">ישנן שתי דרכים להתחבר לממשק ה- API בזמן אמת:</span><span class="sxs-lookup"><span data-stu-id="80d87-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="80d87-132">[באופן עקיף](#connect-via-the-dynamics-365-customer-insights-connector), באמצעות מחבר [Dynamics 365 Customer Insights](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="80d87-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="80d87-133">[באופן ישיר](#connect-directly-to-the-real-time-api), עם קוד</span><span class="sxs-lookup"><span data-stu-id="80d87-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="80d87-134">שתי הדרכים חולקות את התנאים המוקדמים הבאים:</span><span class="sxs-lookup"><span data-stu-id="80d87-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="80d87-135">סביבת Customer Insights</span><span class="sxs-lookup"><span data-stu-id="80d87-135">A Customer Insights environment</span></span>
- <span data-ttu-id="80d87-136">פרופילי לקוחות מאוחדים</span><span class="sxs-lookup"><span data-stu-id="80d87-136">Unified customer profiles</span></span>
- <span data-ttu-id="80d87-137">פעילויות מוגדרות ומופעלות</span><span class="sxs-lookup"><span data-stu-id="80d87-137">Activities configured and run</span></span>
- <span data-ttu-id="80d87-138">הרשאות משתתף או מנהל מערכת לאימות החשבון שלך</span><span class="sxs-lookup"><span data-stu-id="80d87-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="80d87-139">התחברות דרך מחבר Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="80d87-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="80d87-140">ה- API בזמן אמת יכול לקלוט נתונים מחבר Power Platform ייעודי, מחבר [Dynamics 365 Customer Insights](/connectors/customerinsights/), מבלי לכתוב ולפרוס קוד כלשהו.</span><span class="sxs-lookup"><span data-stu-id="80d87-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="80d87-141">המחבר יכול לבצע את אותן פעולות בזמן אמת כמו ה- API.</span><span class="sxs-lookup"><span data-stu-id="80d87-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="80d87-142">אתה זקוק לרישיון תקף עבור מחברים מתקדמים.</span><span class="sxs-lookup"><span data-stu-id="80d87-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="80d87-143">לקבלת מידע נוסף, ראה [שאלות נפוצות בנוגע לרישוי Power Apps ו- Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="80d87-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="80d87-144">Power Platform [Power Apps ו/או Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="80d87-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="80d87-145">[יישומים לוגיים של Azure](/azure/connectors/apis-list)</span><span class="sxs-lookup"><span data-stu-id="80d87-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="80d87-146">לקבלת פרטים אודות יצירת זרימות, עיין ב[תיעוד Power Automate](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="80d87-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="80d87-147">התחברות ישירות לממשק ה- API בזמן אמת</span><span class="sxs-lookup"><span data-stu-id="80d87-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="80d87-148">באפשרותך להשתמש ביכולות בזמן אמת על-ידי בניית ערוץ משלך וחיבור ישיר לממשק ה- API בזמן אמת.</span><span class="sxs-lookup"><span data-stu-id="80d87-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="80d87-149">באפשרותך לפרסם פעילות בתבנית של מערכת המקור שלך או בתבנית UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="80d87-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="80d87-150">קבל את התבנית על-ידי ביצוע קריאת API ל- /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="80d87-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="80d87-151">ניתן למצוא פרטים על ממשק API זה, כולל פרמטרים ותגובות, במקטע **EntityData** ב[הפניה לממשקי API של Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="80d87-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="80d87-152">לקבלת מידע נוסף, עיין בנושא [עבודה עם ממשקי API של Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="80d87-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="80d87-153">הבן את השימוש שלך בזמן אמת באמצעות טלמטריה</span><span class="sxs-lookup"><span data-stu-id="80d87-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="80d87-154">קבל סקירה של היקף הבקשות לממשק ה- API בזמן אמת ומידע על בעיות שהמערכת עלולה להיתקל בהן.</span><span class="sxs-lookup"><span data-stu-id="80d87-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="80d87-155">באפשרותך [לגשת למדידת השימוש בזמן אמת](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="80d87-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]