---
title: חיבור נתונים של Common Data Model לחשבון Azure Data Lake
description: עבוד עם נתונים של Common Data Model באמצעות Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643459"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>חיבור לתיקיה של Common Data Model באמצעות חשבון Azure Data Lake

מאמר זה מספק מידע בנוגע לאופן הקליטה של נתונים מתיקיית Common Data Model באמצעות חשבון Azure Data Lake Storage Gen2 שלך.

## <a name="important-considerations"></a>שיקולים חשובים:

- נתונים ב- Azure Data Lake שלך צריכים לציית לתקן Common Data Model. אין תמיכה בתבניות אחרות כרגע.

- קליטת נתונים תומכת בחשבונות אחסון של Azure Data Lake *Gen2* באופן בלעדי. אין באפשרותך להשתמש בחשבונות אחסון של Azure Data Lake Gen1 לקליטת נתונים.

- כדי לאמת עם מנהל שירות של Azure, ודא שהוא מוגדר בדייר שלך. לקבלת מידע נוסף, ראה [חיבור audience insights לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות של Azure](connect-service-principal.md).

- Azure Data Lake שברצונך לחבר ולקלוט נתונים ממנו צריך להיות באותו אזור Azure כשל סביבת Dynamics 365 Customer Insights. אין תמיכה בחיבורים לתיקיית Common Data Model מ- Data Lake באזור Azure אחר. כדי להכיר את אזור Azure של הסביבה, עבור אל **ניהול** > **מערכת** > **אודות** ב- audience insights.

- נתונים המאוחסנים בשירותים מקוונים עשויים להיות מאוחסנים במיקום אחר מאשר במיקום שבו נתונים מעובדים או מאוחסנים ב- Dynamics 365 Customer Insights. על-ידי ייבוא נתונים או חיבור לנתונים שמאוחסנים בשירותים מקוונים, אתה מסכים שנתונים יועברו אל Dynamics 365 Customer Insights ויאוחסנו בו.  [קבל מידע נוסף במרכז יחסי האמון של Microsoft.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>התחבר לתיקיה של Common Data Model

1. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.

1. בחר **הוסף מקור נתונים**.

1. בחר **התחבר לתיקיית Common Data Model**, הזן **שם** עבור מקור הנתונים ובחר **הבא**.

1. באפשרותך לבחור בין שימוש באפשרות מבוססת-משאב לאפשרות מבוססת-מנוי עבור אימות. לקבלת מידע נוסף, ראה [חיבור audience insights לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות של Azure](connect-service-principal.md). הזן את פרטי **הגורם המכיל** ובחר **הבא**.
   > [!div class="mx-imgBorder"]
   > ![תיבת דו-שיח להזנת פרטי חיבור עבור Azure Data Lake](media/enter-new-storage-details.png)

1. בתיבת הדו-שיח **בחירת תיקיית Common Data Model**, בחר את קובץ model.json לייבוא נתונים ממנו, ובחר **הבא**.
   > [!NOTE]
   > כל קובץ model.json המשויך למקור נתונים אחר בסביבה לא יופיע ברשימה.

1. תקבל רשימה של ישויות זמינות בקובץ model.json שנבחר. ניתן לסקור ולבחור מרשימת הישויות ולבחור **שמור**. כל הישויות שנבחרו ייקלטו ממקור הנתונים החדש.
   > [!div class="mx-imgBorder"]
   > ![תיבת דו-שיח המציגה רשימת ישויות מתוך קובץ model.json](media/review-entities.png)

8. ציין באילו ישויות נתונים ברצונך להפוך יצירת פרופיל נתונים לזמינה ובחר **שמור**. יצירת פרופילים של נתונים הופכת ניתוח ויכולות אחרות לזמינים. באפשרותך לבחור את הישות השלמה, שבוחרת את כל התכונות מהישות, או לבחור בתכונות מסוימות לבחירתך. כברירת מחדל, אף ישות לא תופעל עבור יצירת פרופיל נתונים.
   > [!div class="mx-imgBorder"]
   > ![תיבת דו-שיח המציגה פרופיל נתונים](media/dataprofiling-entities.png)

9. לאחר שמירת הבחירות שלך, הדף **מקורות מידע** נפתח. כעת אתה אמור לראות את החיבור לתיקייה Common Data Model כמקור נתונים.

> [!NOTE]
> קובץ model.json יכול להשתייך למקור נתונים אחד באותה סביבה. עם זאת, ניתן להשתמש באותו קובץ model.json עבור מקורות נתונים בסביבות מרובות.

## <a name="edit-a-common-data-model-folder-data-source"></a>עריכת מקור נתונים של תיקיית Common Data Model

באפשרותך לעדכן את מפתח הגישה עבור חשבון האחסון המכיל את תיקיית Common Data Model. אתה יכול גם לשנות את קובץ model.json. כדי להתחבר לגורם מכיל שונה מתוך חשבון האחסון שלך, או לשנות את שם החשבון, [צור חיבור למקור נתונים חדש](#connect-to-a-common-data-model-folder).

1. ב- audience insights, עבור אל **נתונים** > **מקורות נתונים**.

2. לצד מקור הנתונים שברצונך לעדכן, בחר את שלוש הנקודות.

3. בחר באפשרות **ערוך** מתוך הרשימה.

4. לבחירתך, תוכל לעדכן את **מפתח גישה** ולבחור **הבא**.

   ![תיבת דו-שיח לעריכה ולעדכון של מפתח גישה עבור מקור נתונים קיים](media/edit-access-key.png)

5. לחלופין, באפשרותך לעדכן מחיבור מפתח חשבון לחיבור מבוסס-משאב או מבוסס-מנוי. לקבלת מידע נוסף, ראה [חיבור audience insights לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות של Azure](connect-service-principal.md). אין באפשרותך לשנות מידע **גורם מכיל** בעת עדכון החיבור.
   > [!div class="mx-imgBorder"]
   > ![תיבת דו-שיח להזנת פרטי חיבור עבור Azure Data Lake](media/enter-existing-storage-details.png)

6. אם תרצה בכך, בחר קובץ model.json אחר עם מערכת ישויות שונה מהגורם המכיל.

7. לבחירתך, תוכל לבחור ישויות נוספות לקליטה. תוכל גם להסיר כל ישות שכבר נבחרה, אם אין תלות.

   > [!IMPORTANT]
   > אם קיימים יחסי תלות בקובץ model.json הקיים ובמערכת הישויות, תראה הודעת שגיאה ולא תוכל לבחור קובץ model.json אחר. הסר יחסי תלות אלה לפני שינוי קובץ model.json או צור מקור נתונים חדש עם קובץ model.json שבו ברצונך להשתמש כדי להימנע מהסרת יחסי התלות.

8. לבחירתך תוכל לבחור תכונות או ישויות נוספות כדי להפוך פרופיל נתונים לזמין או כדי להפוך תכונות וישויות שנבחרו כבר ללא זמינות.   
