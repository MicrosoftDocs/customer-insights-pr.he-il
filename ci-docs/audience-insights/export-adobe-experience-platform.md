---
title: ייצוא נתוני Customer Insights אל Adobe Experience Platform
description: למד כיצד להשתמש בפלחי תובנות לגבי קהל בפלטפורמת Adobe Experience.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 1045d0e373fd5ea8987684e51bd9a07b7b535ee3
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305525"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>שימוש בפלחי Customer Insights ב- Adobe Experience Platform (preview)‎

כמשתמש בתובנות לגבי קהלים ב- Dynamics 365 Customer Insights, ייתכן שיצרת פלחים כדי לייעל את הקמפיינים השיווקיים שלך על ידי התמקדות בקהלים הרלוונטיים. כדי להשתמש בפלח מ- Audience Insights ב- Adobe Experience Platform וביישומים כמו Adobe Campaign Standard, עליך לבצע מספר שלבים המתוארים במאמר זה.

:::image type="content" source="media/AEP-flow.png" alt-text="תרשים התהליך של השלבים המתוארים במאמר זה.":::

## <a name="prerequisites"></a>דרישות מוקדמות

-   רשיון Dynamics 365 Customer Insights
-   רישיון Adobe Experience Platform
-   רישיון Adobe Campaign Standard
-   חשבון אחסון Blob של Azure

## <a name="campaign-overview"></a>מבט כולל על קמפיין

כדי להבין טוב יותר כיצד ניתן להשתמש בפלחים מתוך audience insights ב- Adobe Experience Platform, בוא נבחן קמפיין לדוגמה בדוי.

נניח שהחברה שלך מציעה שירות חודשי מבוסס מנוי ללקוחות שלך בארצות הברית. ברצונך לזהות לקוחות שהמנויים שלהם אמורים להתחדש בשמונת הימים הקרובים אך טרם חידשו את המנוי. כדי לשמור לקוחות אלה, ברצונך לשלוח להם הצעת קידום מכירות דרך הדואר, באמצעות Adobe Experience Platform.

בדוגמה זו, אנחנו רוצים להפעיל את קמפיין הדואר לקידום מכירות פעם אחת. מאמר זה אינו מכסה את מקרה השימוש של הפעלת הקמפיין יותר מפעם אחת.

## <a name="identify-your-target-audience"></a>זיהוי קהל היעד שלך

בתרחיש שלנו, אנחנו מניחים שכתובות הדואר של הלקוחות זמינות ב- audience insights ושהעדפות קידום המכירות שלהם נותחו כדי לזהות את החברים בפלח.

ה [פלח שהגדרת ב- audience insights](segments.md) נקרא **ChurnProneCustomers** ובכוונתך לשלוח ללקוחות אלה את קידום הדואר.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="צילום מסך של דף הפלחים שהפלח ChurnProneCustomers נוצר בו.":::

דואר ההצעה שברצונך לשלוח יכלול את השם הפרטי, שם המשפחה, ואת תאריך סיום המנוי של הלקוח. הוא מעדכן את הלקוחות לגבי ההנחה שהם יקבלו אם יחדשו את המנוי שלהם לפני שיסתיים.

## <a name="export-your-target-audience"></a>ייצוא קהל היעד שלך

לאחר שקהל היעד שלנו זוהה, נוכל להגדיר את הייצוא מ- audience insights לחשבון אחסון Blob של Azure.

### <a name="configure-a-connection"></a>קביעת תצורה של חיבור

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Azure Blob Storage** או בחר **הגדר** בתוך אריח **Azure Blob Storage** כדי להגדיר את החיבור.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="אריח 'קביעת תצורה' עבור אחסון Blob של Azure."::: 

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. אם לא תנקוט שום פעולה, ברירת המחדל תהיה מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור חשבון Blob Storage שלך שאליו ברצונך לייצא את הפלח.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="צילום מסך של תצורת חשבון האחסון. "::: 
   
    - לקבלת מידע נוסף אודות האופן שבו ניתן למצוא שם חשבון ומפתח חשבון של Blob Storage, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).
    - כדי ללמוד כיצד ליצור גורם מכיל, ראה [יצירת גורם מכיל](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. בחר **שמור** כדי להשלים את החיבור. 

### <a name="configure-an-export"></a>קביעת תצורה של ייצוא

באפשרותך לקבוע תצורת ייצוא זה אם יש לך גישה לחיבור מסוג זה. לקבלת מידע נוסף, ראה [הרשאות הדרושות לקביעת תצורה של ייצוא](export-destinations.md#set-up-a-new-export).

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. כדי ליצור ייצוא חדש, בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע אחסון Blob של Azure. אם אינך רואה את שם הפלח הזה, אין קשרים זמינים עבורך מסוג זה.

1. בחר את הפלח שברצונך לייצא. בדוגמה זו, זהו **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="צילום מסך של ממשק המשתמש לבחירת פלח עם הפלח ChurnProneCustomers שנבחר בו.":::

1. בחר **שמור**.

לאחר שמירת יעד הייצוא, תמצא אותו תחת **נתונים** > **פעולות ייצוא**.

כעת באפשרותך [לייצא את הפלח לפי דרישה](export-destinations.md#run-exports-on-demand). הייצוא יפעל גם בכל [רענון מתוזמן](system.md).

> [!NOTE]
> ודא שמספר הרשומות בפלח המיוצא לא חורג ממגבלה המותרת של רישיון Adobe Campaign Standard.

הנתונים המיוצאים מאוחסנים בגורם המכיל של Azure Blob Storage שהגדרת לעיל. נתיב התיקיה הבא נוצר אוטומטית בגורם המכיל שלך:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

ה- *model.json* עבור הישויות שיוצאו שוכן ברמה *%ExportDestinationName%*.

דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>הגדרת Experience Data Model‏ (XDM) ב- Adobe Experience Platform

לפני שניתן יהיה להשתמש בנתונים המיוצאים מ- audience insights בתוך Adobe Experience Platform, עלינו להגדיר את סכימת Experience Data Model וכן [לקבוע את תצורת הנתונים עבור פרופיל הלקוח בזמן אמת](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

למד [מהו XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) והבן את [יסודות הרכב הסכימה](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>ייבוא נתונים אל Adobe Experience Platform

עכשיו כשהכל מוכן, עלינו לייבא את נתוני קהל המוכנים מ- audience insights אל Adobe Experience Platform כדי ליצור פרופילים.

תחילה, [צור חיבור למקור אחסון Blob של Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

לאחר הגדרת חיבור המקור, [קבע תצורה של תזרים נתונים](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) עבור חיבור לאצוות אחסון בענן כדי לייבא את פלט הפלח מ- audience insights אל Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>יצירת קהל ב- Adobe Campaign Standard

כדי לשלוח את הדואר האלקטרוני עבור קמפיין זה, נשתמש ב- Adobe Campaign Standard. לאחר ייבוא הנתונים אל Adobe Experience Platform, עלינו [ליצור קהל](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) ב- Adobe Campaign Standard באמצעות הנתונים ב- Adobe Experience Platform.


למד כיצד [להשתמש בבונה הפלחים](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) ב- Adobe Campaign Standard כדי להגדיר קהל המבוסס על הנתונים ב- Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>יצירה ושליחה של הדואר באמצעות Adobe Campaign Standard

צור את תוכן הדואר ולאחר מכן [בדוק ושלח](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) את הדואר שלך.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="דואר לדוגמה עם הצעת חידוש של Adobe Campaign Standard.":::
