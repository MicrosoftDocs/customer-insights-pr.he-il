---
title: תכונות חדשות ועתידיות
description: מידע על תכונות חדשות, שיפורים ותיקוני באגים.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 04/27/2022
ms.locfileid: "8647250"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>מה חדש ב- Dynamics 365 Customer Insights

אנו גאים להכריז על העדכונים החדשים ביותר שלנו! מאמר זה מסכם תכונות של Public Preview, שיפורים בזמינות הכללית ועדכוני תכונות. כדי לראות את התוכניות ארוכות הטווח בנוגע לתכונות, ראה את [תוכניות ההפצה של ‎Dynamics 365 ושל Power Platform](/dynamics365/release-plans/).

אנו מפיצים עדכונים על בסיס אזורי. כך שאזורים מסוימים עשויים לראות תכונות לפני אזורים אחרים. אלא אם כן נקבע אחרת, אינך צריך לנקוט פעולה כלשהי, ואנו נעדכן את האפליקציה אוטומטית וללא השבתה.

> [!TIP]
> כדי לשלוח בקשות לגבי תכונות וכן הצעות למוצרים ולהצביע עבורן, עבור אל [פורטל הרעיונות של Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>עדכוני מרץ 2022

העדכונים במהדורת מרץ 2022 כוללים תכונות חדשות, שדרוגי ביצועים ותיקוני באגים.

### <a name="liveramp-abilitec-enrichment-preview"></a>העשרת LiveRamp AbiliTec‎‏ (Preview)

LiveRamp מספק פתרון זהות ואיחוד של נתוני לקוחות. ניתן למפות מזהים אישיים בנתוני הלקוחות שלך לגרף הזהות של AbiliTec ולקבל מזהים של AbiliTec. לאחר מכן תוכל להשתמש במזהים אלה לאיחוד טוב יותר של נתוני הלקוחות שלך.

למידע נוסף, ראה [העשרת פרופילי לקוחות עם נתוני זהות מ- LiveRamp ‏(Preview)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>ארגן פלחים ומדדים עם תגים ומסננים
אם בארגון שלך קיימים הרבה פלחים או מדדים, מציאת הפריט המתאים יכול להיות מאתגר. תכונה חדשה זו מאפשרת לך לארגן רשימות באמצעות תגים ועמודות. תכונה זו עוזרת למצוא נתונים במהירות ובקלות ולהתאים אישית את התצוגות.

למידע נוסף, ראה [עבודה עם תגים ועמודות](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>אפשר שיתוף נתונים עם Dataverse בעת שימוש בחשבון אחסון משלך

אם הסביבה שלך משתמשת ב- Azure Data Lake Storage לאחסון נתוני Customer Insights, נדרשת הגדרת תצורה נוספת לשיתוף נתונים באמצעות Microsoft Dataverse.
קודם לכן, אפשר היה לאפשר שיתוף נתונים עם Dataverse רק כאשר הנתונים שלך אוחסנו באגם הנתונים המנוהל שלנו. 

למידע נוסף ראה [הפיכת שיתוף נתונים באמצעות Dataverse מ- (Preview) Azure Data Lake Storage משלך לזמין](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>יעדי ייצוא חדשים: Iterable ו- Braze

אנחנו ממשיכים להרחיב את המערכת האקולוגית שלנו של יעדי ייצוא עם קשרים חדשים. כעת תוכל לייצא פלחים ל-Iterable ול-Braze כדי להשתמש בשירותי ההפעלה שלהם.

למידע נוסף, ראה [ייצוא פלחים ל-Iterable (תצוגה מקדימה)](export-iterable.md) ו[ייצוא פלחים ל- Braze ‏(Preview‏)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>שיפורים בייצוא של Marketo ו-Google Ads

שינוי ממשקי API בשירותים מחוברים מוביל לעדכונים כדי שהמחברים יפעלו בצורה מהימנה וחלקה. פרסמנו כמה עדכונים עבור הייצוא לשירותי Marketo ו-Google Ads:

- Google Ads: הגרסה החדשה של מחבר הייצוא של Google Ads מפשטת את חוויית האימות ומאפשרת לך כעת ליצור קהלים חדשים של Google Ads באופן אוטומטי. 
- Marketo: הגרסה החדשה של מחבר הייצוא של Marketo מספקת תמיכה עבור מזהה Marketo, ומאפשרת לך להימנע משכפול נתונים, לעדכן רשומות קיימות וליצור רשומות חדשות ב-Marketo. 


## <a name="february-2022-updates"></a>עדכוני פברואר 2022

העדכונים במהדורת פברואר 2022 כוללים תכונות חדשות, שדרוגי ביצועים ותיקוני באגים.

### <a name="general-availability-for-prediction-models"></a>זמינות כוללת לדגמי חיזוי

לדגמי חיזוי שמגיעים מוכנים לשימוש, כולל **נטישת מנויים**, **נטישת עסקאות**, ו **ערך חיי לקוח (CLV)** תהיה זמינות כוללת כחלק מ- Customer Insights. 

לקבלת מידע נוסף, ראה [מבט כולל על חיזוים](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>מקור נתונים חדש: שילוב עם Azure Synapse Analytics ‏(Preview‎‏)

Azure Synapse Analytics הוא שירות ניתוח ארגוני המאיץ את הזמן לתובנות בין מחסני נתונים ומערכות Big Data.

ארגונים שכבר משתמשים ב- Azure Synapse Analytics יכולים להטמיע את הנתונים האלה ב- Customer Insights. 

למידע נוסף, ראה [חיבור מקורות נתונים של Azure Synapse ‎‏(Preview)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>העשרת LiveRamp‎‏ (Preview)

LiveRamp מספק פתרון זהות ואיחוד של נתוני לקוחות. ניתן למפות מזהים אישיים בנתוני הלקוחות שלך לגרף הזהות של AbiliTec ולקבל מזהים של AbiliTec. לאחר מכן תוכל להשתמש במזהים אלה לאיחוד טוב יותר של נתוני הלקוחות שלך.

למידע נוסף, ראה [העשרת פרופילי לקוחות עם נתוני זהות מ- LiveRamp ‏(Preview)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>העשרה למקורות נתונים (Preview)

השתמש בנתונים ממקורות כמו Microsoft ושותפים אחרים כדי להעשיר את נתוני הלקוחות שלך לפני איחוד הנתונים. העשרות מקור הנתונים עוזרות לייצר שלמות ואיכות טובה יותר של נתונים, שיכולות לעזור להשיג תוצאות טובות לאחר איחוד הנתונים.

למידע נוסף, ראה [העשרה עבור מקורות נתונים (Preview)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>שנה את הבעלים של הסביבה

בעוד של מספר משתמשים יכולים להיות הרשאות ניהול ב- Customer Insights, רק אחד המשתמשים הוא הבעלים של סביבה. חוויה משופרת מאפשרת לך להחליף את הבעלים של סביבה ולתבוע בעלות אם הבעלים הקודמים עזב את הארגון. 

למידע נוסף, ראה [החלף את הבעלים של סביבה](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>תהליך הכנת הנתונים מפרט את הסיבה לרשומות פגומות

הכנת נתונים מציגה כעת את הסיבה לשחיתות עבור כל השדות עם נתונים פגומים. המידע מסופק ברמת הרשומה הבודדת לצורך זיהוי קל. 

למידע נוסף, ראה [מקורות נתונים פגומים](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>סוף ה-Preivew של תכונות דיווח ביכולת התובנות של מעורבות

התצוגה המקדימה של יכולת תובנות לגבי מעורבות של Dynamics 365 Customer Insights הסתיימה ב- 15 בפברואר 2022.  
המשמעות של שינוי זה היא שחוויית הניסיון של Customer Insights אינה כוללת עוד את היכולת ליצור משפכים או פונקציונליות דיווח אחרת.

אנו מזמינים אותך לחקור ולהעריך את התכונות הרבות האחרות של [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), פלטפורמת נתוני הלקוחות של Microsoft‏ (CDP).    
 
למשך תקופת מעבר, למשתתפי תצוגה מקדימה קיימים עדיין יש גישה לכמה יכולות ופונקציונליות של תצוגה מקדימה:

- קבל קוד למכשיר אתר או אפליקציה למכשירים ניידים 
- ראה אירועים ומאפייני אירועים 
- שפר פרופילים מאוחדים עם אירועים שנקלטו וממוקדים כדי ליהנות מהערך המלא של נתוני הלקוחות שלהם
  
הערה: במהלך תקופת המעבר, אירועים שנלכדו עוד מוזרמים ל- Data Lake המחובר. לאחר כיבוי הפונקציונליות הזו, שיתוף הנתונים ייפסק ולא יישלחו אירועים חדשים לאחסון המחובר.
צור קשר ישירות עם צוות חשבון Microsoft שלך אם יש לך שאלות לגבי ה-Preview של היכולת. צוות החשבון שלך ישאיר אותך מעודכן בהשקות הקרובות. 

## <a name="january-2022-updates"></a>עדכוני ינואר 2022

העדכונים בינואר 2022 כוללים תכונות חדשות, דירוגי ביצועים ותיקוני באגים.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>ניתוח הסנטימנט של משוב הלקוח

האפליקציה Customer Insights מספקת תכונה מבוססת AI חדשה, כדי לשלב את הסנטימנט של הלקוח ולזהות היבטים עסקיים ספציפיים בתור הזדמנויות לשיפורים ממוקדים. על-ידי ניתוח המשוב בכתב של הלקוחות שלך, תוכל לקבל תובנות מדויקות בעלות נמוכה. ניתוח הסנטימנט מבוסס על מודלים של עיבוד שפה טבעית (NLP), שיוצרים שתי תובנות נגזרות לכל מזהה לקוח. ניקוד הסנטימנט (בין 5 ל- 5-) ורשימת היבטים עסקיים רלוונטיים. 

לקבלת מידע נוסף, ראה [ניתוח סנטימנט במשוב הלקוח (תצוגה מקדימה)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]