---
title: דף הבית ב- audience insights
description: התחל לסייר ביישום בדף הבית.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477042"
---
# <a name="create-a-new-environment"></a>צור סביבה חדשה

## <a name="create-a-trial-environment"></a>יצירת סביבת ניסיון

ניתן להירשם להירשם לגרסת ניסיון ב-[דף הרשמה לגרסת ניסיון](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> גרסאות נסיון פגות לאחר 30 יום.

1. בחר את האפשרות **הירשם לגרסת ניסיון ללא תשלום** ובחר **הרשם עכשיו**.

1. ספק את כתובת הדואר שלך בעבודה או בבית הספר, ספר לנו עוד על עצמך ובחר **הבא**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="תיבת דו-שיח להרשמה למופע ניסיון":::

1. תן **שם** לסביבה החדשה שלך. 

1. בחר את סוג גרסת הניסיון.

1. בחר את ה **אזור** של הסביבה שלך.

1. לחלופין, עבור מנהלי מערכת של ארגון Dynamics 365: בחר **הגדרות מתקדמות** וספק את כתובת ה-URL של הארגון שלך כדי להשתמש בתכונות חיזוי כמו נטישת לקוחות.

1. בחר **Create** (צור). 

לאחר יצירת הסביבה, תראה את סביבת **ההדגמה**, המאפשרת לך לבדוק את האפליקציה עם נתונים פיקטיביים. ניתן לשנות את נתוני הדוגמה כך שיתאימו לענף שלך. בחר את הסמל **הגדרות** שבכותרת העליונה ובחר **הגדרות הדגמה**. בנוסף, באפשרותך לשנות את הנושא החזותי. 

אתה [עובר לסביבה](#switch-environments) שיצרת בתהליך ההרשמה כדי לעבוד עם הנתונים שלך.

## <a name="create-a-new-production-or-sandbox-environment"></a>יצירת סביבת ייצור או סביבת ארגז חול חדשה

בסביבה שלך, בחר את בורר **הסביבות** בכותרת היישום ובחר **חדש**.

בצע את השלבים [ליצירת סביבת ניסיון](#create-a-trial-environment). כברירת מחדל, הנתונים נשמרים ב-Data Lake המנוהל על ידי Customer Insights. בעת בחירת **הגדרות מתקדמות** תקבל אפשרות נוספת לאחסן את הנתונים ב-Azure Data Lake שלך. ספק את שם החשבון ומפתח החשבון שלך כדי ליצור חיבור ל-Azure Data Lake שלך. 

> [!IMPORTANT]
> על-ידי שמירת הנתונים שלך ב-Azure Data Lake Storage שלך, אתה מסכים שנתונים יועברו למיקום הגיאוגרפי המתאים לחשבון אחסון זה של Azure ויאוחסנו בו. מיקום זה עשוי להיות שונה מהמקום שבו נתונים מאוחסים ב-Dynamics 365 Customer Insights. [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>חקור את דף הבית

באפשרותך [לגשת אל audience insights מתוך Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) בכתובת ה- URL הבאה: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
דף **הבית** מציג מבט כולל על פלחים, מדדים ונתוני העשרה (אם מוגדרים) לאחר השלמת השלבים [מיפוי](map-entities.md), [התאמה](match-entities.md) ו[מיזוג](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![תובנות בדף הבית](media/home-page-insights.png "תובנות בדף הבית")

באזור **פלחים אחרונים**, אתה רואה קבוצות של לקוחות על סמך מאפיינים דמוגרפיים, התנהגותיים או עסקאות שהגדרת. [יצירת פלחים](segments.md) עוזרת לך לקבץ את בסיס הלקוחות שלך ולמקד טוב יותר את הפעילויות העסקיות שלך.

**מדידות אחרונות** מציגות אריחים עם [מחווני ביצועי מפתח (KPI)](measures.md) שהגדרת. לדוגמא, הסבירות הממוצעת של לקוח לנטוש או ההוצאה המקוונת הממוצעת לכל לקוח.

המקטע **העשרות אחרונות** מפרט את התוצאות של ריצות ההעשרה שהושלמו לאחרונה. [העשרות](enrichment-hub.md) מוסיפות מידע על בסיס הלקוחות שלך. למשל על ידי הבנת האינטרסים והמותגים שיש להם זיקה אליהם.

## <a name="switch-environments"></a>החלף סביבות

בחר את הפקד **סביבה** בפינה הימנית העליונה של הדף כדי לשנות סביבות.

> [!div class="mx-imgBorder"] 
> ![החלף סביבה](media/home-page-environment-switcher.png "החלף סביבה")

מנהלי מערכת יכולים ליצור ולנהל [סביבות מרובות](manage-environments.md). שמירה על יותר מסביבה אחת עשויה להועיל אם, למשל, הארגון שלך פועל באופן בינלאומי ואתה צריך להבחין בין נתונים ותובנות בדרכים שונות.

## <a name="next-step"></a>השלב הבא

כדי לראות את התובנות שלך בדף הבית, תחילה עליך [להוסיף מקורות נתונים](data-sources.md) ו- [לאחד](data-unification.md) את הנתונים שלך כדי ליצור פרופילי לקוחות.


[!INCLUDE[footer-include](../includes/footer-banner.md)]