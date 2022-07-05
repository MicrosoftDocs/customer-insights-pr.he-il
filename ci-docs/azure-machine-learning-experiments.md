---
title: שימוש במודלים מבוססי Azure Machine Learning
description: השתמש במודלים מבוססי Azure Machine Learning ב- Dynamics 365 Customer Insights.
ms.date: 12/02/2021
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a1efad2887a02a92ee2960b07b066edc331f3665
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081314"
---
# <a name="use-azure-machine-learning-based-models"></a>שימוש במודלים מבוססי Azure Machine Learning

הנתונים המאוחדים ב- Dynamics 365 Customer Insights הם מקור לבניית מודלי למידת מכונה שיכולים ליצור תובנות עסקיות נוספות. Customer Insights משתלב עם למידת מכונה של Azure כדי להשתמש במודלים המותאמים אישית שלך.

## <a name="prerequisites"></a>דרישות מוקדמות

- גישה ל- Customer Insights
- מנוי Azure Enterprise
- [פרופילי לקוחות מאוחדים](data-unification.md)
- [ייצוא ישות אל אחסון Blob של Azure](export-azure-blob-storage.md) מוגדר

## <a name="set-up-azure-machine-learning-workspace"></a>הגדרת סביבת עבודה של Azure Machine Learning

1. ראה [יצירת סביבת עבודה של Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) עבור אפשרויות שונות ליצירת סביבת העבודה. לקבלת הביצועים הטובים ביותר, צור את סביבת העבודה באזור Azure הקרוב ביותר מבחינה גיאוגרפית לסביבת Customer Insights שלך.

1. קבל גישה לסביבת העבודה שלך דרך [Azure Machine Learning Studio](https://ml.azure.com/). קיימות מספר [דרכים לקיום אינטראקציה](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) עם סביבת העבודה שלך.

## <a name="work-with-azure-machine-learning-designer"></a>עבודה עם Azure Machine Learning designer

מעצב Azure Machine Learning מספק בד ציור חזותי שבו תוכל לגרור ולשחרר ערכות נתונים ומודולים. ניתן לשלב קו צינור של אצווה שנוצר מה- Designer ב- Customer Insights, אם הוא מוגדר בהתאם. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>עבודה עם SDK של Azure Machine Learning

מדעני נתונים ומפתחי AI משתמשים ב- [SDK של Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) כדי לבנות זרימות עבודה של למידת מכונה. נכון לעכשיו, לא ניתן לשלב מודלים שהוכשרו באמצעות ה- SDK ישירות עם Customer Insights. קו צינור של היסק אצווה המשתמש במודל זה נדרש עבור שילוב עם Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>דרישות קו צינור של אצווה לשילוב עם Customer Insights

### <a name="dataset-configuration"></a>תצורת ערכת נתונים

עליך ליצור ערכות נתונים כדי להשתמש בנתוני הישות מ- Customer Insights בקו הצינור של היסק האצווה שלך. יש לרשום ערכות נתונים אלה בסביבת העבודה. לעת עתה, אנחנו תומכים רק ב[ערכות נתונים טבלאיות](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) בתבנית ‎.csv יש לבטא בפרמטרים כפרמטר קו צינור את ערכות הנתונים המתאימות לנתוני הישות.
   
* פרמטרים של ערכת נתונים ב- Designer
   
     ב- Designer, פתח את **בחר עמודות בערכת נתונים** ובחר **הגדר כפרמטר של קו צינור** שבו אתה מספק שם עבור הפרמטר.

     > [!div class="mx-imgBorder"]
     > ![ביטוי בפרמטרים של ערכת נתונים ב- Designer.](media/intelligence-designer-dataset-parameters.png "ביטוי בפרמטרים של ערכת נתונים ב- Designer")
   
* פרמטר ערכת נתונים ב- SDK‏ (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>קו צינור של היסק אצווה
  
* ב- Designer, ניתן להשתמש בקו צינור של הדרכה ליצירה או לעדכון של קו צינור של היסק. נכון לעכשיו, קיימת תמיכה רק בקווי צינור של היסק אצווה.

* באמצעות SDK באפשרותך לפרסם את קו הצינור בנקודת קצה. נכון לעכשיו, Customer Insights משתלב עם קו הצינור של ברירת המחדל בנקודת קצה של קו צינור של אצווה בסביבת העבודה של Machine Learning.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>ייבוא נתוני קו צינור אל Customer Insights

* Designer מספק את [המודול 'ייצוא נתונים'](/azure/machine-learning/algorithm-module-reference/export-data) המאפשר ייצוא של פלט קו צינור אל אחסון Azure. נכון לעכשיו, המודול מוכרח להשתמש בסוג מאגר הנתונים **אחסון Blob של Azure** ולבטא בפרמטרים את **מאגר הנתונים** ו **נתיב** יחסי. Customer Insights עוקף את שני הפרמטרים במהלך ביצוע קו הצינור עם מאגר נתונים ונתיב הנגישים למוצר.
   > [!div class="mx-imgBorder"]
   > ![תצורת מודול 'ייצוא נתונים'.](media/intelligence-designer-importdata.png "תצורת מודול 'ייצוא נתונים'")
   
* בעת כתיבת פלט ההיסק באמצעות קוד, באפשרותך להעלות את הפלט לנתיב בתוך *מאגר נתונים רשום* בסביבת העבודה. אם הנתיב ומאגר הנתונים מבוטאים בפרמטרים בקו הצינור, Customer Insights יוכל לקרוא ולייבא את פלט ההיסק. לעת עתה קיימת תמיכה בפלט טבלאי יחיד בתבנית csv. הנתיב מוכרח לכלול את שם הספריה ואת שם הקובץ.

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


[!INCLUDE [footer-include](includes/footer-banner.md)]