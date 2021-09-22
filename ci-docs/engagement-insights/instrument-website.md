---
title: הוספת קוד לאתר האינטרנט שלך
description: כיצד להוסיף מקטע קוד כדי ללכוד אירועים באתר שלך.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035095"
---
# <a name="install-the-code-snippet-on-a-website"></a>התקנת מקטע הקוד באתר

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

מאמר זה מתאר כיצד מנהל מערכת מתקין את מקטע הקוד באתר. זמן קצר לאחר הוספת קובץ ה- Script לאתר, אירועים יתחילו להופיע בסביבת העבודה. למידע נוסף ראה [ניהול סביבה וסביבות עבודה](manage-environments-workspaces.md). כדי ללכוד אירועים באפליקציות למכשירים ניידים, ראה [סקירה של משאבים למפתחים](developer-resources.md).


### <a name="prerequisites"></a>דרישות מוקדמות

* כדי לאחסן את הנתוני, דרושות הרשאות של מנהל מערכת עבור סביבת העבודה.
* על האתר או הפרויקט שלך להתארח באופן מקוון כדי לשלוח נתוני פעילות. נתונים שנשלחו מקובץ מקומי לא יתקבלו על ידי השרת.


## <a name="add-code-to-your-website"></a>הוספת קוד לאתר האינטרנט שלך
1.  עבור אל **מנהל מערכת** > **סביבת עבודה** ואז בחר **מדריך ההתקנה**.
1. בחר **העתקת קוד** כדי להעתיק את מקטע הקוד. כברירת מחדל, מפתח הקליטה עבור סביבת העבודה שלך מוטבע במקטע הקוד.
:::image type="content" source="media/copy-code.png" alt-text="צילום מסך של דף מקטע הקוד.":::
3. הוסף את מקטע קוד שהועתק לאתר שלך, בסמוך ל <head> תג ולפני כל קובץ Script אחר או תגי CSS.
4.  פרסם את האתר המעודכן שלך והמתן מספר דקות כדי לתפוס את תעבורת האינטרנט הנכנסת.
5.  כדי לראות את הנתונים שלך, בחר את סביבת העבודה מתוך מחליף סביבות העבודה בחלונית הניווט. לאחר מכן בחר באחד הדוחות במקטע **גלה**.

## <a name="configuration-options"></a>אפשרויות תצורה

ניתן לשנות את אפשרויות התצורה הבאות במקטע הקוד:

- **ingestionKey**: מפתח הקליטה המשמש לשליחת אירועים לסביבת העבודה שלך. באפשרותך לשנות את מפתח הקליטה כדי לשלוח אירועים לסביבת עבודה אחרת. מפתח הקליטה ייחודי לכל סביבת עבודה. 
- **autoCapture**: מציין אם הצפיות בדפים והאינטראקציות עם האתר נלכדו. הוא כולל שתי אפשרויות:
    - **צפייה**: מוגדר *true* כדי ללכוד צפיות בדפים. צפיות בדפים נלכדות כ [אירועי](glossary.md#event) *צפייה*, סוג של [אירוע בסיס](glossary.md#base-event).
    - **לחיצה**: מוגדר *true* כדי ללכוד אינטראקציות של מבקרים באתר. אינטראקציות נלכדות כ [אירועי](glossary.md#event) *פעולה*, סוג של [אירוע בסיס](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
