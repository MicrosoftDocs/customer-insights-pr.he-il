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
# <a name="custom-machine-learning-models"></a>מודלי למידת מכונה מותאמים אישית

עם האפשרות **בינה** > **מודלים מותאמים אישית** תוכל לנהל זרימות עבודה על פי מודלים של למידת מכונה של Azure. תהליכי עבודה עוזרים לך לבחור את הנתונים שמהם תרצה לייצר תובנות ולמפות את התוצאות לנתוני הלקוחות המאוחדים שלך. לקבלת מידע נוסף אודות בניית מודלי ML מותאמים אישית, ראה [שימוש במודלים מבוססי-Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>AI אחראי

חיזויים מספקים יכולות ליצירת חוויות לקוח טובות יותר, לשיפור יכולות עסקיות וזרמי הכנסות. אנחנו ממליצים בחום שתאזן את הערך של החיזוי שלך מול ההשפעה שיש לו וההטיות שהוא עשוי להציג בצורה אתית. קבל מידע נוסף על האופן שבו Microsoft [מטפלת ב- AI אחראי](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). באפשרותך גם לקבל מידע נוסף אודות [טכניקות ותהליכים עבור למידת מכונה אחראית](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) הספציפיים ל- Azure Machine Learning.

## <a name="prerequisites"></a>דרישות מוקדמות

- נכון לעכשיו, תכונה זו תומכת בשירותי אינטרנט המתפרסמים דרך [Machine Learning Studio (קלאסי)](https://studio.azureml.net) ו[קווי צינור אצווה של Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- אתה זקוק לחשבון אחסון של Azure Data Lake Gen2 המשויך למופע שלך ב- Azure Studio כדי להשתמש בתכונה זו. לקבלת מידע נוסף, ראה [יצירת חשבון אחסון של Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>הוספת זרימת עבודה חדשה

1. עבור אל **בינה** > **מודלים מותאמים אישית** ובחר **זרימת עבודה חדשה**.

1. תן לדגם המותאם אישית שם הניתן לזיהוי בשדה **שם**.

   > [!div class="mx-imgBorder"]
   > ![צילום מסך של חלונית זרימת העבודה החדשה](media/new-workflowv2.png "צילום מסך של חלונית זרימת העבודה החדשה")

1. בחר ארגון שמכיל את שירות האינטרנט ב- **דייר שמכיל את שירות האינטרנט שלך**.

1. אם המנוי שלך ל'למידת מכונה של Azure' נמצא בדייר שונה מ- Customer Insights, בחר **התחברות** עם האישורים שלך לארגון שנבחר.

1. בחר את **סביבות עבודה** המשויכות לשירות האינטרנט שלך. מופיעים שני מקטעים, אחד עבור Azure Machine Learning v1‏ (Machine Learning Studio (קלאסי)) ו- Azure Machine Learning v2‏ (Azure Machine Learning). אם אינך בטוח איזו סביבת עבודה מתאימה לשירות האינטרנט Machine Learning Studio (קלאסי) שלך, בחר **כלשהי**.

1. בחר את שירות האינטרנט Machine Learning Studio (קלאסי) או את קו הצינור Azure Machine Learning ברשימה הנפתחת **שירות אינטרנט המכיל את המודל שלך**. לאחר מכן בחר **הבא**.
   - קבל מידע נוסף אודות [פרסום שירות אינטרנט ב- Machine Learning Studio (קלאסי)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - קבל מידע נוסף אודות [פרסום קו צינור ב- Azure Machine Learning באמצעות המעצב](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) או [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). עליך לפרסם את קו הצינור שלך תחת [נקודת קצה של קו צינור](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. עבור כל **קלט של שירות אינטרנט**, בחר את **ישות** המתאימה מתוך Customer Insights ובחר **הבא**.
   > [!NOTE]
   > זרימת העבודה של המודל המותאם אישית תחיל היוריסטיקה למיפוי שדות הקלט של שירות האינטרנט לתכונות הישות בהתבסס על השם וסוג הנתונים של השדה. תראה שגיאה אם לא ניתן למפות שדה שירות אינטרנט לישות.

   > [!div class="mx-imgBorder"]
   > ![קביעת תצורה של זרימת עבודה](media/intelligence-screen2-updated.png "קביעת תצורה של זרימת עבודה")
   
1. בשלב **פרמטרים של פלט מודל**, הגדר את המאפיינים הבאים:
   - Machine Learning Studio (קלאסי)
      1. הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של שירות האינטרנט יזרמו אליו.
   - למידת מכונה של Azure
      1. הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של קו הצינור יזרמו אליו.
      1. בחר את **שם הפרמטר של מאגר נתוני הפלט** של קו הצינור של האצווה שלך מהרשימה הנפתחת.
      1. בחר את **שם הפרמטר של נתיב הפלט** של קו הצינור של האצווה שלך מהרשימה הנפתחת.
      
      > [!div class="mx-imgBorder"]
      > ![חלונית של פרמטר פלט מודל](media/intelligence-screen3-outputparameters.png "חלונית של פרמטר פלט מודל")

1. בחר את התכונה המתאימה מתוך הרשימה הנפתחת **מזהה לקוח בתוצאות** אשר מזהה לקוחות ובחר **שמור**.
   
   > [!div class="mx-imgBorder"]
   > ![קשר את התוצאות לחלונית 'נתוני לקוחות'](media/intelligence-screen4-relatetocustomer.png "קשר את התוצאות לחלונית 'נתוני לקוחות'")

1. תראה את המסך **זרימת עבודה נשמרה** עם פרטים על זרימת העבודה.    
   אם הגדרת זרימת עבודה עבור קו צינור של Azure Machine Learning‏, Audience Insights יצרף את סביבת העבודה המכילה את קו הצינור. Audience Insights יקבל תפקיד **משתתף** בסביבת העבודה של Azure.

1. בחר **סיום**.

1. כעת תוכל להפעיל את זרימת העבודה מהדף **מודלים מותאמים אישית**.

## <a name="edit-a-workflow"></a>עריכת זרימת עבודה

1. בדף **מודלים מותאמים אישית**, בחר את שלוש הנקודות האנכיות בעמודה **פעולות** לצד זרימת עבודה שיצרת בעבר, ובחר **ערוך**.

1. באפשרותך לעדכן את השם הניתן לזיהוי של סביבת העבודה שלך בשדה **שם התצוגה**, אבל אין באפשרותך לשנות את שירות האינטרנט או את קו הצינור המוגדרים. בחר **הבא**.

1. עבור כל **קלט של שירות אינטרנט**, באפשרותך לעדכן את ערך **ישות** המתאים מתוך Customer Insights. לאחר מכן בחר **הבא**.

1. בשלב **פרמטרים של פלט מודל**, הגדר את המאפיינים הבאים:
   - Machine Learning Studio (קלאסי)
      1. הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של שירות האינטרנט יזרמו אליו.
   - למידת מכונה של Azure
      1. הזן את הפלט **שם הישות** שברצונך שתוצאות הפלט של קו הצינור יזרמו אליו.
      1. בחר את **שם פרמטר של מאגר נתוני פלט** עבור קו הצינור של הבדיקה שלך.
      1. בחר את **שם פרמטר נתיב הפלט** עבור קו הצינור של הבדיקה שלך.

1. בחר את התכונה המתאימה מתוך הרשימה הנפתחת **מזהה לקוח בתוצאות** אשר מזהה לקוחות ובחר **שמור**.
   עליך לבחור תכונה מתוך פלט המסקנה עם ערכים הדומים לעמודה 'מזהה לקוח' של הישות 'לקוח'. אם אין עמודה כזאת בערכת הנתונים שלך, בחר תכונה המזהה באופן ייחודי את השורה.

## <a name="run-a-workflow"></a>הפעלת זרימת עבודה

1. בדף **מודלים מותאמים אישית**, בחר את שלוש הנקודות האנכיות בעמודה **פעולות** לצד זרימת עבודה שיצרת בעבר.

1. בחר **הפעל**.

זרימת העבודה שלך פועלת גם באופן אוטומטי עם כל רענון מתוזמן. קבל מידע נוסף על [הגדרת רענונים מתוזמנים](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>מחיקת זרימת עבודה

1. בדף **מודלים מותאמים אישית**, בחר את שלוש הנקודות האנכיות בעמודה **פעולות** לצד זרימת עבודה שיצרת בעבר.

1. בחר **מחיקה**, ואשר את המחיקה.

זרימת העבודה שלך תימחק. [הישות](entities.md) שנוצרה כאשר יצרת את זרימת העבודה ממשיכה להתקיים וניתן להציג אותה דרך הדף **ישויות**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]