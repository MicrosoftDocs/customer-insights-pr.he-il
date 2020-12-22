---
title: בקשות של של זכויות נושא נתונים (DSR) במסגרת GDPR | Microsoft Docs
description: הגב לבקשות נושא נתונים עבור יכולת Audience Insights של Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f276a73feca52023391ad92fbc84359921b85328
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405895"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>בקשות של של זכויות נושא נתונים (DSR) במסגרת GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>תגובה לבקשות מחיקת נושא נתוניםש ל GDPR עבור יכולת Audience Insights של Dynamics 365 Customer Insights

"הזכות למחוק מידע" על ידי הסרת נתונים אישיים מנתוני לקוחות של ארגון הינה הגנה מרכזית בתקנה הכללית להגנה על נתונים (GDPR). הסרת נתונים אישיים כוללת הסרת כל הנתונים האישיים והיומנים שנוצרו על ידי המערכת, למעט מידע ביומן ביקורת.

### <a name="manage-data-subject-delete-requests"></a>נהל בקשות למחיקת נתונים

Audience Insights מציע את חוויות המוצר הבאות למחיקת נתונים אישיים עבור לקוח או משתמש ספציפיים:

- **נהל בקשות מחיקה של נתוני לקוחות**: נתוני לקוחות ב- Customer Insights מעובדים ממקורות נתונים מקוריים וחיצוניים ל- Customer Insights. יש לבצע את כל בקשות המחיקה של GDPR במקור הנתונים המקורי.
- **נהל בקשות מחיקה עבור נתוני משתמש Customer Insights**: הנתונים עבור משתמשים נוצרים על-ידי Customer Insights. יש לבצע את כל בקשות המחיקה של GDPR ב- Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>נהל בקשות מחיקה של נתוני לקוחות

מנהל Customer Insights יכול לבצע את הצעדים הבאים להסרת נתוני לקוחות שנמחקו במקור הנתונים:

1. היכנס אל Dynamics 365 Customer Insights.
2. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**
3. עבור כל מקור נתונים ברשימה המכילה נתוני לקוחות שנמחקו:
   1. בחר (...) ולאחר מכן בחר **רענן**.
   2. בדוק את המצב של מקור הנתונים תחת **מצב**. סימן וי פירושו שהרענון בוצע בהצלחה. משולש אזהרה פירושו שמשהו השתבש. אם מוצג משולש אזהרה, צור קשר עם D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![טיפול בבקשות מחיקה של GDPR של נתוני לקוחות](media/gdpr-data-sources.png "טיפול בבקשות מחיקה של GDPR של נתוני לקוחות")

#### <a name="manage-delete-requests-for-user-data"></a>ניהול בקשות מחיקה עבור נתוני משתמשים

מנהל מערכת של Customer Insights יכול לבצע את הצעדים הבאים למחיקת נתוני לקוחות ב- Customer Insights:

1. היכנס אל Dynamics 365 Customer Insights.
2. ב- audience insights, עבור אל **ניהול** > **הרשאות**.
3. בחר את תיבת הסימון עבור המשתמשים שברצונך למחוק.
4. בחר **הסר**.

> [!div class="mx-imgBorder"]
> ![טיפול בבקשות מחיקה של GDPR עבור נתוני משתמשים](media/gdpr-permissions.png "טיפול בבקשות מחיקה של GDPR עבור נתוני משתמשים")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>תגובה לבקשות לייצוא נתוני GDPR

כחלק מהמחויבות שלנו לעבוד יחד אתך במסע שלך עם התקנה הכללית להגנה על נתונים (GDPR), פיתחנו תיעוד שיעזור לך להתכונן. תיעוד זה מתאר שלבים שניתן לבצע עוד היום כדי לתמוך בתאימות ל- GDPR בעת השימוש ב- Audience Insights.

### <a name="manage-export-and-view-requests"></a>נהל ייצוא וצפה בבקשות

הזכות לניידות נתונים מאפשרת לאדם שאותו הנתונים מתארים לבקש עותק של הנתונים האישיים שלו בתבנית אלקטרונית ("תבנית מובנית, נפוצה, קריאה על-ידי מכונה ומאפשרת פעולה הדדית") שניתנת להעברה לבקר נתונים אחר.

#### <a name="export-customer-data-tenant-admin"></a>ייצוא נתוני לקוחות (מנהל דייר)

מנהל דייר יכול לבצע את השלבים הבאים לייצוא נתונים:

1. לשלוח דואר אלקטרוני אל D365CI@microsoft.com עם ציון כתובת הדואר האלקטרוני של הלקוח בבקשה. צוות Customer Insights ישלח דואר לכתובת הדואר הרשומה של מנהל הדייר, עם בקשה לאשר ייצוא נתונים.
2. יש לקבל את האישור לייצוא הנתונים עבור הלקוח המבוקש.
3. קבל את הנתונים המיוצאים באמצעות כתובת הדואר של מנהל הדייר.

#### <a name="export-user-data-tenant-admin"></a>ייצוא נתוני משתמשים (מנהל דייר)

1. שלח דואר אלקטרוני אל D365CI@microsoft.com עם ציון כתובת הדואר האלקטרוני של המשתמש בבקשה. צוות Customer Insights ישלח דואר לכתובת הדואר הרשומה של מנהל הדייר, עם בקשה לאשר ייצוא נתונים.
2. יש לקבל את האישור לייצוא הנתונים עבור המשתמש המבוקש.
3. קבל את הנתונים המיוצאים באמצעות כתובת הדואר של מנהל הדייר.
