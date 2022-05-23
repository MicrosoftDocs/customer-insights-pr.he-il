---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755545"
---
לאחר הטמעת הנתונים, התחל בתהליך איחוד הנתונים כדי ליצור פרופיל לקוח מאוחד. לקבלת מידע נוסף, ראה [איחוד נתונים](../data-unification.md).

### <a name="select-source-fields"></a>בחר שדות מקור

1. לאחר קליטת הנתונים, מפה את אנשי הקשר מנתוני eCommerce ו- Loyalty לסוגי נתונים נפוצים. עבור אל **נתונים** > **איחוד**.

1. בחר את הישויות המייצגות את פרופיל הלקוח – **eCommerceContacts** ו- **loyCustomers**.

   ![איחוד מקורות הנתונים ecommerce ו- loyalty.](../media/unify-ecommerce-loyalty.png)

1. בחר **ContactId** כמפתח העיקרי עבור **eCommerceContacts** ו- **LoyaltyID** כמפתח העיקרי עבור **loyCustomers**.

1. בחר **הבא**. דלג על רשומות כפולות ובחר **הבא**.

### <a name="match-conditions"></a>התאם תנאים

1. בחר **eCommerceContacts : eCommerce** בתור הישות הראשית וכלול את כל הרשומות.

1. בחר **LoyCustomers: LoyaltyScheme** וכלול את כל הרשומות.

1. הוסף כלל:
   - בחר **FullName** עבור eCommerceContacts ועבור loyCustomers.
   - בחר **סוג (טלפון, שם, כתובת,...)** לצורך **נרמול**.
   - הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.
   - הזן **FullName, Email** עבור השם.

1. הוסף תנאי שני עבור כתובת הדואר:
   - בחר **דואר** עבור eCommerceContacts ועבור loyCustomers.
   - השאר את השדה 'נרמל' ריק.
   - הגדר **רמת דיוק**: **בסיסית** ו **ערך**: **גבוה**.

   ![איחוד כלל התאמה עבור שם ודואר אלקטרוני.](../media/unify-match-rule.png)

1. בחר **סיום**.

1. בחר **הבא**.

### <a name="unify-fields"></a>אחד שדות

1. שנה את שם הישות **ContactId** עבור **loyCustomers** שיהיה **ContactIdLOYALTY** כדי להבדיל אותו משאר המזהים שעובדו.

1. בחר **הבא** כדי לסקור ולאחר מכן בחר **צור פרופילי לקוחות**.
