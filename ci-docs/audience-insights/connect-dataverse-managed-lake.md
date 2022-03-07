---
title: התחבר לטבלאות ב- Microsoft Dataverse
description: ייבא נתונים מאגם נתונים מנוהל של Microsoft Dataverse.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 8e11b60295fa5c187b1ac4877fb347e2d9bb41a1
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354142"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>התחבר לנתונים בתוך אגם נתונים מנוהל של Microsoft Dataverse



מאמר זה מספק מידע כיצד יכולים משתמשי Dataverse להתחבר במהירות לישויות אנליטיות באגם מנוהל של Microsoft Dataverse. 

> [!NOTE]
> עליך להיות מנהל מערכת בארגון Dataverse כדי להמשיך ולהציג את רשימת הישויות הזמינות באגם המנוהל.

## <a name="important-considerations"></a>שיקולים חשובים:

נתונים המאוחסנים בשירותים מקוונים כגון Azure Data Lake Storage עשויים להיות מאוחסנים במקום אחר שאינו מקום העיבוד או האחסון של הנתונים ב- Dynamics 365 Customer Insights. על-ידי ייבוא או התחברות לנתונים המאוחסנים בשירותים מקוונים, אתה מסכים להעברה ולאחסון של נתונים אלה ב- Dynamics 365 Customer Insights. [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-dataverse-managed-lake"></a>התחבר אל אגם נתונים מנוהל של Dataverse

1. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.

2. בחר **הוסף מקור נתונים**.

3. בחר **Microsoft Dataverse** ובחר **הבא**.

4. הזן **שם** עבור מקור הנתונים ובחר **הבא**. 

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
