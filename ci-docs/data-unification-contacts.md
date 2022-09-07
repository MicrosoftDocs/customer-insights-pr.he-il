---
title: יצירת פרופיל איש קשר מאוחד (Preview)
description: בצע את תהליך איחוד הנתונים כדי ליצור ערכת נתונים ראשית אחת אנשי קשר.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305028"
---
# <a name="create-a-unified-contact-profile-preview"></a>יצירת פרופיל איש קשר מאוחד (Preview)

לאחר [איחוד תיקי לקוח עסקיים](map-entities.md), באפשרותך לאחד את אנשי הקשר עבור תיקי לקוח אלה ולקשר את אנשי הקשר המאוחדים לתיקי הלקוח המאוחדים. תהליך איחוד אנשי הקשר ממפה נתוני אנשי קשר ממקורות נתונים מרובים, מסיר כפילויות, מתאים את הנתונים בין ישויות, מגדיר מיפוי סמנטי, יוצר קשרים בין אנשי קשר ותיקי לקוח, ולאחר מכן יוצר פרופיל איש קשר מאוחד.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

השלבים הראשונים זהים לשלבי איחוד תיקי לקוחות.

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

לרשומות תיק לקוח ואנשי קשר חייב להיות מפתח ייחודי (הנקרא מפתח זר) המחבר ביניהם. לדוגמה, מזהה תיק לקוח שקיים ברשומת תיק הלקוח וברשומת איש הקשר הקושרת את תיק הלקוח והאיש קשר.

## <a name="preview-limitations"></a>מגבלות של ה-Preview

- אנשי קשר ללא קישור תיק לקוח יוסרו.
- אם תיק לקוח משוכפל, מזוהה רשומה מנצחת בהתבסס על העדפות המיזוג. שיאי מפסידים אינם נבחרים ולכן הם נשמטים. אנשי קשר הקשורים לרשומות שאינן המנצחות יוסרו.
- תיק לקוח יכול להכיל מספר אנשי קשר, אך איש קשר מקושר לתיק לקוח יחיד.
- תכונות אנשי הקשר הממופות בשלב המיפוי הסמנטי הן התכונות היחידות שניתן להציג בכרטיס הלקוח. עם זאת, 17 תכונות זמינות.

## <a name="select-source-fields"></a>בחר שדות מקור

1. תחת **איחוד אנשי קשר (Preview)**, בחר **תחילת העבודה**.

1. [בחר את הישויות והשדות](map-entities.md) עבור מקורות הנתונים ליצירת קשר, כולל המפתחות הראשיים וסוגי התכונות.

1. בחר **הבא**.

## <a name="remove-duplicate-records"></a>הסר רשומות כפולות

1. באופן אופציונלי, [ניתן להגדיר כללי מניעת כפילות](remove-duplicates.md) עבור הישויות שבחרת.

1. בחר **הבא**.

## <a name="match-conditions"></a>התאם תנאים

1. [הגדר את סדר ההתאמה והכללים](match-entities.md) עבור התאמה בין ישויות.

1. בחר **הבא**.

## <a name="unify-contact-fields"></a>איחוד שדות אנשי קשר

1. [שילוב ואי הכללה של שדות אנשי קשר](merge-entities.md).

1. בחר **הבא**.

## <a name="define-the-semantic-fields-for-unified-contacts"></a>הגדרת השדות הסמנטיים עבור אנשי קשר מאוחדים

שלב זה בתהליך האיחוד ממפה את שדות אנשי הקשר המאוחדים שלך לסוגים סמנטיים. ב'מעסק לעסק', כרטיסי הלקוחות מציגים תיקי לקוח. כאשר הכרטיס נבחר, כל אנשי הקשר המשויכים לתיק לקוח יוצגו. השדות שתמפה בשלב זה הם השדות שיוצגו בכרטיסים.

1. בחר את הסוג הסמנטי שימופע לכל אחד מהשדות המאוחדים. בחר **אף אחד** אם סוג סמנטי אינו זמין.

   :::image type="content" source="media/semantic_mapping.png" alt-text="צילום מסך של דף שדות סמנטיים כדי להגדיר את הסוגים הסמנטיים." lightbox="media/semantic_mapping.png":::

1. לאחר מיפוי כל השדות המאוחדים, בחר **הבא**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>הגדרת קשר בין איש קשר לתיק לקוח

בשלב זה תהליך האיחוד מחבר את נתוני איש הקשר שלך לנתוני תיק הלקוח המתאים.

1. עבור כל ישות, יש להזין את המידע הבא:

   - **מפתח זר מיישות מסוג איש קשר**: בחר את התכונה המחברת את ישות איש הקשר שלך לתיק הלקוח.
   - **לישות תיק הלקוח**: בחר את ישות תיק הלקוח המשויכת לאיש הקשר.

   :::image type="content" source="media/contact_relationship.png" alt-text="צילום מסך של הדף 'קשרים' לחיבור בין ישויות איש קשר ותיק לקוח.":::

1. בחר **הבא**.

## <a name="review-contact-unification"></a>בדוק את איחוד איש הקשר

