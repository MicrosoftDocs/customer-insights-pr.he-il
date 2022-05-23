---
title: יצירה וניהול של סביבות
description: למד כיצד להירשם לשירות וכיצד לנהל סביבות.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 599cbaf4e19c3a7331e92bfc54c701fefe6c69b3
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741042"
---
# <a name="manage-environments"></a>ניהול סביבות

## <a name="switch-environments"></a>החלף סביבות

בחר את הפקד **סביבה** בפינה הימנית העליונה של הדף כדי לשנות סביבות.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="צילום מסך של הפקד להחלפת סביבות.":::

מנהלי מערכת יכולים [ליצור](create-environment.md) ולנהל סביבות.

## <a name="edit-an-existing-environment"></a>עריכת סביבה קיימת

באפשרותך לערוך חלק מהפרטים של סביבות קיימות.

1.  בחר את בורר **הסביבה** בכותרת היישום.

2.  בחר את סמל **עריכה**.

3. בתיבה **ערוך סביבה**, באפשרותך לעדכן את הגדרות הסביבה.

לקבלת מידע נוסף על הגדרות הסביבה, ראה [יצירת סביבה חדשה](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>חיבור אל Microsoft Dataverse
   
השלב של **Microsoft Dataverse** מאפשר לך לחבר את Customer Insights לסביבת Dataverse. 

ספק סביבת Microsoft Dataverse משלך לשיתוף נתונים (פרופילים ותובנות) עם אפליקציות עסקיות המבוססות על Dataverse, כמו Dynamics 365 Marketing או אפליקציות מונחות דגמים ב- Power Apps.

כדי להשתמש ב[מודלים של חיזויים מוכנים לשימוש](predictions-overview.md#out-of-box-models), קבע את תצורת שיתוף הנתונים עם Dataverse. לחלופין, תוכל להפעיל עיבוד נתונים ממקורות נתונים מקומיים, על-ידי אספקת כתובת ה- URL של סביבת Microsoft Dataverse שהארגון שלך מנהל.

הפעלת שיתוף נתונים עם Microsoft Dataverse על ידי בחירה בתיבת הסימון של שיתוף הנתונים תפעיל רענון מלא חד פעמי של מקורות הנתונים שלך וכל שאר התהליכים.

> [!IMPORTANT]
> 1. Customer Insights ו- Dataverse צריכים להיות באותו אזור כדי לאפשר שיתוף נתונים.
> 1. נדרש לך תפקיד מנהל מערכת גלובלי בסביבת Dataverse. ודא אם [סביבת Dataverse זו משוייכת](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) לקבוצות אבטחה מסוימות וודא שאתה מתווסף לקבוצות אבטחה אלה.
> 1. אף סביבה קיימת של Customer Insights לא משויכת לסביבת Dataverse זו. למד כיצד [להסיר חיבור קיים לסביבת Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="אפשרויות קביעת תצורה כדי להפוך שיתוף נתונים לזמין עם Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>הפוך שיתוף נתונים מ- Azure Data Lake Storage משלך לזמין באמצעות Dataverse ‏(Preview)

אם הסביבה שלך מוגדרת לשימוש ב- Azure Data Lake Storage משלך לאחסון נתוני Customer Insights, נדרשת הגדרת תצורה נוספת על מנת להפוך שיתוף נתונים באמצעות Microsoft Dataverse לזמין.

1. צור שתי קבוצות אבטחה במנוי Azure שלך - קבוצת אבטחה אחת מסוג **קורא** וקבוצת אבטחה אחת מסוג **משתתף** והגדר את שירות Microsoft Dataverse כבעלים של שתי קבוצות האבטחה.
2. נהל את רשימת בקרת הגישה (ACL) בגורם המכיל של CustomerInsights בחשבון האחסון שלך באמצעות קבוצות אבטחה אלה. תוסיף את שירות Microsoft Dataverse וכל אפליקציה עסקית מבוססי Dataverse כמו Dynamics 365 Marketing לקבוצה האבטחה **קורא** עם הרשאות **קריאה בלבד**. הוסף *רק* האפליקציית Customers Insights לקבוצת האבטחה **משתתף** כדי להעניק לה הרשאות **קריאה וכתיבה** לכתיבת פרופילים ותובנות.
   
#### <a name="prerequisites"></a>דרישות מוקדמות

כדי להפעיל את הסקריפטים של PowerShell, עליך לייבא את שלושת המודולים הבאים. 

1. התקן את הגירסה העדכנית ביותר של [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. במחשב שלך, בחר את מקש Windows במקלדת וחפש **Windows PowerShell‎** ובחר **הפעל בתור מנהל מערכת**.
   1. בחלון PowerShell שנפתח, הזן `Install-Module AzureAD`.
2. ייבא שלושה מודולים.
    1. בחלון PowerShell, הזן את `Install-Module -Name Az.Accounts` ובצע את הצעדים הבאים. 
    1. חזור על הפעולה עבור `Install-Module -Name Az.Resources` ועובר `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>שלבי קביעת תצורה

1. הורד את שני הסקריפטים של PowerShell שאתה צריך להפעיל [ממאגר GitHub](https://github.com/trin-msft/byol) של המנהדס שלנו.
    1. `CreateSecurityGroups.ps1`
       - כדי להפעיל סקריפט PowerShell זה, דרושות לך הרשאות של *מנהל דייר* . 
       - סקריפט PowerShell זה יוצר שתי קבוצות אבטחה במנוי Azure שלך. אחד לקבוצת 'קורא' ואחר לקבוצת 'משתתף' ויהפוך את שירות Microsoft Dataverse לבעלים של שתי קבוצות האבטחה האלו.
       - בצע סקריפט PowerShell זה ב-Windows PowerShell על ידי מתן מזהה המנוי של Azure המכיל את Azure Data Lake Storage שלך. פתח את סקריפט ה- PowerShell בעורך כדי לסקור מידע נוסף ואת הלוגיקה שיושמה.
       - שמור את שני ערכי מזהי קבוצת האבטחה שנוצרו על ידי הסקריפט הזה מכיוון שנשתמש בהם בסקריפט `ByolSetup.ps1`.
       
        > [!NOTE]
        > ניתן להשבית יצירת קבוצת אבטחה בדייר שלך. במקרה כזה, יהיה צורך בהגדרה ידנית ומנהל מערכת Azure AD יצטרך[ להפוך יצירת קבוצת אבטחה לזמינה](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - דרושות לך הרשאות *בעל נתונים של Blob האחסון* ברמת גורם מכיל/חשבון האחסון על מנת להפעיל את הסקריפט הזה או שהסקריפט הזה יצור אחד עבורך. ניתן להסיר את הקצאת התפקיד שלך באופן ידני לאחר הפעלה מוצלחת של הסקריפט.
        - סקריפט PowerShell זה מוסיף את בקרת הגישה מבוססת התפקיד הנדרשת (RBAC) עבור שירות Microsoft Dataverse  וכל אפליקציה עסקית מבוססת Dataverse. הסקריפט גם מעדכן את רשימת בקרת הגישה (ACL) בגורם המכיל של CustomerInsights עבור קבוצות האבטחה שנוצרו באמצעות הסקריפט `CreateSecurityGroups.ps1`. לקבוצה 'משתתף' תהיה הרשאת *rwx* ולקבוצת 'קוראים' תהיה הרשאת *r-x* בלבד.
        - בצע סקריפט זה של PowerShell ב- Windows PowerShell על ידי מתן מזהה המנוי של Azure המכיל את Azure Data Lake Storage, שם חשבון האחסון, שם קבוצת משאבים וערכי מזהי קבוצות האבטחה 'קורא' ו'משתתף'. פתח את סקריפט ה- PowerShell בעורך כדי לסקור מידע נוסף ואת הלוגיקה שיושמה.
        - העתק את מחרוזת הפלט לאחר הפעלה מוצלחת של הסקריפט. מחרוזת הפלט נראית כך: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. הזן את מחרוזת הפלט שהועתקה מלמעלה לשדה **מזהה הרשאות** של שלב הגדרת התצורה של הסביבה עבור Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="אפשרויות הגדרת תצורה להפיכת שיתוף נתונים מ- Azure Data Lake Storage משלך באמצעות Microsoft Dataverse לזמין.":::

Customer Insights אינו תומך בתרחישי שיתוף הנתונים הבאים:
- אם תאפשר שיתוף נתונים עם אגם נתונים מנוהל של Dataverse, לא תוכל [ליצור ערכים חזויים או חסרים בישות](predictions.md).
- אם תאפשר שיתוף נתונים באמצעות Dataverse, לא תוכל להציג דוחות אופציונליים של PowerBI Embedded בסביבת Customer Insights שלך.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>הסרת חיבור קיים לסביבת Dataverse

כאשר מתחברים לסביבת Dataverse, משמעותה של הודעת השגיאה **ארגון CDS זה כבר מחובר למופע אחר של Customer Insights** היא שסביבת Dataverse כבר נמצאת בשימוש בסביבת Customer Insights. אפשר להסיר את החיבור הקיים כמנהל מערכת גלובלי בסביבת Dataverse. אכלוס השינויים עשוי לקחת כמה שעות.

1. עבור אל [Power Apps](https://make.powerapps.com).
1. בחר את הסביבה מבורר הסביבה.
1. עבור ל **פתרונות** 
1. הסר או מחק את הפתרון בשם **תוסף לכרטיס לקוח של Dynamics 365 Customer Insights ‏(Preview‏‏‏)**.

או 

1. פתח את סביבת Dataverse.
1. עבור אל **הגדרות מתקדמות** > **פתרונות**.
1. הסר את ההתקנה של פתרון **CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>העתקת תצורת הסביבה

כמנהל מערכת, אתה יכול לבחור להעתיק את התצורה מסביבה קיימת בעת יצירת סביבה חדשה. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="צילום מסך של אפשרויות ההגדרות בהגדרות הסביבה.":::

תראה רשימה של כל הסביבות הזמינות בארגון שלך, שממנה אתה יכול להעתיק נתונים.

הגדרות התצורה הבאות מועתקות:

- מקורות נתונים שנקלטו/יובאו
- תצורת איחוד נתונים
- פלחי שוק
- מדידות
- קשרים
- פעילויות
- אינדקס חיפוש וסינון
- יעדי ייצוא
- רענון מתוזמן
- העשרות
- ניהול מודלים
- הקצאת תפקידים

## <a name="set-up-a-copied-environment"></a>הגדרת סביבת שהועתקה

כאשר אתה מעתיק את תצורת הסביבה, הנתונים הבאים *לֹא* מועתקים:

- פרופילי לקוחות.
- אישורים של מקור נתונים. יהיה עליך לספק את האישורים עבור כל מקור נתונים ולרענן את מקורות הנתונים באופן ידני.
- מקורות נתונים מתיקיית Common Data Model ומאגם הנתונים המנוהל של Dataverse. יהיה עליך ליצור מקורות נתונים אלה באופן ידני עם אותו שם כמו בסביבת המקור.
- סודות חיבור המשמשים לפעולות ייצוא והעשרה. עליך לאמת מחדש את החיבורים ולאחר מכן להפעיל מחדש העשרות וייצוא. 

כשאתה מעתיק סביבה תראה הודעת אישור שהסביבה החדשה נוצרה. בחר **עבור למקורות נתונים** כדי לראות את רשימת מקורות הנתונים.

כל מקורות הנתונים יציגו את המצב **אישורים נדרשים**. ערוך את מקורות הנתונים והזן את האישורים כדי לרענן אותם.

:::image type="content" source="media/data-sources-copied.png" alt-text="רשימת מקורות הנתונים שהועתקו וזקוקים לאימות.":::

לאחר רענון מקורות הנתונים, עבור אל **נתונים** > **איחוד**. כאן תוכל למצוא הגדרות מסביבת המקור. ערוך אותן לפי הצורך או בחר **הפעל** כדי להתחיל את תהליך איחוד הנתונים וליצור את ישות הלקוח המאוחדת.

לאחר איחוד הנתונים, עבור אל **מדידות‬** ואל **פלחים** כדי לרענן גם אותם.

לפני שתפעיל מחדש את הייצוא וההעשרות, עבור אל **מנהל מערכת** > **חיבורים** כדי לאמת מחדש את החיבורים בסביבה החדשה שלך.

## <a name="change-the-owner-of-an-environment"></a>שינוי הבעלים של הסביבה

בעוד של מספר משתמשים יכולים להיות הרשאות ניהול ב- Customer Insights, רק אחד המשתמשים הוא הבעלים של סביבה. כברירת מחדל, מנהל המערכת הוא זה שיוצר סביבה תחילה. כמנהל מערכת של סביבה, תוכל להקצות בעלות למשתמש אחר עם הרשאות מנהל מערכת.

1. בחר את בורר **הסביבה** בכותרת היישום.

1. בחר את סמל **עריכה**.

1. בתיבה **ערוך סביבה**, עבור אל הצעד **מידע בסיסי**.

1. בשדה **שנה את הבעלים של הסביבה**, בחר את הבעלים החדשים של הסביבה.  

1. בחר **בדיקה וסיום**, לאחר מכן **עדכון** כדי להחיל את השינויים. 

## <a name="claim-ownership-of-an-environment"></a>טעינת בעלות על סביבה

אם הבעלים של סביבה עזב את הארגון או שחשבון המשתמש שלו נמחק, לסביבה לא יהיה בעלים. משתמש עם הרשאות מנהל מערכת יכול לתבוע את הבעלות ולהפוך לבעלים החדש. הוא יכול להמשיך כבעלים של הסביבה או [להעביר את הבעלות למנהל מערכת אחר](#change-the-owner-of-an-environment). 

כדי לתבוע בעלות, בחר את הלחצן **לקחת בעלות** שמופיע בראש כל עמוד ב- Customer Insights כאשר הבעלים המקורי עזב את הארגון.

## <a name="reset-an-existing-environment"></a>איפוס סביבה קיימת

כבעלים של סביבה, אתה יכול לאפס סביבה למצב ריק אם ברצונך למחוק את כל התצורות ולהסיר את הנתונים שעובדו.

1.  בחר את בורר **הסביבה** בכותרת היישום. 

2.  בחר את הסביבה שברצונך לאפס ובחר את שלוש הנקודות (**...**). 

3. בחר את האפשרות **איפוס**. 

4.  לאישור המחיקה, הזן את שם הסביבה ובחר **אפס**.

## <a name="delete-an-existing-environment"></a>מחק סביבה קיימת

כבעלים של סביבה, אתה יכול למחוק סביבה שאתה מנהל.

1.  בחר את בורר **הסביבה** בכותרת היישום.

2.  בחר את הסביבה שברצונך לאפס ובחר את שלוש הנקודות (**...**). 

3. בחר את האפשרות **מחיקה**. 

4.  כדי לאשר את המחיקה, הזן את שם הסביבה ובחר **מחק**.

> [!NOTE]
> מחיקת סביבה אינה מסירה את השיוך לסביבת Dataverse. למד כיצד [להסיר חיבור קיים לסביבת Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE [footer-include](includes/footer-banner.md)]
