---
title: יצירת סביבה חדשה
description: המטרה של סביבה וכיצד ליצור סביבה חדשה.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648118"
---
# <a name="create-a-new-environment"></a>יצירת סביבה חדשה 

## <a name="overview"></a>מבט כולל

סביבה היא מרחב לניהול של סביבות העבודה והחיבורים שלך. אופן השימוש בסביבות תלוי בארגון ובאופי השימוש שלך. לדוגמה, באפשרותך ליצור:

- סביבה יחידה.
- סביבות נפרדות עבור בדיקה וייצור.
- סביבות נפרדות עבור צוותים ספציפיים או מחלקות בארגון שלך, שיכילו אירועים רלוונטיים עבור כל קהל.
- סביבות נפרדות עבור סניפים שונים של החברה שלך ברחבי העולם.
- חיבורים ליכולת תובנות לגבי קהלים של Customer Insights.

## <a name="create-a-new-environment"></a>יצירת סביבה חדשה

1. בצד ימין של הכרזה הראשית, בחר בבורר הסביבות ולאחר מכן **+חדש**.

   :::image type="content" source="media/environment-picker.png" alt-text="בחר בבורר הסביבות.":::

1. בחלונית **הגדרה**, הקלד **שם סביבה**.

1. בחר את **סוג** החשבון, בהתאם לסוג התוכנית שלך.

1. בחר את ה- **אזור** ובחר **הבא**. 

1. הקלד **שם סביבת עבודה**, שמאפשר לך לאסוף נתונים לאתר אינטרנט ספציפי או ליישומים ספציפיים. לקבלת מידע נוסף, ראה [יצירת סביבת עבודה](create-workspace.md).

1. בחר את **סוג סביבת העבודה** (אינטרנט או נייד) שברצונך ליצור. 

1. בחר **הצג הגדרות מתקדמות** כדי להפעיל או להשבית את ההגדרות האופציונליות הבאות:

   - שנה את האפשרות **לא ידוע לידוע** למצב 'מופעל' כדי לשייך אירועי אינטרנט למשתמשים שאומתו בעבר. למידע נוסף, ראה [זיהוי אירועי אינטרנט ממבקרים שאומתו בעבר](unknown-to-known.md)
   - שנה את האפשרות **‏‫סינון תעבורה של תוכניות Bot‬** למצב 'מופעל' כדי להסיר תעבורת אינטרנט לפי תוכניות Bot עבור סביבת עבודה זו. 

1. לסיום, בחר **הושלם**. 

1. התקן את מקטע הקוד כדי להתחיל לקבל נתונים ולאחר מכן בחר **סיום** כדי ליצור את סביבת העבודה. לקבלת מידע נוסף, ראה [סקירה של משאבים למפתחים](developer-resources.md)‬‏‫.

> [!NOTE]
> כעת באפשרותך להוסיף חברים ולהקצות את רמת ההרשאה שלהם מהרשימה **תפקיד**. למידע נוסף ראה [תפקידים והרשאות](user-roles.md). 

למידע נוסף ראה [ניהול סביבות וסביבות עבודה](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>עבודה עם הסביבה החדשה

- [צור סביבת עבודה](../engagement-insights/create-workspace.md) והוסף חברים.
- [הוסף קוד לאתר האינטרנט שלך](../engagement-insights/instrument-website.md) או [יישום למכשירים ניידים](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- הצג [דוח בזמן אמת](../engagement-insights/view-reports.md) או צור [דוחות מותאמים אישית](../engagement-insights/custom-reports.md).
- [צור אירועים ממוקדים](../engagement-insights/refined-events.md) לייצוא.
- [ייצא את הנתונים](../engagement-insights/export-events.md) אל Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
