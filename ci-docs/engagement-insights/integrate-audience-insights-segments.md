---
title: השתמש בקטעי תובנות קהל כדי לסנן דוחות תובנות מעורבות
description: השתמש בקטעי תובנות קהל בניתוחים אינטראקטיביים של נתוני התנהגות שנלכדו על ידי תובנות מעורבות באתר של לקוח.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: bdd5641bb17384725491f22f70ae967ad90b1696
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461059"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>השתמש בקטעי תובנות קהל כדי לסנן דוחות תובנות מעורבות

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

בעזרת תובנות מעורבות, אתה יכול להשתמש בקטעי תפלחי ובנות קהל בניתוחים אינטראקטיביים של נתוני התנהגות שנלכדו על ידי תובנות מעורבות באתרים שלך.

## <a name="prerequisite"></a>דרישה מוקדמת

- סביבת תובנות מעורבות שבה יש לך נתוני פלחי תובנות קהל המקושרים לסביבת תובנות קהל שבה נוצרים הפלחים ופרופילי הלקוחות. מידע נוסף: [צור קישור בין תובנות קהל לבין תובנות מעורבות](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>צור פלחי תובנות קהל 

> [!IMPORTANT]
> כדי שפלחי תובנות קהל יופיעו בתובנות מעורבות, עליך תחילה [להריץ תהליכי מיזוג וקבץ הורדה](../audience-insights/merge-entities.md). תהליכי קצב הורדה חשובים מכיוון שהם יוצרים טבלה ייחודית המכינה פלחי תובנות קהל לשיתוף עם תובנות מעורבות. (אם מתוזמן רענון מערכת, הוא יכלול באופן אוטומטי תהליכי קצב הורדה).

תוכל להשתמש בפלחי תובנות קהל בדוחות מחוץ לקופסא של תובנות מעורבות או בדוחות מותאמים אישית שיצרת. למידע נוסף, עבור אל [דוחות פרופיל מחוץ לקופסה](profile-reports.md) ו- [צור וערוך דוחות מותאמים אישית](custom-reports.md).

**כדי להשתמש בקטעי תובנות קהל בדוחות תובנות מעורבות**

1. מעמוד **סביבת העבודה** שלך, בחר **נתונים** ולאחר מכן בחר בכרטיסיית **פלחים**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="בחר את כרטיסיית פלחים":::

   >[!NOTE]
   > בחירת פלח תובנות קהל תוביל אותך לתובנות קהל, שם תוכל לברר כיצד נוצר פלח זה מבחינת החוקים וההיגיון. למידע נוסף אודות פלחי תובנות קהל, עבור אל [הצג וצור פלחים](../audience-insights/segments.md).

2. בחר דוח מחוץ לקופסה או [צור דוח מותאם אישית](custom-reports.md) ולאחר מכן בחר **הוסף תנאי**. (לדוגמא זו בחרנו בדוח **צפיות בדף**).

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="הוסף תנאי.":::

3. בחר **סנן לפי פלח**, הרחב את רשימת **סוג הפלח** ולאחר מכן בחר **דמוגרפי**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="בחר את סוג הפלח הדמוגרפי.":::

4. הרחב את רשימת **שם הפלח** ולאחר מכן בחר בפלח תובנות קהל.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text=" בחר פלח.":::

5. תוכל להחיל פלח אחד או יותר, כולל פלח התנהגותי (תובנות מעורבות) ודמוגרפי (תובנות קהל). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="דוח צפיות בדף מוגבל ללקוחות בארצות הברית ולפלחי דף הבית.":::

בתמונה הקודמת, פלחי **לקוחות ארה"ב** ו-**דף הבית** נבחרו, מה שמגביל את דוח **צפיות בדף** להציג רק את שני הפלחים האלה. 


>[!NOTE]
> תוכל להשתמש בפלחי תובנות קהל בדוחות כדי לסנן דוחות מחוץ לקופסא, להתאים אישית דוחות ומשפכים בתובנות מעורבות . 


[!INCLUDE[footer-include](../includes/footer-banner.md)]