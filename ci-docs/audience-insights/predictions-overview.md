---
title: סקירה כללית על תרחישי חיזוי נתמכים
description: תרחישי חיזוי ואפשרויות המכוסות על-ידי היישום Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095713"
---
# <a name="predictions-overview"></a><span data-ttu-id="d0859-103">מבט כולל על חיזויים</span><span class="sxs-lookup"><span data-stu-id="d0859-103">Predictions overview</span></span>

<span data-ttu-id="d0859-104">Dynamics 365 Customer Insights מגיע עם מגוון אפשרויות שמנצלות את AI ולמידת מכונה לחיזוי נתונים.</span><span class="sxs-lookup"><span data-stu-id="d0859-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="d0859-105">מודלים מוכנים לשימוש</span><span class="sxs-lookup"><span data-stu-id="d0859-105">Out-of-box models</span></span>

<span data-ttu-id="d0859-106">הדרך הקלה ביותר להתחיל עם חיזוי נתונים היא באמצעות מודלים מוגדרים מראש, שלעתים קרובות נקראים 'מודלים מוכנים לשימוש'.</span><span class="sxs-lookup"><span data-stu-id="d0859-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="d0859-107">כדי ליצור תובנות במהירות, נדרשים רק נתונים ומבנים מסוימים.</span><span class="sxs-lookup"><span data-stu-id="d0859-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="d0859-108">נכון לעכשיו, המודלים הבאים זמינים:</span><span class="sxs-lookup"><span data-stu-id="d0859-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="d0859-109">[‏‫‏‫ערך אורך החיים של הלקוח‬](predict-customer-lifetime-value.md): חוזה את ההכנסות הפוטנציאליות של לקוח לאורך כל האינטראקציה עם עסק.</span><span class="sxs-lookup"><span data-stu-id="d0859-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="d0859-110">[המלצת מוצר](predict-product-recommendation.md): מציע קבוצה של המלצות תחזיתיות למוצרים בהתבסס על התנהגות רכישה ולקוחות עם דפוסי רכישה דומים.</span><span class="sxs-lookup"><span data-stu-id="d0859-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="d0859-111">[נטישת מנויים](predict-subscription-churn.md): חוזה אם קיימת סכנה שלקוח לא ישתמש עוד במוצרי המנוי או בשירותי המנוי של החברה שלך.</span><span class="sxs-lookup"><span data-stu-id="d0859-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="d0859-112">[נטישה של עסקאות‬‏‫](predict-transactional-churn.md): חוזה אם לקוח לא ירכוש עוד את המוצרים או השירותים שלך במסגרת זמן מסוימת.</span><span class="sxs-lookup"><span data-stu-id="d0859-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="d0859-113">שילוב למידת מכונה של Azure</span><span class="sxs-lookup"><span data-stu-id="d0859-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="d0859-114">אם ארגון כבר משתמש בתרחישי למידת מכונה המבוססים על חוויות למידת מכונה של Azure, תכונת המודלים המותאמים אישית ב- Customer Insights עוזרת לחבר את הנקודות.</span><span class="sxs-lookup"><span data-stu-id="d0859-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="d0859-115">צור זרימות עבודה שיעזרו לך לבחור את הנתונים שמהם ברצונך לייצר תובנות ולמפות את התוצאות לפרופילי הלקוחות המאוחדים שלך.</span><span class="sxs-lookup"><span data-stu-id="d0859-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="d0859-116">למידע נוסף ראה [דגמי למידת מכונה מותאמים אישית](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="d0859-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="d0859-117">חיזוי של AI Builder</span><span class="sxs-lookup"><span data-stu-id="d0859-117">AI Builder prediction</span></span>

<span data-ttu-id="d0859-118">לפעמים ערכות נתונים אינן שלמות וחסרים בהן ערכים מסוימים.</span><span class="sxs-lookup"><span data-stu-id="d0859-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="d0859-119">Customer Insights יכול לסייע בחיזוי ערכים חסרים עבור ישות הלקוח והפלחים.</span><span class="sxs-lookup"><span data-stu-id="d0859-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="d0859-120">למידע נוסף, ראה [השלמת נתונים חלקיים בעזרת חיזויים](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="d0859-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
