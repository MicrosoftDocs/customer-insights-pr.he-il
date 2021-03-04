---
title: ייצוא נתוני Customer Insights אל מארחי SPTF
description: למד כיצד להגדיר את החיבור אל מארח SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267999"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="3cf76-103">מחבר עבור SFTP‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="3cf76-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="3cf76-104">השתמש בנתוני הלקוחות שלך ביישומי צד שלישי על-ידי ייצוא שלהם אל מארח Secure File Transfer Protocol‏ (SFTP).</span><span class="sxs-lookup"><span data-stu-id="3cf76-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3cf76-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="3cf76-105">Prerequisites</span></span>

- <span data-ttu-id="3cf76-106">זמינות של מארח SFTP ואישורים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="3cf76-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="3cf76-107">התחבר ל- SFTP</span><span class="sxs-lookup"><span data-stu-id="3cf76-107">Connect to SFTP</span></span>

1. <span data-ttu-id="3cf76-108">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="3cf76-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="3cf76-109">ב- **SFTP**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="3cf76-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="3cf76-110">תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="3cf76-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="3cf76-111">ספק **שם משתמש**, **סיסמה**, **שם מארח** ו **תיקיית ייצוא** עבור חשבון SFTP שלך.</span><span class="sxs-lookup"><span data-stu-id="3cf76-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="3cf76-112">בחר **אימות** כדי לבדוק את החיבור.</span><span class="sxs-lookup"><span data-stu-id="3cf76-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="3cf76-113">לאחר האימות המוצלח, בחר אם ברצונך לייצא את הנתונים שלך כשהם **דחוסים** או **לא דחוסים** ובחר את **מפריד השדה** עבור הקבצים המיוצאים.</span><span class="sxs-lookup"><span data-stu-id="3cf76-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="3cf76-114">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="3cf76-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3cf76-115">בחר **הבא** כדי להתחיל בהגדרת הייצוא.</span><span class="sxs-lookup"><span data-stu-id="3cf76-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="3cf76-116">קביעת תצורה של הייצוא</span><span class="sxs-lookup"><span data-stu-id="3cf76-116">Configure the export</span></span>

1. <span data-ttu-id="3cf76-117">בחר את הישויות, לדוגמה פלחים, שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="3cf76-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3cf76-118">כל ישות שנבחרה תכלול עד חמישה קבצי פלט בעת הייצוא.</span><span class="sxs-lookup"><span data-stu-id="3cf76-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="3cf76-119">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="3cf76-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="3cf76-120">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="3cf76-120">Export the data</span></span>

<span data-ttu-id="3cf76-121">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="3cf76-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="3cf76-122">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3cf76-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3cf76-123">מגבלות ידועות</span><span class="sxs-lookup"><span data-stu-id="3cf76-123">Known limitations</span></span>

- <span data-ttu-id="3cf76-124">זמן הריצה של ייצוא תלוי בביצועי המערכת שלך.</span><span class="sxs-lookup"><span data-stu-id="3cf76-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="3cf76-125">מומלץ שתי ליבות CPU וזיכרון של 1‎ GB כתצורה מינימלית עבור השרת שלך.</span><span class="sxs-lookup"><span data-stu-id="3cf76-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="3cf76-126">ייצוא ישויות עם עד 100 מיליון פרופילי לקוחות יכול להימשך 90 דקות בעת שימוש בתצורה המינימלית המומלצת של שתי ליבות CPU וזיכרון של 1‎ GB.</span><span class="sxs-lookup"><span data-stu-id="3cf76-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3cf76-127">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="3cf76-127">Data privacy and compliance</span></span>

<span data-ttu-id="3cf76-128">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים דרך SPTF, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="3cf76-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3cf76-129">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא שיעד הייצוא עומד בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="3cf76-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3cf76-130">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3cf76-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3cf76-131">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="3cf76-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]