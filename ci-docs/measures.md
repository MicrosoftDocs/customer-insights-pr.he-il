---
title: מבט כולל על מדדים
description: למד כיצד מדדים עוזרים לנתח ולשקף את הביצועים של העסק שלך.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245374"
---
# <a name="measures-overview"></a>מבט כולל על מדדים

מדדים עוזרים לך להבין טוב יותר התנהגויות של לקוחות וביצועים עסקיים. הם בוחנים ערכים רלוונטיים מ[פרופילים מאוחדים](data-unification.md). לדוגמה, עסק רוצה לראות את *סך ההוצאות עבור לקוח* כדי להבין את היסטוריית הרכישה של לקוח בודד או למדוד את *סך המכירות של החברה* כדי להבין את ההכנסות המצטברות בכל העסק.

צור מדדים כדי לתכנן פעילויות עסקיות על-ידי ביצוע שאילתות על נתוני הלקוח וחילוץ תובנות. לדוגמה, צור מדד של *הוצאות כוללות ללקוח* ו *החזרה כוללת ללקוח* כדי לעזור לזהות קבוצת לקוחות בעלי הוצאות גבוהות אבל החזרה גבוהה. לאחר מכן, [צור מקטע](segments.md) בהתבסס על מדדים אלה כדי להניע את הפעולות הבאות הטובות ביותר.

## <a name="create-a-measure"></a>יצירת מדד

בחר כיצד ליצור מדד בהתאם לקהל היעד שלך.

# <a name="individual-consumers-b-to-c"></a>[צרכנים בודדים (B-to-C)](#tab/b2c)

- מההתחלה בעזרת בונה המדדים: [בנה מדד שלך](measure-builder.md).
- ממדדים שנמצאים בשימוש תכוף: [השתמש בתניות מוגדרות מראש](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[תיקי לקוחות עסקיים (B-to-B)](#tab/b2b)

מההתחלה בעזרת בונה המדדים: [בנה מדד שלך](measure-builder.md).

---

## <a name="manage-existing-measures"></a>ניהול מדדים קיימים

עבור אל הדף **מדדים** כדי להציג את המדדים שיצרת, את המצב שלהם, את סוג המדד ואת הפעם האחרונה שבה הנתונים רועננו. אתה יכול למיין את רשימת המדדים לפי כל עמודה או להשתמש בתיבת החיפוש כדי למצוא את המדד שברצונך לנהל.

בחר ליד המדד כדי להציג פעולות זמינות. בחר שם מדד כדי להציג תצוגה מקדימה של הפלט ולהוריד קובץ CSV.

:::image type="content" source="media/measures-actions.png" alt-text="פעולות לניהול מדידות יחידות."lightbox="media/measures-actions.png":::

- **ערוך** את המדד כדי לשנות את המאפיינים שלו.
- **רענן** את המדד כדי לכלול את הנתונים העדכניים ביותר.
- **שנה שם** של המדד.
- **הפעל** או **השבת** את המדד. לא יתבצע רענון למדדים לא פעילים במהלך [רענון מתוזמן](schedule-refresh.md) וה **מצב** שלהם הוא **המערכת דילגה** מה שמצביע על כך שלא היה אפילו ניסיון לבצע רענון.
- **תג** ל[ניהול תגים](work-with-tags-columns.md#manage-tags) עבור המדד.
- **מחק** את המדד.
- **עמודות** ל[התאמה אישית של העמודות](work-with-tags-columns.md#customize-columns) בתצוגה הזו.
- **מסנן** ל[סינון לפי תגים](work-with-tags-columns.md#filter-on-tags).
- **חפש שם** כדי לחפש לפי שם המדד.

## <a name="refresh-measures"></a>רענן מדדים

ניתן לרענן את המדדים בלוח זמנים אוטומטי או לרענן אותם באופן ידני לפי דרישה. כדי לרענן באופן ידני מדד אחד או יותר, בחר אותם ובחר **רענן**. כדי [לתזמן רענון אוטומטי](schedule-refresh.md), עבור אל **מנהל מערכת** > **מערכת** > **לוח זמנים**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