עיין בסיכום השינויים, צור את הפרופיל המאוחד ובדוק את התוצאות.

### <a name="review-and-create-contact-profiles"></a>סקירה ויצירה של פרופילי אנשי קשר

שלב אחרון זה בתהליך האיחוד מציג סיכום של השלבים בתהליך ומספק הזדמנות לבצע שינויים לפני שתיצור את הפרופיל איש הקשר המאוחד.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="צילום מסך של בדיקה ויצירת פרופילי איש קשר.":::

1. בחר **ערוך** בכל אחד משלבי איחוד אישר הקשר כדי לבדוק ולבצע שינויים כלשהם.

1. אם אתה מרוצה מהבחירות שלך, בחר **צור פרופילי איש קשר**. הדף **איחוד** מוצג בזמן יצירת פרופיל איש קשר מאוחד.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="צילום מסך של דף 'איחוד איש קשר' עם אריחים המציגים 'בתור' או 'מרענן'.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

לאלגוריתם האיחוד לוקח קצת זמן להשלים ולא ניתן לשנות את התצורה עד שהיא תושלם.

### <a name="view-the-results-of-contact-unification"></a>הצג את תוצאות איחוד איש הקשר

לאחר האיחוד, הדף **נתונים** > **איחוד‎** מציג את המספר של פרופילי אנשי קשר מאוחדים. התוצאות של כל שלב בתהליך האיחוד מוצגות בכל אריח. לדוגמה, **שדות מקור** מציג את מספר התכונות הממופות (שדות) והאפשרות **רשומות כפולות** מציגה את מספר הרשומות הכפולות שנמצאו.

:::image type="content" source="media/unified_contacts.png" alt-text="צילום מסך של הדף 'איחוד נתונים' לאחר איחוד אנשי קשר.":::

> [!TIP]
> האריח **תנאים תואמים** מוצג רק אם נבחרו ישויות מרובות.

אנו ממליצים לבדוק את התוצאות, במיוחד את האיכות של [חוקי ההתאמה](data-unification-update.md#manage-match-rules) ולהתאים אותם במידת הצורך.

במקרה הצורך, [בצע שינויים בהגדרות האיחוד של אנשי קשר](data-unification-update.md) והפעל מחדש את הפרופיל המאוחד.

### <a name="verify-output-entities-from-data-unification"></a>אמת ישויות פלט מאיחוד נתונים

עבור אל **נתונים** > **ישויות** כדי לאמת את ישויות הפלט.

הישות המאוחדת של פרופיל איש קשר, הנקראת *ContactProfile*, מוצגת במקטע **ישויות סמנטיות**. הפעלת האיחוד המוצלחת הראשונה יוצרת את הישות המאוחדת *ContactProfile*. כל ההפעלות הבאות מרחיבות את הישות הזו.

הישות *ContactsCustomer*‏ (Preview‏) נוצרת ומוצגת במקטע **פרופילים**. ישות זו מכילה את נתוני אנשי הקשר ללא הקישורים לתיקי לקוח. ישות זו משמשת כקלט בשלבי המיפוי הסמנטי והקשרים של איחוד אנשי קשר.

ישויות ביטול כפילויות וקונפלציה נוצרות ומוצגות במקטע **מערכת**. תהליך ביטול הכפילות עבור כל אחת ישויות המקור נוצרת יישות בשם **Deduplication_DataSource_Entity**. הישות **ContactsConflationMatchPairs** מכילה מידע על התאמות בין ישויות.

ישות של פלט ביטול כפילויות מכילה את המידע הבא:
- מזהים / מפתחות
  - שדות מפתח ראשי ומזהה חלופי. השדה 'מזהה חלופי' מורכב מכל המזהים החלופיים שזוהו עבור רשומה.
  - השדה Deduplication_GroupId מציג את הקבוצה או האשכול המזוהים בתוך ישות המקבצת את כל הרשומות הדומות בהתבסס על שדות ביטול הכפילויות שצוינו. הוא משמש למטרות עיבוד מערכת. אם לא צוינו כללי ביטול כפילויות ידניים וכללי ביטול כפילויות שהוגדרו על-ידי המערכת חלים, ייתכן שלא תמצא שדה זה בישות פלט ביטול הכפילויות.
  - Deduplication_WinnerId: שדה זה מכיל את המזהה המנצח מהקבוצות או האשכולות שזוהו. אם Deduplication_WinnerId זהה לערך המפתח הראשי עבור רשומה, המשמעות היא שהרשומה היא הרשומה המנצחת.
- שדות המשמשים להגדרה של כללי ביטול הכפילויות.
- השדות 'כלל' ו'ניקוד' כדי לציין אילו כללי ביטול כפילויות הוחלו והניקוד הוחזר על-ידי אלגוריתם ההתאמה.

## <a name="next-step"></a>השלב הבא

הגדר [פעילויות](activities.md), [העשרה](enrichment-hub.md), או [קשרים](relationships.md) לקבלת תובנות נוספות לגבי אנשי הקשר שלך.