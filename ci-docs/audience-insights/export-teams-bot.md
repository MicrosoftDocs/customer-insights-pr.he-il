---
title: תוכנית Bot עבור Microsoft Teams
description: חפש פרופילי לקוחות מאוחדים ב- Microsoft Teams בעזרת תוכנית Bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 9bf401124b0ffb21b046954056141e7703386d4911f89f34ffc0fcb84bf0f4be
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032483"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>תוכנית Bot של Teams עבור Dynamics 365 Customer Insights‎‏ (preview)

התחבר עם Microsoft Teams כדי לאפשר לתוכנית Bot לחפש פרופילי לקוחות מאוחדים בערוצי Teams.

> [!div class="mx-imgBorder"]
> ![תוכנית Bot של Teams המציגה רשומת לקוח.](media/teams-bot.png "תוכנית Bot של Teams המציגה רשומת לקוח")

## <a name="prerequisites"></a>דרישות מוקדמות

כדי להגדיר ולקבוע את התצורה של תוכנית ה- Bot, הדרישות המוקדמות הבאות מוכרחות להתקיים:

- נוסף לפחות [מקור נתונים אחד](data-sources.md).
- [תהליך האיחוד](data-unification.md) הושלם.
- שדות מתווספים ל[אינדקס חיפוש וסינון ](search-filter-index.md).
- Customer Insights ו- Teams נמצאים באותו ארגון.

## <a name="configure-the-bot"></a>קביעת התצורה של תוכנית ה- Bot

1. ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.
1. באריח Microsoft Teams, בחר **הגדר**.
1. אתה מנותב מחדש אל האזור **יישומים** ב- Teams. באפשרותך גם לפתוח את Teams ולבחור **יישומים** בפינה השמאלית התחתונה או [להשיג אותו דרך AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) ישירות.
1. חפש את **Customer Insights** ובחר את היישום.
1. בחר **הוסף**.
1. לאחר הכניסה ל- Customer Insights ב- Teams, תראה הודעת קבלת פנים ותוכל להתחיל בעבודה.

## <a name="things-you-can-do-with-the-bot"></a>דברים שניתן לעשות עם תוכנית ה- Bot

תוכנית ה- Bot מספקת יכולות בדיקת מידע עבור פרופילי לקוחות מאוחדים.

- הזן **חיפוש** ולאחר מכן שם, כתובת דוא"ל או כל שדה אחר בפרופיל הלקוח המאוחד המתווסף לאינדקס החיפוש והסינון.

  תקבל כרטיס עם עד 15 שדות מפרופיל הלקוח המתקבל. התאמות מרובות מחזירות רשימת תוצאות שבה תוכל לבחור פרופיל. באפשרותך להוסיף את מונח החיפוש במרכאות כפולות כדי לחפש התאמה מדויקת.

- אם הארגון שלך מתחזק מספר סביבות של Customer Insights באותו ארגון, באפשרותך להזין **switchinstance** כדי לבחור לאיזו סביבה ברצונך לחבר את תוכנית ה- Bot.

- הזן **עזרה** כדי לראות רשימת פקודות זמינות עבור תוכנית ה- Bot.  


[!INCLUDE[footer-include](../includes/footer-banner.md)]