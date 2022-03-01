---
title: העשרה באמצעות HERE Technologies להעשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668679"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>העשרת פרופילי לקוחות באמצעות HERE Technologies‏ (Preview)

HERE Technologies היא חברת פלטפורמת מיקום המספקת נתונים ושירותים הממוקדים במיקום. באמצעות שירותי העשרת הנתונים של HERE Technologies, תוכל לבנות הבנת מיקום מדויקת יותר של לקוחותיך בעזרת נורמליזציה של כתובות, חילוץ קו רוחב וקו אורך, ועוד.

## <a name="prerequisites"></a>דרישות מוקדמות

כדי לקבוע את תצורת ההעשרות של HERE Technologies, יש לעמוד בתנאים המוקדמים הבאים:

- יש לך מנוי פעיל ל- HERE Technologies. כדי לקבל מנוי, באפשרותך [להירשם כאן](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) או [ליצור קשר עם HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) ישירות. [קבל מידע נוסף אודות העשרת מיקום של HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- יש לך את מפתח ה- API של HERE Technologies.

- יש לך הרשאות [מנהל מערכת](permissions.md#administrator).

## <a name="configuration"></a>תצורה

1. עבור אל **נתונים** > **העשרה**.

1. בחר **העשר את הנתונים שלי** באריח HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![אריח HERE Technologies](media/HERE-tile.png "אריח HERE Technologies")

1. הזן **מפתח API של HERE Technologies** פעיל. סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**. 

1. אשר את שני ערכי הקלט על-ידי בחירת **התחבר ל- HERE**.

1. בחר **הוסף נתונים** ובחר אם ברצונך למפות שדות לכתובת הראשית ו/או המשנית. באפשרותך לציין מיפוי שדות עבור שתי הכתובות (לדוגמה, כתובת בבית וכתובת עסק) ולהעשיר את הפרופילים עבור שתי הכתובות בנפרד. בחר **הבא**.

1. הגדר באילו שדות מהפרופילים המאוחדים שלך יש להשתמש כדי לחפש נתוני מיקום מתאימים מ- HERE Technologies. השדות **רחוב 1** ו **מיקוד** נדרשים עבור הכתובת הראשית ו/או המשנית שנבחרה. עבור דיוק התאמות גבוה יותר, ניתן להוסיף שדות נוספים.

   > [!div class="mx-imgBorder"]
   > ![דף קביעת תצורה של העשרת HERE Technologies](media/enrichment-HERE-configuration.png "דף קביעת תצורה של העשרת HERE Technologies")

1. בחר **החל** להשלמת מיפוי השדה.

## <a name="enrichment-results"></a>תוצאות העשרה

כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות. ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab). זמן העיבוד יהיה תלוי בגודל נתוני הלקוחות שלך ובזמני התגובה של ה- API מ- HERE Technologies.

לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**. בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.

אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.

## <a name="next-steps"></a>השלבים הבאים

בנה על נתוני הלקוחות המועשרים שלך. צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.

## <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל HERE Technologies, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'. Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- HERE Technologies עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.
