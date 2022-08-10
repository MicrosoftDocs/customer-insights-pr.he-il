---
title: קליטת נתונים בזמן אמת (תצוגה מקדימה)
description: מידע כללי על יכולות בזמן אמת ב- Customer Insights.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 403cc9dbd3bddcf67f59b5cb0be936af4d268fc2
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195659"
---
# <a name="real-time-data-ingestion-preview"></a>קליטת נתונים בזמן אמת (תצוגה מקדימה)

הפונקציונליות של כמעט בזמן אמת מאפשרת לך לראות, תוך שניות, את האינטראקציות האחרונות שביצעו הלקוחות שלך עם המוצרים או השירותים שלך.

הכרטיסיה [רענונים מתוזמנים](system.md#schedule-tab) כוללת מספר רב של רשומות וכמה פעולות מורכבות. ראשית, הנתונים נמשכים ממקור הנתונים. בשלב הבא, הנתונים מאוחדים ולאחר מכן מועשרים בעזרת מידע נוסף. כל הפעלה של תהליך זה עשויה לארוך דקות עד שעות.

הפונקציונליות בזמן אמת מספקת מיד נתונים לצריכה, עד שהרענון המתוזמן הבא ימשוך נתונים אלה ממקור הנתונים.

לעדכונים בזמן אמת יש זמן תפוגה שלאחריו הם כבר לא עוקפים את הערך ממקור הנתונים:

- עדכוני הפרופיל יישמרו למשך ארבע שעות
- פעילויות יישמרו למשך 30 יום

ערכים אלה הם פרמטרים של קרית API שניתן לשנות. הם שואפים להבטיח שנתוני המקור שלך יישארו מקור האמת שלך. אם ברצונך לכלול עדכונים בזמן אמת לזמן ארוך יותר, עליך להוסיף אותם למקור נתונים כדי שימשכו אותם במהלך הרענון המתוזמן הבא.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>עדכון בזמן אמת של שדות פרופיל של הלקוח המאוחד

פרופילים מעודכנים יופיעו בתצוגת כרטיס הלקוח, או בכל תצוגה חזותית אחרת, תוך שניות ספורות.

משום שפעולות בזמן אמת מתרחשות לאחר שאיחוד הנתונים התרחש, הן חלות רק על פרופילי הלקוחות המאוחדים. כתוצאה מכך, שינויים בפרופיל בזמן אמת לא יעדכנו מדדים, חברות בפלח או העשרות.

### <a name="limitations"></a>מגבלות

- ניתן לעדכן פרופילי לקוחות, אך לא ליצור או למחוק אותם.
- ייצוא עדכונים בזמן אמת למערכות חיצוניות, כגון Power BI, אינו אפשרי כרגע.

## <a name="real-time-creation-of-activities"></a>יצירת פעילויות בזמן אמת

ממשק ה- API בזמן אמת מאפשר לך לפרסם פעילות חדשה ממערכת המקור שלך (רשומת מקור בודדת) לפרופיל לקוח מאוחד. הפעילות החדשה תהיה זמינה כפעילות מאוחדת בציר הזמן של פרופיל הלקוח המאוחד תוך שניות. באפשרותך לראות את ציר הזמן בתצוגת כרטיס הלקוח או כל שילוב אחר של ציר הזמן שהגדרת.

> [!NOTE]
>
> - הפעילויות אינן ניתנות לשינוי. הן לא משתנות לאחר שנוצרו.
> - לעת עתה, פלחי שוק ומדדים לא יתעדכנו על סמך הפעילות החדשה.
> - פעילויות שנוספו רק דרך ממשק ה- API בזמן אמת אינן חלק מפעולות הייצוא ולא יופיעו ב- PowerBI.

ישנן שתי דרכים להתחבר לממשק ה- API בזמן אמת:

- [באופן עקיף](#connect-via-the-dynamics-365-customer-insights-connector), באמצעות מחבר [Dynamics 365 Customer Insights](/connectors/customerinsights/)
- [באופן ישיר](#connect-directly-to-the-real-time-api), עם קוד

שתי הדרכים חולקות את התנאים המוקדמים הבאים:

- סביבת Customer Insights
- פרופילי לקוחות מאוחדים
- פעילויות מוגדרות ומופעלות
- הרשאות משתתף או מנהל מערכת לאימות החשבון שלך

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>התחברות דרך מחבר Dynamics 365 Customer Insights

ה- API בזמן אמת יכול לקלוט נתונים מחבר Power Platform ייעודי, מחבר [Dynamics 365 Customer Insights](/connectors/customerinsights/), מבלי לכתוב ולפרוס קוד כלשהו.    
המחבר יכול לבצע את אותן פעולות בזמן אמת כמו ה- API. אתה זקוק לרישיון תקף עבור מחברים מתקדמים. לקבלת מידע נוסף, ראה [שאלות נפוצות בנוגע לרישוי Power Apps ו- Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps ו/או Power Automate](/connectors/)
- [יישומים לוגיים של Azure](/azure/connectors/apis-list)

לקבלת פרטים אודות יצירת זרימות, עיין ב[תיעוד Power Automate](/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>התחברות ישירות לממשק ה- API בזמן אמת

באפשרותך להשתמש ביכולות בזמן אמת על-ידי בניית ערוץ משלך וחיבור ישיר לממשק ה- API בזמן אמת.    
באפשרותך לפרסם פעילות בתבנית של מערכת המקור שלך או בתבנית UnifiedActivity. קבל את התבנית על-ידי ביצוע קריאת API ל- /api/instances/{instanceId}/manage/entities/UnifiedActivity.

ניתן למצוא פרטים על ממשק API זה, כולל פרמטרים ותגובות, במקטע **EntityData** ב[הפניה לממשקי API של Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). לקבלת מידע נוסף, עיין בנושא [עבודה עם ממשקי API של Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>הבן את השימוש שלך בזמן אמת באמצעות טלמטריה

קבל סקירה של היקף הבקשות לממשק ה- API בזמן אמת ומידע על בעיות שהמערכת עלולה להיתקל בהן. באפשרותך [לגשת למדידת השימוש בזמן אמת](system.md#api-usage-tab). 


[!INCLUDE [footer-include](includes/footer-banner.md)]
