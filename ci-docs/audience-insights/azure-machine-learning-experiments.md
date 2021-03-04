---
title: ניסויי Azure Machine Learning
description: השתמש במודלים מבוססי Azure Machine Learning ב- Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: mhart
ms.reviewer: m-hartmann
manager: shellyha
ms.openlocfilehash: c166015b92596da0c6097e3d25e89579a5186ce0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267907"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="18733-103">שימוש במודלים מבוססי Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="18733-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="18733-104">הנתונים המאוחדים ב- Dynamics 365 Customer Insights הם מקור לבניית מודלי למידת מכונה שיכולים ליצור תובנות עסקיות נוספות.</span><span class="sxs-lookup"><span data-stu-id="18733-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="18733-105">Customer Insights משתלב עם Machine Learning Studio (קלאסי) ו- Azure Maching Learning כדי להשתמש במודלים המותאמים אישית שלך.</span><span class="sxs-lookup"><span data-stu-id="18733-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="18733-106">עיין ב[ניסויי Machine Learning Studio (קלאסי)](machine-learning-studio-experiments.md) לקבלת דוגמאות של ניסויים המוכללים ב- Machine Learning Studio (קלאסי).</span><span class="sxs-lookup"><span data-stu-id="18733-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="18733-107">דרישות מוקדמות</span><span class="sxs-lookup"><span data-stu-id="18733-107">Prerequisites</span></span>

