---
title: הסר כפילויות לפני איחוד נתונים
description: השלב השני בתהליך האיחוד הוא בחירת הרשומה שברצונך לשמור כאשר יימצאו כפילויות.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741661"
---
# <a name="remove-duplicates-before-unifying-data"></a>הסר כפילויות לפני איחוד נתונים

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

שלב זה באיחוד מאפשר לך להגדיר כללים לטיפול ברשומות כפולות בתוך ישות. *ביטול כפילות* מזהה רשומות כפולות וממזג אותן לרשומה אחת. רשומות המקור נקשרות לרשומה הממוזגת עם מזהים חלופיים. אם כללים אינם מוגדרים, כללים שמוגדרים על ידי המערכת יחולו.

## <a name="include-enriched-entities-preview"></a>כלול ישויות מועשרות (Preview)

אם העשרת ישויות ברמת מקור הנתונים כדי לעזור לשפר את תוצאות האיחוד, בחר בהן. למידע נוסף, ראה [העשרה עבור מקורות נתונים](data-sources-enrichment.md).

1. בדף **רשומות כפולות**, בחר **השתמש בישויות מועשרות** בראש הדף.

1. מחלונית **השתמש בישויות מועשרות**, בחר ישות מועשרת אחת או יותר.

1. בחר **סיום**.

## <a name="define-deduplication-rules"></a>הגדר כללים לביטול כפילויות

