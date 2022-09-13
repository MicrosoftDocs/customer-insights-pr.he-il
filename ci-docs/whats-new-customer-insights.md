---
title: מה חדש ב- Dynamics 365 Customer Insights
description: מידע על תכונות חדשות, שיפורים ותיקוני באגים.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: acba06cba5fb5cbf0bca5aeb30b603003555fc32
ms.sourcegitcommit: 3ab8f1c0ba5874095a19f0b6367b9a4432f72ed1
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409358"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>מה חדש ב- Dynamics 365 Customer Insights

אנו גאים להכריז על העדכונים החדשים ביותר שלנו! מאמר זה מסכם תכונות של Public Preview, שיפורים בזמינות הכללית ועדכוני תכונות. כדי לראות את התוכניות ארוכות הטווח בנוגע לתכונות, ראה את [תוכניות ההפצה של ‎Dynamics 365 ושל Power Platform](/dynamics365/release-plans/).

אנו מפיצים עדכונים על בסיס אזורי. כך שאזורים מסוימים עשויים לראות תכונות לפני אזורים אחרים. אלא אם כן נקבע אחרת, אינך צריך לנקוט פעולה כלשהי, אנו נעדכן את האפליקציה אוטומטית וללא השבתה.

> [!TIP]
> כדי לשלוח בקשות לגבי תכונות וכן הצעות למוצרים ולהצביע עבורן, עבור אל [פורטל הרעיונות של Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>עדכוני אוגוסט 2022

העדכונים באוגוסט 2022 כוללים תכונות חדשות, דירוגי ביצועים ותיקוני באגים.

### <a name="contact-unification-in-b-to-b-environments"></a>איחוד אנשי קשר בסביבות B-to-B

סביבות B-to-B ב- Customer Insights תומכות כעת בחוויית איחוד נתונים משופרת.

כעת תוכל לאחד אנשי קשר בנוסף לחשבונות כדי לקבל תצוגה מלאה של אנשי הקשר העסקיים שלך. אנשי קשר מאוחדים משויכים לחשבונות מאוחדים והם רשומים כעת בכרטיסי הלקוחות. 

לקבלת מידע נוסף, ראה [יצירת פרופיל איש קשר מאוחד](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>יצירה וייצוא של פלחים על סמך אנשי קשר מאוחדים

הודות לתכונה החדשה של איחוד אנשי קשר, אתה יכול ליצור פלחים של אנשי קשר באמצעות קריטריונים מאנשי קשר, חשבונות או שניהם. ניתן לייצא פלחים אלו להפעלה בשירותים אחרים.

לקבלת מידע נוסף, ראה [מבט כולל על פעולות ייצוא‬](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>אזורי פריסה מותאמים ל- Microsoft Dataverse

בעת יצירת סביבת Customer Insights חדשה, תוכל לבחור את האזור שבו תרצה שהשירות יתפרס ויתארח. עדכנו את בחירת האזור כך שתתאים ל- Microsoft Dataverse ול- Power Platform.

כעת תוכל לבחור בקלות באותו אזור כמו סביבת Microsoft Dataverse הקיימת שלך או חשבון Azure Data Lake Storage (אם תבחר באפשרות זו), בכפוף לזמינות של Customer Insights באזור זה.

למידע נוסף, ראה [צור סביבה חדשה](create-environment.md) ו[זמינות המוצר לפי גיאוגרפיה](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>עדכוני יולי 2022

העדכונים ביולי 2022 כוללים תכונות חדשות, דירוגי ביצועים ותיקוני באגים.

### <a name="export-to-moengage"></a>ייצוא ל- MoEngage

יצא פלחים של פרופילי לקוחות מאוחדים ל- MoEngage והשתמש בהם עבור שיווק בדואר אלקטרוני ב- MoEngage.

לקבלת מידע נוסף, ראה [‏‫ייצוא פלחים אל MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>תמיכת SSH לייצוא מבוסס SFTP

בחר אם ברצונך לבצע אימות באמצעות SSH או שם משתמש/סיסמה עבור חיבורים ליעדי ייצוא מסוג SFTP.

לקבלת מידע נוסף, ראה [ייצוא נתונים למארחי SFTP](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>התאם אישית חוויות עם נתונים על משתמשים ידועים ולא ידועים

ניהול נתוני לקוחות אינו אתגר חדש, אך הוא הופך לקשה יותר ויותר בזמן שמשתמשים מנווטים בין הערוצים הדיגיטליים השונים שמוצעים על ידי מותגים. משתמש ידוע (מאומת) בערוץ אחד הופך ללא ידוע (לא מאומת) בערוץ אחר אם הוא לא מחובר. לעתים קרובות הבעיה היא שלמשתמשים לא מאומתים (לא ידועים) אין מזהה משותף. ניתן להשתמש בו כדי לשייך תכונות משמעותיות של פרופילים וליצור פרופילי לקוחות מאוחדים. Customer Insights עוזר לפתור בעיה זו על ידי קליטת נתונים משיטות מעקב במערכות המקור שלך.

למידע נוסף, ראה [התאם אישית את החוויות שלך עם נתונים על משתמשים ידועים ולא ידועים](unknown-to-known.md).

## <a name="june-2022-updates"></a>עדכוני יוני 2022

העדכונים ביוני 2022 כוללים תכונות חדשות, דירוגי ביצועים ותיקוני באגים.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>חוויית משתמש מעודכנת עבור מקורות נתונים וקליטת נתונים

ייבוא נתונים ממגוון רחב של מקורות נתונים הוא הבסיס לאיחוד נתוני הלקוחות שלך ב- Dynamics 365 Customer Insights. בדקנו מחדש את חוויית המשתמש עבור ייבוא וחיבור של מקורות נתונים. עדכון זה נועד להקל עליך לקלוט נתונים ל- Customer Insights.

לקבלת מידע נוסף, עיין ב[מבט כולל על מקורות נתונים](data-sources.md).

### <a name="export-to-inmobi"></a>ייצוא ל- InMobi

InMobi עוזר למותגים להבין, לזהות, לעסוק ולהשיג צרכנים. תוכל לייצא פלחים ונתונים אחרים לשירות InMobi דרך חשבונות Azure Blob Storage.

לקבלת מידע נוסף, ראה [ייצוא נתונים ל- InMobi ‏(Preview‏)‎](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>תמיכה בכספת ב- Customer Insights

כספת לקוח מספק ממשק לבדיקה ואישור (או דחיית) של בקשות גישה לנתונים. בקשות אלו מתרחשות כאשר יש צורך בגישה לנתונים של לקוחות כדי לפתור מקרה תמיכה.

לקבלת מידע נוסף, ראה [גישה מאובטחת לנתוני לקוח באמצעות כספת לקוח (‏Preview)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>התחבר לנתונים שלך באמצעות קישור פרטי של Azure

קישור פרטי של Azure מאפשר ל- Customer Insights להתחבר אל חשבון Azure Data Lake Storage שלך באמצעות נקודת קצה פרטית ברשת הוירטואלית שלך. עבור נתונים בחשבון אחסון שאינו חשוף לאינטרנט הציבורי, קישור פרטי מאפשר את החיבור לרשת מוגבלת זו.

למידע נוסף, ראה [שימוש בקישור פרטים ב- Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>עדכוני מאי 2022

העדכונים במהדורת מאי 2022 כוללים תכונות חדשות, שדרוגי ביצועים ותיקוני באגים.

### <a name="updated-data-unification-experience"></a>חוויית איחוד נתונים מעודכנת

 איחוד נתונים מאפשר לך לאחד מקורות נתונים שהיו נבדלים פעם אחת לתוך ערכת נתונים ראשית המספקת תצוגה אחידה של הנתונים הללו. ניתן לאחד נתונים בישות אחת או במספר ישויות. קודם [בוחרים ישויות ושדות מקור](map-entities.md), [מסירים רשומות כפולות](remove-duplicates.md), מציינים כללים עבור [תנאים תואמים](match-entities.md), ומגדירים איזה [שדות לכלול בפרופילי הלקוחות המאוחדים](merge-entities.md).

לקבלת מידע נוסף, עיין ב[מבט כולל על איחוד נתונים](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>דף הבית מרעונן ב- Customer Insights

הדף **בית** מדריך אותך בתהליך ההגדרה של תכונות עיקריות ומספק סקירה כללית על פלחים, מדדים ונתוני העשרה. ריעננו את החוויה כדי לספק מידע רלוונטי יותר במבט חטוף.

למידע נוסף, ראה [‏‫גילוי Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>מעקב אחר השימוש בפלח

עכשיו אפשר [לעקוב אחר השימוש בפלח](segments.md#track-usage-of-a-segment) באפליקציות שמבוססות על ארגון ה- Dataverse שמחובר ל- Customer Insights. עבור [פלחי Customer Insights המשמשים במסעות לקוחות של Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), המערכת מודיעה לך על השימוש בפלח זה.

### <a name="export-to-criteo"></a>ייצוא ל- Criteo

Criteo היא פלטפורמה מקוונת המסייעת למשתמשים לנהל פרסום דיגיטלי. עכשיו אפשר לייצא פלחים של פריטי unified customer profile כדי ליצור קמפיינים, לספק שיווק בדואר אלקטרוני ולהשתמש בקבוצות ספציפיות של לקוחות באמצעות Criteo.

לקבלת מידע נוסף, ראה [ייצוא נתונים ל- Criteo (preview)‎](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>מבנה תיעוד ממוקד ליצירת סביבה

בדקנו מחדש את מסמכי העזרה הקשורים ליצירה וניהול של סביבות ב- Customer Insights. המאמרים מקובצים כעת תחת הצומת 'סביבות' בתוכן העניינים. המאמרים המחודשים מספקים הדרכה רבה יותר לגבי הדרכים השונות להקמת סביבות ובעלות מבנה ברור יותר. אם יש לך משוב לשתף, הודע לנו באמצעות הפקדים לקראת סוף מאמרי העזרה.

לקבלת מידע נוסף, ראה [כיצד: ליצור סביבה חדשה](create-environment.md).

## <a name="april-2022-updates"></a>עדכוני אפריל 2022

העדכונים במהדורת אפריל 2022 כוללים תכונות חדשות, שדרוגי ביצועים ותיקוני באגים.

### <a name="dun--bradstreet-enrichment-preview"></a>העשרת Dun & Bradstreet‏ (Preview)

חברת Dun & Bradstreet מספקת נתונים מסחריים, ניתוחים ותובנות לעסקים. היא מאפשרת ללקוחות עם פרופילי לקוחות אחידים לחברות להעשיר את הנתונים שלהם. ההעשרה כוללת תכונות כגון מספר DUNS, גודל החברה, המיקום, הענף ועוד.

למידע נוסף, ראה [העשרת פרופילי החברה עם Dun & Bradstreet ‏(Preview)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>הגדר את סוג המדד בעת יצירת מדד חדש

כעת תוכל להבחין בין מדדים עבור פרופילים בודדים לבין מדדים שמתייחסים לכל העסק שלך. בעוד שמדדים עסקיים מופיעים בדף הבית של Customer Insights, מדדי לקוחות מופיעים בתצוגות הלקוחות המפורטות.

לפרטים נוספים, ראה [השתמש בבונה מדדים ליצירת מדדים מאפס](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>איחוד של תיעוד ב- Customer Insights

עדכנו את מאמרי התיעוד שלנו והסרנו אזכורים של יכולות לגבי תובנות ולגבי מעורבות וקהל. בהמשך נתייחס באופן עקבי לשם המוצר Customer Insights כאשר נכתוב על תכונות הליבה של האפליקציה. שינוי זה מביא גם לארגון משמעותי מחדש של תוכן העניינים, מבנה ה- URL ונתיבי הקבצים במאגר התיעוד הבסיסי. כל הסימניות או הקישורים הקיימים שלך ממשיכים לעבוד ולהפנות לכתובות האתרים המעודכנות.

אם אתה רוצה ליידע אותנו איך אתה תופס את השינוי הזה או אם תמצא משהו שלא עובד כצפוי, ספר לנו על ידי [שליחת משוב עבור דף זה](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

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

למידע נוסף ראה [הפיכת שיתוף נתונים באמצעות Dataverse מ- (Preview) Azure Data Lake Storage משלך לזמין](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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