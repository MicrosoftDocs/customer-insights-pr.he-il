---
title: ניהול סביבות
description: למד כיצד לנהל סביבות קיימות של Customer Insights כמנהל מערכת.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588813"
---
# <a name="manage-environments"></a>ניהול סביבות

מנהלי מערכת [יוצרים](create-environment.md) ומנהלים סביבות. הם יכולים לשנות הגדרות מסוימות בסביבות קיימות. עסק, סוג, אזור, אפשרות אחסון והגדרות Dataverse קבועות לאחר יצירת הסביבה. אם ברצונך לשנות הגדרות אלה, [אפס את הסביבה](#reset-an-existing-environment-preview) או [צור סביבה חדשה](create-environment.md).

## <a name="edit-an-existing-environment"></a>עריכת סביבה קיימת

ערוך פרטים של סביבה קיימת כגון השם או הגדרת סביבת ברירת המחדל.

1. בחר את בורר **הסביבה** בכותרת היישום.

1. בחר את סמל **עריכה**.

   :::image type="content" source="media/edit-environment.png" alt-text="סמל לעריכת הגדרות הסביבה.":::

1. בחלונית **ערוך סביבה**, עדכן את הגדרות הסביבה.

1. בחר **בדיקה וסיום**, לאחר מכן **עדכון** כדי להחיל את השינויים.

## <a name="change-the-owner-of-an-environment"></a>שינוי הבעלים של הסביבה

בעוד שלמספר משתמשים יכולים להיות הרשאות ניהול, רק אחד מהם הוא הבעלים של סביבה. כברירת מחדל, מנהל המערכת הוא זה שיוצר סביבה תחילה. כמנהל מערכת של סביבה, תוכל להקצות בעלות למשתמש אחר עם הרשאות מנהל מערכת.

1. בחר את בורר **הסביבה** בכותרת היישום.

1. בחר את סמל **עריכה**.

1. בחלונית **ערוך סביבה**, עבור אל הצעד **מידע בסיסי**.

1. בשדה **שנה את הבעלים של הסביבה**, בחר את הבעלים החדשים של הסביבה.  

1. בחר **בדיקה וסיום**, לאחר מכן **עדכון** כדי להחיל את השינויים.

## <a name="claim-ownership-of-an-environment"></a>טעינת בעלות על סביבה

אם חשבון המשתש של הבעלים נמחק או מושהה, לסביבה לא יהיה בעלים. כל משתמש עם הרשאות מנהל מערכת יכול לתבוע את הבעלות ולהפוך לבעלים החדש. מנהל המערכת שהוא הבעלים יכול להמשיך כבעלים של הסביבה או [להעביר את הבעלות למנהל מערכת אחר](#change-the-owner-of-an-environment).

כדי לתבוע בעלות, בחר את הלחצן **לקחת בעלות** שמופיע בראש כל עמוד ב- Customer Insights כאשר הבעלים המקורי עזב את הארגון.

## <a name="reset-an-existing-environment-preview"></a>איפוס מסביבה קיימת (Preview)

כבעלים של סביבה,אפס סביבה למצב ריק אם ברצונך למחוק את כל התצורות ולהסיר את הנתונים שעובדו.

1. בחר את בורר **הסביבה** בכותרת היישום.

1. בחר את הסביבה שברצונך לאפס ובחר את שלוש הנקודות האנכיות (&vellip;).

1. בחר **אפס (Preview)**.

   :::image type="content" source="media/reset-environment.png" alt-text="פקד לאיפוס סביבה.":::

1. בחר אם ברצונך לאפס את כל הסביבה, הכל מלבד מקורות הנתונים, או כל דבר שמוגדר על גבי unified customer profile.

1. לאישור, הזן את שם הסביבה, ובחר באפשרות **איפוס**.

## <a name="delete-an-existing-environment"></a>מחק סביבה קיימת

כבעלים של סביבה, אתה יכול למחוק אותה.

> [!IMPORTANT]
> מחיקת סביבה אינה מסירה את החיבור לסביבת Dataverse. אם אתה מתכנן לחבר את אותו סביבת Dataverse לסביבת Customer Insights חדשה בעתיד, עליך [להסיר את החיבור הזה לסביבת Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. בחר את בורר **הסביבה** בכותרת היישום.

1. בחר את הסביבה שברצונך למחוק ובחר את שלוש הנקודות האנכיות (&vellip;). 

1. בחר **מחק**.

   :::image type="content" source="media/delete-environment.png" alt-text="פקד למחיקת הסביבה.":::

1. כדי לאשר את המחיקה, הזן את שם הסביבה ובחר **מחק**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
