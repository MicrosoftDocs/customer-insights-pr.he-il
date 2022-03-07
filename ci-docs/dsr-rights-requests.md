---
title: בקשות של של זכויות נושא נתונים (DSR) במסגרת GDPR | Microsoft Docs
description: הגב לבקשות נושא נתונים עבור יכולת Audience Insights של Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350270"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>בקשות של של זכויות נושא נתונים (DSR) במסגרת GDPR

התקנה הכללית להגנה על נתונים של האיחוד האירופי (GDPR) הייתה בתוקף מאז 25 במאי 2018. היא מעניקה ליחידים זכויות משמעותיות לגבי הנתונים שלהם. תקנת ה- GDPR נועדו לאפשר זכויות פרטיות של יחידים ולהגן עליהן. תוכל לקרוא עוד על המחויבות של Microsoft לאבטחה ולתאימות באתר [מרכז יחסי האמון של Microsoft](https://www.microsoft.com/trust-center).

אנחנו מחויבים לעזור ללקוחותינו לעמוד בדרישות ה- GDPR שלהם. זה כולל את הזכות למחוק ולייצא נתונים הכוללים פרטים אישיים כגון מזהי משתמש, מספרי טלפון וכתובות דואר אלקטרוני. מנהלים יכולים ליישם בקשות של משתמשים למחיקה או ייצוא של נתונים אישיים.

## <a name="audience-insights"></a>תובנות לגבי קהלים

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>תגובה לבקשות מחיקת נושא נתוניםש ל GDPR עבור יכולת Audience Insights של Dynamics 365 Customer Insights

"הזכות למחוק מידע" על ידי הסרת נתונים אישיים מנתוני לקוחות של ארגון הינה הגנה מרכזית בתקנה הכללית להגנה על נתונים (GDPR). הסרת נתונים אישיים כוללת הסרת כל הנתונים האישיים והיומנים שנוצרו על ידי המערכת, למעט מידע ביומן ביקורת.

#### <a name="manage-data-subject-delete-requests"></a>נהל בקשות למחיקת נתונים

Audience Insights מציע את חוויות המוצר הבאות למחיקת נתונים אישיים עבור לקוח או משתמש ספציפיים:

- **נהל בקשות מחיקה של נתוני לקוחות**: נתוני לקוחות ב- Customer Insights מעובדים ממקורות נתונים מקוריים וחיצוניים ל- Customer Insights. יש לבצע את כל בקשות המחיקה של GDPR במקור הנתונים המקורי.
- **נהל בקשות מחיקה עבור נתוני משתמש Customer Insights**: הנתונים עבור משתמשים נוצרים על-ידי Customer Insights. יש לבצע את כל בקשות המחיקה של GDPR ב- Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>נהל בקשות למחיקת נתוני לקוחות

מנהל Customer Insights יכול לבצע את הצעדים הבאים להסרת נתוני לקוחות שנמחקו במקור הנתונים:

1. היכנס אל Dynamics 365 Customer Insights.
2. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**
3. עבור כל מקור נתונים ברשימה המכילה נתוני לקוחות שנמחקו:
   1. בחר (...) ולאחר מכן בחר **רענן**.
   2. בדוק את המצב של מקור הנתונים תחת **מצב**. סימן וי פירושו שהרענון בוצע בהצלחה. משולש אזהרה פירושו שמשהו השתבש. אם מוצג משולש אזהרה, צור קשר עם D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![טיפול בבקשות מחיקה של GDPR של נתוני לקוחות.](audience-insights/media/gdpr-data-sources.png "טיפול בבקשות מחיקה של GDPR של נתוני לקוחות")

##### <a name="manage-delete-requests-for-user-data"></a>ניהול בקשות מחיקה עבור נתוני משתמשים

מנהל מערכת של Customer Insights יכול לבצע את הצעדים הבאים למחיקת נתוני לקוחות ב- Customer Insights:

1. היכנס אל Dynamics 365 Customer Insights.
2. ב- audience insights, עבור אל **ניהול** > **הרשאות**.
3. בחר את תיבת הסימון עבור המשתמשים שברצונך למחוק.
4. בחר **הסר**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>תגובה לבקשות לייצוא נתוני GDPR

כחלק מהמחויבות שלנו לעבוד יחד אתך במסע שלך עם התקנה הכללית להגנה על נתונים (GDPR), פיתחנו תיעוד שיעזור לך להתכונן. תיעוד זה מתאר שלבים שניתן לבצע עוד היום כדי לתמוך בתאימות ל- GDPR בעת השימוש ב- Audience Insights.

#### <a name="manage-export-and-view-requests"></a>נהל ייצוא וצפה בבקשות

הזכות לניידות נתונים מאפשרת לאדם שאותו הנתונים מתארים לבקש עותק של הנתונים האישיים שלו בתבנית אלקטרונית ("תבנית מובנית, נפוצה, קריאה על-ידי מכונה ומאפשרת פעולה הדדית") שניתנת להעברה לבקר נתונים אחר.

##### <a name="export-customer-data-tenant-admin"></a>ייצוא נתוני לקוחות (מנהל דייר)

מנהל דייר יכול לבצע את השלבים הבאים לייצוא נתונים:

1. לשלוח דואר אלקטרוני אל D365CI@microsoft.com עם ציון כתובת הדואר האלקטרוני של הלקוח בבקשה. צוות Customer Insights ישלח דואר לכתובת הדואר הרשומה של מנהל הדייר, עם בקשה לאשר ייצוא נתונים.
2. יש לקבל את האישור לייצוא הנתונים עבור הלקוח המבוקש.
3. קבל את הנתונים המיוצאים באמצעות כתובת הדואר של מנהל הדייר.

##### <a name="export-user-data-tenant-admin"></a>ייצוא נתוני משתמשים (מנהל דייר)

1. שלח דואר אלקטרוני אל D365CI@microsoft.com עם ציון כתובת הדואר האלקטרוני של המשתמש בבקשה. צוות Customer Insights ישלח דואר לכתובת הדואר הרשומה של מנהל הדייר, עם בקשה לאשר ייצוא נתונים.
2. יש לקבל את האישור לייצוא הנתונים עבור המשתמש המבוקש.
3. קבל את הנתונים המיוצאים באמצעות כתובת הדואר של מנהל הדייר.

## <a name="consent-management-preview"></a>ניהול הסכמה (Preview)

יכולת ניהול ההסכמה אינה אוספת נתוני משתמשים ישירות. היא רק מייבאת ומעבדת נתוני הסכמה המתקבלים ממשתמשים ביישומים אחרים.

כדי להסיר נתוני הסכמה לגבי משתמשים ספציפיים, יש להסיר אותם במקורות הנתונים שנקלטו ליכולת ניהול ההסכמה. לאחר רענון מקור הנתונים, הנתונים שהוסרו יימחקו גם ממרכז ההסכמה. יישומים שמשתמשים בישות ההסכמה ימחקו גם נתונים שהוסרו מהמקור לאחר [רענון](audience-insights/system.md#refresh-processes). אנחנו ממליצים לרענן את מקורות הנתונים במהירות לאחר מענה לבקשת נושא הנתונים להסיר את נתוני המשתמש מכל התהליכים והיישומים האחרים.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]