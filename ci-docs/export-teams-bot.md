---
title: תוכנית Bot של Teams עבור Dynamics 365 Customer Insights‎‏ (preview)
description: חפש פרופילי לקוחות מאוחדים ב- Microsoft Teams בעזרת תוכנית Bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195843"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>תוכנית Bot של Teams עבור Dynamics 365 Customer Insights‎‏ (preview)

התחבר עם Microsoft Teams כדי לאפשר לתוכנית Bot לחפש פרופילי לקוחות מאוחדים בערוצי Teams.

:::image type="content" source="media/teams-bot.png" alt-text="תוכנית Bot של Teams המציגה רשומת לקוח":::

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- התווסף לפחות [מקור נתונים אחד](data-sources.md).
- [תהליך האיחוד](data-unification.md) הושלם.
- שדות מתווספים ל[אינדקס חיפוש וסינון ](search-filter-index.md).
- Customer Insights ו- Teams נמצאים באותו ארגון.
- הסביבה שלך כוללת את קהל היעד הראשי המוגדר ללקוחות בודדים. חשבונות עסקיים אינם נתמכים.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>קביעת התצורה של תוכנית ה- Bot

1. עבור אל **ניהול** > **חיבורים**.
1. באריח Microsoft Teams, בחר **הגדר**.
1. אתה מנותב מחדש אל האזור **יישומים** ב- Teams. באפשרותך גם לפתוח את Teams ולבחור **יישומים** בפינה השמאלית התחתונה או [להשיג אותו דרך AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) ישירות.
1. חפש את **Customer Insights** ובחר את היישום.
1. בחר **הוסף**.
1. היכנס אל Customer Insights ב- Teams. מוצגת הודעת פתיחה.

## <a name="things-you-can-do-with-the-bot"></a>דברים שניתן לעשות עם תוכנית ה- Bot

תוכנית ה- Bot מספקת יכולות בדיקת מידע עבור פרופילי לקוחות מאוחדים.

- הזן **חיפוש** ולאחר מכן שם, כתובת דוא"ל או כל שדה אחר בפרופיל הלקוח המאוחד המתווסף לאינדקס החיפוש והסינון.

  תקבל כרטיס עם עד 15 שדות מפרופיל הלקוח המתקבל. התאמות מרובות מחזירות רשימת תוצאות שבה תוכל לבחור פרופיל. כדי לחפש התאמה מדויקת, הוסף את מונח החיפוש במרכאות כפולות.

- אם הארגון שלך מתחזק מספר סביבות של Customer Insights באותו ארגון, הזן **switchinstance** כדי לבחור לאיזו סביבה ברצונך לחבר את תוכנית ה- Bot.

- הזן **עזרה** כדי לראות רשימת פקודות זמינות עבור תוכנית ה- Bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]