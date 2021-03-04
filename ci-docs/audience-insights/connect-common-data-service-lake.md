---
title: התחבר לישויות באגם המנוהל של Common Data Service
description: ייבא נתונים מאגם נתונים מנוהל של Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.reviewer: adkuppa
ms.openlocfilehash: 18b6cd3fdaf5b738877a73b520b91dbc6ded40de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267815"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>התחבר לנתונים בתוך אגם נתונים מנוהל של Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

מאמר זה מספק מידע על האופן שבו לקוחות קיימים של Dynamics 365 יכולים להתחבר במהירות ליישויות האנליטיות שלהם באגם מנוהל של Common Data Service. אתה חייב להיות מנהל מערכת בארגון Common Data Service כדי להמשיך ולראות את רשימת הישויות הזמינות באגם המנוהל.

## <a name="important-considerations"></a>שיקולים חשובים:

נתונים המאוחסנים בשירותים מקוונים כגון Azure Data Lake Storage עשויים להיות מאוחסנים במקום אחר שאינו מקום העיבוד או האחסון של הנתונים ב- Dynamics 365 Customer Insights. על-ידי ייבוא נתונים או חיבור לנתונים שמאוחסנים בשירותים מקוונים, אתה מסכים שנתונים יועברו אל Dynamics 365 Customer Insights ויאוחסנו בו.  [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>התחבר אל אגם נתונים מנוהל של Common Data Service

1. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.

2. בחר **הוסף מקור נתונים**.

3. בחר **התחבר אל Common Data Service** ובחר **הבא**.

4. הזן **שם** עבור מקור הנתונים ובחר **הבא**. קווים מנחים של שם: 
   - התחל עם אות.
   - השתמש באותיות ומספרים בלבד. אסור להזין תווים מיוחדים ורווחים.
   - השתמש בין 3 ל- 64 תווים.

5. ספק **כתובת שרת** של ארגון Common Data Service שלך ובחר **התחבר**.

   > [!div class="mx-imgBorder"]
   > ![תיבת דו-שיח להזנת כתובת שרת Common Data Service](media/enter-CDS-org-details.png)

6. בחר את הישויות שברצונך לקלוט מהרשימה הזמינה.    

   > [!NOTE]
   > אם ישויות מסוימות כבר נבחרו, הן עשויות לשמש ביישומי Dynamics 365 אחרים (כגון Dynamics 365 Sales Insights או Customer Service Insights). אין באפשרותך לשנות את הבחירה. ישויות אלה יהיו זמינות לאחר יצירת מקור נתונים.

   > [!div class="mx-imgBorder"]
   > ![תיבת דו-שיח המציגה רשימת ישויות בארגון Common Data Service](media/select-analytical-entities.png)

7. שמור את הבחירה שלך כדי להתחיל לסנכרן את הישויות שנבחרו עם אגם מנוהל של Common Data Service. תמצא את החיבור החדש שנוסף בדף **מקורות מידע**. הוא יופיע בתור לרענון ויראה שהישויות נספרות כ- 0 עד לסנכרון של כל הישויות.

רק מקור נתונים אחד של סביבה יכול להשתמש בו-זמנית באותו אגם מנוהל של Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>ערוך מקור נתונים של אגם מנוהל של Common Data Service

אתה עורך רק את בחירת הישויות לאחר יצירת מקור נתונים. לדוגמא, אם נוספו ישויות נוספות ל- Common Data Service ואתה רוצה לייבא גם אותם.    
כדי להתחבר ל- Common Data Service אחר, [צור מקור נתונים חדש](#connect-to-a-common-data-service-managed-lake).

1. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.

2. לצד מקור הנתונים שברצונך לעדכן, בחר את שלוש הנקודות.

3. בחר באפשרות **ערוך** מתוך הרשימה.

4. בחר ישויות נוספות מרשימת הישויות הזמינה ובחר **שמור**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]