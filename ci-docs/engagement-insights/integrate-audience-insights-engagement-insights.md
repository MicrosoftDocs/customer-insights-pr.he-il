---
title: צור קישור בין תובנות קהל לבין תובנות מעורבות
description: צור קישור פעיל בין תובנות קהל לתובנות מעורבות כדי לאפשר שיתוף נתונים דו-כיווני.
ms.date: 07/22/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 870209a7e19fec464ec41462a02365771bd653bd
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461014"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>צור קישור בין תובנות קהל לבין תובנות מעורבות

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

האינטגרציה בין תובנות מעורבות ותובנות קהל מקשרת בין סביבות משתי היכולות ומאפשרת שיתוף נתונים ביניהם.

השתמש בפרופילים ופלחים מאוחדים מתוך תובנות קהל לאפשרויות ניתוח נוספות בתובנות מעורבות. ייצא אירועים בעלי ערך עסקי גבוה מתובנות מעורבות. השתמש באירועים אלה כדי להוסיף נתונים לפרופילים מאוחדים בתובנות קהל.

## <a name="prerequisites"></a>דרישות מוקדמות

- יש לאחסן פרופילי תובנות קהל בחשבון Azure Data Lake Storage שבבעלותך או בתוך [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md)&ndash;אגם נתונים מנוהל. 

- אתה צריך הרשאות מנהל מערכת הן לתובנות מעורבות והן לסביבות תובנות קהל.

- סביבות מקושרות חייבות להיות באותו אזור גיאוגרפי.

> [!NOTE]
> - אם המנוי שלך לתובנות קהל הוא ניסיוני, שמשתמש בתובנות קהל שמנוהל באופן פנימי באגם נתונים, צור קשר עם [pirequest@microsoft.com](mailto:pirequest@microsoft.com) לעזרה. 
> - אם סביבת תובנות הקהל משתמשת ב-Azure Data Lake Storage שלך כדי לאחסן נתונים, עליך להוסיף מנהל שירות Azure לתובנות מעורבות לחשבון האחסון שלך. לפרטים, עבור אל [התחבר לחשבון Azure Data Lake Storage עם מנהל שירות Azure לתובנות קהל](../audience-insights/connect-service-principal.md). כמו כן, סביבת תובנות הקהל שלך צריכה לכלול סביבת [Dataverse משויכת](../audience-insights/get-started-paid.md). 

## <a name="create-an-environment-link"></a>צור קישור סביבה

תוכל ליצור קישור לסביבה על ידי עדכון **מנהל מערכת** > **סביבה** הגדרות בתובנות מעורבות.

**כדי לבסס קישור פעיל בין תובנות קהל לתובנות מעורבות‎‎**

1. בדף **מנהל איכות הסביבה**, בחר את כרטיסיית **קישור סביבות**.

    :::image type="content" source="media/integrate1.png" alt-text="הגדר סביבה.":::

1. בחר **הגדרת סביבות** בפינה השמאלית העליונה או בתחתית המסך.

     :::image type="content" source="media/integrate2.png" alt-text="בחירה של סביבת תובנות קהל.":::

1. בחר סביבת תובנות קהל ולאחר מכן בחר ***הבא** לסיום. כעת תוכל לבחור תכונות אופציונאליות עבור הסביבות המקושרות.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>אפשר תכונות ופלחים פרופילים מאוחדים של תבונות קהל

לאחר קישור הסביבות, תוכל לבחור תכונות אופציונאליות עבור הסביבות המקושרות. תכונות אלה מאפשרות מאפייני פרופיל ופלחים מאוחדים מתוך תבונות קהל לניתוח אינטראקטיבי של נתוני לקוחות.

**כדי לנתח נתוני אינטרנט בתובנות מעורבות**

1. בעמוד **מנהל איכות הסביבה** הפעל את **שתף נתונים מתובנות קהל עם תובנות מעורבות** החלף ולאחר מכן בחר **הבא**.

    :::image type="content" source="media/integrate4.png" alt-text="בחר מאפיינים.":::

1. בחר את המאפיינים של הפרופילים המאוחדים שיהפכו למימדים בתובנות מעורבות. (לא כל המאפיינים הינם מידות שימושיות. לדוגמה, לא סביר שתזדקק ל-**שם פרטי** אוֹ **שם משפחה** כמאפיין לניתוח אירועי האתר שלך.)

    :::image type="content" source="media/integrate5.png" alt-text="אצור ממדים.":::

   >[!NOTE]
   > כל מאפייני הפרופיל של תובנות הקהל המייצגות מזהים (כגון **תעודת זהות** ו-**תעודה מזהה חלופית**) מסוננים מתוך המאפיינים הזמינים והופכים למימדים בתובנות מעורבות.

1. לאחר שתסיים לבחור מאפיינים, בחר **הבא**.
1. הוסף משתמשים שיכולים לצפות בממדי הפרופיל של תובנות קהל ופלחים בתובנות מעורבות.

    :::image type="content" source="media/integrate6.png" alt-text="ניהול גישה לנתוני לקוחות.":::

   > [!IMPORTANT]
   > אם לא תוסיף במפורש משתמשים בשלב זה, הנתונים יוסתרו ממשתמשים בתובנות מעורבות.

1. סקור את הבחירות שלך ולאחר מכן לחץ על ‎ **סיום‎‎‎**.

    :::image type="content" source="media/integrate7.png" alt-text="סקור את הגדרות נתוני הלקוח.":::

## <a name="export-refined-events-to-audience-insights"></a>ייצא אירועים מעודנים לתובנות קהל

לאחר שתיצור קישור בין סביבות, תוכל לייצא אירועים מעודנים מתובנות מעורבות לתובנות קהל ולהטמיע אותן כמקור נתונים חדש. 

למידע נוסף, עבור אל [שלב נתוני אינטרנט מתובנות מעורבות עם תובנות קהל](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
