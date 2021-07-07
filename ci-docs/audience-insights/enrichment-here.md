---
title: העשרה באמצעות העשרת צד שלישי של HERE Technologies
description: מידע כללי אודות העשרה של צד שלישי באמצעות HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305295"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="491aa-103">העשרת פרופילי לקוחות באמצעות HERE Technologies‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="491aa-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="491aa-104">HERE Technologies היא חברת פלטפורמת מיקום המספקת נתונים ושירותים הממוקדים במיקום.</span><span class="sxs-lookup"><span data-stu-id="491aa-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="491aa-105">באמצעות שירותי העשרת הנתונים של HERE Technologies, תוכל לבנות הבנת מיקום מדויקת יותר של לקוחותיך בעזרת נורמליזציה של כתובות, חילוץ קו רוחב וקו אורך, ועוד.</span><span class="sxs-lookup"><span data-stu-id="491aa-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="491aa-106">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="491aa-106">Prerequisites</span></span>

<span data-ttu-id="491aa-107">כדי לקבוע את תצורת ההעשרות של HERE Technologies, יש לעמוד בתנאים המוקדמים הבאים:</span><span class="sxs-lookup"><span data-stu-id="491aa-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="491aa-108">יש לך מנוי פעיל ל- HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="491aa-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="491aa-109">כדי לקבל מנוי, באפשרותך [להירשם כאן](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) או [ליצור קשר עם HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) ישירות.</span><span class="sxs-lookup"><span data-stu-id="491aa-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="491aa-110">קבל מידע נוסף אודות העשרת מיקום של HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="491aa-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="491aa-111">[חיבור](connections.md) HERE זמין *או* שיש לך הרשאות [מנהל מערכת](permissions.md#administrator) ומפתח API של HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="491aa-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="491aa-112">קביעת תצורת ההעשרה</span><span class="sxs-lookup"><span data-stu-id="491aa-112">Configure the enrichment</span></span>

1. <span data-ttu-id="491aa-113">עבור אל **נתונים** > **העשרה**.</span><span class="sxs-lookup"><span data-stu-id="491aa-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="491aa-114">בחר **העשר את הנתונים שלי** באריח HERE Technologies ובחר **תחילת העבודה**.</span><span class="sxs-lookup"><span data-stu-id="491aa-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="491aa-115">![אריח HERE Technologies](media/HERE-tile.png "אריח HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="491aa-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="491aa-116">בחר [חיבור](connections.md) מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="491aa-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="491aa-117">צור קשר עם מנהל מערכת אם אין חיבור זמין.</span><span class="sxs-lookup"><span data-stu-id="491aa-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="491aa-118">אם אתה מנהל מערכת, באפשרותך ליצור חיבור על-ידי בחירת **הוסף חיבור**.</span><span class="sxs-lookup"><span data-stu-id="491aa-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="491aa-119">בחר **HERE Technologies** מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="491aa-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="491aa-120">בחר **התחבר ל- HERE Technologies** כדי לאשר את הבחירה.</span><span class="sxs-lookup"><span data-stu-id="491aa-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="491aa-121">בחר **הבא** ובחר את **ערכת הנתונים של הלקוח** שברצונך להעשיר בנתוני מיקום מתוך HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="491aa-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="491aa-122">באפשרותך לבחור את הישות **לקוח** כדי להעשיר את כל פרופילי הלקוחות שלך או לבחור ישות פלח כדי להעשיר רק פרופילי לקוחות הנכללים בפלח זה.</span><span class="sxs-lookup"><span data-stu-id="491aa-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="צילום מסך בעת בחירה של ערכת נתוני הלקוח.":::

1. <span data-ttu-id="491aa-124">בחר אם ברצונך למפות שדות לכתובת הראשית ו/או המשנית.</span><span class="sxs-lookup"><span data-stu-id="491aa-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="491aa-125">באפשרותך לציין מיפוי שדה עבור שתי הכתובות ולהעשיר את הפרופילים עבור שתי הכתובות בנפרד.</span><span class="sxs-lookup"><span data-stu-id="491aa-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="491aa-126">לדוגמא, אם יש כתובת בית וכתובת עסק.</span><span class="sxs-lookup"><span data-stu-id="491aa-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="491aa-127">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="491aa-127">Select **Next**.</span></span>

1. <span data-ttu-id="491aa-128">הגדר באילו שדות מהפרופילים המאוחדים שלך יש להשתמש כדי לחפש נתוני מיקום מתאימים מ- HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="491aa-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="491aa-129">השדות **רחוב 1** ו **מיקוד** נדרשים עבור הכתובת הראשית ו/או המשנית שנבחרה.</span><span class="sxs-lookup"><span data-stu-id="491aa-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="491aa-130">עבור דיוק התאמות גבוה יותר, ניתן להוסיף שדות נוספים.</span><span class="sxs-lookup"><span data-stu-id="491aa-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="491aa-131">![דף קביעת תצורה של העשרת HERE Technologies](media/enrichment-HERE-configuration.png "דף קביעת תצורה של העשרת HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="491aa-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="491aa-132">בחר **הבא** כדי להשלים את מיפוי השדה.</span><span class="sxs-lookup"><span data-stu-id="491aa-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="491aa-133">ספק שם עבור ההעשרה.</span><span class="sxs-lookup"><span data-stu-id="491aa-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="491aa-134">בחר **שמור העשרה** לאחר סקירת האפשרויות שלך.</span><span class="sxs-lookup"><span data-stu-id="491aa-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="491aa-135">הגדת את תצורת החיבור של HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="491aa-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="491aa-136">עליך להיות מנהל מערכת כדי לקבוע תצורת חיבורים.</span><span class="sxs-lookup"><span data-stu-id="491aa-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="491aa-137">בחר **הוסף חיבור** בעת קביעת תצורת העשרה *או* עבור אל **ניהול** > **חיבורים** ובחר **הגדר** באריח HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="491aa-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="491aa-138">הזן שם עבור החיבור בתיבה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="491aa-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="491aa-139">ספק מפתח API חוקי של HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="491aa-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="491aa-140">סקור את **פרטיות ותאימות נתונים** ותן את הסכמתך על-ידי בחירת **אני מסכים**.</span><span class="sxs-lookup"><span data-stu-id="491aa-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="491aa-141">בחר **אימות** כדי לאמת את התצורה.</span><span class="sxs-lookup"><span data-stu-id="491aa-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="491aa-142">לאחר השלמת האימות, בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="491aa-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="491aa-143">![דף תצורת החיבור של HERE Technologies](media/enrichment-HERE-connection.png "דף תצורת החיבור של HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="491aa-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="491aa-144">תוצאות העשרה</span><span class="sxs-lookup"><span data-stu-id="491aa-144">Enrichment results</span></span>

<span data-ttu-id="491aa-145">כדי להתחיל בתהליך ההעשרה בחר **הפעל** מסרגל הפקודות.</span><span class="sxs-lookup"><span data-stu-id="491aa-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="491aa-146">ניתן גם לתת למערכת להפעיל את ההעשרה באופן אוטומטי כחלק מ[פעולת רענון מתוזמנת](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="491aa-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="491aa-147">זמן העיבוד יהיה תלוי בגודל נתוני הלקוחות שלך ובזמני התגובה של ה- API מ- HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="491aa-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="491aa-148">לאחר סיום תהליך ההעשרה, תוכל לבדוק את לסקור פרופילי הלקוחות שעושרו זה עתה תחת **ההעשרות שלי**.</span><span class="sxs-lookup"><span data-stu-id="491aa-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="491aa-149">בנוסף, תמצא את שעת העדכון האחרון ואת מספר הפרופילים המועשרים.</span><span class="sxs-lookup"><span data-stu-id="491aa-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="491aa-150">אתה יכול לגשת לתצוגה מפורטת של כל פרופיל מועשר על ידי בחירה באפשרות **צפה בנתונים מועשרים**.</span><span class="sxs-lookup"><span data-stu-id="491aa-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="491aa-151">השלבים הבאים</span><span class="sxs-lookup"><span data-stu-id="491aa-151">Next steps</span></span>

<span data-ttu-id="491aa-152">בנה על נתוני הלקוחות המועשרים שלך.</span><span class="sxs-lookup"><span data-stu-id="491aa-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="491aa-153">צור [פלחים](segments.md) ו[מדידות](measures.md), ואפילו [יצא את הנתונים](export-destinations.md) כדי להעניק ללקוחות שלך חוויות מותאמות אישית.</span><span class="sxs-lookup"><span data-stu-id="491aa-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="491aa-154">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="491aa-154">Data privacy and compliance</span></span>

<span data-ttu-id="491aa-155">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים אל HERE Technologies, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="491aa-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="491aa-156">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא ש- HERE Technologies עומדת בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="491aa-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="491aa-157">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="491aa-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="491aa-158">מנהל המערכת של Dynamics 365 Customer Insights יכול להסיר העשרה זו בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="491aa-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
