---
title: ייצוא נתוני Customer Insights אל AdRoll
description: למד כיצד לקבוע את תצורת החיבור אל AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697075"
---
# <a name="connector-for-adroll-preview"></a>מחבר עבור AdRoll‏ (Preview)

יצא פלחים של פרופילי לקוח מאוחדים אל AdRoll והשתמש בהם עבור פרסום. 

## <a name="prerequisites"></a>דרישות מוקדמות

-   יש לך [חשבון AdRoll](https://www.adroll.com/) ואישורי מנהל מערכת מתאימים.
-   יש לך [פלחים מוגדרים](segments.md) ב- Audience Insights.
-   פרופילי לקוחות מאוחדים בפלחים המיוצאים מכילים שדה המייצג כתובת דוא"ל.

## <a name="connect-to-adroll"></a>התחבר ל- AdRoll

1. עבור אל **מנהל** > **יעדי ייצוא**.

1. תחת **AdRoll**, בחר **הגדר**.

1. תן ליעד הייצוא שלך שם הניתן לזיהוי בשדה **שם תצוגה**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="חלונית תצורה עבור חיבור AdRoll.":::

1. בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.

1. בחר **התחבר** כדי לאתחל את החיבור אל AdRoll.

1. בחר **בצע אימות באמצעות AdRoll** וספק את אישורי מנהל המערכת שלך עבור AdRoll. 

1. בחר **הוסף את עצמך כמשתמש ייצוא** וספק את אישורי Customer Insights שלך.

1. הזן את **מזהה מפרסם AdRoll** [פריט ניתן לפרסום של AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. בחר **הבא** להגדרת התצורה של הייצוא.

## <a name="configure-the-connector"></a>קביעת תצורת המחבר

1. במקטע **התאמת נתונים**, בשדה **דואר אלקטרוני**, בחר את השדה בפרופיל הלקוח המאוחד שלך המייצג את כתובת הדוא"ל של לקוח. ייצוא פלחים אל AdRoll הוא הכרחי.

1. בחר את הפלחים שברצונך לייצא. בחר פלח עם 100 חברים לפחות. אין באפשרותך לייצא פלחים קטנים יותר. בנוסף, הגודל המרבי של פלח לייצוא הוא 250,000 חברים לייצוא. 

1. בחר **שמור**.

## <a name="export-the-data"></a>ייצוא הנתונים

באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md). הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).

## <a name="known-limitations"></a>מגבלות ידועות

- באפשרותך לייצא עד 250,000 פרופילים לייצוא אל AdRoll.
- אין באפשרותך לייצא פלחים עם פחות מ- 100 פרופילים ל- AdRoll. 
- הייצוא ל- AdRoll מוגבל לפלחים.
- ייצוא של עד 250,000 פרופילים ל- AdRoll יכול להימשך עד 10 דקות. 
- מספר הפרופילים שתוכל לייצא ל- AdRoll תלוי ומוגבל בחוזה שלך עם AdRoll.

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל AdRoll, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- AdRoll עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
