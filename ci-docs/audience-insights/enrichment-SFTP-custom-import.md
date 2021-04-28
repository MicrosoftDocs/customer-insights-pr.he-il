---
title: העשרה עם ייבוא מותאם אישית של SPTF
description: מידע כללי אודות העשרת ייבוא מותאם אישית של SPTF.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a2d450635c19432bdd88db74b61c17febdeb568d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896282"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="69a01-103">העשרת פרופילי לקוחות עם נתונים מותאמים אישית (Preview)</span><span class="sxs-lookup"><span data-stu-id="69a01-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="69a01-104">ייבוא מותאם אישית באמצעות Secure File Transfer Protocol‏ (SFTP) מאפשר לך לייבא נתונים שלא צריכים לעבור את תהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="69a01-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that does not have to go through the process of data unification.</span></span> <span data-ttu-id="69a01-105">זו דרך גמישה, מאובטחת וקלה להכנסת הנתונים שלך.</span><span class="sxs-lookup"><span data-stu-id="69a01-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="69a01-106">ניתן להשתמש בייבוא מותאם אישית של SFTP בשילוב עם [ייצוא SFTP](export-sftp.md) המאפשר לך לייצא את נתוני פרופיל הלקוח הדרושים להעשרה.</span><span class="sxs-lookup"><span data-stu-id="69a01-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="69a01-107">לאחר מכן ניתן לעבד את הנתונים, להעשיר אותם ולבצע ייבוא מותאם אישית של SFTP כדי להחזיר את הנתונים המועשרים ליכולת תובנות הקהל של Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="69a01-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69a01-108">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="69a01-108">Prerequisites</span></span>

<span data-ttu-id="69a01-109">כדי לקבוע את תצורת הייבוא המותאם אישית של SFTP, יש לעמוד בתנאים המוקדמים הבאים:</span><span class="sxs-lookup"><span data-stu-id="69a01-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="69a01-110">יש לך את שם הקובץ ואת המיקום (הנתיב) של הקובץ שיש לייבא במארח SFTP.</span><span class="sxs-lookup"><span data-stu-id="69a01-110">You have the filename and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="69a01-111">קיים קובץ *model.json* שמציין את [סכימת Common Data Model](/common-data-model/) עבור הנתונים שיש לייבא.</span><span class="sxs-lookup"><span data-stu-id="69a01-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="69a01-112">קובץ זה חייב להיות באותה ספריה שבה נמצא הקובץ לייבוא.</span><span class="sxs-lookup"><span data-stu-id="69a01-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="69a01-113">חיבור SFTP כבר הוגדר על-ידי מנהל מערכת *או* שיש לך הרשאות [מנהל מערכת](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="69a01-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="69a01-114">תזדקק לאישורי המשתמש, לכתובת ה- URL ולמספר היציאה עבור מיקום ה- SFTP שממנו ברצונך לייבא נתונים.</span><span class="sxs-lookup"><span data-stu-id="69a01-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="69a01-115">קביעת תצורת הייבוא</span><span class="sxs-lookup"><span data-stu-id="69a01-115">Configure the import</span></span>

1. <span data-ttu-id="69a01-116">עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.</span><span class="sxs-lookup"><span data-stu-id="69a01-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="69a01-117">ב **אריח ייבוא מותאם אישית של SFTP**, בחר **העשר את הנתונים שלי** ובחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="69a01-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="אריח של ייבוא מותאם אישית של SFTP.":::

1. <span data-ttu-id="69a01-119">‏‏בחר [חיבור](connections.md) מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="69a01-119">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="69a01-120">צור קשר עם מנהל מערכת אם אין חיבור זמין.</span><span class="sxs-lookup"><span data-stu-id="69a01-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="69a01-121">אם אתה מנהל מערכת, באפשרותך ליצור חיבור על-ידי בחירת **הוסף חיבור** ובחירת **ייבוא מותאם אישית של SFTP** מתוך התפריט הנפתח.</span><span class="sxs-lookup"><span data-stu-id="69a01-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the drop-down.</span></span>

