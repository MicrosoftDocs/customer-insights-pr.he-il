---
title: התחבר לטבלאות ב- Microsoft Dataverse
description: ייבא נתונים מאגם נתונים מנוהל של Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011704"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>התחבר לנתונים בתוך אגם נתונים מנוהל של Microsoft Dataverse

משתמשי Microsoft Dataverse יכולים להתחבר במהירות לישויות אנליטיות באגם מנוהל על ידי Microsoft Dataverse.

> [!NOTE]
> עליך להיות מנהל מערכת בארגון Dataverse כדי להמשיך ולהציג את רשימת הישויות הזמינות באגם המנוהל.

## <a name="important-considerations"></a>שיקולים חשובים:

1. נתונים המאוחסנים בשירותים מקוונים כגון Azure Data Lake Storage עשויים להיות מאוחסנים במקום אחר שאינו מקום העיבוד או האחסון של הנתונים ב- Dynamics 365 Customer Insights. על-ידי ייבוא או התחברות לנתונים המאוחסנים בשירותים מקוונים, אתה מסכים להעברה ולאחסון של נתונים אלה ב- Dynamics 365 Customer Insights. [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center).
2. רק ישויות של Dataverse [שבהן התכונה 'מעקב אחר שינויים' זמינה](/power-platform/admin/enable-change-tracking-control-data-synchronization) יהיו גלויים. ניתן לייצא ישויות אלה אל Data Lake שמנוהל על-ידי Dataverse ולעשות בהן שימוש ב- Customer Insights. בטבלאות Dataverse שמגיעות מוכנות לשימוש, התכונה 'מעקב אחר שינויים' זמינה כברירת מחדל. עליך להפעיל את מעקב אחר שינויים עבור טבלאות מותאמות אישית. כדי לבדוק אם מעקב אחר שינויים זמין בטבלת Dataverse, עבור אל [Power Apps](https://make.powerapps.com)  > **נתונים** > **טבלאות**. מצא את הטבלה שמעניינת אותך ובחר בה. עבור אל **הגדרות** > **אפשרויות מתקדמות** ובדוק את ההגדרה **מעקב אחר שינויים**.

## <a name="connect-to-a-dataverse-managed-lake"></a>התחבר אל אגם נתונים מנוהל של Dataverse

1. עבור אל **נתונים** > **מקורות נתונים**.

1. בחר **הוסף מקור נתונים**.

1. בחר **Microsoft Dataverse**.

1. הזן **שם** עבור מקור הנתונים ו **תיאור** אופציונלי.

1. ספק את **כתובתה שרת** עבור ארגון Dataverse, ובחר **התחברות**.

1. בחר את הטבלאות שברצונך להטמיע כישויות לתוך Customer Insights מהרשימה הזמינה.

   > [!NOTE]
   > אם טבלאות מסוימות כבר נבחרו, הן יכולות לשמש ביישומי Dynamics 365 אחרים (כגון Dynamics 365 Sales Insights או Customer Service Insights). אין באפשרותך לשנות את הבחירה. טבלאות אלה יהיו זמינות כישויות לאחר יצירת מקור הנתונים.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="תיבת דו-שיח המציגה רשימה של ישויות בסביבת Dataverse.":::

1. שמור את הבחירה שלך כדי להתחיל לסנכרן את הטבלאות שנבחרו מ- Dataverse. תמצא את החיבור החדש שנוסף בדף **מקורות מידע**. הוא יעמוד בתור לרענון ויציג את ספירת הישות כ- 0 עד שכל הטבלאות שנבחרו יסונכרנו.

רק מקור נתונים אחד של סביבה יכול להשתמש בו-זמנית באותו אגם מנוהל של Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>ערוך מקור נתונים של אגם מנוהל של Dataverse

אתה עורך רק את בחירת הישויות לאחר יצירת מקור נתונים. לדוגמא, אם נוספו ישויות נוספות ל- Dataverse ואתה רוצה לייבא גם אותם.
כדי להתחבר לאגם Dataverse אחר, [צור מקור נתונים חדש](#connect-to-a-dataverse-managed-lake).

1. עבור אל **נתונים** > **מקורות נתונים**.

1. לצד מקור הנתונים שברצונך לעדכן, בחר את **עריכה**.

1. בחר ישויות נוספות מרשימת הישויות הזמינה ובחר **שמור**.
