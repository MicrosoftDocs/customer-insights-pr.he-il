---
title: מחבר Power Apps
description: התחבר ל- Power Apps ו- Power Automate.
ms.date: 01/19/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a8bbb9a09218d54228589d43c21c8894680b56e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268917"
---
# <a name="microsoft-power-apps-connector-preview"></a>מחבר Microsoft Power Apps (תצוגה מקדימה)

שלב פרופילי לקוחות מאוחדים ביישומים המותאמים אישית שלך עם Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>התחבר ל- Power Apps ו- Dynamics 365 Customer Insights

Customer Insights הוא אחד מהמקורות הזמינים [הרבים עבור נתונים ב- Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/working-with-data-sources).

עיין בתיעוד Power Apps כדי לקבל מידע נוסף אודות [הוספת חיבור נתונים ליישום](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-data-connection). אנו ממליצים שתבדוק גם [איך Power Apps משתמש בהקצאה כדי לטפל בערכות נתונים גדולות ביישומי בד ציור](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>ישויות זמינות

לאחר הוספת Customer Insights כחיבור נתונים, באפשרותך לבחור את הישויות הבאות ב- Power Apps:

- לקוח: כדי להשתמש בנתונים מ[פרופיל הלקוח המאוחד](customer-profiles.md).
- UnifiedActivity: כדי להציג את [ציר הזמן של הפעילות](activities.md) ביישום.

## <a name="limitations"></a>מגבלות

### <a name="retrievable-entities"></a>ישויות הניתנות להחזרה

אתה יכול לאחזר רק את הישויות **צרכן**, **UnifiedActivity** ו **פלחים** דרך מחבר Power Apps. ישויות אחרות מוצגות מכיוון שהמחבר הבסיסי תומך בהן באמצעות טריגרים ב-Power Automate.  

### <a name="delegation"></a>הקצאה

הקצאה עובדת עבור ישות הלקוח והישות UnifiedActivity. 

- הקצאה עבור הישות **לקוח**: כדי להשתמש בהקצאה עבור ישות זו, יש לסדר את השדות באינדקס ב[אינדקס חיפוש וסינון](search-filter-index.md).  

- הקצאה ל- **UnifiedActivity**: הקצאה לישות זו פועלת רק עבור השדות **ActivityId** ו- **מספר לקוח**.  

- לקבלת מידע נוסף על הקצאה, ראה [פונקציות ופעולות של Power Apps שניתנות להקצאה](https://docs.microsoft.com/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>פקד גלריה לדוגמה

לדוגמה, עליך להוסיף פרופילי לקוחות אל [פקד גלריה](https://docs.microsoft.com/powerapps/maker/canvas-apps/add-gallery).

1. הוסף פקד **גלריה** ליישום שאתה בונה.

> [!div class="mx-imgBorder"]
> ![הוסף רכיב גלריה](media/connector-powerapps9.png "הוסף רכיב גלריה")

1. בחר **לקוח** בתור מקור הנתונים לפריטים.

    > [!div class="mx-imgBorder"]
    > ![בחר מקור נתונים](media/choose-datasource-powerapps.png "בחר מקור נתונים")

1. אתה יכול לשנות את לוח הנתונים בצד ימין כדי לבחור איזה שדה להציג עבור יישות הלקוח בגלריה.

1. אם ברצונך להציג בגלריה שדה כלשהו מהלקוח שנבחר, הזן את מאפיין הטקסט של תווית: **{Name_of_the_gallery}.Selected.{property_name}**

    דוגמה: Gallery1.Selected.address1_city

1. כדי להציג את ציר הזמן המאוחד עבור לקוח, הוסף רכיב גלריה והוסף את מאפיין הפריטים: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    דוגמה: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]