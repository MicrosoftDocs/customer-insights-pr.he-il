---
title: ייצוא נתוני Customer Insights אל Adobe Campaign Standard
description: למד כיצד להשתמש ב- audience insights ב- Adobe Campaign Standard.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: a5d0154c3d7c473dcba03fac0847bafcf97de2f2
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596316"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>שימוש בפלחי Customer Insights ב- Adobe Campaign Standard (preview)‎

כמשתמש של Audience Insights עבור Dynamics 365 Customer Insights, ייתכן שיצרת פלחים כדי להפוך את הקמפיינים השיווקיים שלך ליעילים יותר על-ידי התמקדות בקהלים רלוונטיים. כדי להשתמש בפלח מ- Audience Insights ב- Adobe Experience Platform וביישומים כמו Adobe Campaign Standard, עליך לבצע מספר שלבים המתוארים במאמר זה.

:::image type="content" source="media/ACS-flow.png" alt-text="תרשים התהליך של השלבים המתוארים במאמר זה.":::

## <a name="prerequisites"></a>דרישות מוקדמות

-   רשיון Dynamics 365 Customer Insights
-   רישיון Adobe Campaign Standard
-   חשבון אחסון Blob של Azure

## <a name="campaign-overview"></a>מבט כולל על קמפיין

כדי להבין טוב יותר כיצד ניתן להשתמש בפלחים מתוך audience insights ב- Adobe Experience Platform, בוא נבחן קמפיין לדוגמה בדוי.

נניח שהחברה שלך מציעה שירות חודשי מבוסס מנוי ללקוחות שלך בארצות הברית. ברצונך לזהות לקוחות שהמנויים שלהם אמורים להתחדש בשמונת הימים הקרובים אך טרם חידשו את המנוי. כדי לשמור לקוחות אלה, ברצונך לשלוח להם הצעת קידום מכירות דרך הדואר, באמצעות Adobe Campaign Standard.

בדוגמה זו, אנחנו רוצים להפעיל את קמפיין הדואר לקידום מכירות פעם אחת. מאמר זה אינו מכסה את מקרה השימוש של הפעלת הקמפיין יותר מפעם אחת. עם זאת, ניתן להגדיר audience insights ו- Adobe Campaign Standard כך שיפעלו גם עבור תרחיש קמפיין חוזר.

## <a name="identify-your-target-audience"></a>זיהוי קהל היעד שלך

בתרחיש שלנו, אנחנו מניחים שכתובות הדואר של הלקוחות זמינות ב- audience insights ושהעדפות קידום המכירות שלהם נותחו כדי לזהות את החברים בפלח.

ה [פלח שהגדרת ב- audience insights](segments.md) נקרא **ChurnProneCustomers** ובכוונתך לשלוח ללקוחות אלה את קידום הדואר.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="צילום מסך של דף הפלחים שהפלח ChurnProneCustomers נוצר בו.":::

דואר ההצעה שברצונך לשלוח יכלול את השם הפרטי, שם המשפחה, ואת תאריך סיום המנוי של הלקוח. הוא מעדכן את הלקוחות לגבי ההנחה שהם יקבלו אם יחדשו את המנוי שלהם לפני שיסתיים.

## <a name="export-your-target-audience"></a>ייצוא קהל היעד שלך

לאחר שקהל היעד שלנו זוהה, נוכל להגדיר את הייצוא מ- audience insights לחשבון אחסון Blob של Azure.

1. ב- audience insights, עבור אל **ניהול** > **יעדי ייצוא**.

1. באריח **Adobe Campaign**, בחר **הגדר**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="אריח תצורה עבור Adobe Campaign Standard.":::

1. ספק **שם תצוגה** עבור יעד ייצוא חדש זה והזן את **שם החשבון**, **מפתח החשבון** ו **הגורם המכיל** של חשבון אחסון Blob של Azure שאליו ברצונך לייצא את הפלח.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="צילום מסך של תצורת חשבון האחסון. "::: 

   - כדי לקבל מידע נוסף אודות אופן מציאת שם החשבון ומפתח החשבון של אחסון Blob של Azure, ראה [ניהול הגדרות חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).

   - כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. בחר **הבא**.

1. בחר את הפלח שברצונך לייצא. בדוגמה זו, זהו **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="צילום מסך של ממשק המשתמש לבחירת פלח עם הפלח ChurnProneCustomers שנבחר בו.":::

1. בחר **הבא**.

