---
title: השתמש בפרופילים מאוחדים ב- Dynamics 365 Marketing
description: למד כיצד לשלב פרופילים מאוחדים ופלחים ב- Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 99ec463299a24ea81cfe26bb785e36bdefdcd080
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9054433"
---
# <a name="use-unified-customer-profiles-in-dynamics-365-marketing"></a>השתמש ב- Unified Customer Profiles ב- Dynamics 365 Marketing

[Dynamics 365 Marketing](/dynamics365/marketing/overview) משפר את חוויות הלקוח ומאפשר לך לנהל מסעות מותאמים אישית בכל נקודות המגע כדי לחזק קשרים ולהרוויח נאמנות. האפליקציה Dynamics 365 Marketing פועלת בצורה חלקה עם Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams ומוצרים אחרים, ומאפשרת לך לקבל החלטות מהירות וטובות יותר באמצעות העוצמה של הנתונים וה- AI.

על-ידי חיבור נתוני Customer Insights אל Marketing, אפשר:

- לפלח פריטי unified customer profile ופלחים. פעולה זו מאפשרת לך ליצור מעורבות עם כל לקוח, ללא קשר למיקום של נתוני הלקוח.
- לבסס תוכן דינמי (כגון אסימונים מותאמים אישית) בהודעות דואר אלקטרוני, SMS והודעות דחיפה על מדידות כגון מצב מועדון לקוחות, תאריך חידוש מנוי, תיק לקוח אב או כל מדידה אחרת שלקדת בפרופיל Customer Insights.
- לטעון נתונים מ- Marketing אל Customer Insights ולשלב אותם עם נתוני לקוח ממקורות אחרים.
- להחיל כלים של Customer Insights לניקוי, להעשרה ולהתאמה לא מדויקת של נתונים.

## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>שימוש בפרופילי לקוח עשירים בשיווק בזמן אמת

שיווק בזמן אמת מאפשר לך ליצור [גורמים מפעילים מותאמים אישית](/dynamics365/marketing/real-time-marketing-custom-triggers) המפעילים מסעות לקוח בהתבסס על כל פעולת לקוח. ככל שהנתונים שלך יהיו מותאמים אישית יותר, כך המסעות שלך יהיו מותאמים אישית ורלוונטיים יותר. זה מה שהופך את השילוב של Marketing ו- Customer Insights לכל כך עוצמתי. ניתן [לאחד נתונים](data-unification.md) מכל מקור, ולאחר מכן להשתמש בהם כדי להמריץ מסעות לקוח ברמה גבוהה של התאמה אישית.

מידע נוסף: [שימוש בפרופילים ובפלחי שוק של Customer Insights בשיווק בזמן אמת](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>שימוש בפלחי שוק מאוחדים במסעות לקוח יוצאים

האפליקציה Customer Insights מאפשרת לך לזקק נתונים ממקורות רבים ולשלב אותם בפלחי לקוחות שנצברו. על-ידי [חיבור Customer Insights עם שיווק יוצא](export-dynamics365-marketing.md), פלחי שוק אלה יופיעו *וגם* יתרעננו באופן אוטומטי במעצב מסע הלקוח.

מידע נוסף: [שימוש בפלחים מ- Dynamics 365 Customer Insights עם Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>משיכת נתונים מ- Azure Data Lake Storage משלך

אתה לא מוגבל לאחסון בענן אם אתה רוצה להשתמש בנתוני Customer Insights עם Marketing. אם כבר הגדרת Azure Data Lake Storage משלך, באפשרותך להתחבר ל- Customer Insights ולאחר מכן לשתף את הנתונים עם האפליקציה Marketing בדיוק כפי שהיית עושה עם הגדרה מבוססת ענן.

מידע נוסף: [הפוך שיתוף נתונים באמצעות Dataverse לזמין מ- Azure Data Lake Storage משלך](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)
