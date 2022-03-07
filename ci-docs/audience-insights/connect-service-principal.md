---
title: התחבר לחשבון Azure Data Lake Storage באמצעות מנהל שירות
description: השתמש במנהל שירות של Azure כדי להתחבר לאגם הנתונים שלך.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: d593880b06bd21e96826039a67382b75a4296a87
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354189"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>התחבר לחשבון Azure Data Lake Storage באמצעות מנהל שירות של Azura

מאמר זה בוחן כיצד לחבר את Dynamics 365 Customer Insights עם Azure Data Lake Storage חשבון על ידי שימוש במנהל שירות Azure במקום במפתחות של חשבון אחסון. 

כלים אוטומטיים המשתמשים בשירותי Azure צריכים תמיד להיות בעלי הרשאות מוגבלות. במקום כניסה ליישומים כמשתמש בעל הרשאות מלאות, Azure מספק מנהלי שירות. תוכל להשתמש במנהלי שירות כדי להוסיף או לערוך [תיקיה של Common Data Model באופן מאובטח כמקור נתונים](connect-common-data-model.md) או [ליצור או לעדכן סביבה](create-environment.md).

> [!IMPORTANT]
> - חשבון Data Lake Storage שישתמש במנהל השירות חייב להיות Gen2 ועם [מרחב שמות היררכי מופעל](/azure/storage/blobs/data-lake-storage-namespace). חשבונות Azure Data Lake Gen1 storage לא נתמכים.
> - תזדקק להרשאות של מנהל מערכת עבור המנוי ל- Azure שלך כדי ליצור מנהל שירות.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>צור מנהל שירות של Azure עבור Customer Insights

לפני יצירת מנהל שירות חדש עבור Customer Insights, בדוק אם הוא כבר קיים בארגון שלך.

### <a name="look-for-an-existing-service-principal"></a>חיפוש מנהל שירות קיים

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com) והיכנס לארגון שלך.

2. מתוך **שירותי Azure**, בחר **Azure Active Directory**.

3. תחת **ניהול**, בחר **יישומים ארגוניים**.

4. חפש את מזהה היישום של Microsoft:
   - תובנות קהל:`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` עם השם `Dynamics 365 AI for Customer Insights`
   - תובנות מעורבות: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` עם השם `Dynamics 365 AI for Customer Insights engagement insights`

5. אם אתה מוצא רשומה תואמת, פירוש הדבר שמנהל השירות כבר קיים. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="צילום מסך המציג מנהל שירות קיים.":::
   
6. אם לא מוחזרות תוצאות, צור מנהל שירות חדש.

>[!NOTE]
>כדי לנצל את מלוא העוצמה של Dynamics 365 Customer Insights, אנו מציעים שתוסיף את שתי האפליקציות למנהל השירות.

### <a name="create-a-new-service-principal"></a>יצירת מנהל שירות חדש

1. התקן את הגירסה העדכנית ביותר של Azure Active Directory PowerShell לגרף. למידע נוסף, עבור אל [התקן Azure Active Directory PowerShell לגרף](/powershell/azure/active-directory/install-adv2).

   1. במחשב שלך, בחר את מקש Windows במקלדת וחפש **Windows PowerShell‎** ובחר **הפעל בתור מנהל מערכת**.
   
   1. בחלון PowerShell שנפתח, הזן `Install-Module AzureAD`.

2. צור את מנהל השירות עבור Customer Insights באמצעות מודול Azure AD PowerShell.

   1. בחלון PowerShell, הזן `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. החלף את *[מזהה הדייר שלך]* במזהה בפועל של הדייר שלך שבו ברצונך ליצור את מנהל השירות. פרמטר שם הסביבה, `AzureEnvironmentName` הוא אופציונלי.
  
   1. הזן `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. פקודה זו יוצרת את מנהל השירות עבור audience insights בדייר שנבחר. 

   1. הזן `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. פקודה זו יוצרת את מנהל השירות לתובנות לגבי מעורבות בדייר שנבחר.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>הענק הרשאות למנהל השירות כדי לגשת לחשבון האחסון

עבור לפורטל Azure כדי להעניק הרשאות למנהל השירות עבור חשבון האחסון שבו ברצונך להשתמש ב- audience insights.

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com) והיכנס לארגון שלך.

1. פתח את חשבון האחסון שאליו אתה רוצה שתהיה למנהל השירות עבור audience insights גישה.

1. בחלונית השמאלית, בחר **בקרת גישה (IAM)** ולאחר מכן בחר **הוסף** > **הוסף הקצאת תפקיד**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="צילום מסך המציג את פורטל Azure תוך הוספת הקצאת תפקידים.":::

1. בחלונית **הוסף הקצאת תפקיד**, הגדר את המאפיינים הבאים:
   - תפקיד: **תורם נתונים של Blob אחסון**
   - הקצה גישה ל: **משתמש, קבוצה או מנהל שירות**
   - בחר: **Dynamics 365 AI for Customer Insights** וגם **תובנות מעורבות של Dynamics 365 AI for Customer Insights** (שני [מנהלי השירות](#create-a-new-service-principal) שיצרת קודם לכן בהליך זה)

1.  בחר **שמור**.

הפצת השינויים עשויה להימשך עד 15 דקות.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>הזן את מזהה משאב Azure או את פרטי מנוי Azure בקובץ המצורף לחשבון האחסון בתובנות קהל

באפשרותך לצרף חשבון Data Lake Storage לתובנות לגבי קהלים כדי [לאחסן נתוני פלט](manage-environments.md) או [להשתמש בו כמקור נתונים](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). אפשרות זו מאפשרת לך לבחור בין גישה מבוססת משאבים או גישה מבוססת מנוי. בהתאם לגישה שבחרת, בצע את ההליך באחד הסעיפים הבאים.

### <a name="resource-based-storage-account-connection"></a>חיבור לחשבון אחסון מבוסס-משאב

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com), היכנס למנוי שלך ופתח את חשבון האחסון.

1. בחלונית השמאלית, עבור אל **הגדרות** > **נכסים**.

1. העתק את ערך המזהה של משאב חשבון האחסון.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="העתק את המזהה של משאב חשבון האחסון.":::

1. בתובנות קהל, הכנס את מזהה המשאב בשדה המשאב המוצג במסך החיבור של חשבון האחסון.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="הזן את מידע המזהה של משאב חשבון האחסון.":::   

1. המשך בשלבים הנותרים ב- Audience Insights כדי לצרף את חשבון האחסון.

### <a name="subscription-based-storage-account-connection"></a>חיבור לחשבון אחסון מבוסס-מנוי

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com), היכנס למנוי שלך ופתח את חשבון האחסון.

1. בחלונית השמאלית, עבור אל **הגדרות** > **נכסים**.

1. סקור את **מנוי**, **קבוצת משאבים** ו **שם** של חשבון האחסון כדי לוודא שאתה בוחר את הערכים המתאימים ב- Audience Insights.

1. בתובנות קהל, בחר את הערכים של השדות המתאימים בעת צירוף חשבון האחסון.

1. המשך בשלבים הנותרים ב- Audience Insights כדי לצרף את חשבון האחסון.


[!INCLUDE[footer-include](../includes/footer-banner.md)]