- <span data-ttu-id="18733-108">גישה ל- Customer Insights</span><span class="sxs-lookup"><span data-stu-id="18733-108">Access to Customer Insights</span></span>
- <span data-ttu-id="18733-109">מנוי Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="18733-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="18733-110">פרופילי לקוחות מאוחדים</span><span class="sxs-lookup"><span data-stu-id="18733-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="18733-111">[ייצוא ישות אל אחסון Blob של Azure](export-azure-blob-storage.md) מוגדר</span><span class="sxs-lookup"><span data-stu-id="18733-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="18733-112">הגדרת סביבת עבודה של Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="18733-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="18733-113">ראה [יצירת סביבת עבודה של Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) עבור אפשרויות שונות ליצירת סביבת העבודה.</span><span class="sxs-lookup"><span data-stu-id="18733-113">See [create a Azure Machine Learning workspace](https://docs.microsoft.com/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="18733-114">לקבלת הביצועים הטובים ביותר, צור את סביבת העבודה באזור Azure הקרוב ביותר מבחינה גיאוגרפית לסביבת Customer Insights שלך.</span><span class="sxs-lookup"><span data-stu-id="18733-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="18733-115">קבל גישה לסביבת העבודה שלך דרך [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="18733-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="18733-116">קיימות מספר [דרכים לקיום אינטראקציה](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) עם סביבת העבודה שלך.</span><span class="sxs-lookup"><span data-stu-id="18733-116">There are several [ways to interact](https://docs.microsoft.com/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="18733-117">עבודה עם Azure Machine Learning designer</span><span class="sxs-lookup"><span data-stu-id="18733-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="18733-118">Azure Machine Learning Designer מספק בד ציור חזותי שבו ניתן לגרור ולשחרר ערכות נתונים ומודולים, בדומה ל- Machine Learning Studio (קלאסי).</span><span class="sxs-lookup"><span data-stu-id="18733-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="18733-119">ניתן לשלב קו צינור של אצווה שנוצר מה- Designer ב- Customer Insights, אם הוא מוגדר בהתאם.</span><span class="sxs-lookup"><span data-stu-id="18733-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="18733-120">עבודה עם SDK של Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="18733-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="18733-121">מדעני נתונים ומפתחי AI משתמשים ב- [SDK של Azure Machine Learning](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) כדי לבנות זרימות עבודה של למידת מכונה.</span><span class="sxs-lookup"><span data-stu-id="18733-121">Data scientists and AI developers use the [Azure Machine Learning SDK](https://docs.microsoft.com/python/api/overview/azure/ml/?view=azure-ml-py&preserve-view=true) to build machine learning workflows.</span></span> <span data-ttu-id="18733-122">נכון לעכשיו, לא ניתן לשלב מודלים שהוכשרו באמצעות ה- SDK ישירות עם Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="18733-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="18733-123">קו צינור של היסק אצווה המשתמש במודל זה נדרש עבור שילוב עם Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="18733-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="18733-124">דרישות קו צינור של אצווה לשילוב עם Customer Insights</span><span class="sxs-lookup"><span data-stu-id="18733-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="18733-125">תצורת ערכת נתונים</span><span class="sxs-lookup"><span data-stu-id="18733-125">Dataset Configuration</span></span>

<span data-ttu-id="18733-126">עליך ליצור ערכות נתונים כדי להשתמש בנתוני הישות מ- Customer Insights בקו הצינור של היסק האצווה שלך.</span><span class="sxs-lookup"><span data-stu-id="18733-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="18733-127">יש לרשום ערכות נתונים אלה בסביבת העבודה.</span><span class="sxs-lookup"><span data-stu-id="18733-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="18733-128">לעת עתה, אנחנו תומכים רק ב[ערכות נתונים טבלאיות](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) בתבנית ‎.csv</span><span class="sxs-lookup"><span data-stu-id="18733-128">Currently, we only support [tabular datasets](https://docs.microsoft.com/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="18733-129">יש לבטא בפרמטרים כפרמטר קו צינור את ערכות הנתונים המתאימות לנתוני הישות.</span><span class="sxs-lookup"><span data-stu-id="18733-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="18733-130">פרמטרים של ערכת נתונים ב- Designer</span><span class="sxs-lookup"><span data-stu-id="18733-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="18733-131">ב- Designer, פתח את **בחר עמודות בערכת נתונים** ובחר **הגדר כפרמטר של קו צינור** שבו אתה מספק שם עבור הפרמטר.</span><span class="sxs-lookup"><span data-stu-id="18733-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="18733-132">![ביטוי בפרמטרים של ערכת נתונים ב- Designer](media/intelligence-designer-dataset-parameters.png "ביטוי בפרמטרים של ערכת נתונים ב- Designer")</span><span class="sxs-lookup"><span data-stu-id="18733-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="18733-133">פרמטר ערכת נתונים ב- SDK‏ (Python)</span><span class="sxs-lookup"><span data-stu-id="18733-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="18733-134">קו צינור של היסק אצווה</span><span class="sxs-lookup"><span data-stu-id="18733-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="18733-135">ב- Designer, ניתן להשתמש בקו צינור של הדרכה ליצירה או לעדכון של קו צינור של היסק.</span><span class="sxs-lookup"><span data-stu-id="18733-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="18733-136">נכון לעכשיו, קיימת תמיכה רק בקווי צינור של היסק אצווה.</span><span class="sxs-lookup"><span data-stu-id="18733-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="18733-137">באמצעות SDK באפשרותך לפרסם את קו הצינור בנקודת קצה.</span><span class="sxs-lookup"><span data-stu-id="18733-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="18733-138">נכון לעכשיו, Customer Insights משתלב עם קו הצינור של ברירת המחדל בנקודת קצה של קו צינור של אצווה בסביבת העבודה של Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="18733-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="18733-139">ייבוא נתוני קו צינור אל Customer Insights</span><span class="sxs-lookup"><span data-stu-id="18733-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="18733-140">Designer מספק את [המודול 'ייצוא נתונים'](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) המאפשר ייצוא של פלט קו צינור אל אחסון Azure.</span><span class="sxs-lookup"><span data-stu-id="18733-140">The designer provides the [Export Data module](https://docs.microsoft.com/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="18733-141">נכון לעכשיו, המודול מוכרח להשתמש בסוג מאגר הנתונים **אחסון Blob של Azure** ולבטא בפרמטרים את **מאגר הנתונים** ו **נתיב** יחסי.</span><span class="sxs-lookup"><span data-stu-id="18733-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="18733-142">Customer Insights עוקף את שני הפרמטרים במהלך ביצוע קו הצינור עם מאגר נתונים ונתיב הנגישים למוצר.</span><span class="sxs-lookup"><span data-stu-id="18733-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18733-143">![תצורת מודול 'ייצוא נתונים'](media/intelligence-designer-importdata.png "תצורת מודול 'ייצוא נתונים'")</span><span class="sxs-lookup"><span data-stu-id="18733-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="18733-144">בעת כתיבת פלט ההיסק באמצעות קוד, באפשרותך להעלות את הפלט לנתיב בתוך *מאגר נתונים רשום* בסביבת העבודה.</span><span class="sxs-lookup"><span data-stu-id="18733-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="18733-145">אם הנתיב ומאגר הנתונים מבוטאים בפרמטרים בקו הצינור, Customer Insights יוכל לקרוא ולייבא את פלט ההיסק.</span><span class="sxs-lookup"><span data-stu-id="18733-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="18733-146">לעת עתה קיימת תמיכה בפלט טבלאי יחיד בתבנית csv.</span><span class="sxs-lookup"><span data-stu-id="18733-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="18733-147">הנתיב מוכרח לכלול את שם הספריה ואת שם הקובץ.</span><span class="sxs-lookup"><span data-stu-id="18733-147">The path must include the directory and filename.</span></span>

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]