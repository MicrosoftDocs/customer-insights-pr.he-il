---
title: העשרה באמצעות העשרת צד שלישי של HERE Technologies
description: מידע כללי אודות העשרה של צד שלישי באמצעות HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 1cbbad9bfe559bcb15b23894fc7475507aae8add
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376351"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>העשרת פרופילי לקוחות באמצעות HERE Technologies‏ (Preview)

HERE Technologies היא חברת פלטפורמת מיקום המספקת נתונים ושירותים הממוקדים במיקום. באמצעות שירותי העשרת הנתונים של HERE Technologies, תוכל לבנות הבנת מיקום מדויקת יותר של לקוחותיך בעזרת נורמליזציה של כתובות, חילוץ קו רוחב וקו אורך, ועוד.

## <a name="prerequisites"></a>דרישות מוקדמות

כדי לקבוע את תצורת ההעשרות של HERE Technologies, יש לעמוד בתנאים המוקדמים הבאים:

- יש לך מנוי פעיל ל- HERE Technologies. כדי לקבל מנוי, באפשרותך [להירשם כאן](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) או [ליצור קשר עם HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) ישירות. [קבל מידע נוסף אודות העשרת מיקום של HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- [חיבור](connections.md) HERE זמין *או* שיש לך הרשאות [מנהל מערכת](permissions.md#admin) ומפתח API של HERE Technologies.

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה**. 

1. בחר **העשר את הנתונים שלי** באריח HERE Technologies ובחר **תחילת העבודה**.

   > [!div class="mx-imgBorder"]
   > ![אריח HERE Technologies.](media/HERE-tile.png "אריח HERE Technologies")

1. בחר [חיבור](connections.md) מהרשימה הנפתחת. צור קשר עם מנהל מערכת אם אין חיבור זמין. אם אתה מנהל מערכת, באפשרותך ליצור חיבור על-ידי בחירת **הוסף חיבור**. בחר **HERE Technologies** מהרשימה הנפתחת. 

1. בחר **התחבר ל- HERE Technologies** כדי לאשר את הבחירה.

1.  בחר **הבא** ובחר את **ערכת הנתונים של הלקוח** שברצונך להעשיר בנתוני מיקום מתוך HERE Technologies. באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. בחר אם ברצונך למפות שדות לכתובת הראשית ו/או המשנית. באפשרותך לציין מיפוי שדה עבור שתי הכתובות ולהעשיר את הפרופילים עבור שתי הכתובות בנפרד. לדוגמא, אם יש כתובת בית וכתובת עסק. בחר **הבא**.

1. הגדר באילו שדות מהפרופילים המאוחדים שלך יש להשתמש כדי לחפש נתוני מיקום מתאימים מ- HERE Technologies. השדות **רחוב 1** ו **מיקוד** נדרשים עבור הכתובת הראשית ו/או המשנית שנבחרה. עבור דיוק התאמות גבוה יותר, ניתן להוסיף שדות נוספים.

   > [!div class="mx-imgBorder"]
   > ![דף קביעת תצורה של העשרת HERE Technologies.](media/enrichment-HERE-configuration.png "דף קביעת תצורה של העשרת HERE Technologies")

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. ספק שם עבור ההעשרה. 

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

## <a name="configure-the-connection-for-here-technologies"></a>הגדת את תצורת החיבור של HERE Technologies 

עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים. בחר **הוסף חיבור** בעת קביעת תצורת העשרה *או* עבור אל **ניהול** > **חיבורים** ובחר **הגדר** באריח HERE Technologies.

1. הזן שם עבור החיבור בתיבה **שם תצוגה**.

1. ספק מפתח API חוקי של HERE Technologies.

1. סקור את **פרטיות ותאימות נתונים** ותן את הסכמתך על-ידי בחירת **אני מסכים**.

1. בחר **אימות** כדי לאמת את התצורה.

1. לאחר השלמת האימות, בחר **שמור**.

   > [!div class="mx-imgBorder"]
   > ![דף תצורת החיבור של HERE Technologies.](media/enrichment-HERE-connection.png "דף תצורת החיבור של HERE Technologies")

## <a name="enrichment-results"></a>תוצאות העשרה

כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות. ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab). זמן העיבוד יהיה תלוי בגודל נתוני הלקוחות שלך ובזמני התגובה של ה- API מ- HERE Technologies.

לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**. בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.

אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.

## <a name="next-steps"></a>השלבים הבאים

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל HERE Technologies, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- HERE Technologies עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
