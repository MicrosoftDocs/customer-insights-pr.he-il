---
title: משימות משותפות לתרחישי חיזוי
description: למד כיצד לנהל, לפתור ולשכלל חיזויים.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315879"
---
# <a name="manage-predictions"></a><span data-ttu-id="8f0b6-103">ניהול חיזויים</span><span class="sxs-lookup"><span data-stu-id="8f0b6-103">Manage predictions</span></span>

<span data-ttu-id="8f0b6-104">מאמר זה עוסק בכמה מהמשימות המשותפות לרוב תרחישי החיזוי.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="8f0b6-105">פתור בעיה של חיזוי שנכשל</span><span class="sxs-lookup"><span data-stu-id="8f0b6-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="8f0b6-106">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="8f0b6-107">בחר את שלוש הנקודות האנכיות לצד התחזית שברצונך להציג יומני שגיאה עבורה.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="8f0b6-108">בחר **יומנים**.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-108">Select **Logs**.</span></span>

1. <span data-ttu-id="8f0b6-109">סקירת כל השגיאות.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-109">Review all the errors.</span></span> <span data-ttu-id="8f0b6-110">יש מספר סוגים של שגיאות שיכולות להתרחש, והם מתארים איזה מצב גרם לשגיאה.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="8f0b6-111">לדוגמה, שגיאה כי אין מספיק נתונים כדי לחזות במדויק נפתרת בדרך כלל על ידי טעינת נתונים נוספים ל- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="8f0b6-112">דוח שימושיות של נתוני קלט</span><span class="sxs-lookup"><span data-stu-id="8f0b6-112">Input data usability report</span></span>

<span data-ttu-id="8f0b6-113">דוח השימושיות של נתוני הקלט מספק תצוגה מאוחדת של השגיאות והאזהרות שהחיזויים המוכנים לשימוש עלולים ליצור.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="8f0b6-114">הוא מציג גם המלצות לשיפור ביצועי המודל.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="8f0b6-115">הדוח זמין לאחר שהמודל השלים את תהליך ההדרכה שלו.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="8f0b6-116">הוא נוצר עבור כל מודל בנפרד, בין אם הוא הושלם בהצלחה ובין אם לאו.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="8f0b6-117">הצגת דוח השימושיות של נתוני הקלט</span><span class="sxs-lookup"><span data-stu-id="8f0b6-117">View the input data usability report</span></span>

<span data-ttu-id="8f0b6-118">לאחר שמודל מוכן לשימוש השלים את שלב ההדרכה שלו, הצג את הדוח:</span><span class="sxs-lookup"><span data-stu-id="8f0b6-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="8f0b6-119">בחר בשלוש נקודות לצד שם המודל ובחר **דוח השימושיות של נתוני הקלט**.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="8f0b6-120">בחר את המצב של מודל ולאחר מכן בחר **‏‫הצג דוח שימושיות של נתוני קלט‬** בחלונית הצדדית.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="8f0b6-121">בחירה באחד המודלים ברשימה ובחר **‏‫דוח שימושיות של נתוני קלט‬** בשורת הפקודה.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="8f0b6-122">פתח את דף תוצאות המודל ובחר **‏‫דוח שימושיות של נתוני קלט‬** בשורת הפקודה.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="8f0b6-123">מידע בדוח השימושיות של נתוני הקלט</span><span class="sxs-lookup"><span data-stu-id="8f0b6-123">Information in the input data usability report</span></span>

<span data-ttu-id="8f0b6-124">העמודות הבאות בדוח מכילות מידע מועיל לשיפור הנתונים עבור המודל.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="דוגמה לדוח שימושיות של נתוני הקלט מציגה טבלה עם שגיאות, אזהרות והמלצות.":::

- <span data-ttu-id="8f0b6-126">שם: שם תיאורי של השגיאה, האזהרה או ההמלצה.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="8f0b6-127">שלב: שלב המודל, ההדרכה או הניקוד שאליהם מתייחס המידע.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="8f0b6-128">מצב: דרגת החומרה של המידע (שגיאה, אזהרה, המלצה).</span><span class="sxs-lookup"><span data-stu-id="8f0b6-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="8f0b6-129">שם עמודה: העמודה בישות שאותה צריך לשנות כדי לשפר את ביצועי המודל.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="8f0b6-130">שם ישות: שם הישות שצריך לשנות כדי לשפר את ביצועי המודל.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="8f0b6-131">פרטים: פרטים על השגיאה, האזהרה או ההמלצה.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="8f0b6-132">רענן חיזוי</span><span class="sxs-lookup"><span data-stu-id="8f0b6-132">Refresh a prediction</span></span>

<span data-ttu-id="8f0b6-133">החיזוי יחודש באופן אוטומטי באותו [תזמון של רענון הנתונים](system.md#schedule-tab) כפי שהוגדר בהגדרות.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="8f0b6-134">באפשרותך לרענן אותם גם באופן ידני.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="8f0b6-135">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="8f0b6-136">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך לרענן.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="8f0b6-137">בחר **רענן**.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="8f0b6-138">מחק חיזוי</span><span class="sxs-lookup"><span data-stu-id="8f0b6-138">Delete a prediction</span></span>

<span data-ttu-id="8f0b6-139">מחיקת חיזוי גם מסירה את ישות הפלט שלו.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="8f0b6-140">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="8f0b6-141">בחר בשלוש הנקודות האנכיות לצד החיזוי שברצונך למחוק.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="8f0b6-142">בחר **מחק**.</span><span class="sxs-lookup"><span data-stu-id="8f0b6-142">Select **Delete**.</span></span>
