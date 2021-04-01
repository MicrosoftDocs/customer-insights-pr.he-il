---
title: התחברות לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות
description: השתמש במנהל שירות של Azure עבור audience insights כדי להתחבר לאגם הנתונים שלך בעת צירופו ל- audience insights.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596500"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>התחברות לחשבון Azure Data Lake Storage Gen2 עם מנהל שירות של Azure עבור audience insights

כלים אוטומטיים המשתמשים בשירותי Azure צריכים תמיד להיות בעלי הרשאות מוגבלות. במקום כניסה ליישומים כמשתמש בעל הרשאות מלאות, Azure מספק מנהלי שירות. המשך לקרוא כדי ללמוד כיצד לחבר את audience insights לחשבון Azure Data Lake Storage Gen2 באמצעות מנהל שירות של Azure במקום מפתחות של חשבון אחסון. 

באפשרותך להשתמש במנהל השירות כדי [להוסיף או לערוך תיקיית Common Data Model כמקור נתונים](connect-common-data-model.md) או [ליצור סביבה חדשה או לעדכן סביבה קיימת](manage-environments.md#create-an-environment-in-an-existing-organization) באופן מאובטח.

> [!IMPORTANT]
> - חשבון האחסון של Azure Data Lake Gen2 שמתכוון להשתמש במנהל השירות חייב להיות בעל [מרחב שמות הירארכי (HNS) מופעל](/azure/storage/blobs/data-lake-storage-namespace).
> - אתה זקוק להרשאות מנהל עבור המנוי שלך ב- Azure כדי ליצור את מנהל השירות.

## <a name="create-azure-service-principal-for-audience-insights"></a>יצירת מנהל שירות של Azure עבור audience insights

לפני שתיצור מנהל שירות חדש עבור audience insights, בדוק אם הוא קיים כבר בארגון שלך.

### <a name="look-for-an-existing-service-principal"></a>חיפוש מנהל שירות קיים

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com) והיכנס לארגון שלך.

2. בחר את **Azure Active Directory** משירותי Azure.

3. תחת **ניהול**, בחר **יישומים ארגוניים**.

4. חפש את מזהה היישום של הצד הראשון של תובנות הקהל `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` או את השם `Dynamics 365 AI for Customer Insights`.

5. אם אתה מוצא רשומה תואמת, המשמעות היא שמנהל השירות של audience insights קיים. אינך צריך ליצור אותו שוב.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="צילום מסך המציג את מנהל השירות הקיים.":::
   
6. אם לא מוחזרות תוצאות, צור מנהל שירות חדש.

### <a name="create-a-new-service-principal"></a>יצירת מנהל שירות חדש

1. התקן את הגירסה האחרונה של **Azure Active Directory PowerShell for Graph**. לקבלת מידע נוסף, ראה [התקנת Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   - במחשב שלך, בחר את מקש Windows במקלדת שלך וחפש את **Windows PowerShell** ואת **הפעל כמנהל מערכת**.
   
   - בחלון PowerShell שנפתח, הזן `Install-Module AzureAD`.

2. צור את מנהל השירות עבור audience insights עם מודול PowerShell של Azure AD.
   - בחלון PowerShell, הזן `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. החלף את "מזהה הדייר שלך" במזהה בפועל של הדייר שלך שבו ברצונך ליצור את מנהל השירות. פרמטר שם הסביבה `AzureEnvironmentName` הוא אופציונלי.
  
   - הזן `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. פקודה זו יוצרת את מנהל השירות עבור audience insights בדייר שנבחר.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>הענק הרשאות למנהל השירות כדי לגשת לחשבון האחסון

עבור לפורטל Azure כדי להעניק הרשאות למנהל השירות עבור חשבון האחסון שבו ברצונך להשתמש ב- audience insights.

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com) והיכנס לארגון שלך.

1. פתח את חשבון האחסון שאליו אתה רוצה שתהיה למנהל השירות עבור audience insights גישה.

1. בחר **בקרת גישה (IAM)** מתוך חלונית הניווט ובחר **הוסף** > **הוסף הקצאת תפקיד**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="צילום מסך המציג את פורטל Azure במהלך הוספת הקצאת תפקיד.":::
   
1. בחלונית **הוסף הקצאת תפקיד**, הגדר את המאפיינים הבאים:
   - תפקיד: *תורם נתונים של Blob אחסון*
   - הקצה גישה ל: *משתמש, קבוצה או מנהל שירות*
   - בחר: *Dynamics 365 AI for Customer Insights* ([מנהל השירות שיצרת](#create-a-new-service-principal))

1.  בחר **שמור**.

הפצת השינויים עשויה להימשך עד 15 דקות.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>הזן את מזהה משאב Azure או את פרטי מנוי Azure בקובץ המצורף לחשבון האחסון ב- Audience Insights.

צרף חשבון אחסון ב- Azure Data Lake ל- Audience Insights כדי [לאחסן נתוני פלט](manage-environments.md) או [השתמש בו כמקור נתונים](connect-common-data-service-lake.md). הבחירה באפשרות Azure Data Lake מאפשרת לבחור בין גישה מבוססת-משאב או גישה מבוססת-מנוי.

בצע את השלבים הבאים כדי לספק את המידע הנדרש על הגישה שנבחרה.

### <a name="resource-based-storage-account-connection"></a>חיבור לחשבון אחסון מבוסס-משאב

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com), היכנס למנוי שלך ופתח את חשבון האחסון.

1. עבור אל **הגדרות** > **מאפיינים** בחלונית הניווט.

1. העתק את ערך המזהה של משאב חשבון האחסון.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="העתק את המזהה של משאב חשבון האחסון.":::

1. ב- Audience Insights, הוסף את מזהה המשאב בשדה המשאב המוצג במסך של חיבור חשבון האחסון.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="הזן את מידע המזהה של משאב חשבון האחסון.":::   
   
1. המשך בשלבים הנותרים ב- Audience Insights כדי לצרף את חשבון האחסון.

### <a name="subscription-based-storage-account-connection"></a>חיבור לחשבון אחסון מבוסס-מנוי

1. עבור אל [פורטל הניהול של Azure](https://portal.azure.com), היכנס למנוי שלך ופתח את חשבון האחסון.

1. עבור אל **הגדרות** > **מאפיינים** בחלונית הניווט.

1. סקור את **מנוי**, **קבוצת משאבים** ו **שם** של חשבון האחסון כדי לוודא שאתה בוחר את הערכים המתאימים ב- Audience Insights.

1. ב- Audience Insights, בחר את הערכים עבור השדות המתאימים בעת צירוף חשבון האחסון.
   
1. המשך בשלבים הנותרים ב- Audience Insights כדי לצרף את חשבון האחסון.


[!INCLUDE[footer-include](../includes/footer-banner.md)]