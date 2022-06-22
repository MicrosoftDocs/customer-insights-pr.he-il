---
title: העשרה באמצעות Experian העשרה של צד שלישי
description: מידע כללי על העשרת צד שלישי של Experian.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 735da18e584b0d9db76b557f4d16dbdf1757f33c
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954088"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>העשר פרופילי לקוחות באמצעות נתונים דמוגרפיים מ- Experian ‏(Preview)

Experian הינה מובילה עולמית בתחום שירותי דיווח ושיווק של אשראי צרכני ועסקי. באמצעות שירותי העשרת הנתונים של Experian, תוכל לבנות הבנה עמוקה יותר של הלקוחות שלך על-ידי העשרת פרופילי הלקוחות בנתונים דמוגרפיים כמו גודל משק בית, הכנסה ועוד.

## <a name="supported-countriesregions"></a>מדינות/אזורים נתמכים

נכון לעכשיו אנחנו תומכים בהעשרת פרופילי לקוחות בארצות הברית בלבד.

## <a name="prerequisites"></a>דרישות מוקדמות

- מנוי Experian פעיל. כדי לקבל מינוי, [פנה ישירות ל- Experian](https://www.experian.com/marketing-services/contact). [קבל מידע נוסף על Experian העשרת נתונים](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- תצורת [החיבור](connections.md) של Experian [מוגדרת](#configure-the-connection-for-experian) על ידי מנהל מערכת.

- מזהה משתמש Experian, מזהה צד ומספר דגם עבור חשבון תחבורה מאובטחת (ST) שלך התומך ב-SSH שנוצר עבורך על ידי Experian.

## <a name="configure-the-connection-for-experian"></a>קבע את תצורת החיבור של Experian

עליך להיות [מנהל מערכת](permissions.md#admin) ב- Customer Insights ולהיות בעל מזהה לקוח Experian, מזהה צד ומספר מודל.

1. בחר **הוסף חיבור** בעת הגדרת העשרה או עבור אל **מנהל מערכת** > **חיבורים** ובחר **הגדר** באריח Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Experian חלונית תצורת החיבור.":::

1. הזן שם לחיבור ומזהה משתמש תקין, מזהה צד ומספר מודל עבור חשבון תחבורה מאובטח שלך ב- Experian.

1. סקור את [פרטיות ותאימות נתונים](#data-privacy-and-compliance) ותן את הסכמתך על-ידי בחירת **אני מסכים**.

1. בחר **אמת** כדי לאמת את התצורה ולאחר מכן בחר **שמור**.

### <a name="data-privacy-and-compliance"></a>פרטיות ותאימות של נתונים

כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים ל- Experian, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעלולים להיות רגישים, כגון נתונים אישיים. Microsoft תעביר נתונים כאלה בהוראתך, אבל אתה אחראי להבטיח ש- Experian עומדת בכל התחייבויות הפרטיות והאבטחה שלך. לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.

## <a name="configure-the-enrichment"></a>קביעת תצורת ההעשרה

1. עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.

1. בחר **העשר את הנתונים שלי** ב **נתונים דמוגרפיים** מהאריח של Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="האריח Experian בדף 'מבט כולל על העשרה'."::: 

1. בדוק את הסקירה הכללית ולאחר מכן בחר **הבא**.

1. בחר את החיבור. פנה אל מנהל מערכת אם אחד לא זמין.

1. בחר **הבא**.

1. בחר את **ערכת הנתונים של הלקוח** ובחר בפרופיל או בפלח שברצונך להעשיר בנתונים דמוגרפיים מ- Experian. הישות *לקוח* מעשיר את כל פרופילי הלקוחות שלך בעוד שפלח מעשיר רק פרופילי לקוחות הנכללים באותו פלח.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. קבע באילו סוגי שדות מהפרופילים המאוחדים יש להשתמש עבור נתונים דמוגרפיים תואמים מ- Experian. לפחות אחד מהשדות **שם וכתובת**, **טלפון** או **דואר** נדרש. לדיוק התאמה גבוה יותר, הוסף שדות נוספים. בחר **הבא**.

1. מפה את השדות שלך לנתונים הדמוגרפיים מ- Experian.

1. בחר **הבא** כדי להשלים את מיפוי השדה.

1. ספק **שם** עבור ההעשרה ועבור **שם ישות הפלט**.

1. בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.

1. בחר **הפעל** כדי להתחיל את תהליך ההעשרה או לסגור כדי לחזור אל דף **העשרה**.

## <a name="enrichment-results"></a>תוצאות העשרה

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

הנתון **מספר לקוחות מועשרים לפי שדה** מספק הסבר מפורט על הכיסוי של כל שדה מועשר.

## <a name="next-steps"></a>‏‫השלבים הבאים‬

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
