---
title: מחבר Power Apps
description: התחבר ל- Power Apps ו- Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3fa91553fd50a22ab62b5a2b1e3f13b9483776a8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598156"
---
# <a name="microsoft-power-apps-connector-preview"></a><span data-ttu-id="54d06-103">מחבר Microsoft Power Apps (תצוגה מקדימה)</span><span class="sxs-lookup"><span data-stu-id="54d06-103">Microsoft Power Apps connector (preview)</span></span>

<span data-ttu-id="54d06-104">שלב פרופילי לקוחות מאוחדים ביישומים המותאמים אישית שלך עם Power Apps.</span><span class="sxs-lookup"><span data-stu-id="54d06-104">Bring unified customer profiles into your personalized apps with Power Apps.</span></span>

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a><span data-ttu-id="54d06-105">התחבר ל- Power Apps ו- Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="54d06-105">Connect Power Apps and Dynamics 365 Customer Insights</span></span>

<span data-ttu-id="54d06-106">Customer Insights הוא אחד מהמקורות הזמינים [הרבים עבור נתונים ב- Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span><span class="sxs-lookup"><span data-stu-id="54d06-106">Customer Insights is one of the many [available sources for data in Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).</span></span>

<span data-ttu-id="54d06-107">עיין בתיעוד Power Apps כדי לקבל מידע נוסף אודות [הוספת חיבור נתונים ליישום](/powerapps/maker/canvas-apps/add-data-connection).</span><span class="sxs-lookup"><span data-stu-id="54d06-107">Refer to the Power Apps documentation to learn how to [add a data connection to an app](/powerapps/maker/canvas-apps/add-data-connection).</span></span> <span data-ttu-id="54d06-108">אנו ממליצים שתבדוק גם [איך Power Apps משתמש בהקצאה כדי לטפל בערכות נתונים גדולות ביישומי בד ציור](/powerapps/maker/canvas-apps/delegation-overview).</span><span class="sxs-lookup"><span data-stu-id="54d06-108">We recommend you also review [how Power Apps uses delegation to handle large datasets in Canvas apps](/powerapps/maker/canvas-apps/delegation-overview).</span></span>

## <a name="available-entities"></a><span data-ttu-id="54d06-109">ישויות זמינות</span><span class="sxs-lookup"><span data-stu-id="54d06-109">Available entities</span></span>

<span data-ttu-id="54d06-110">לאחר הוספת Customer Insights כחיבור נתונים, באפשרותך לבחור את הישויות הבאות ב- Power Apps:</span><span class="sxs-lookup"><span data-stu-id="54d06-110">After adding Customer Insights as a data connection, you can choose the following entities in Power Apps:</span></span>

- <span data-ttu-id="54d06-111">לקוח: כדי להשתמש בנתונים מ[פרופיל הלקוח המאוחד](customer-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="54d06-111">Customer: to use data from the [unified customer profile](customer-profiles.md).</span></span>
- <span data-ttu-id="54d06-112">UnifiedActivity: כדי להציג את [ציר הזמן של הפעילות](activities.md) ביישום.</span><span class="sxs-lookup"><span data-stu-id="54d06-112">UnifiedActivity: to display the [activity timeline](activities.md) on the app.</span></span>

## <a name="limitations"></a><span data-ttu-id="54d06-113">מגבלות</span><span class="sxs-lookup"><span data-stu-id="54d06-113">Limitations</span></span>

### <a name="retrievable-entities"></a><span data-ttu-id="54d06-114">ישויות הניתנות להחזרה</span><span class="sxs-lookup"><span data-stu-id="54d06-114">Retrievable entities</span></span>

<span data-ttu-id="54d06-115">אתה יכול לאחזר רק את הישויות **צרכן**, **UnifiedActivity** ו **פלחים** דרך מחבר Power Apps.</span><span class="sxs-lookup"><span data-stu-id="54d06-115">You can only retrieve the **Customer**, **UnifiedActivity**, and **Segments** entities through the Power Apps connector.</span></span> <span data-ttu-id="54d06-116">ישויות אחרות מוצגות מכיוון שהמחבר הבסיסי תומך בהן באמצעות טריגרים ב-Power Automate.</span><span class="sxs-lookup"><span data-stu-id="54d06-116">Other entities are shown because the underlying connector supports them through triggers in Power Automate.</span></span>  

### <a name="delegation"></a><span data-ttu-id="54d06-117">הקצאה</span><span class="sxs-lookup"><span data-stu-id="54d06-117">Delegation</span></span>

<span data-ttu-id="54d06-118">הקצאה עובדת עבור ישות הלקוח והישות UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="54d06-118">Delegation works for the Customer entity and UnifiedActivity entity.</span></span> 

- <span data-ttu-id="54d06-119">הקצאה עבור הישות **לקוח**: כדי להשתמש בהקצאה עבור ישות זו, יש לסדר את השדות באינדקס ב[אינדקס חיפוש וסינון](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="54d06-119">Delegation for **Customer** entity: To use delegation for this entity, the fields need to be indexed in [Search & filter index](search-filter-index.md).</span></span>  

- <span data-ttu-id="54d06-120">הקצאה ל- **UnifiedActivity**: הקצאה לישות זו פועלת רק עבור השדות **ActivityId** ו- **מספר לקוח**.</span><span class="sxs-lookup"><span data-stu-id="54d06-120">Delegation for **UnifiedActivity**: Delegation for this entity only works for the fields **ActivityId** and **CustomerId**.</span></span>  

- <span data-ttu-id="54d06-121">לקבלת מידע נוסף על הקצאה, ראה [פונקציות ופעולות של Power Apps שניתנות להקצאה](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span><span class="sxs-lookup"><span data-stu-id="54d06-121">For more information about delegation, see [Power Apps delegable functions and operations](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps).</span></span> 

## <a name="example-gallery-control"></a><span data-ttu-id="54d06-122">פקד גלריה לדוגמה</span><span class="sxs-lookup"><span data-stu-id="54d06-122">Example gallery control</span></span>

<span data-ttu-id="54d06-123">לדוגמה, עליך להוסיף פרופילי לקוחות אל [פקד גלריה](/powerapps/maker/canvas-apps/add-gallery).</span><span class="sxs-lookup"><span data-stu-id="54d06-123">For example, you add customer profiles to a [gallery control](/powerapps/maker/canvas-apps/add-gallery).</span></span>

1. <span data-ttu-id="54d06-124">הוסף פקד **גלריה** ליישום שאתה בונה.</span><span class="sxs-lookup"><span data-stu-id="54d06-124">Add a **Gallery** control to an app you're building.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="54d06-125">![הוסף רכיב גלריה](media/connector-powerapps9.png "הוסף רכיב גלריה")</span><span class="sxs-lookup"><span data-stu-id="54d06-125">![Add a gallery element](media/connector-powerapps9.png "Add a gallery element")</span></span>

1. <span data-ttu-id="54d06-126">בחר **לקוח** בתור מקור הנתונים לפריטים.</span><span class="sxs-lookup"><span data-stu-id="54d06-126">Select **Customer** as the data source for items.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="54d06-127">![בחר מקור נתונים](media/choose-datasource-powerapps.png "בחר מקור נתונים")</span><span class="sxs-lookup"><span data-stu-id="54d06-127">![Select a data source](media/choose-datasource-powerapps.png "Select a data source")</span></span>

1. <span data-ttu-id="54d06-128">אתה יכול לשנות את לוח הנתונים בצד ימין כדי לבחור איזה שדה להציג עבור יישות הלקוח בגלריה.</span><span class="sxs-lookup"><span data-stu-id="54d06-128">You can change the data panel on the right to select which field for the Customer entity to show on the gallery.</span></span>

1. <span data-ttu-id="54d06-129">אם ברצונך להציג בגלריה שדה כלשהו מהלקוח שנבחר, הזן את מאפיין הטקסט של תווית: **{Name_of_the_gallery}.Selected.{property_name}**</span><span class="sxs-lookup"><span data-stu-id="54d06-129">If you want to show any field from the selected customer on the gallery, fill in the Text property of a label:  **{Name_of_the_gallery}.Selected.{property_name}**</span></span>

    <span data-ttu-id="54d06-130">דוגמה: Gallery1.Selected.address1_city</span><span class="sxs-lookup"><span data-stu-id="54d06-130">Example: Gallery1.Selected.address1_city</span></span>

1. <span data-ttu-id="54d06-131">כדי להציג את ציר הזמן המאוחד עבור לקוח, הוסף רכיב גלריה והוסף את מאפיין הפריטים: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span><span class="sxs-lookup"><span data-stu-id="54d06-131">To display the unified timeline for a customer, add a Gallery element, and add the Items property: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**</span></span>

    <span data-ttu-id="54d06-132">דוגמה: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span><span class="sxs-lookup"><span data-stu-id="54d06-132">Example: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]