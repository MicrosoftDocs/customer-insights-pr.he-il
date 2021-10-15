---
title: הצג וצור פלחים
description: כיצד ליצור, לערוך ולמחוק פלחים והיכן להשתמש בהם.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036149"
---
# <a name="view-and-create-segments"></a>הצג וצור פלחים

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

פלחים מאפשרים לזהות קבוצות משנה של מבקרים בהתבסס על מאפיינים או אינטראקציות בין אתרי אינטרנט. פלחים מאפשרים להחיל מסננים ולנתח קבוצות משנה אלה. הניתוח יכול לעזור לבחון מגמות בעסק שלך ולהגיב להן. 

:::image type="content" source="media/segments-page.png" alt-text="צילום מסך של יישום תובנות המעורבות שמציג את רשימת הפלחים הקיימים בסביבת עבודה.":::

## <a name="view-segments"></a>הצגת פלחים

1. עבור אל **נתונים** בחלונית הניווט הימנית. 

1. בחר בכרטיסיה **פלחים** כדי לראות רשימה של כל הפלחים בסביבת העבודה. 

## <a name="create-a-segment"></a>צור פלח

פלחים מורכבים מכללים ותנאים המחוברים זה לזה באמצעות אופרטורים לוגיים. התנאים מחילים מסננים על ממד שנבחר. כל פלח יכול להשתמש בחמישה ממדים לכל היותר.

הדוגמה הבאה מציגה פלח עם שני תנאים בכלל אחד. הוא מסנן את כל האירועים באתר אינטרנט שבהם הדפדפן הוא Chrome ומערכות ההפעלה הן iOS או Android.

:::image type="content" source="media/segment-sample.png" alt-text="פלחים לדוגמה עם שני תנאים בכלל לסינון אירועים באתר אינטרנט.":::

מקטע זה מתאר כיצד ליצור *פלח ריק* מאפס.

1. עבור אל **נתונים** > **פלחים**.

1. בחר **פלח חדש**.

1. ב **ספריית המשאבים**, בחר בתכונה שלפיה ברצונך לסנן. נכון לעכשיו, ניתן ליצור פלחים בהתבסס על ממדים.

1. בחר אופרטור וערך עבור התכונה שנבחרה. הפעולות הבאות נתמכות.
   - **הוא**: נדרשת התאמה מדויקת כדי לכלול ערכים. משתמש בערך **שווה ל** עבור ערך יחיד או **כל אחד מ** כדי לכלול ערכים מרובים.
   - **אינו**: נדרשת התאמה מדויקת כדי לא לכלול ערכים. משתמש בערך **שווה ל** עבור ערך יחיד או **כל אחד מ** כדי לכלול ערכים מרובים.
   - **מתחיל ב**: מחרוזת שתואמת לערכים שמתחילים בתווים שצוינו.
   - **מסתיים ב**: מחרוזת שתואמת לערכים שמסתיימים בתווים שצוינו.
   - **מכיל**: מחרוזת הכלולה בערכים תואמים.

1. כדי להוסיף תנאים לקבוצה, אתה יכול להשתמש בשני אופרטורים לוגיים. תכונות חזויות נלקחות בחשבון בעת שימוש ב‏‫אופרטורי הגדרה.
   - אופרטור **AND**: יש לעמוד בשני התנאים כחלק מתהליך הפילוח. אפשרות זו שימושית ביותר כאשר אתה מגדיר תנאים בין ישויות שונות.
   - אופרטור **OR**: צריך להתקיים אחד מהתנאים כחלק מתהליך הפילוח. אפשרות זו שימושית ביותר כאשר אתה מגדיר מספר תנאים לאותה ישות.

1. בחר **שמור** והענק שם לפלח. 

הפל יופיע בדף 'פלחים' ותוכל להחיל אותו על כל הדוחות והמשפכים בסביבת העבודה.

## <a name="use-a-segment-in-a-report-or-funnel"></a>שימוש בפלח בדוח או במשפך

באפשרותך להחיל פלחים על דוח או משפך כדי לסנן אותם בהתבסס על התנאים בפלח. עם זאת, אינך יכול להחיל פלחים על דוח השימוש בזמן אמת.

:::image type="content" source="media/segment-reports-filter.png" alt-text="דוח צפיות בדף עם רשימה נפתחת מורחבת כדי לבחור אילו פלחים להחיל.":::

כדי להחיל פלח, פתח את הדוח או המשפך. בחר **הוסף תנאי** ובחר **סנן לפי פלח**. בחר את הפלח מהרשימה שברצונך להחיל. הפלח יוחל על הדוח. אם תרשים אינו תומך בפלח, מוצגת שגיאה.
 
תוכל להחיל *עד שלושה פלחים* לדוח או משפך.

## <a name="edit-a-segment"></a>ערוך פלח

1. עבור אל **נתונים** > **פלחים**.
1. בחר את הפלח ברשימה כדי לפתוח אותו. 
1. שנה או הוסף ערכים לפי הצורך.
1. בחר **שמור** כדי להחיל את השינויים.

## <a name="change-the-name-of-a-segment"></a>שינוי השם של פלח

1. עבור אל **נתונים** > **פלחים**.
1. ברשימת הפלחים, בחר **עוד [...]**. 
1. מהרשימה הנפתחת בחר **ערוך שם**.
1. הזן את השם החדש, ובחר **שנה שם**.

## <a name="delete-a-segment"></a>מחיקת פלח

1. עבור אל **נתונים** > **פלחים**.
1. ברשימת הפלחים, בחר **עוד [...]**. 
1. מהרשימה הנפתחת בחר **מחק**.
1. בחר **מחק** כדי לאשר.

[!INCLUDE[footer-include](../includes/footer-banner.md)]