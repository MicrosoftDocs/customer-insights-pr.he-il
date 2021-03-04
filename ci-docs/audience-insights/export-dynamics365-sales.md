---
title: ייצוא נתוני Customer Insights אל Dynamics 365 Sales
description: למדו כיצד להגדיר את החיבור אל Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269009"
---
# <a name="connector-for-dynamics-365-sales-preview"></a>מחבר עבור Dynamics 365 Sales (תצוגה מקדימה)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

השתמש בנתוני הלקוחות שלך כדי ליצור רשימות שיווק, להמשיך לטפל בזרימות עבודה ולשלוח מבצעים באמצעות Dynamics 365 Sales.

## <a name="prerequisite"></a>דרישה מוקדמת

1. רשומות אנשי קשר מוכרחות להיות קיימות ב- Dynamics 365 Sales לפני שתוכל לייצא פלח מ- Customer Insights אל Sales. המשך לקרוא על אופן הקליטה של אנשי קשר ב- [Dynamics 365 Sales באמצעות Common Data Services](connect-power-query.md).

   > [!NOTE]
   > ייצוא פלחים מ- audience insights אל Sales לא ייצור רשומות אנשי קשר חדשות במופעי Sales. יש לקלוט את רשומות אנשי הקשר מ- Sales ב- audience insights ולהשתמש בהן כמקור נתונים. יש גם לכלול אותן בישות 'לקוח' המאוחדת כדי למפות מזהי לקוחות למזהי אנשי קשר לפני ייצוא הפלחים.

## <a name="configure-the-connector-for-sales"></a>קביעת תצורת המחבר עבור Sales

1. ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.

1. תחת **Dynamics 365 Sales**, בחר **הגדר**.

1. תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

1. הזן את כתובת ה- URL של Sales של הארגון שלך בשדה **כתובת שרת**.

1. במקטע **חשבון מנהל שרת**, בחר **היכנס** ובחר חשבון Dynamics 365 Sales.

1. מפה שדה של מזהה לקוח למזהה איש הקשר של Dynamics 365.

1. בחר **הבא**.

1. בחר קטע אחד או יותר.

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]