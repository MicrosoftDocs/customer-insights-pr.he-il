---
title: התחבר לחשבון Azure Data Lake Storage באמצעות מנהל שירות של Azura
description: השתמש במנהל שירות של Azure כדי להתחבר לאגם הנתונים שלך.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 949caa73578dbe0a511726ec045c0fd5f4621de4
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9081296"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>התחבר לחשבון Azure Data Lake Storage באמצעות מנהל שירות של Azura

מאמר זה בוחן כיצד לחבר את Dynamics 365 Customer Insights עם Azure Data Lake Storage חשבון על ידי שימוש במנהל שירות Azure במקום במפתחות של חשבון אחסון.

כלים אוטומטיים המשתמשים בשירותי Azure צריכים תמיד להיות בעלי הרשאות מוגבלות. במקום כניסה ליישומים כמשתמש בעל הרשאות מלאות, Azure מספק מנהלי שירות. תוכל להשתמש במנהלי שירות כדי להוסיף או לערוך [תיקיה של Common Data Model באופן מאובטח כמקור נתונים](connect-common-data-model.md) או [ליצור או לעדכן סביבה](create-environment.md).

> [!IMPORTANT]
>
> - חשבון Data Lake Storage שישתמש במנהל השירות חייב להיות Gen2 ועם [מרחב שמות היררכי מופעל](/azure/storage/blobs/data-lake-storage-namespace). חשבונות Azure Data Lake Gen1 storage לא נתמכים.
> - תזדקק להרשאות של מנהל מערכת עבור דייר Azure שלך כדי ליצור מנהל שירות.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>צור מנהל שירות של Azure עבור Customer Insights

לפני יצירת מנהל שירות חדש עבור Customer Insights, בדוק אם הוא כבר קיים בארגון שלך.

### <a name="look-for-an-existing-service-principal"></a>חיפוש מנהל שירות קיים

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com) והיכנס לארגון שלך.

2. מתוך **שירותי Azure**, בחר **Azure Active Directory**.

3. תחת **ניהול**, בחר **אפליקציית Microsoft**.