1. <span data-ttu-id="69a01-122">בחר **התחבר לייבוא מותאם אישית** כדי לאשר את החיבור שנבחר.</span><span class="sxs-lookup"><span data-stu-id="69a01-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="69a01-123">בחר **הבא** והזן את **שם הקובץ** ואת **הנתיב** של קובץ הנתונים שברצונך לייבא.</span><span class="sxs-lookup"><span data-stu-id="69a01-123">Select **Next** and enter the **Filename** and **Path** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="צילום מסך בעת הזנת מיקום הנתונים.":::

1. <span data-ttu-id="69a01-125">בחר **הבא** וספק שם עבור ההעשרה ושם עבור ישות הפלט.</span><span class="sxs-lookup"><span data-stu-id="69a01-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="69a01-126">בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.</span><span class="sxs-lookup"><span data-stu-id="69a01-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="69a01-127">קביעת תצורת החיבור עבור ייבוא מותאם אישית של SFTP</span><span class="sxs-lookup"><span data-stu-id="69a01-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="69a01-128">עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים.</span><span class="sxs-lookup"><span data-stu-id="69a01-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="69a01-129">בחר **הוסף חיבור** בעת קביעת תצורת העשרה *או* עבור אל **ניהול** > **חיבורים** ובחר **הגדר** באריח 'ייבוא מותאם אישית'.</span><span class="sxs-lookup"><span data-stu-id="69a01-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="69a01-130">הזן שם עבור החיבור בתיבה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="69a01-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="69a01-131">הזן שם משתמש חוקי, סיסמה וכתובת URL של אתר מארח עבור שרת SFTP שהנתונים שיש לייבא שוכנים בו.</span><span class="sxs-lookup"><span data-stu-id="69a01-131">Enter valid user name, password, and host URL for the STFP server the data to be imported resides on.</span></span>

1. <span data-ttu-id="69a01-132">סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="69a01-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="69a01-133">בחר **אימות** כדי לאמת את התצורה.</span><span class="sxs-lookup"><span data-stu-id="69a01-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="69a01-134">לאחר השלמת האימות, ניתן לשמור את החיבור על-ידי לחיצה על **שמור**.</span><span class="sxs-lookup"><span data-stu-id="69a01-134">Once the verification has completed, the connection can be saved by clicking **Save**.</span></span>

> [!div class="mx-imgBorder"]
   > <span data-ttu-id="69a01-135">![דף תצורת החיבור של Experian](media/enrichment-SFTP-connection.png "דף תצורת החיבור של Experian")</span><span class="sxs-lookup"><span data-stu-id="69a01-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="69a01-136">הגדרת מיפויי שדות</span><span class="sxs-lookup"><span data-stu-id="69a01-136">Defining field mappings</span></span> 

<span data-ttu-id="69a01-137">הספריה המכילה את הקובץ המיועד לייבוא בשרת SPTF מוכרחה גם לכלול קובץ *model.json*.</span><span class="sxs-lookup"><span data-stu-id="69a01-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="69a01-138">קובץ זה מגדיר את הסכימה לשימוש עבור ייבוא הנתונים.</span><span class="sxs-lookup"><span data-stu-id="69a01-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="69a01-139">יש להשתמש בסכימה [Common Data Model](/common-data-model/) כדי לציין את מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="69a01-139">The schema has to use [the Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="69a01-140">דוגמה פשוטה לקובץ model.json נראית כך:</span><span class="sxs-lookup"><span data-stu-id="69a01-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="69a01-141">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="69a01-141">Enrichment results</span></span>

<span data-ttu-id="69a01-142">כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="69a01-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="69a01-143">ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="69a01-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="69a01-144">זמן העיבוד יהיה תלוי בגודל הנתונים לייבוא ובחיבור לשרת SPTF.</span><span class="sxs-lookup"><span data-stu-id="69a01-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="69a01-145">לאחר סיום תהליך ההעשרה, תוכל לסקור את נתוני ההעשרה המותאמים אישית שלך שיובאו לאחרונה תחת **ההעשרות שלי**.</span><span class="sxs-lookup"><span data-stu-id="69a01-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="69a01-146">בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="69a01-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="69a01-147">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="69a01-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="69a01-148">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="69a01-148">Next steps</span></span>

<span data-ttu-id="69a01-149">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="69a01-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="69a01-150">צור [פלחים](segments.md), [מדידות](measures.md) ו[יצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="69a01-150">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
