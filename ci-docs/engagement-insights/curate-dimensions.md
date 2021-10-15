---
title: השתמש בממדים דמוגרפיים לפיצול נתונים התנהגותיים (ממדים מאוחדים)
description: השתמש בממדים מאוחדים בפרופיל כדי לאפשר תכונות תובנות קהל של פרופיל לקוחות.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8a3d7f9276330a6daacbe9428d84a371b81bbefe
ms.sourcegitcommit: 971716c761871cee390519cacef617dac21ecd60
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/01/2021
ms.locfileid: "7466349"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>השתמש בממדים דמוגרפיים לפיצול נתונים התנהגותיים

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

על ידי שימוש בממדים דמוגרפיים בעלי פרופיל אחיד, משתמשים בתובנות מעורבות יכולים לגשת אל מאפייני פרופיל של תובנות קהל. לאחר מכן תוכל להשתמש במאפיינים אלה בניתוחים אינטראקטיביים של נתוני התנהגות, כולל נתונים שנלכדו על ידי תובנות מעורבות באתר שלך או באפליקציה לנייד.

>[!NOTE]
> תובנות לגבי מעורבות כוללות ממדים מוכנים לשימוש עבור מאפייני אירועים. מידע נוסף: [יצירה והצגה של ממדים](dimensions.md)

## <a name="prerequisite"></a>דרישה מוקדמת

- סביבת תובנות מעורבות שבה יש לך נתוני פרופילי לקוחות המקושרים לסביבת תובנות קהל שבה נוצרים פרופילי הלקוחות. מידע נוסף: [צור קישור בין תובנות קהל לבין תובנות מעורבות](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> לאחר שתיצור קישור בין וסביבות תובנות הקהל ותובנות מעורבות, ייתכן שתרצה רק נתונים ספציפיים למאפיינים של פרופילי לקוחות, שיכולים להיות שימושיים כממדים בתובנות מעורבות. למידע נוסף, עבור אל [אפשר תכונות ופלחים של פרופילים מאוחדים לתבונות קהל](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).

## <a name="create-a-new-custom-report"></a>צור דוח מותאם אישית חדש

1. בחלונית השמאלית, בחר **התאמה אישית** > **דוח חדש** ולאחר מכן בחר את המדד הרצוי. (לדוגמא זו בחרנו **צפיות בדף לפי שעה**).

    :::image type="content" source="media/curated-dimensions1.png" alt-text="בחר מדד.":::

2. בעורך ההדמיה, בחר **ממדים** ולאחר מכן בחר **דמוגרפי** בתוך **סוג ממד** תפריט נפתח.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="בחר דמוגרפיה.":::

3. בחר **Signal.Customer.*xxx*** מימד. (דוגמה זו מציגה את Signal.Customer.Country).

    :::image type="content" source="media/curated-dimensions3.png" alt-text="בחר ממד.":::
  
## <a name="limitations"></a>מגבלות

כרגע אתה יכול להשתמש בממדים דמוגרפיים לפיצול נתונים התנהגותיים.


[!INCLUDE[footer-include](../includes/footer-banner.md)]