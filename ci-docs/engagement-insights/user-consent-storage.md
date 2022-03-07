---
title: ניהול קבצי Cookie והסכמת משתמש לאחסון נתוני משתמש ב- Dynamics 365 Customer Insights
description: כיצד קובצי Cookie והסכמת משתמש משמשים לזיהוי של מבקרים באתר.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228986"
---
# <a name="manage-cookies-and-user-consent"></a>נהל קובצי Cookie והסכמת משתמש

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

יכולת התובנות לגבי מעורבות של Dynamics 365 Customer Insights משתמשת בקבצי Cookie ובמפתחות (`localStorage`) כדי לזהות מבקרים באתר אינטרנט.

קובצי Cookie הם קבצים קטנים המאחסנים פיסות מידע על האינטראקציות של המשתמש עם האתר. הם מאוחסנים בדפדפני האינטרנט. כאשר משתמש מבקר באתר שעבורו מאוחסנים קובצי Cookie אצל המשתמש, הדפדפן שולח את המידע לשרת, שמחזיר מידע שהוא ייחודי למשתמש. זו הטכנולוגיה המאפשרת, למשל, לעגלת קניות מקוונת לשמור פריטים נבחרים גם אם משתמש ממשיך לגלוש הרחק מהאתר.

## <a name="user-consent"></a>הסכמת משתמש

[התקנה הכללית להגנה על נתונים (GDPR)](/dynamics365/get-started/gdpr/) היא תקנה של האיחוד האירופי (EU) המכתיבה כיצד ארגונים צריכים לטפל בנושא פרטיותם וביטחונם של המשתמשים שלהם. לעתים קרובות קובצי Cookie מאחסנים או אוספים "נתונים אישיים", כגון מזהה מקוון, המכוסה על-ידי GDPR. אם העסק שלך מעסיק נושאי נתונים של האיחוד האירופי או מוכר להם, תקנת GDPR משפיעה עליך. [למידע נוסף על האופן שבו Microsoft יכולה לעזור לך לעמוד בתנאי ה- GDPR](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

כדי לאפשר ל- SDK של התובנות לגבי מעורבות לאחסן קובצי Cookie או מידע רגיש אחר, עליך לציין אם המשתמשים שלך הסכימו לכך. זה קורה בעת אתחול ה- SDK על-ידי הגדרת שדה `userConsent` בתצורה.

אם תציין שאין הסכמת משתמש, ה- SDK לא ישמור נתונים ולא ישלח אירועים שניתן להשתמש בהם כדי לעקוב אחר התנהגות המשתמש. כל הנתונים שנשמרו בעבר יימחקו מהדפדפן.

אם לא צויין ערך הסכמת המשתמש, ה- SDK יניח שהמשתמש נתן את הסכמתו. המשמעות היא שאם אתה (כלקוח שלנו) לא מציין ב- SDK ערך להסכמת המשתמש, איסוף הנתונים יתבצע. עם זאת, אם תציין שהערך של הסכמת המשתמש צריך להיות "true", הנתונים לא ייאספו אם המשתמש סירב או לא הצליח לספק הסכמה מפורשת.

להלן מקטע קוד לאתחול SDK של אינטרנט עם הסכמת משתמש:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>אחסון נתוני מבקרים ביכולת התובנות לגבי מעורבות

### <a name="cookies"></a>עוגיות

- _msei
    - מאחסן את מזהה המשתמש האנונימי. קובץ Cookie זה מוגדר בתחום הלקוח ותוקפו יפוג תוך 365 יום.

### <a name="local-storage"></a>אחסון מקומי

יכולת תובנות לגבי מעורבות משתמשת גם במפתחות (`localStorage`) כדי לעקוב אחר נתונים לא רגישים. נתונים אלה נשמרים במלואם בדפדפן עצמו, ללא תעבורה הנשלחת אל השרתים שלך או מהם.

- *EISession.Id*
    - מאחסן מידע על ההפעלה המתמשכת של המשתמש, כגון המזהה של ההפעלה, מתי התחילה ומתי תפוג.
- *EISession.Previous*
    - מאחסן את כתובת ה- URL של הדף שביקרת בו בעבר בהפעלה הנוכחית.

תוקף מפתחות באחסון המקומי לא פג באופן אוטומטי, והם יאופסו בהפעלת ה- SDK הבאה.

## <a name="deleting-cookies"></a>מחיקת קובצי Cookie

הלקוחות שלך יכולים למחוק באופן ידני קובצי Cookie ומפתחות אחסון מקומיים בכל עת באמצעות הגדרות הדפדפן שלהם.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
