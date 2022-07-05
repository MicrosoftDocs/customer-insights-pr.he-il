---
title: יצוא פלחי Customer Insights אל Adobe Campaign Standard‏(Preview‏)
description: למד כיצד להשתמש ב- Customer Insights בפלחים ב- Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 9915591cd969bf825f5d1669de43ed4f9953f898
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081347"
---
# <a name="export-customer-insights-segments-to-adobe-campaign-standard-preview"></a>יצוא פלחי Customer Insights אל Adobe Campaign Standard‏(Preview‏)

בתור משתמש Dynamics 365 Customer Insights, ייתכן שיצרת פלחים כדי להפוך את הקמפיינים השיווקיים שלך ליעילים יותר על ידי כיוון לקהלים רלוונטיים. כדי להשתמש בפלח מתוך Customer Insights ב- Adobe Experience Platform באפליקציות כמו Adobe Campaign Standard, עליך לבצע מספר שלבים המתוארים במאמר זה.

:::image type="content" source="media/ACS-flow.png" alt-text="תרשים התהליך של השלבים המתוארים במאמר זה.":::

## <a name="prerequisites"></a>דרישות מוקדמות

- רשיון Dynamics 365 Customer Insights
- רישיון Adobe Campaign Standard
- חשבון אחסון Blob של Azure

## <a name="campaign-overview"></a>מבט כולל על קמפיין

כדי להבין טוב יותר כיצד ניתן להשתמש בפלחים מתוך Customer Insights ב- Adobe Experience Platform, בואו נסתכל על קמפיין פיקטיבי לדוגמה.

נניח שהחברה שלך מציעה שירות חודשי מבוסס מנוי ללקוחות שלך בארצות הברית. ברצונך לזהות לקוחות שהמנויים שלהם אמורים להתחדש בשמונת הימים הקרובים אך טרם חידשו את המנוי. כדי לשמור על לקוחות אלה, תרצה לשלוח להם מבצע קידום מכירות דרך דוא"ל, באמצעות  Adobe Campaign Standard.

בדוגמה זו, אנחנו רוצים להפעיל את קמפיין הדואר לקידום מכירות פעם אחת. מאמר זה אינו מכסה את מקרה השימוש של הפעלת הקמפיין יותר מפעם אחת. עם זאת, ניתן להגדיר את התצורה של Customer Insights ו-Adobe Campaign Standard כך שיפעלו  גם בתרחיש של קמפיין שחוזר על עצמו.

## <a name="identify-your-target-audience"></a>זיהוי קהל היעד שלך

בתרחיש שלנו, אנו מניחים שכתובות האימייל של הלקוחות זמינות והעדפות הקידום שלהם נותחו כדי לזהות חברים בפלח.

[הפלח שהגדרת ב- Customer Insights](segments.md) נקרא **ChurnProneCustomers** ואתה מתכנן לשלוח ללקוחות אלה את קידום המכירות בדואר אלקטרוני.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="צילום מסך של דף הפלחים שהפלח ChurnProneCustomers נוצר בו.":::

דואר ההצעה שברצונך לשלוח יכלול את השם הפרטי, שם המשפחה, ואת תאריך סיום המנוי של הלקוח. הוא מעדכן את הלקוחות לגבי ההנחה שהם יקבלו אם יחדשו את המנוי שלהם לפני שיסתיים.

## <a name="export-your-target-audience"></a>ייצוא קהל היעד שלך

### <a name="configure-a-connection"></a>קביעת תצורה של חיבור

עם זיהוי היעד קהל שלנו, אנו יכולים להגדיר את הייצוא לחשבון Azure Blob Storage.

1. ב- Customer Insights, עבור אל **מנהל מערכת** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Adobe Campaign** כדי לקבוע את תצורת החיבור או בחר **הגדר** באריח **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="אריח תצורה עבור Adobe Campaign Standard.":::

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. הזן את **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** של חשבון אחסון Blob של Azure שלך שאליו ברצונך לייצא את הפלח.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="צילום מסך של תצורת חשבון האחסון. "::: 

   - כדי לקבל מידע נוסף אודות אופן מציאת שם החשבון ומפתח החשבון של Azure Blob Storage, ראה [ניהול הגדרות חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).

   - כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. בחר **שמור** כדי להשלים את החיבור.

### <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מהמקטע Adobe Campaign section. אם אינך רואה את שם הפלח הזה, אין קשרים זמינים עבורך מסוג זה.

