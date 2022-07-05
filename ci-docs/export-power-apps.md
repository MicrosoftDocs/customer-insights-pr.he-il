---
title: מחבר Power Apps (תצוגה מקדימה)
description: התחבר ל- Power Apps ו- Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 0b71f723d1e491d422d24b1be6616d2f33c95d40
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9055261"
---
# <a name="power-apps-connector-preview"></a>מחבר Power Apps (תצוגה מקדימה)

שלב פרופילי לקוחות מאוחדים ביישומים המותאמים אישית שלך עם Microsoft Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>התחבר ל- Power Apps ו- Dynamics 365 Customer Insights

Customer Insights הוא אחד מהמקורות הזמינים [הרבים עבור נתונים ב- Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

עיין בתיעוד Power Apps כדי לקבל מידע נוסף אודות [הוספת חיבור נתונים ליישום](/powerapps/maker/canvas-apps/add-data-connection). אנו ממליצים שתבדוק גם [איך Power Apps משתמש בהקצאה כדי לטפל בערכות נתונים גדולות ביישומי בד ציור](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>ישויות זמינות

לאחר הוספת Customer Insights כחיבור נתונים, באפשרותך לבחור את הישויות הבאות ב- Power Apps:

- **לקוח**: כדי להשתמש בנתונים מ[פרופיל הלקוח המאוחד](customer-profiles.md).
- **UnifiedActivity**: כדי להציג את [ציר הזמן של פעילות](activities.md) ביישום.
- **ContactProfile**: כדי להציג את אנשי הקשר של לקוח. ישות זו זמינה רק בסביבות Customer Insights עבור תיקי לקוחות עסקיים.

## <a name="limitations"></a>מגבלות

### <a name="retrievable-entities"></a>ישויות הניתנות להחזרה

באפשרותך לאחזר את הישויות **לקוח**, **UnifiedActivity**, **פלחים** ו- **ContactProfile** באמצעות מחבר Power Apps בלבד. הישות ContactProfile זמינה רק במופע Customer Insights עבור תיקי לקוחות עסקיים. ישויות אחרות מוצגות מכיוון שהמחבר הבסיסי תומך בהן באמצעות טריגרים ב-Power Automate.

אתה יכול לבצע מקסימום 100 שיחות ל-60 שניות. אתה יכול לקרוא לנקודת הקצה של ה- API מספר פעמים על ידי שימוש בפרמטר ‏‏‎skip$. [קבל מידע נוסף על הפרמטר skip‎‏$](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>הקצאה

הקצאה פועלת עבור הישות **לקוח** והישות **UnifiedActivity**. 

- הקצאה עבור הישות **לקוח**: כדי להשתמש בהקצאה עבור ישות זו, יש לסדר את השדות באינדקס ב[אינדקס חיפוש וסינון](search-filter-index.md).  
- הקצאה ל- **UnifiedActivity**: הקצאה לישות זו פועלת רק עבור השדות **ActivityId** ו- **מספר לקוח**.  
- משלחת עבור **ContactProfile**: הקצאה עבור ישות זו פועלת עבור **ContactId** ו- **CustomerId** בלבד. הישות ContactProfile זמינה רק בסביבות של Customer Insights עבור תיקי לקוחות עסקיים.

למידע נוסף אודות הקצאה, עבור אל [פונקציות ופעולות ניתנות להקצאה של Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>פקד גלריה לדוגמה

תוכל להוסיף פרופילי לקוחות ל[פקד גלריה](/powerapps/maker/canvas-apps/add-gallery).

1. הוסף פקד **גלריה** ליישום שאתה בונה.

    > [!div class="mx-imgBorder"]
    > ![הוסף רכיב גלריה.](media/connector-powerapps9.png "הוסף רכיב גלריה.")

2. בחר **לקוח** בתור מקור הנתונים לפריטים.

    > [!div class="mx-imgBorder"]
    > ![בחר מקור נתונים.](media/choose-datasource-powerapps.png "בחר מקור נתונים.")

3. אתה יכול לשנות את לוח הנתונים בצד ימין כדי לבחור איזה שדה להציג עבור יישות הלקוח בגלריה.

4. אם ברצונך להציג בגלריה שדה כלשהו מהלקוח שנבחר, הזן את מאפיין ה **טקסט** של תווית באמצעות **{Name_of_the_gallery}.Selected.{property_name}**  
    - לדוגמה: _Gallery1.Selected.address1_city_

5. כדי להציג את ציר הזמן המאוחד עבור לקוח, הוסף רכיב גלריה והוסף את המאפיין **פריטים** באמצעות **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - לדוגמה: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