4. הוסף מסנן עבור **מזהה יישום שמתחיל עם** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` או חפש את השם `Dynamics 365 AI for Customer Insights`.

5. אם אתה מוצא רשומה תואמת, פירוש הדבר שמנהל השירות כבר קיים.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="צילום מסך המציג מנהל שירות קיים.":::

6. אם לא מוחזרות תוצאות, אתה יכול [ליצור מנהל שירות חדש](#create-a-new-service-principal). ברוב המקרים, הוא כבר קיים ואתה צריך רק להעניק הרשאות גישה למנהל השירות עבור חשבון האחסון.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>הענק הרשאות למנהל השירות כדי לגשת לחשבון האחסון

עבור לפורטל Azure כדי להעניק הרשאות למנהל השירות עבור חשבון האחסון שבו ברצונך להשתמש ב- Customer Insights. יש להקצות אחד מהתפקידים הבאים לחשבון האחסון או לגורם המכיל:

|אישור|דרישות|
|----------|------------|
|משתמש מחובר כרגע|**תפקיד**: קורא Blob אחסון, משתתף Blog אחסון, או הבעלים של Blob אחסון.<br>**רמה**: ניתן להעניק הרשאות בחשבון האחסון או בגורם המכיל.</br>|
|מנהל שירות של Customer Insights -<br>שימוש ב- Azure Data Lake Storage כמקור נתונים</br>|אפשרות 1<ul><li>**תפקיד**: קורא Blob אחסון, משתתף Blog אחסון, או הבעלים של נתוני Blob אחסון.</li><li>**רמה**: יש להעניק הרשאות בחשבון האחסון.</li></ul>אפשרות 2 *(ללא שיתוף גישת מנהל השירות לחשבון האחסון)*<ul><li>**תפקיד 1**: קורא Blob אחסון, משתתף Blog אחסון, או הבעלים של נתוני Blob אחסון.</li><li>**רמה**: יש להעניק הרשאות בגורם המכיל.</li><li>**תפקיד 2** גורם מקצה של נתוני Blob אחסון.</li><li>**רמה**: יש להעניק הרשאות בחשבון האחסון.</li></ul>|
|מנהל שירות של Customer Insights - <br>באמצעות Azure Data Lake Storage כפלט או יעד</br>|אפשרות 1<ul><li>**תפקיד**: משתתף Blog אחסון, או הבעלים של Blob אחסון.</li><li>**רמה**: יש להעניק הרשאות בחשבון האחסון.</li></ul>אפשרות 2 *(ללא שיתוף גישת מנהל השירות לחשבון האחסון)*<ul><li>**תפקיד**: משתתף Blog אחסון, או הבעלים של Blob אחסון.</li><li>**רמה**: יש להעניק הרשאות בגורם המכיל.</li><li>**תפקיד 2** גורם מקצה של Blob אחסון.</li><li>**רמה**: יש להעניק הרשאות בחשבון האחסון.</li></ul>|

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com) והיכנס לארגון שלך.

1. פתח את חשבון האחסון שאליו תרצה להעניק גישה למנהל השירות של Customer Insights.

1. בחלונית השמאלית, בחר **בקרת גישה (IAM)** ולאחר מכן בחר **הוסף** > **הוסף הקצאת תפקיד**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="צילום מסך המציג את פורטל Azure תוך הוספת הקצאת תפקידים.":::

1. בחלונית **הוסף הקצאת תפקיד**, הגדר את המאפיינים הבאים:
   - תפקיד: קורא Blob אחסון, משתתף Blog אחסון, או הבעלים של Blob אחסון אל סמך האישורים הרשומים לעיל.
   - הקצה גישה ל: **משתמש, קבוצה או מנהל שירות**
   - בחר חברים: **Dynamics 365 AI for Customer Insights** ([מנהל השירות](#create-a-new-service-principal) שחיפשת מוקדם יותר בתהליך זה)

1. בחר **סקירה והקצאה**.

הפצת השינויים עשויה להימשך עד 15 דקות.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>הזן את מזהה המשאב של Azure או את פרטי המנוי של Azure בקובץ המצורף של חשבון האחסון ל- Customer Insights

אפשר לצרף חשבון Data Lake Storage ב- Customer Insights [לאיחסן נתוני פלט](manage-environments.md) או [לשימוש בו בתור מקור נתונים](connect-dataverse-managed-lake.md). אפשרות זו מאפשרת לך לבחור בין גישה מבוססת משאבים או גישה מבוססת מנוי. בהתאם לגישה שבחרת, בצע את ההליך באחד הסעיפים הבאים.

### <a name="resource-based-storage-account-connection"></a>חיבור לחשבון אחסון מבוסס-משאב

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com), היכנס למנוי שלך ופתח את חשבון האחסון.

1. עבור אל **הגדרות** > **נקודות קצה** בחלונית הימנית.

1. העתק את ערך המזהה של משאב חשבון האחסון.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="העתק את המזהה של משאב חשבון האחסון.":::

1. ב- Customer Insights, הוסף את מזהה המשאב בשדה המשאב המוצג במסך חיבור של חשבון האחסון.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="הזן את מידע המזהה של משאב חשבון האחסון.":::   

1. המשך לבצעת את השלבים שנותרו ב- Customer Insights כדי לצרף את חשבון האחסון.

### <a name="subscription-based-storage-account-connection"></a>חיבור לחשבון אחסון מבוסס-מנוי

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com), היכנס למנוי שלך ופתח את חשבון האחסון.

1. בחלונית השמאלית, עבור אל **הגדרות** > **נכסים**.

1. סקור את **המינוי**, את **קבוצת המשאבים**, ואת **השם** של חשבון האחסון כדי לוודא שאתה בוחר את הערכים הנכונים ב- Customer Insights.

1. ב- Customer Insights, בחר את הערכים עבור השדות המתאימים בעת צירוף חשבון האחסון.

1. המשך לבצעת את השלבים שנותרו ב- Customer Insights כדי לצרף את חשבון האחסון.

### <a name="create-a-new-service-principal"></a>יצירת מנהל שירות חדש

1. התקן את הגירסה העדכנית ביותר של Azure Active Directory PowerShell לגרף. למידע נוסף, עבור אל [התקן Azure Active Directory PowerShell לגרף](/powershell/azure/active-directory/install-adv2).

   1. במחשב, הקש על מקש Windows במקלדת וחפש **Windows PowerShell** ובחר **הפעל בתור מנהל מערכת**.

   1. בחלון PowerShell שנפתח, הזן `Install-Module AzureAD`.

2. צור את מנהל השירות עבור Customer Insights באמצעות מודול Azure AD PowerShell.

   1. בחלון PowerShell, הזן `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. החלף את *[מזהה הספרייה שלך]* עם מזהה הספריה בפועל של מנוי ה-Azure שלך שבו ברצונך ליצור את מנהל השירות. פרמטר שם הסביבה, `AzureEnvironmentName` הוא אופציונלי.
  
   1. הזן `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. פקודה זו יוצרת את מנהל שירות עבור Customer Insights במנוי Azure שנבחר.

[!INCLUDE [footer-include](includes/footer-banner.md)]