1. בחר את הפלח שברצונך לייצא. בדוגמה זו, זהו **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="צילום מסך של ממשק המשתמש לבחירת פלח עם הפלח ChurnProneCustomers שנבחר בו.":::

1. בחר **הבא**.

1. כעת אנו ממפים את השדות **מקור** מהמקטע Customer Insights שמות של שדות ה **יעד** סכמת הפרופיל של  Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="מיפוי שדות עבור מחבר Adobe Campaign Standard.":::

   אם ברצונך להוסיף תכונות נוספות, בחר **הוסף תכונה**. שם היעד יכול להיות שונה משם שדה המקור, כך שעדיין תוכל למפות פלט של פלחים מ- Customer Insights אל Adobe Campaign Standard אם לשדות אין שם זהה בשתי המערכות.

   > [!NOTE]
   > כתובת דואר אלקטרוני משמשת כשדv זהות, אך ניתן להשתמש בכל מזהה אחר מפרופיל הלקוח כדי למפות נתונים אל Adobe Campaign Standard.

1. בחר **Save**.

לאחר שמירת יעד הייצוא, תמצא אותו תחת **נתונים** > **פעולות ייצוא**.

כעת באפשרותך [לייצא את הפלח לפי דרישה](export-destinations.md#run-exports-on-demand). הייצוא יפעל גם בכל [רענון מתוזמן](system.md).

> [!NOTE]
> ודא שמספר הרשומות בפלח המיוצא נמצאים במגבלת הרישיון שלך ל- Adobe Campaign Standard license.

הנתונים המיוצאים מאוחסנים בגורם המכיל של Azure Blob Storage שהגדרת לעיל. נתיב התיקיה הבא נוצר אוטומטית בגורם המכיל שלך:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>הגדר Adobe Campaign Standard

פלחים מיוצאים מכילים את העמודות שבחרת בעת הגדרת יעד הייצוא בשלב הקודם. ניתן להשתמש בנתונים אלה בכדי [ליצור פרופילים ב-Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

כדי להשתמש בפל ב-Adobe Campaign Standard, עלינו להרחיב את סכמת הפרופיל ב-Adobe Campaign Standardשתכלול שני שדות נוספים. למד איך[להרחיב את משאב הפרופיל](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) עם שדות חדשים ב-Adobe Campaign Standard.

בדוגמה שלנו, שדות אלה הם *שם פלח ותאריך פלח (אופציונלי)*.

נשתמש בשדות אלה כדי לזהות את הפרופילים ב- Adobe Campaign Standard שאותם אנו רוצים למקד לקמפיין זה.

אם אין רשומות אחרות ב-Adobe Campaign Standard, מלבד מה שאתה עומד לייבא, תוכל לדלג על צעד זה.

## <a name="import-data-into-adobe-campaign-standard"></a>ייבא נתונים אל Adobe Campaign Standard

כעת כשהכל במקום, עלינו לייבא את נתוני קהל המוכנים מ- Customer Insights לתוך Adobe Campaign Standard ליצירת פרופילים. תלמד [כיצד לייבא פרופילים ב- Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) באמצעות תזרים עבודה.

זרימת העבודה של הייבוא בתמונה למטה הוגדרה לפעול כל שמונה שעות ולחפש מקטעי Customer Insights מיוצאים (קובץ ‏csv. ב- Azure Blob Storage). זרימת העבודה מחלצת את תוכן קובץ ה- ‎.csv בסדר עמודות שצוין. תזרים עבודה זה נבנה בכדי לבצע טיפול בסיסי בשגיאות ולוודא שלכל רשומה יש כתובת דוא"ל לפני ייבוש הנתונים ב-Adobe Campaign Standard. תזרים העבודה גם מחלץ את שם הפלח משם הקובץ לפני ביצוע Upsert לנתוני פרופיל Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="צילום מסך של תזרים עבודה של יבוא ממשק משתמש ב-Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>אחזר את הקהל ב-Adobe Campaign Standard

לאחר ייבוא הנתונים ל-Adobe Campaign Standard, אתה [יכול ליצור תזרים עבודה](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) וגם [לשאול](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) את הלקוחות על בסיס *שם הפלח* ו-*תאריך פילוח* כדי לבחור פרופילים שזוהו הקמפיין לדוגמה שלנו.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>צור ושלח את הדוא"ל באמצעות Adobe Campaign Standard

צור את תוכן הדואר ולאחר מכן [בדוק ושלח](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) את הדואר שלך.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="דוגמא לדואר אלקטרוני עם הצעת חידוש מאת Adobe Campaign Standard.":::
