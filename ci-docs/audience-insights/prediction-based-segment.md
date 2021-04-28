---
title: פלחים המבוססים על פלט חיזוי
description: צור פלחים המבוססים על ישות הפלט של מודל חיזוי.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741430"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="ba1d5-103">יצירת פלח המבוסס על מודל חיזוי (Preview)</span><span class="sxs-lookup"><span data-stu-id="ba1d5-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="ba1d5-104">תוצאות החיזויים חלות לפעמים רק על ערכת משנה של הלקוחות שלך.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="ba1d5-105">הגדל את ההתאמה האישית של ההמלצות על-ידי יצירת פלחים מתוצאות של מודלי חיזוי.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="ba1d5-106">לדוגמה, ייתכן שתרצה לתת המלצות ספציפיות ללקוחות שמעדיפים סוג מסוים של שירות.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="ba1d5-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="ba1d5-107">Prerequisites</span></span>

- <span data-ttu-id="ba1d5-108">לפחות [הרשאות משתתף](permissions.md) ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="ba1d5-109">המלצה על מוצר, נטישת עסקאות, נטישת מנויים, או מודל ערך אורך חיים של לקוח מוגדרים ב- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="ba1d5-110">סקור את הדרישות להגדרת המודלים השונים:</span><span class="sxs-lookup"><span data-stu-id="ba1d5-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="ba1d5-111">מודל המלצות על מוצרים</span><span class="sxs-lookup"><span data-stu-id="ba1d5-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="ba1d5-112">מודל נטישת מנויים</span><span class="sxs-lookup"><span data-stu-id="ba1d5-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="ba1d5-113">מודל נטישה של עסקאות</span><span class="sxs-lookup"><span data-stu-id="ba1d5-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="ba1d5-114">מודך ערך אורך החיים של הלקוח</span><span class="sxs-lookup"><span data-stu-id="ba1d5-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="ba1d5-115">יצירת פלח לקוחות המבוסס על חיזויים</span><span class="sxs-lookup"><span data-stu-id="ba1d5-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="ba1d5-116">עבור אל **בינה** > **חיזויים** ובחר את הכרטיסיה **החיזויים שלי**.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="ba1d5-117">בחר את שלוש הנקודות האנכיות לצד המודל שברצונך לסקור ובחר **הצג**.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="ba1d5-118">בדף התוצאות, בחר **צור פלח**.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="ba1d5-119">לקבלת מידע נוסף על דף התוצאות, סקור את המאמר אודות המודל.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="צילום מסך של דף תוצאות החיזוי עם הדגשה על פעולת יצירת הפלח.":::

1. <span data-ttu-id="ba1d5-121">צור פלח חדש המבוסס על ישות הפלט של המודל שנבחר.</span><span class="sxs-lookup"><span data-stu-id="ba1d5-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="ba1d5-122">למידע נוסף: [יצירה וניהול של פלחים](segments.md).</span><span class="sxs-lookup"><span data-stu-id="ba1d5-122">For more information, see [Create and manage segments](segments.md).</span></span>