1. בדף **רשומות כפולות**, בחר ישות ובחר **הוסף כלל** כדי להגדיר את הכללים לביטול כפילויות.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="צילום מסך של דפי רשומות כפולות עם האפשרות 'הצג יותר' מודגשת":::

   1. בחלונית **הוסף כלל** הזן את הפרטים הבאים:
      - **בחר שדה**: בחר מרשימת השדות הזמינים מהישות שברצונך לבדוק כפילויות. בחר שדות שעשויים להיות ייחודיים עבור כל לקוח יחיד. לדוגמה, כתובת דואר, או השילוב של שם, עיר ומספר טלפון.
      - **נרמל**: בחר מבין אפשרויות הנרמול הבאות עבור התכונות שנבחרו.
        - **ספרות**: ממיר מערכות ספרות אחרות, כגון ספרות רומיות, לספרות בערבית. *VIII* הופך להיות *8*.
        - **סמלים**: מסיר את כל הסמלים והתווים המיוחדים. *ראש&כתף* הופך להיות *ראשכתף*.
        - **טקסט לאותיות קטנות: ממיר את כל התווים לאותיות קטנות**. *ALL CAPS and Title Case* הופך להיות *all caps and title case*.
        - **סוג (טלפון, שם, כתובת, ארגון)**: מבצע תקנון של שמות, תפקידים, מספרי טלפון, כתובות ועוד.
        - **Unicode ל- ASCII**: ממיר את סימון ה- Unicode לתווי ASCII. */u00B2* הופך להיות *2*.
        - **רווח לבן**: מסיר את כל הרווחים. *שלום   עולם* הופך להיות *שלוםעולם*.
      - **דיוק**: מגדיר את רמת הדיוק להחלה עבור תנאי זה.
        - **בסיסי**: בחר בין *נמוך (30%)*, *בינוני (60%)*, *גבוה (80%)*, או *מדויק (100%)*. בחר **מדויקת** כדי להתאים רק רשומות עם התאמה של 100%.
        - **מותאם אישית**: הגדר אחוז התאמה רצוי עבור רשומות. המערכת תתאים רק רשומות שעוברות ערך סף זה.
      - **שם**: שם הכלל.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="צילום מסך של חלונית 'הוסף כלל' להסרת כפילויות.":::

   1. לחלופין, בחר **הוסף** > **הוסף תנאי** כדי להוסיף תנאים נוספים לכלל. התנאים קשורים לאופרטור AND לוגי וכך הם מופעלים רק אם כל התנאים מתקיימים.

   1. לחלופין, **הוסף** > **הוסף חריגה** כדי [להוסיף חריגים לכלל](match-entities.md#add-exceptions-to-a-rule). חריגים משמשים לטיפול במקרים נדירים של תוצאות חיוביות מוטעות ותוצאות שליליות מוטעות.

   1. בחר **בוצע** כדי ליצור את הכלל.

1. לבחירתך, [הוסף כללים נוספים](#define-deduplication-rules).

1. בחר ישות ולאחר מכן **ערוך העדפות מיזוג**.

1. בחלונית **מיזוג העדפות**:
   1. בחר אחת משלוש אפשרויות כדי לקבוע איזו רשומה לשמור אם תימצא כפילות:
      - **הכי הרבה אנשים מילאו**: מזהה את הרשומה עם הכי הרבה שדות תכונה מאוכלסים כרשומה המנצחת. זוהי אפשרות המיזוג של ברירת המחדל.
      - **החדשים ביותר**: מזהה את הרשומה המנצחת בהתבסס על העדכניות. דורש תאריך או שדה מספרי להגדרת העדכניות.
      - **הישנים ביותר**: מזהה את הרשומה המנצחת בהתבסס על העדכניות הנמוכה ביותר. דורש תאריך או שדה מספרי להגדרת העדכניות.
      
      במקרה של תיקו, הרשומה שתישאר היא זו עם MAX(PK)‎ או ערך המפתח הראשי הגדול יותר.
      
   1. לחלופין, כדי להגדיר העדפות מיזוג על תכונות בודדות של ישות, בחר **מתקדם** בחלק התחתון של החלונית. לדוגמה, אתה יכול לבחור לשמור את הדואר האלקטרוני העדכני ביותר ואת הכתובת המלאה ביותר מרשומות שונות. הרחב את הישות כדי לראות את כל התכונות שלה ולהגדיר באיזו אפשרות להשתמש עבור תכונות בודדות. אם תבחר באפשרות מבוססת עדכניות, עליך לציין גם שדה תאריך/שעה שמגדיר את העדכניות.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="חלונית העדפות מיזוג מתקדמות המציגה את הדואר העדכני ביותר ואת הכתובת המלאה":::

   1. בחר **בוצע** כדי להחיל את העדפות המיזוג שבחרת.

1. לאחר הגדרת כללי מניעת הכפילויות והעדפות המיזוג, בחר **הבא**.
  
> [!div class="nextstepaction"]
> [השלב הבא עבור ישות אחת: איחוד שדות](merge-entities.md)

> [!div class="nextstepaction"]
> [השלב הבא עבור ישויות מרובות: תנאי התאמה](match-entities.md)

## <a name="deduplication-output-as-an-entity"></a>פלט ביטול כפילויות כישות

תהליך ביטול הכפילות יוצר ישות חדשה ללא כפילויות עבור כל אחת ישויות המקור. ניתן למצוא ישויות אלה ביחד עם **ConflationMatchPairs:CustomerInsights** במקטע **מערכת** בדף **ישויות** בשם **Deduplication_DataSource_Entity**.

ישות של פלט ביטול כפילויות מכילה את המידע הבא:

- מזהים / מפתחות
  - שדות מפתח ראשי ומזהה חלופי. השדה 'מזהה חלופי' מורכב מכל המזהים החלופיים שזוהו עבור רשומה.
  - השדה Deduplication_GroupId מציג את הקבוצה או האשכול המזוהים בתוך ישות המקבצת את כל הרשומות הדומות בהתבסס על שדות ביטול הכפילויות שצוינו. הוא משמש למטרות עיבוד מערכת. אם לא צוינו כללי ביטול כפילויות ידניים וכללי ביטול כפילויות שהוגדרו על-ידי המערכת חלים, ייתכן שלא תמצא שדה זה בישות פלט ביטול הכפילויות.
  - Deduplication_WinnerId: שדה זה מכיל את המזהה המנצח מהקבוצות או האשכולות שזוהו. אם Deduplication_WinnerId זהה לערך המפתח הראשי עבור רשומה, המשמעות היא שהרשומה היא הרשומה המנצחת.
- שדות המשמשים להגדרה של כללי ביטול הכפילויות.
- השדות 'כלל' ו'ניקוד' כדי לציין אילו כללי ביטול כפילויות הוחלו והניקוד הוחזר על-ידי אלגוריתם ההתאמה.

[!INCLUDE[footer-include](includes/footer-banner.md)]