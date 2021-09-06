---
title: התחבר לטבלאות ב- Microsoft Dataverse
description: ייבא נתונים מאגם נתונים מנוהל של Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: ffeccffd0e353cb5490b537552d585c184ad672f9c806e673bd04743214ad068
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033081"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>התחבר לנתונים בתוך אגם נתונים מנוהל של Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

מאמר זה מלמד כיצד משתמשי Dataverse יכולים להתחבר במהירות לישויות האנליטיות שלהם באגם בניהול Dataverse. אתה חייב להיות מנהל מערכת בארגון Dataverse כדי להמשיך ולראות את רשימת הישויות הזמינות באגם המנוהל.

## <a name="important-considerations"></a>שיקולים חשובים:

נתונים המאוחסנים בשירותים מקוונים כגון Azure Data Lake Storage עשויים להיות מאוחסנים במקום אחר שאינו מקום העיבוד או האחסון של הנתונים ב- Dynamics 365 Customer Insights. על-ידי ייבוא נתונים או חיבור לנתונים שמאוחסנים בשירותים מקוונים, אתה מסכים שנתונים יועברו אל Dynamics 365 Customer Insights ויאוחסנו בו.  [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>התחבר אל אגם נתונים מנוהל של Dataverse

1. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.

2. בחר **הוסף מקור נתונים**.

3. בחר **התחבר אל אגם בניהול Microsoft Dataverse** ובחר **הבא**.

4. הזן **שם** עבור מקור הנתונים ובחר **הבא**. קווים מנחים של שם: 
   - התחל עם אות.
   - השתמש באותיות ומספרים בלבד. אסור להזין תווים מיוחדים ורווחים.
   - השתמש בין 3 ל- 64 תווים.

5. ספק את **כתובתה שרת** עבור ארגון Dataverse, ובחר **התחברות**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="מסך בשלב קליטת נתונים שבו משתמש יכול להזין את כתובת ה- URL של סביבת Dataverse.":::

6. בחר את הטבלאות שברצונך לקלוט כישויות לתובנות לגבי קהלים מהרשימה הזמינה.    

   > [!NOTE]
   > אם טבלאות מסוימות כבר נבחרו, הן יכולות לשמש ביישומי Dynamics 365 אחרים (כגון Dynamics 365 Sales Insights או Customer Service Insights). אין באפשרותך לשנות את הבחירה. טבלאות אלה יהיו זמינות כישויות לאחר יצירת מקור הנתונים.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="תיבת דו-שיח המציגה רשימה של ישויות בסביבת Dataverse.":::

7. שמור את הבחירה שלך כדי להתחיל לסנכרן את הטבלאות שנבחרו מ- Dataverse. תמצא את החיבור החדש שנוסף בדף **מקורות מידע**. הוא יעמוד בתור לרענון ויציג את ספירת הישות כ- 0 עד שכל הטבלאות שנבחרו יסונכרנו.

רק מקור נתונים אחד של סביבה יכול להשתמש בו-זמנית באותו אגם מנוהל של Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>ערוך מקור נתונים של אגם מנוהל של Dataverse

אתה עורך רק את בחירת הישויות לאחר יצירת מקור נתונים. לדוגמא, אם נוספו ישויות נוספות ל- Dataverse ואתה רוצה לייבא גם אותם.    
כדי להתחבר לאגם Dataverse אחר, [צור מקור נתונים חדש](#connect-to-a-dataverse-managed-lake).

1. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.

2. לצד מקור הנתונים שברצונך לעדכן, בחר את שלוש הנקודות.

3. בחר באפשרות **ערוך** מתוך הרשימה.

4. בחר ישויות נוספות מרשימת הישויות הזמינה ובחר **שמור**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]