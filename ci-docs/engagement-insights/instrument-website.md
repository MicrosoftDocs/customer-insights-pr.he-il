---
title: הוספת קוד לאתר האינטרנט שלך
description: כיצד להוסיף מקטע קוד כדי ללכוד אירועי Dynamics 365 Customer Insights באתר האינטרנט שלך.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558858"
---
# <a name="install-the-web-sdk-on-a-website"></a>התקנת SDK האינטרנט באתר אינטרנט

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

מאמר זה מתאר כיצד מנהל מערכת מתקין את ערכת הכלים לפיתוח תוכנת אינטרנט (SDK) באתר אינטרנט. תתחיל לראות אירועים בסביבת העבודה שלך זמן קצר לאחר ביצוע האינסטרומנטציה של אתר האינטרנט שלך. למידע נוסף ראה [ניהול סביבה וסביבות עבודה](manage-environments-workspaces.md). כדי ללכוד אירועים באפליקציות למכשירים ניידים, ראה [סקירה של משאבים למפתחים](developer-resources.md).


### <a name="prerequisites"></a>דרישות מוקדמות

* כדי לאחסן את הנתוני, דרושות הרשאות של מנהל מערכת עבור סביבת העבודה.
* על האתר או הפרויקט שלך להתארח באופן מקוון כדי לשלוח נתוני פעילות. נתונים שנשלחו מקובץ מקומי לא יתקבלו על ידי השרת.


## <a name="add-web-sdk-to-your-website"></a>הוספת SDK של אינטרנט לאתר האינטרנט שלך

עבור אל **מנהל מערכת** > **סביבת עבודה** ואז בחר **מדריך ההתקנה**. קיימות שתי אפשרויות להתקנת SDK של אינטרנט. הראשונה היא להשתמש בקישור הורדה, והשנייה היא התקנת חבילה של מנהל חבילות צומת (NPM).

### <a name="option-1-using-the-download-link"></a>אפשרות 1: שימוש בקישור להורדה

1. בחר **העתקת קוד** כדי להעתיק את מקטע הקוד. כברירת מחדל, מפתח הקליטה עבור סביבת העבודה שלך מוטבע במקטע הקוד.
  :::image type="content" source="media/copy-code.png" alt-text="צילום מסך של דף מקטע הקוד.":::

1. הוסף את הקוד שהועתק לאתר האינטרנט שלך, בקרבת <head> תג ולפני כל קובץ Script אחר או תגי CSS.
1. פרסם את האתר המעודכן שלך והמתן מספר דקות כדי לתפוס את תעבורת האינטרנט הנכנסת.
1. כדי לראות את הנתונים שלך, בחר את סביבת העבודה מתוך מחליף סביבות העבודה בחלונית הניווט. לאחר מכן בחר באחד הדוחות במקטע **גלה**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>אפשרות 2: שימוש בחבילת NPM (מומלץ עבור יישומי אינטרנט מבוססי-JavaScript)

1. עבור אל [דף האינטרנט של NPM](https://www.npmjs.com/package/engagementinsights-web) שלנו ופעל לפי ההוראות כדי להתקין ולהגדיר את חבילת NPM של SDK.
1. פרסם את האתר המעודכן שלך והמתן מספר דקות כדי לתפוס את תעבורת האינטרנט הנכנסת.
1. כדי לראות את הנתונים שלך, בחר את סביבת העבודה מתוך מחליף סביבות העבודה בחלונית הניווט. לאחר מכן בחר באחד הדוחות במקטע **גלה**.

## <a name="configuration-options"></a>אפשרויות תצורה

ניתן לשנות את אפשרויות התצורה הבאות במקטע הקוד:

- **ingestionKey**: מפתח הקליטה המשמש לשליחת אירועים לסביבת העבודה שלך. באפשרותך לשנות את מפתח הקליטה כדי לשלוח אירועים לסביבת עבודה אחרת. מפתח הקליטה ייחודי לכל סביבת עבודה.
- **autoCapture**: מציין אם הצפיות בדפים והאינטראקציות עם האתר נלכדו. הוא כולל שתי אפשרויות:
    - **צפייה**: מוגדר *true* כדי ללכוד צפיות בדפים. צפיות בדפים נלכדות כ [אירועי](glossary.md#event) *צפייה*, סוג של [אירוע בסיס](glossary.md#base-event).
    - **לחיצה**: מוגדר *true* כדי ללכוד אינטראקציות של מבקרים באתר. אינטראקציות נלכדות כ [אירועי](glossary.md#event) *פעולה*, סוג של [אירוע בסיס](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
