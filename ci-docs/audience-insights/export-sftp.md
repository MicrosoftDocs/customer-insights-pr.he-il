---
title: ייצוא נתוני Customer Insights אל מארחי SPTF
description: למד כיצד להגדיר את החיבור אל מארח SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643504"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="26860-103">מחבר עבור SFTP‏ (Preview)</span><span class="sxs-lookup"><span data-stu-id="26860-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="26860-104">השתמש בנתוני הלקוחות שלך ביישומי צד שלישי על-ידי ייצוא שלהם אל מארח Secure File Transfer Protocol‏ (SFTP).</span><span class="sxs-lookup"><span data-stu-id="26860-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26860-105">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="26860-105">Prerequisites</span></span>

- <span data-ttu-id="26860-106">זמינות של מארח SFTP ואישורים מתאימים.</span><span class="sxs-lookup"><span data-stu-id="26860-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="26860-107">התחברות ל- SFTP</span><span class="sxs-lookup"><span data-stu-id="26860-107">Connect to SFTP</span></span>

1. <span data-ttu-id="26860-108">עבור אל **מנהל** > **יעדי ייצוא**.</span><span class="sxs-lookup"><span data-stu-id="26860-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="26860-109">ב- **SFTP**, בחר **הגדר**.</span><span class="sxs-lookup"><span data-stu-id="26860-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="26860-110">תן ליעד שלך שם הניתן לזיהוי בשדה **שם תצוגה**.</span><span class="sxs-lookup"><span data-stu-id="26860-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="26860-111">ספק **שם משתמש**, **סיסמה** ו **שם מארח** עבור חשבון SPTF שלך.</span><span class="sxs-lookup"><span data-stu-id="26860-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="26860-112">דוגמה: אם תיקיית הבסיס של שרת SPTF שלך היא /root/folder, וברצונך לבצע ייצוא של הנתונים אל /root/folder/ci_export_destination_folder, המארח צריך להיות sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="26860-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="26860-113">בחר **אימות** כדי לבדוק את החיבור.</span><span class="sxs-lookup"><span data-stu-id="26860-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="26860-114">לאחר אימות מוצלח, בחר אם ברצונך לייצא את הנתונים כשהם **מכווצים** או **לא מכווצים**, ובחר את **מפריד בין שדות** עבור הקבצים המיוצאים.</span><span class="sxs-lookup"><span data-stu-id="26860-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="26860-115">בחר **אני מסכים** כדי לאשר **פרטיות ותאימות נתונים**.</span><span class="sxs-lookup"><span data-stu-id="26860-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="26860-116">בחר **הבא** כדי להתחיל בהגדרת הייצוא.</span><span class="sxs-lookup"><span data-stu-id="26860-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="26860-117">הגדרת החיבור</span><span class="sxs-lookup"><span data-stu-id="26860-117">Configure the connection</span></span>

1. <span data-ttu-id="26860-118">בחר **תכונות לקוח** שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="26860-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="26860-119">ניתן לייצא תכונה אחת או כמה תכונות.</span><span class="sxs-lookup"><span data-stu-id="26860-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="26860-120">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="26860-120">Select **Next**.</span></span>

1. <span data-ttu-id="26860-121">בחר את הפלחים שברצונך לייצא.</span><span class="sxs-lookup"><span data-stu-id="26860-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="26860-122">בחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="26860-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="26860-123">ייצוא הנתונים</span><span class="sxs-lookup"><span data-stu-id="26860-123">Export the data</span></span>

<span data-ttu-id="26860-124">באפשרותך [לייצא נתונים לפי דרישה](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="26860-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="26860-125">הייצוא יפעל גם בכל [רענון מתוזמן](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="26860-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="26860-126">פרטיות ותאימות של נתונים</span><span class="sxs-lookup"><span data-stu-id="26860-126">Data privacy and compliance</span></span>

<span data-ttu-id="26860-127">כאשר אתה מאפשר ל- Dynamics 365 Customer Insights להפיץ נתונים דרך SPTF, אתה מאפשר העברת נתונים מחוץ לגבול התאימות עבור Dynamics 365 Customer Insights, כולל נתונים שעשויים להיות רגישים כגון 'נתונים אישיים'.</span><span class="sxs-lookup"><span data-stu-id="26860-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="26860-128">Microsoft תעביר נתונים אלה בהוראתך, אבל אתה אחראי לוודא שיעד הייצוא עומד בכל התחייבויות הפרטיות או האבטחה שעשויות להיות לך.</span><span class="sxs-lookup"><span data-stu-id="26860-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="26860-129">לקבלת מידע נוסף, עיין ב[הצהרת הפרטיות של Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="26860-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="26860-130">מנהל המערכת של Dynamics 365 Customer Insights שלך יכול להסיר יעד ייצוא זה בכל עת כדי להפסיק את השימוש בפונקציונליות זו.</span><span class="sxs-lookup"><span data-stu-id="26860-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
