---
title: העשרה עם ייבוא מותאם אישית של SPTF
description: מידע כללי אודות העשרת ייבוא מותאם אישית של SPTF.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568447"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="c6d57-103">העשרת פרופילי לקוחות עם נתונים מותאמים אישית (Preview)</span><span class="sxs-lookup"><span data-stu-id="c6d57-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="c6d57-104">ייבוא מותאם אישית באמצעות Secure File Transfer Protocol‏ (SFTP) מאפשר לך לייבא נתונים שלא צריכים לעבור את תהליך איחוד הנתונים.</span><span class="sxs-lookup"><span data-stu-id="c6d57-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="c6d57-105">זו דרך גמישה, מאובטחת וקלה להכנסת הנתונים שלך.</span><span class="sxs-lookup"><span data-stu-id="c6d57-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="c6d57-106">ניתן להשתמש בייבוא מותאם אישית של SFTP בשילוב עם [ייצוא SFTP](export-sftp.md) המאפשר לך לייצא את נתוני פרופיל הלקוח הדרושים להעשרה.</span><span class="sxs-lookup"><span data-stu-id="c6d57-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="c6d57-107">לאחר מכן ניתן לעבד את הנתונים, להעשיר אותם ולבצע ייבוא מותאם אישית של SFTP כדי להחזיר את הנתונים המועשרים ליכולת תובנות הקהל של Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="c6d57-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="c6d57-108">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="c6d57-108">Prerequisites</span></span>

<span data-ttu-id="c6d57-109">כדי לקבוע את תצורת הייבוא המותאם אישית של SFTP, יש לעמוד בתנאים המוקדמים הבאים:</span><span class="sxs-lookup"><span data-stu-id="c6d57-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="c6d57-110">יש לך אישורי משתמש (שם משתמש וסיסמה) עבור מיקום ה- SFTP שממנו יתבצע ייבוא הנתונים.</span><span class="sxs-lookup"><span data-stu-id="c6d57-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="c6d57-111">יש לך את כתובת ה- URL ומספר היציאה (בדרך כלל 22) עבור מארח STFP.</span><span class="sxs-lookup"><span data-stu-id="c6d57-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="c6d57-112">יש לך את שם הקובץ ואת המיקום של הקובץ המיובא במארח ה- SFTP.</span><span class="sxs-lookup"><span data-stu-id="c6d57-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="c6d57-113">קיים קובץ *model.json* המציין את הסכימה עבור הנתונים המיועדים לייבוא.</span><span class="sxs-lookup"><span data-stu-id="c6d57-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="c6d57-114">קובץ זה חייב להיות באותה ספריה שבה נמצא הקובץ לייבוא.</span><span class="sxs-lookup"><span data-stu-id="c6d57-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="c6d57-115">יש לך הרשאת [מנהל מערכת](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="c6d57-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="c6d57-116">תצורה</span><span class="sxs-lookup"><span data-stu-id="c6d57-116">Configuration</span></span>

1. <span data-ttu-id="c6d57-117">עבור אל **נתונים** > **העשרה** ובחר בכרטיסיה **גלה**.</span><span class="sxs-lookup"><span data-stu-id="c6d57-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="c6d57-118">ב **אריח ייבוא מותאם אישית של SPTF**, בחר **העשר את הנתונים שלי**.</span><span class="sxs-lookup"><span data-stu-id="c6d57-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6d57-119">![אריח של ייבוא מותאם אישית של SPTF](media/SFTP_Custom_Import_tile.png "אריח של ייבוא מותאם אישית של SPTF")</span><span class="sxs-lookup"><span data-stu-id="c6d57-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="c6d57-120">בחר **תחילת העבודה** וספק את האישורים ואת הכתובת עבור שרת SPTF.</span><span class="sxs-lookup"><span data-stu-id="c6d57-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="c6d57-121">לדוגמה, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="c6d57-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="c6d57-122">הזן את שם הקובץ שמכיל את הנתונים ואת הנתיב לקובץ בשרת SFTP אם הוא לא נמצא בתיקיית הבסיס.</span><span class="sxs-lookup"><span data-stu-id="c6d57-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="c6d57-123">אשר את כל פריטי הקלט על-ידי בחירת **התחבר לייבוא מותאם אישית**.</span><span class="sxs-lookup"><span data-stu-id="c6d57-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="c6d57-124">![תפריט נשלף של תצורת ייבוא מותאם אישית של SPTF](media/SFTP_Custom_Import_Configuration_flyout.png "תפריט נשלף של תצורת ייבוא מותאם אישית של SPTF")</span><span class="sxs-lookup"><span data-stu-id="c6d57-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="c6d57-125">הגדרת מיפויי שדות</span><span class="sxs-lookup"><span data-stu-id="c6d57-125">Defining field mappings</span></span> 

<span data-ttu-id="c6d57-126">הספריה המכילה את הקובץ המיועד לייבוא בשרת SPTF מוכרחה גם לכלול קובץ *model.json*.</span><span class="sxs-lookup"><span data-stu-id="c6d57-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="c6d57-127">קובץ זה מגדיר את הסכימה לשימוש עבור ייבוא הנתונים.</span><span class="sxs-lookup"><span data-stu-id="c6d57-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="c6d57-128">יש להשתמש בסכימה [Common Data Model](https://docs.microsoft.com/common-data-model/) כדי לציין את מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="c6d57-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="c6d57-129">דוגמה פשוטה לקובץ model.json נראית כך:</span><span class="sxs-lookup"><span data-stu-id="c6d57-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="c6d57-130">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="c6d57-130">Enrichment results</span></span>

<span data-ttu-id="c6d57-131">כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="c6d57-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="c6d57-132">ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c6d57-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c6d57-133">זמן העיבוד יהיה תלוי בגודל הנתונים לייבוא ובחיבור לשרת SPTF.</span><span class="sxs-lookup"><span data-stu-id="c6d57-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="c6d57-134">לאחר סיום תהליך ההעשרה, תוכל לסקור את נתוני ההעשרה המותאמים אישית שלך שיובאו לאחרונה תחת **ההעשרות שלי**.</span><span class="sxs-lookup"><span data-stu-id="c6d57-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="c6d57-135">בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="c6d57-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="c6d57-136">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="c6d57-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c6d57-137">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="c6d57-137">Next steps</span></span>

<span data-ttu-id="c6d57-138">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="c6d57-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="c6d57-139">צור [פלחים](segments.md), [מדידות](measures.md) ו[יצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="c6d57-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


