---
title: מודלי למידת מכונה מותאמים אישית | Microsoft Docs
description: עבוד עם מודלים מותאמים אישית מ- Azure Machine Learning ב- Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267235"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="f67f7-103">מודלי למידת מכונה מותאמים אישית</span><span class="sxs-lookup"><span data-stu-id="f67f7-103">Custom machine learning models</span></span>

<span data-ttu-id="f67f7-104">עם האפשרות **בינה** > **מודלים מותאמים אישית** תוכל לנהל זרימות עבודה על פי מודלים של למידת מכונה של Azure.</span><span class="sxs-lookup"><span data-stu-id="f67f7-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="f67f7-105">תהליכי עבודה עוזרים לך לבחור את הנתונים שמהם תרצה לייצר תובנות ולמפות את התוצאות לנתוני הלקוחות המאוחדים שלך.</span><span class="sxs-lookup"><span data-stu-id="f67f7-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="f67f7-106">לקבלת מידע נוסף אודות בניית מודלי ML מותאמים אישית, ראה [שימוש במודלים מבוססי-Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="f67f7-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="f67f7-107">AI אחראי</span><span class="sxs-lookup"><span data-stu-id="f67f7-107">Responsible AI</span></span>

<span data-ttu-id="f67f7-108">חיזויים מספקים יכולות ליצירת חוויות לקוח טובות יותר, לשיפור יכולות עסקיות וזרמי הכנסות.</span><span class="sxs-lookup"><span data-stu-id="f67f7-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="f67f7-109">אנחנו ממליצים בחום שתאזן את הערך של החיזוי שלך מול ההשפעה שיש לו וההטיות שהוא עשוי להציג בצורה אתית.</span><span class="sxs-lookup"><span data-stu-id="f67f7-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="f67f7-110">קבל מידע נוסף על האופן שבו Microsoft [מטפלת ב- AI אחראי](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="f67f7-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="f67f7-111">באפשרותך גם לקבל מידע נוסף אודות [טכניקות ותהליכים עבור למידת מכונה אחראית](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) הספציפיים ל- Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="f67f7-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f67f7-112">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="f67f7-112">Prerequisites</span></span>

- <span data-ttu-id="f67f7-113">נכון לעכשיו, תכונה זו תומכת בשירותי אינטרנט המתפרסמים דרך [Machine Learning Studio (קלאסי)](https://studio.azureml.net) ו[קווי צינור אצווה של Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="f67f7-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="f67f7-114">אתה זקוק לחשבון אחסון של Azure Data Lake Gen2 המשויך למופע שלך ב- Azure Studio כדי להשתמש בתכונה זו.</span><span class="sxs-lookup"><span data-stu-id="f67f7-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="f67f7-115">לקבלת מידע נוסף, ראה [יצירת חשבון אחסון של Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="f67f7-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="f67f7-116">הוספת זרימת עבודה חדשה</span><span class="sxs-lookup"><span data-stu-id="f67f7-116">Add a new workflow</span></span>

1. <span data-ttu-id="f67f7-117">עבור אל **בינה** > **מודלים מותאמים אישית** ובחר **זרימת עבודה חדשה**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="f67f7-118">תן לדגם המותאם אישית שם הניתן לזיהוי בשדה **שם**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f67f7-119">![צילום מסך של חלונית זרימת העבודה החדשה](media/new-workflowv2.png "צילום מסך של חלונית זרימת העבודה החדשה")</span><span class="sxs-lookup"><span data-stu-id="f67f7-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="f67f7-120">בחר ארגון שמכיל את שירות האינטרנט ב- **דייר שמכיל את שירות האינטרנט שלך**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="f67f7-121">אם המנוי שלך ל'למידת מכונה של Azure' נמצא בדייר שונה מ- Customer Insights, בחר **התחברות** עם האישורים שלך לארגון שנבחר.</span><span class="sxs-lookup"><span data-stu-id="f67f7-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="f67f7-122">בחר את **סביבות עבודה** המשויכות לשירות האינטרנט שלך.</span><span class="sxs-lookup"><span data-stu-id="f67f7-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="f67f7-123">מופיעים שני מקטעים, אחד עבור Azure Machine Learning v1‏ (Machine Learning Studio (קלאסי)) ו- Azure Machine Learning v2‏ (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="f67f7-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="f67f7-124">אם אינך בטוח איזו סביבת עבודה מתאימה לשירות האינטרנט Machine Learning Studio (קלאסי) שלך, בחר **כלשהי**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="f67f7-125">בחר את שירות האינטרנט Machine Learning Studio (קלאסי) או את קו הצינור Azure Machine Learning ברשימה הנפתחת **שירות אינטרנט המכיל את המודל שלך**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="f67f7-126">לאחר מכן בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="f67f7-127">קבל מידע נוסף אודות [פרסום שירות אינטרנט ב- Machine Learning Studio (קלאסי)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="f67f7-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="f67f7-128">קבל מידע נוסף אודות [פרסום קו צינור ב- Azure Machine Learning באמצעות המעצב](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) או [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="f67f7-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="f67f7-129">עליך לפרסם את קו הצינור שלך תחת [נקודת קצה של קו צינור](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="f67f7-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="f67f7-130">עבור כל **קלט של שירות אינטרנט**, בחר את **ישות** המתאימה מתוך Customer Insights ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="f67f7-131">זרימת העבודה של המודל המותאם אישית תחיל היוריסטיקה למיפוי שדות הקלט של שירות האינטרנט לתכונות הישות בהתבסס על השם וסוג הנתונים של השדה.</span><span class="sxs-lookup"><span data-stu-id="f67f7-131">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="f67f7-132">תראה שגיאה אם לא ניתן למפות שדה שירות אינטרנט לישות.</span><span class="sxs-lookup"><span data-stu-id="f67f7-132">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f67f7-133">![קביעת תצורה של זרימת עבודה](media/intelligence-screen2-updated.png "קביעת תצורה של זרימת עבודה")</span><span class="sxs-lookup"><span data-stu-id="f67f7-133">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>
   
1. <span data-ttu-id="f67f7-134">בשלב **פרמטרים של פלט מודל**, הגדר את המאפיינים הבאים:</span><span class="sxs-lookup"><span data-stu-id="f67f7-134">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="f67f7-135">Machine Learning Studio (קלאסי)</span><span class="sxs-lookup"><span data-stu-id="f67f7-135">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="f67f7-136">הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של שירות האינטרנט יזרמו אליו.</span><span class="sxs-lookup"><span data-stu-id="f67f7-136">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="f67f7-137">למידת מכונה של Azure</span><span class="sxs-lookup"><span data-stu-id="f67f7-137">Azure Machine Learning</span></span>
      1. <span data-ttu-id="f67f7-138">הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של קו הצינור יזרמו אליו.</span><span class="sxs-lookup"><span data-stu-id="f67f7-138">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="f67f7-139">בחר את **שם הפרמטר של מאגר נתוני הפלט** של קו הצינור של האצווה שלך מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="f67f7-139">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="f67f7-140">בחר את **שם הפרמטר של נתיב הפלט** של קו הצינור של האצווה שלך מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="f67f7-140">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="f67f7-141">![חלונית של פרמטר פלט מודל](media/intelligence-screen3-outputparameters.png "חלונית של פרמטר פלט מודל")</span><span class="sxs-lookup"><span data-stu-id="f67f7-141">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="f67f7-142">בחר את התכונה המתאימה מתוך הרשימה הנפתחת **מזהה לקוח בתוצאות** אשר מזהה לקוחות ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-142">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="f67f7-143">![קשר את התוצאות לחלונית 'נתוני לקוחות'](media/intelligence-screen4-relatetocustomer.png "קשר את התוצאות לחלונית 'נתוני לקוחות'")</span><span class="sxs-lookup"><span data-stu-id="f67f7-143">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="f67f7-144">תראה את המסך **זרימת עבודה נשמרה** עם פרטים על זרימת העבודה.</span><span class="sxs-lookup"><span data-stu-id="f67f7-144">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="f67f7-145">אם הגדרת זרימת עבודה עבור קו צינור של Azure Machine Learning‏, Audience Insights יצרף את סביבת העבודה המכילה את קו הצינור.</span><span class="sxs-lookup"><span data-stu-id="f67f7-145">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="f67f7-146">Audience Insights יקבל תפקיד **משתתף** בסביבת העבודה של Azure.</span><span class="sxs-lookup"><span data-stu-id="f67f7-146">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="f67f7-147">בחר **סיום**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-147">Select **Done**.</span></span>

1. <span data-ttu-id="f67f7-148">כעת תוכל להפעיל את זרימת העבודה מהדף **מודלים מותאמים אישית**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-148">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="f67f7-149">עריכת זרימת עבודה</span><span class="sxs-lookup"><span data-stu-id="f67f7-149">Edit a workflow</span></span>

1. <span data-ttu-id="f67f7-150">בדף **מודלים מותאמים אישית**, בחר את שלוש הנקודות האנכיות בעמודה **פעולות** לצד זרימת עבודה שיצרת בעבר, ובחר **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-150">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="f67f7-151">באפשרותך לעדכן את השם הניתן לזיהוי של סביבת העבודה שלך בשדה **שם התצוגה**, אבל אין באפשרותך לשנות את שירות האינטרנט או את קו הצינור המוגדרים.</span><span class="sxs-lookup"><span data-stu-id="f67f7-151">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="f67f7-152">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-152">Select **Next**.</span></span>

1. <span data-ttu-id="f67f7-153">עבור כל **קלט של שירות אינטרנט**, באפשרותך לעדכן את ערך **ישות** המתאים מתוך Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f67f7-153">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="f67f7-154">לאחר מכן בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-154">Then, select **Next**.</span></span>

1. <span data-ttu-id="f67f7-155">בשלב **פרמטרים של פלט מודל**, הגדר את המאפיינים הבאים:</span><span class="sxs-lookup"><span data-stu-id="f67f7-155">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="f67f7-156">Machine Learning Studio (קלאסי)</span><span class="sxs-lookup"><span data-stu-id="f67f7-156">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="f67f7-157">הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של שירות האינטרנט יזרמו אליו.</span><span class="sxs-lookup"><span data-stu-id="f67f7-157">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="f67f7-158">למידת מכונה של Azure</span><span class="sxs-lookup"><span data-stu-id="f67f7-158">Azure Machine Learning</span></span>
      1. <span data-ttu-id="f67f7-159">הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של קו הצינור יזרמו אליו.</span><span class="sxs-lookup"><span data-stu-id="f67f7-159">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="f67f7-160">בחר את **שם פרמטר של מאגר נתוני פלט** עבור קו הצינור של הבדיקה שלך.</span><span class="sxs-lookup"><span data-stu-id="f67f7-160">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="f67f7-161">בחר את **שם פרמטר נתיב הפלט** עבור קו הצינור של הבדיקה שלך.</span><span class="sxs-lookup"><span data-stu-id="f67f7-161">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="f67f7-162">בחר את התכונה המתאימה מתוך הרשימה הנפתחת **מזהה לקוח בתוצאות** אשר מזהה לקוחות ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-162">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="f67f7-163">עליך לבחור תכונה מתוך פלט המסקנה עם ערכים הדומים לעמודה 'מזהה לקוח' של הישות 'לקוח'.</span><span class="sxs-lookup"><span data-stu-id="f67f7-163">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="f67f7-164">אם אין עמודה כזאת בערכת הנתונים שלך, בחר תכונה המזהה באופן ייחודי את השורה.</span><span class="sxs-lookup"><span data-stu-id="f67f7-164">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="f67f7-165">הפעלת זרימת עבודה</span><span class="sxs-lookup"><span data-stu-id="f67f7-165">Run a workflow</span></span>

1. <span data-ttu-id="f67f7-166">בדף **מודלים מותאמים אישית**, בחר את שלוש הנקודות האנכיות בעמודה **פעולות** לצד זרימת עבודה שיצרת בעבר.</span><span class="sxs-lookup"><span data-stu-id="f67f7-166">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="f67f7-167">בחר **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-167">Select **Run**.</span></span>

<span data-ttu-id="f67f7-168">זרימת העבודה שלך פועלת גם באופן אוטומטי עם כל רענון מתוזמן.</span><span class="sxs-lookup"><span data-stu-id="f67f7-168">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="f67f7-169">קבל מידע נוסף על [הגדרת רענונים מתוזמנים](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f67f7-169">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="f67f7-170">מחיקת זרימת עבודה</span><span class="sxs-lookup"><span data-stu-id="f67f7-170">Delete a workflow</span></span>

1. <span data-ttu-id="f67f7-171">בדף **מודלים מותאמים אישית**, בחר את שלוש הנקודות האנכיות בעמודה **פעולות** לצד זרימת עבודה שיצרת בעבר.</span><span class="sxs-lookup"><span data-stu-id="f67f7-171">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="f67f7-172">בחר **מחיקה**, ואשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="f67f7-172">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="f67f7-173">זרימת העבודה שלך תימחק.</span><span class="sxs-lookup"><span data-stu-id="f67f7-173">Your workflow will be deleted.</span></span> <span data-ttu-id="f67f7-174">[הישות](entities.md) שנוצרה כאשר יצרת את זרימת העבודה ממשיכה להתקיים וניתן להציג אותה דרך הדף **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="f67f7-174">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]