---
title: ייצוא פלחים ל- Adobe Experience Platform‏ (Preview)
description: למד כיצד להשתמש בפלחי Customer Insights ב- Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195291"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>ייצוא פלחים ל- Adobe Experience Platform‏ (Preview)

יצא פלחים המתמקדים בקהלים רלוונטיים אל Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="תרשים התהליך של השלבים המתוארים במאמר זה.":::

## <a name="prerequisites"></a>‏‫דרישות מוקדמות‬

- רישיון Adobe Experience Platform.
- רישיון ל- Adobe Campaign Standard.
- שם [חשבון Azure Blob Storage](/azure/storage/blobs/create-data-lake-storage-account) ומפתח חשבון. כדי לחפש את השם ואת המפתח, ראה [ניהול הגדרות של חשבון אחסון בפורטל Azure](/azure/storage/common/storage-account-manage).
- [גורם מכיל של Azure Blob Storage](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container)

## <a name="campaign-overview"></a>מבט כולל על קמפיין

כדי להבין טוב יותר כיצד ניתן להשתמש בפלחים מתוך Customer Insights ב- Adobe Experience Platform, בואו נסתכל על קמפיין פיקטיבי לדוגמה.

נניח שהחברה שלך מציעה שירות חודשי מבוסס מנוי ללקוחות שלך בארצות הברית. ברצונך לזהות לקוחות שהמנויים שלהם אמורים להתחדש בשמונת הימים הקרובים אך טרם חידשו את המנוי. כדי לשמור על לקוחות אלה, תרצה לשלוח להם מבצע קידום מכירות דרך דוא"ל, באמצעות Adobe Experience Platform.

בדוגמה זו, אנחנו רוצים להפעיל את קמפיין הדואר לקידום מכירות פעם אחת. מאמר זה אינו מכסה את מקרה השימוש של הפעלת הקמפיין יותר מפעם אחת.

## <a name="identify-your-target-audience"></a>זיהוי קהל היעד שלך

בתרחיש שלנו, אנו מניחים שכתובות האימייל של הלקוחות זמינות ב-Customer Insights והעדפות הקידום שלהם נותחו כדי לזהות חברים בפלח.

[הפלח שהגדרת ב- Customer Insights](segments.md) נקרא **ChurnProneCustomers** ואתה מתכנן לשלוח ללקוחות אלה את קידום המכירות בדואר אלקטרוני.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="צילום מסך של דף הפלחים שהפלח ChurnProneCustomers נוצר בו.":::

דואר ההצעה שברצונך לשלוח יכלול את השם הפרטי, שם המשפחה, ואת תאריך סיום המנוי של הלקוח. הוא מעדכן את הלקוחות לגבי ההנחה שהם יקבלו אם יחדשו את המנוי שלהם לפני שיסתיים.

## <a name="export-your-target-audience"></a>ייצוא קהל היעד שלך

נוכל להגדיר את הייצוא מ- Customer Insights לחשבון Azure Blob Storage.

### <a name="set-up-connection-to-azure-blob-storage"></a>הגדרת חיבור ל- Azure Blob Storage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. עבור אל **ניהול** > **חיבורים**.

1. בחר **הוסף חיבור** ובחר **Azure Blob Storage**.

1. תן לחיבור שלך שם הניתן לזיהוי בשדה **שם תצוגה**. השם וסוג החיבור מתארים חיבור זה. מומלץ לבחור שם המסביר את המטרה והיעד של החיבור.

1. בחר מי יכול להשתמש בחיבור זה. כברירת מחדל, רק מנהלי מערכת. לקבלת מידע נוסף, ראה [אפשר למשתתפים להשתמש בחיבור עבור פעולות ייצוא](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. הזן **שם חשבון**, **מפתח חשבון** ו **גורם מכיל** עבור חשבון Blob Storage שלך שאליו ברצונך לייצא את הפלח.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="צילום מסך של תצורת חשבון האחסון. ":::

1. סקור את [פרטיות ותאימות הנתונים](connections.md#data-privacy-and-compliance) ובחר **אני מסכים**.

1. בחר **שמור** כדי להשלים את החיבור.

### <a name="configure-an-export"></a>קביעת תצורה של ייצוא

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. עבור אל **נתונים** > **פעולות ייצוא**.

1. בחר **הוסף ייצוא**.

1. בשדה **חיבור לייצוא**, בחר חיבור מתוך מקטע אחסון Blob של Azure. צור קשר עם מנהל מערכת אם אין חיבור זמין.

1. הזן שם עבור הייצוא.

1. בחר את הפלח שברצונך לייצא. בדוגמה זו, זהו **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="צילום מסך של ממשק המשתמש לבחירת פלח עם הפלח ChurnProneCustomers שנבחר בו.":::

1. בחר **Save**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> ודא שמספר הרשומות בפלח המיוצא נמצאים במגבלת הרישיון שלך ל- Adobe Campaign Standard license.

נתונים מיוצאים מאוחסנים בגורם המכיל של Azure Blob Storage שהגדרת. נתיבי התיקיות הבאים נוצרים באופן אוטומטי בגורם המכיל שלך:

- עבור ישויות מקור וישויות שנוצרו על-ידי המערכת:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- ה- *model.json* עבור הישויות שיוצאו שוכן ברמה *%ExportDestinationName%*.

  דוגמה: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>הגדר מודל נתוני ניסיון (XDM) ב-Adobe Experience Platform

לפני שניתן להשתמש בנתונים המיוצאים מ- Customer Insights בתוך Adobe Experience Platform, הגדר את סכימת מודל נתוני Experience ו[הגדר את תצורת סכמת מודל הנתונים של Experience עבור פרופיל הלקוח בזמן אמת](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

למד [מהו XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) והבן את [יסודות הרכב הסכימה](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>ייבוא נתונים לתוך Adobe Experience Platform

יבא את נתוני קהל המוכנים מ- Customer Insights אל Adobe Experience Platform.

1. [צור חיבור למקור Azure Blob Storage](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [הגדר תצורה של זרימת נתונים](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) עבור חיבור אצוות אחסון בענן כדי לייבא את הפלט של הפלח מ- Customer Insights אל Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>צור קהל ב-Adobe Campaign Standard

כדי לשלוח את הדוא"ל עבור קמפיין זה, נשתמש ב- Adobe Campaign Standard.

1. [צור קהל](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) ב- Adobe Campaign Standard באמצעות הנתונים ב- Adobe Experience Platform.

1. [השתמש בבונה הפלחים](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) ב- Adobe Campaign Standard להגדרת קהל בהתבסס על הנתונים ב- Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>צור ושלח את הדוא"ל באמצעות Adobe Campaign Standard

צור את תוכן הדואר ולאחר מכן [בדוק ושלח](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) את הדואר שלך.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="דוגמא לדואר אלקטרוני עם הצעת חידוש מאת Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