1. כעת אנחנו ממפים את שדות **מקור** מפלח audience insights אל שמות השדה **יעד** בסכימת הפרופיל של Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="מיפוי שדות עבור מחבר Adobe Campaign Standard.":::

   אם ברצונך להוסיף תכונות נוספות, בחר **הוסף תכונה**. שם היעד יכול להיות שונה משם שדה המקור, כך שתוכל עדיין למפות את פלט הפלח מ- audience insights ל- Adobe Campaign Standard אם לשדות אין שם זהה בשתי המערכות.

   > [!NOTE]
   > כתובת דואר משמשת כשדה זהות, אך באפשרותך להשתמש בכל מזהה אחר מפרופיל הלקוח של audience insights כדי למפות נתונים ל- Adobe Campaign Standard.

1. בחר **שמור**.

לאחר שמירת יעד הייצוא, תמצא אותו ב **ניהול** > **פעולות ייצוא** > **יעדי הייצוא שלי**.

:::image type="content" source="media/export-destination-adobe-campaign-standard.png" alt-text="צילום מסך עם רשימת פעולות ייצוא ופלח לדוגמה מודגשים.":::

כעת באפשרותך [לייצא את הפלח לפי דרישה](export-destinations.md#export-data-on-demand). הייצוא יפעל גם בכל [רענון מתוזמן](system.md).

> [!NOTE]
> ודא שמספר הרשומות בפלח המיוצא לא חורג ממגבלה המותרת של רישיון Adobe Campaign Standard.

הנתונים המיוצאים מאוחסנים בגורם המכיל של אחסון Blob של Azure שהגדרת לעיל. נתיב התיקיה הבא נוצר אוטומטית בגורם המכיל שלך:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>קביעת התצורה של Adobe Campaign Standard

כאשר פלח מ-audience insights מיוצא, הוא כולל את העמודות שבחרת בעת הגדרת יעד הייצוא בשלב הקודם. ניתן להשתמש בנתונים אלה כדי [ליצור פרופילים ב- Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

כדי להשתמש בפלח ב- Adobe Campaign Standard, עלינו להרחיב את סכימת הפרופיל ב- Adobe Campaign Standard כך שתכלול שני שדות נוספים. למד כיצד [להרחיב את משאב הפרופיל](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) עם שדות חדשים ב- Adobe Campaign Standard.

בדוגמה שלנו, שדות אלה הם *שם פלח ותאריך פלח (אופציונלי).*

אנחנו נשתמש בשדות אלה כדי לזהות את הפרופילים ב- Adobe Campaign Standard שאנחנו רוצים להתמקד בהם עבור קמפיין זה.

אם אין רשומות אחרות ב- Adobe Campaign Standard, מלבד מה שבכוונתך לייבא, תוכל לדלג על שלב זה.

## <a name="import-data-into-adobe-campaign-standard"></a>ייבוא נתונים אל Adobe Campaign Standard

עכשיו כשהכל מוכן, עלינו לייבא את נתוני קהל המוכנים מ- audience insights אל Adobe Campaign Standard כדי ליצור פרופילים. למד [כיצד לייבא פרופילים ב- Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) באמצעות זרימת עבודה.

זרימת העבודה של הייבוא בתמונה למטה הוגדרה לפעול כל 8 שעות ומחפשת פלחי audience insights שיוצאו (קובץ ‎.csv באחסון Blob של Azure). זרימת העבודה מחלצת את תוכן קובץ ה- ‎.csv בסדר עמודות שצוין. זרימת עבודה זו נבנתה על מנת לבצע טיפול בסיסי בשגיאות ולהבטיח שלכל רשומה יש כתובת דואר לפני שילוב הנתונים ב- Adobe Campaign Standard. זרימת העבודה גם מחלצת את שם הפלח משם הקובץ לפני העלאתו לנתוני פרופיל ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="צילום מסך של זרימת עבודה לייבוא בממשק המשתמש של Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>אחזור הקהל ב- Adobe Campaign Standard

לאחר ייבוא הנתונים ל- Adobe Campaign Standard, [באפשרותך ליצור זרימת עבודה](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) ו [לבצע שאילתה](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) של הלקוחות בהתבסס על *שם פלח* ו *תאריך הפלח* כדי לבחור פרופילים שזוהו עבור הקמפיין לדוגמה שלנו.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>יצירה ושליחה של הדואר באמצעות Adobe Campaign Standard

צור את תוכן הדואר ולאחר מכן [בדוק ושלח](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) את הדואר שלך.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="דואר לדוגמה עם הצעת חידוש של Adobe Campaign Standard.":::