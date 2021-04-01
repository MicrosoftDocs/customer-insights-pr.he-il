---
title: העשרה באמצעות HERE Technologies להעשרה של צד שלישי
description: מידע כללי אודות העשרה של צד שלישי באמצעות HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597742"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="8566f-103">העשרת פרופילי לקוחות באמצעות HERE Technologies‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="8566f-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="8566f-104">HERE Technologies היא חברת פלטפורמת מיקום המספקת נתונים ושירותים הממוקדים במיקום.</span><span class="sxs-lookup"><span data-stu-id="8566f-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="8566f-105">באמצעות שירותי העשרת הנתונים של HERE Technologies, תוכל לבנות הבנת מיקום מדויקת יותר של לקוחותיך בעזרת נורמליזציה של כתובות, חילוץ קו רוחב וקו אורך, ועוד.</span><span class="sxs-lookup"><span data-stu-id="8566f-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8566f-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="8566f-106">Prerequisites</span></span>

<span data-ttu-id="8566f-107">כדי לקבוע את תצורת ההעשרות של HERE Technologies, יש לעמוד בתנאים המוקדמים הבאים:</span><span class="sxs-lookup"><span data-stu-id="8566f-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="8566f-108">יש לך מנוי פעיל ל- HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8566f-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="8566f-109">כדי לקבל מנוי, באפשרותך [להירשם כאן](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) או [ליצור קשר עם HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) ישירות.</span><span class="sxs-lookup"><span data-stu-id="8566f-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="8566f-110">קבל מידע נוסף אודות העשרת מיקום של HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8566f-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="8566f-111">יש לך את מפתח ה- API של HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8566f-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="8566f-112">יש לך הרשאות [מנהל מערכת](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="8566f-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="8566f-113">תצורה</span><span class="sxs-lookup"><span data-stu-id="8566f-113">Configuration</span></span>

1. <span data-ttu-id="8566f-114">עבור אל **נתונים** > **העשרה**.</span><span class="sxs-lookup"><span data-stu-id="8566f-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="8566f-115">בחר **העשר את הנתונים שלי** באריח HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8566f-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8566f-116">![אריח HERE Technologies](media/HERE-tile.png "אריח HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="8566f-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="8566f-117">הזן **מפתח API של HERE Technologies** פעיל.</span><span class="sxs-lookup"><span data-stu-id="8566f-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="8566f-118">סקור וספק את הסכמתך עבור **פרטיות נתונים ותאימות** על-ידי בחירת תיבת הסימון **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="8566f-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="8566f-119">אשר את שני ערכי הקלט על-ידי בחירת **התחבר ל- HERE**.</span><span class="sxs-lookup"><span data-stu-id="8566f-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="8566f-120">בחר **הוסף נתונים** ובחר את **ערכת נתוני הלקוח** שברצונך להעשיר עם נתונים מיקום מ- HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8566f-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="8566f-121">באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.</span><span class="sxs-lookup"><span data-stu-id="8566f-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. <span data-ttu-id="8566f-123">בחר אם ברצונך למפות שדות לכתובת הראשית ו/או המשנית.</span><span class="sxs-lookup"><span data-stu-id="8566f-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="8566f-124">באפשרותך לציין מיפוי שדות עבור שתי הכתובות (לדוגמה, כתובת בבית וכתובת עסק) ולהעשיר את הפרופילים עבור שתי הכתובות בנפרד.</span><span class="sxs-lookup"><span data-stu-id="8566f-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="8566f-125">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="8566f-125">Select **Next**.</span></span>

1. <span data-ttu-id="8566f-126">הגדר באילו שדות מהפרופילים המאוחדים שלך יש להשתמש כדי לחפש נתוני מיקום מתאימים מ- HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8566f-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="8566f-127">השדות **רחוב 1** ו **מיקוד** נדרשים עבור הכתובת הראשית ו/או המשנית שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="8566f-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="8566f-128">עבור דיוק התאמות גבוה יותר, ניתן להוסיף שדות נוספים.</span><span class="sxs-lookup"><span data-stu-id="8566f-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8566f-129">![דף קביעת תצורה של העשרת HERE Technologies](media/enrichment-HERE-configuration.png "דף קביעת תצורה של העשרת HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="8566f-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="8566f-130">בחר **החל** להשלמת מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="8566f-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="8566f-131">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="8566f-131">Enrichment results</span></span>

<span data-ttu-id="8566f-132">כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="8566f-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="8566f-133">ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8566f-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8566f-134">זמן העיבוד יהיה תלוי בגודל נתוני הלקוחות שלך ובזמני התגובה של ה- API מ- HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="8566f-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="8566f-135">לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**.</span><span class="sxs-lookup"><span data-stu-id="8566f-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="8566f-136">בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="8566f-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="8566f-137">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="8566f-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8566f-138">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="8566f-138">Next steps</span></span>

<span data-ttu-id="8566f-139">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="8566f-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="8566f-140">צור [פלחים](segments.md), [מדדים](measures.md), ואפילו [ייצא את הנתונים](export-destinations.md) כדי לספק חוויות מותאמות אישית ללקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="8566f-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8566f-141">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="8566f-141">Data privacy and compliance</span></span>

<span data-ttu-id="8566f-142">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל HERE Technologies, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="8566f-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8566f-143">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- HERE Technologies עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="8566f-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8566f-144">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8566f-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8566f-145">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="8566f-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]