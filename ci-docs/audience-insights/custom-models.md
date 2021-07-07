---
title: מודלי למידת מכונה מותאמים אישית | Microsoft Docs
description: עבוד עם מודלים מותאמים אישית מ- Azure Machine Learning ב- Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305634"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="add44-103">מודלי למידת מכונה מותאמים אישית</span><span class="sxs-lookup"><span data-stu-id="add44-103">Custom machine learning models</span></span>

<span data-ttu-id="add44-104">עם האפשרות **בינה** > **מודלים מותאמים אישית** תוכל לנהל זרימות עבודה על פי מודלים של למידת מכונה של Azure.</span><span class="sxs-lookup"><span data-stu-id="add44-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="add44-105">תהליכי עבודה עוזרים לך לבחור את הנתונים שמהם תרצה לייצר תובנות ולמפות את התוצאות לנתוני הלקוחות המאוחדים שלך.</span><span class="sxs-lookup"><span data-stu-id="add44-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="add44-106">לקבלת מידע נוסף אודות בניית מודלי ML מותאמים אישית, ראה [שימוש במודלים מבוססי-Azure Machine Learning](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="add44-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="add44-107">AI אחראי</span><span class="sxs-lookup"><span data-stu-id="add44-107">Responsible AI</span></span>

<span data-ttu-id="add44-108">חיזויים מספקים יכולות ליצירת חוויות לקוח טובות יותר, לשיפור יכולות עסקיות וזרמי הכנסות.</span><span class="sxs-lookup"><span data-stu-id="add44-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="add44-109">אנחנו ממליצים בחום שתאזן את הערך של החיזוי שלך מול ההשפעה שיש לו וההטיות שהוא עשוי להציג בצורה אתית.</span><span class="sxs-lookup"><span data-stu-id="add44-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="add44-110">קבל מידע נוסף על האופן שבו Microsoft [מטפלת ב- AI אחראי](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="add44-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="add44-111">באפשרותך גם לקבל מידע נוסף אודות [טכניקות ותהליכים עבור למידת מכונה אחראית](/azure/machine-learning/concept-responsible-ml) הספציפיים ל- Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="add44-111">You can also learn about [techniques and processes for responsible machine learning](/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="add44-112">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="add44-112">Prerequisites</span></span>

- <span data-ttu-id="add44-113">נכון לעכשיו, תכונה זו תומכת בשירותי אינטרנט המתפרסמים דרך [Machine Learning Studio (קלאסי)](https://studio.azureml.net) ו[קווי צינור אצווה של Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="add44-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="add44-114">אתה זקוק לחשבון אחסון של Azure Data Lake Gen2 המשויך למופע שלך ב- Azure Studio כדי להשתמש בתכונה זו.</span><span class="sxs-lookup"><span data-stu-id="add44-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="add44-115">לקבלת מידע נוסף, ראה [יצירת חשבון אחסון של Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span><span class="sxs-lookup"><span data-stu-id="add44-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](/azure/storage/blobs/data-lake-storage-quickstart-create-account).</span></span>

- <span data-ttu-id="add44-116">עבור סביבות עבודה של למידת מכונה של Azure עם צינורות, אתה זקוק להרשאות מנהל מערכת מסוג 'בעלים' או 'גישת משתמש' לסביבת העבודה של למידת המכונה של Azure.</span><span class="sxs-lookup"><span data-stu-id="add44-116">For Azure Machine Learning workspaces with pipelines, you need Owner or User Access Administrator permissions to the Azure Machine Learning Workspace.</span></span>

   > [!NOTE]
   > <span data-ttu-id="add44-117">הנתונים מועברים בין מופעי Customer Insights שלך לשירותי האינטרנט של Azure שנבחרו או לצינורות בזרימת העבודה.</span><span class="sxs-lookup"><span data-stu-id="add44-117">Data is transferred between your Customer Insights instances and the selected Azure web services or pipelines in the workflow.</span></span> <span data-ttu-id="add44-118">בעת העברת נתונים לשירות של Azure, ודא שתצורת השירות נקבעה לעיבוד נתונים באופן ובמיקום הדרושים כדי לעמוד בדרישות המשפטיות או הרגולטוריות לגבי נתונים אלה עבור הארגון שלך.</span><span class="sxs-lookup"><span data-stu-id="add44-118">When you transfer data to an Azure service, please ensure that service is configured to process data in the manner and location necessary to comply with any legal or regulatory requirements for that data for your organization.</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="add44-119">הוספת זרימת עבודה חדשה</span><span class="sxs-lookup"><span data-stu-id="add44-119">Add a new workflow</span></span>

1. <span data-ttu-id="add44-120">עבור אל **בינה** > **מודלים מותאמים אישית** ובחר **זרימת עבודה חדשה**.</span><span class="sxs-lookup"><span data-stu-id="add44-120">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="add44-121">תן לדגם המותאם אישית שם הניתן לזיהוי בשדה **שם**.</span><span class="sxs-lookup"><span data-stu-id="add44-121">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="add44-122">![צילום מסך של חלונית זרימת העבודה החדשה](media/new-workflowv2.png "צילום מסך של חלונית זרימת העבודה החדשה")</span><span class="sxs-lookup"><span data-stu-id="add44-122">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="add44-123">בחר ארגון שמכיל את שירות האינטרנט ב- **דייר שמכיל את שירות האינטרנט שלך**.</span><span class="sxs-lookup"><span data-stu-id="add44-123">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="add44-124">אם המנוי שלך ל'למידת מכונה של Azure' נמצא בדייר שונה מ- Customer Insights, בחר **התחברות** עם האישורים שלך לארגון שנבחר.</span><span class="sxs-lookup"><span data-stu-id="add44-124">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="add44-125">בחר את **סביבות עבודה** המשויכות לשירות האינטרנט שלך.</span><span class="sxs-lookup"><span data-stu-id="add44-125">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="add44-126">מופיעים שני מקטעים, אחד עבור Azure Machine Learning v1‏ (Machine Learning Studio (קלאסי)) ו- Azure Machine Learning v2‏ (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="add44-126">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="add44-127">אם אינך בטוח איזו סביבת עבודה מתאימה לשירות האינטרנט Machine Learning Studio (קלאסי) שלך, בחר **כלשהי**.</span><span class="sxs-lookup"><span data-stu-id="add44-127">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="add44-128">בחר את שירות האינטרנט Machine Learning Studio (קלאסי) או את קו הצינור Azure Machine Learning ברשימה הנפתחת **שירות אינטרנט המכיל את המודל שלך**.</span><span class="sxs-lookup"><span data-stu-id="add44-128">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="add44-129">לאחר מכן בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="add44-129">Then, select **Next**.</span></span>
   - <span data-ttu-id="add44-130">קבל מידע נוסף אודות [פרסום שירות אינטרנט ב- Machine Learning Studio (קלאסי)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="add44-130">Learn more about [publishing a web service in Machine Learning Studio (classic)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="add44-131">קבל מידע נוסף אודות [פרסום קו צינור ב- Azure Machine Learning באמצעות המעצב](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) או [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="add44-131">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> <span data-ttu-id="add44-132">עליך לפרסם את קו הצינור שלך תחת [נקודת קצה של קו צינור](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="add44-132">Your pipeline must be published under a [pipeline endpoint](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="add44-133">עבור כל **קלט של שירות אינטרנט**, בחר את **ישות** המתאימה מתוך Customer Insights ובחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="add44-133">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="add44-134">זרימת העבודה של המודל המותאם אישית תחיל היוריסטיקה למיפוי שדות הקלט של שירות האינטרנט לתכונות הישות בהתבסס על השם וסוג הנתונים של השדה.</span><span class="sxs-lookup"><span data-stu-id="add44-134">The custom model workflow will apply heuristics to map the web service input fields to the entity attributes based on the name and data type of the field.</span></span> <span data-ttu-id="add44-135">תראה שגיאה אם לא ניתן למפות שדה שירות אינטרנט לישות.</span><span class="sxs-lookup"><span data-stu-id="add44-135">You'll see an error if a web service field can't be mapped to an entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="add44-136">![קביעת תצורה של זרימת עבודה](media/intelligence-screen2-updated.png "קביעת תצורה של זרימת עבודה")</span><span class="sxs-lookup"><span data-stu-id="add44-136">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="add44-137">בשלב **פרמטרים של פלט מודל**, הגדר את המאפיינים הבאים:</span><span class="sxs-lookup"><span data-stu-id="add44-137">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="add44-138">Machine Learning Studio (קלאסי)</span><span class="sxs-lookup"><span data-stu-id="add44-138">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="add44-139">הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של שירות האינטרנט יזרמו אליו.</span><span class="sxs-lookup"><span data-stu-id="add44-139">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="add44-140">למידת מכונה של Azure</span><span class="sxs-lookup"><span data-stu-id="add44-140">Azure Machine Learning</span></span>
      1. <span data-ttu-id="add44-141">הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של קו הצינור יזרמו אליו.</span><span class="sxs-lookup"><span data-stu-id="add44-141">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="add44-142">בחר את **שם הפרמטר של מאגר נתוני הפלט** של קו הצינור של האצווה שלך מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="add44-142">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="add44-143">בחר את **שם הפרמטר של נתיב הפלט** של קו הצינור של האצווה שלך מהרשימה הנפתחת.</span><span class="sxs-lookup"><span data-stu-id="add44-143">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="add44-144">![חלונית של פרמטר פלט מודל](media/intelligence-screen3-outputparameters.png "חלונית של פרמטר פלט מודל")</span><span class="sxs-lookup"><span data-stu-id="add44-144">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="add44-145">בחר את התכונה המתאימה מתוך הרשימה הנפתחת **מזהה לקוח בתוצאות** שמזהה לקוחות ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="add44-145">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="add44-146">![קשר את התוצאות לחלונית 'נתוני לקוחות'](media/intelligence-screen4-relatetocustomer.png "קשר את התוצאות לחלונית 'נתוני לקוחות'")</span><span class="sxs-lookup"><span data-stu-id="add44-146">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="add44-147">תראה את המסך **זרימת עבודה נשמרה** עם פרטים על זרימת העבודה.</span><span class="sxs-lookup"><span data-stu-id="add44-147">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="add44-148">אם הגדרת זרימת עבודה עבור קו צינור של Azure Machine Learning‏, Audience Insights יצרף את סביבת העבודה המכילה את קו הצינור.</span><span class="sxs-lookup"><span data-stu-id="add44-148">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="add44-149">Audience Insights יקבל תפקיד **משתתף** בסביבת העבודה של Azure.</span><span class="sxs-lookup"><span data-stu-id="add44-149">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="add44-150">בחר **סיום**.</span><span class="sxs-lookup"><span data-stu-id="add44-150">Select **Done**.</span></span>

1. <span data-ttu-id="add44-151">כעת תוכל להפעיל את זרימת העבודה מהדף **מודלים מותאמים אישית**.</span><span class="sxs-lookup"><span data-stu-id="add44-151">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="add44-152">עריכת זרימת עבודה</span><span class="sxs-lookup"><span data-stu-id="add44-152">Edit a workflow</span></span>

1. <span data-ttu-id="add44-153">בדף **מודלים מותאמים אישית**, בחר את שלוש הנקודות האנכיות בעמודה **פעולות** לצד זרימת עבודה שיצרת בעבר, ובחר **ערוך**.</span><span class="sxs-lookup"><span data-stu-id="add44-153">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="add44-154">באפשרותך לעדכן את השם הניתן לזיהוי של סביבת העבודה שלך בשדה **שם התצוגה**, אבל אין באפשרותך לשנות את שירות האינטרנט או את קו הצינור המוגדרים.</span><span class="sxs-lookup"><span data-stu-id="add44-154">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="add44-155">בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="add44-155">Select **Next**.</span></span>

1. <span data-ttu-id="add44-156">עבור כל **קלט של שירות אינטרנט**, באפשרותך לעדכן את ערך **ישות** המתאים מתוך Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="add44-156">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="add44-157">לאחר מכן בחר **הבא**.</span><span class="sxs-lookup"><span data-stu-id="add44-157">Then, select **Next**.</span></span>

1. <span data-ttu-id="add44-158">בשלב **פרמטרים של פלט מודל**, הגדר את המאפיינים הבאים:</span><span class="sxs-lookup"><span data-stu-id="add44-158">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="add44-159">Machine Learning Studio (קלאסי)</span><span class="sxs-lookup"><span data-stu-id="add44-159">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="add44-160">הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של שירות האינטרנט יזרמו אליו.</span><span class="sxs-lookup"><span data-stu-id="add44-160">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="add44-161">למידת מכונה של Azure</span><span class="sxs-lookup"><span data-stu-id="add44-161">Azure Machine Learning</span></span>
      1. <span data-ttu-id="add44-162">הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של קו הצינור יזרמו אליו.</span><span class="sxs-lookup"><span data-stu-id="add44-162">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="add44-163">בחר את **שם פרמטר של מאגר נתוני פלט** עבור קו הצינור של הבדיקה שלך.</span><span class="sxs-lookup"><span data-stu-id="add44-163">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="add44-164">בחר את **שם פרמטר נתיב הפלט** עבור קו הצינור של הבדיקה שלך.</span><span class="sxs-lookup"><span data-stu-id="add44-164">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="add44-165">בחר את התכונה המתאימה מתוך הרשימה הנפתחת **מזהה לקוח בתוצאות** שמזהה לקוחות ובחר **שמור**.</span><span class="sxs-lookup"><span data-stu-id="add44-165">Select the matching attribute from the **Customer ID in results** dropdown list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="add44-166">בחר תכונה מתוך פלט המסקנה עם ערכים הדומים לעמודה 'מזהה לקוח' של הישות 'לקוח'.</span><span class="sxs-lookup"><span data-stu-id="add44-166">Choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="add44-167">אם אין עמודה כזאת בערכת הנתונים שלך, בחר תכונה המזהה באופן ייחודי את השורה.</span><span class="sxs-lookup"><span data-stu-id="add44-167">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="add44-168">הפעלת זרימת עבודה</span><span class="sxs-lookup"><span data-stu-id="add44-168">Run a workflow</span></span>

1. <span data-ttu-id="add44-169">בדף **מודלים מותאמים אישית**, בחר את שלוש הנקודות האנכיות בעמודה **פעולות** לצד זרימת עבודה שיצרת בעבר.</span><span class="sxs-lookup"><span data-stu-id="add44-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="add44-170">בחר **הפעל**.</span><span class="sxs-lookup"><span data-stu-id="add44-170">Select **Run**.</span></span>

<span data-ttu-id="add44-171">זרימת העבודה שלך פועלת גם באופן אוטומטי עם כל רענון מתוזמן.</span><span class="sxs-lookup"><span data-stu-id="add44-171">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="add44-172">קבל מידע נוסף על [הגדרת רענונים מתוזמנים](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="add44-172">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="add44-173">מחיקת זרימת עבודה</span><span class="sxs-lookup"><span data-stu-id="add44-173">Delete a workflow</span></span>

1. <span data-ttu-id="add44-174">בדף **מודלים מותאמים אישית**, בחר את שלוש הנקודות האנכיות בעמודה **פעולות** לצד זרימת עבודה שיצרת בעבר.</span><span class="sxs-lookup"><span data-stu-id="add44-174">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="add44-175">בחר **מחיקה**, ואשר את המחיקה.</span><span class="sxs-lookup"><span data-stu-id="add44-175">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="add44-176">זרימת העבודה שלך תימחק.</span><span class="sxs-lookup"><span data-stu-id="add44-176">Your workflow will be deleted.</span></span> <span data-ttu-id="add44-177">[הישות](entities.md) שנוצרה כאשר יצרת את זרימת העבודה ממשיכה להתקיים וניתן להציג אותה דרך הדף **ישויות**.</span><span class="sxs-lookup"><span data-stu-id="add44-177">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>

## <a name="results"></a><span data-ttu-id="add44-178">תוצאות</span><span class="sxs-lookup"><span data-stu-id="add44-178">Results</span></span>

<span data-ttu-id="add44-179">תוצאות מזרימת עבודה מאוחסנות בישות שהוגדרה בשלב 'פרמטר פלט המודל'.</span><span class="sxs-lookup"><span data-stu-id="add44-179">Results from a workflow are stored in the entity configured during the Model Output Parameter phase.</span></span> <span data-ttu-id="add44-180">באפשרותך לגשת לנתונים אלה מתוך [דף הישויות](entities.md) או עם [גישת API](apis.md).</span><span class="sxs-lookup"><span data-stu-id="add44-180">You can access this data from the [entities page](entities.md) or with [API access](apis.md).</span></span>

### <a name="api-access"></a><span data-ttu-id="add44-181">גישת API</span><span class="sxs-lookup"><span data-stu-id="add44-181">API Access</span></span>

<span data-ttu-id="add44-182">כדי ששאילתת OData הספציפית תקבל נתונים מישות מודל מותאמת אישית, השתמש בתבנית הבאה:</span><span class="sxs-lookup"><span data-stu-id="add44-182">For the specific OData query to get data from a custom model entity, use the following format:</span></span>

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. <span data-ttu-id="add44-183">החלף את `<your instance id>` במזהה של סביבת Customer Insights שלך, אשר תמצא בשורת הכתובת של הדפדפן שלך כאשר תקבל גישה ל- Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="add44-183">Replace `<your instance id>` with the ID of your Customer Insights environment, which you find in the in the address bar of your browser when accessing Customer Insights.</span></span>

1. <span data-ttu-id="add44-184">החלף את `<custom model output entity>` בשם הישות שסיפקת במהלך השלב 'פרמטרי פלט מודל' של תצורת המודל המותאמת אישית.</span><span class="sxs-lookup"><span data-stu-id="add44-184">Replace `<custom model output entity>` with the entity name you provided during the Model Output Parameters step of the custom model configuration.</span></span>

1. <span data-ttu-id="add44-185">החלף את `<guid value>` במזהה הלקוח של הלקוח שברצונך לגשת לרשומה עבורו.</span><span class="sxs-lookup"><span data-stu-id="add44-185">Replace `<guid value>` with the Customer ID of the customer you'd like to access the record for.</span></span> <span data-ttu-id="add44-186">בדרך כלל תוכל למצוא מזהה זה ב[דף פרופילי הלקוח](customer-profiles.md) בשדה 'מזהה לקוח'.</span><span class="sxs-lookup"><span data-stu-id="add44-186">You can usually find this ID on the [customer profiles page](customer-profiles.md) in the CustomerID field.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="add44-187">שאלות נפוצות</span><span class="sxs-lookup"><span data-stu-id="add44-187">Frequently Asked Questions</span></span>

- <span data-ttu-id="add44-188">מדוע איני יכול לראות את קו הצינור שלי בעת הגדרת זרימת עבודה מותאמת אישית של מודל?</span><span class="sxs-lookup"><span data-stu-id="add44-188">Why can't I see my pipeline when setting up a custom model workflow?</span></span>    
  <span data-ttu-id="add44-189">בעיה זו נגרמת בדרך כלל על-ידי בעיית תצורה בצינור.</span><span class="sxs-lookup"><span data-stu-id="add44-189">This issue is frequently caused by a configuration issue in the pipeline.</span></span> <span data-ttu-id="add44-190">ודא [שפרמטר הקלט מוגדר](azure-machine-learning-experiments.md#dataset-configuration) וש[פרמטרי מאגר הנתונים של הפלט והנתיב](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) מוגדרים גם הם.</span><span class="sxs-lookup"><span data-stu-id="add44-190">Ensure the [input parameter is configured](azure-machine-learning-experiments.md#dataset-configuration), and the [output datastore and path parameters](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) are also configured.</span></span>

- <span data-ttu-id="add44-191">מה משמעות השגיאה "לא ניתן לשמור זרימת עבודה של בינה"?</span><span class="sxs-lookup"><span data-stu-id="add44-191">What does the error "Couldn't save intelligence workflow" mean?</span></span>    
  <span data-ttu-id="add44-192">משתמשים רואים בדרך כלל הודעת שגיאה זו אם אין להם הרשאות מנהל מערכת מסוג 'בעלים' או 'גישת משתמש' בסביבת העבודה.</span><span class="sxs-lookup"><span data-stu-id="add44-192">Users usually see this error message if they don't have Owner or User Access Administrator privileges on the workspace.</span></span> <span data-ttu-id="add44-193">המשתמש זקוק לרמת הרשאות גבוהה יותר כדי לאפשר ל- Customer Insights לעבד את זרימת העבודה כשירות במקום להשתמש באישורי המשתמש עבור ההפעלות הבאות של זרימת העבודה.</span><span class="sxs-lookup"><span data-stu-id="add44-193">The user needs a higher level of permissions to enable Customer Insights to process the workflow as a service rather than using the user credentials for subsequent runs of the workflow.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
