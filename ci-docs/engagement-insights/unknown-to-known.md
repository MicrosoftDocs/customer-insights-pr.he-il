---
title: זיהוי אירועי אינטרנט ממבקרים שאומתו בעבר באמצעות 'לא ידוע לידוע'
description: התכונה 'לא ידוע לידוע' מאפשרת לשייך אירועים באתר למבקרים שאומתו בעבר.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: he-IL
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036784"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>זיהוי אירועי אינטרנט ממבקרים שאומתו בעבר

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

התכונה **לא ידוע לידוע** ביכולת התובנות לגבי מעורבות מאפשרת שיוך של אירועים באתר למבקרים שאומתו בעבר. אם התכונה אינה זמינה, מבקרים שאומתו במהלך ביקור קודם ועזבו לאחר מכן לא יזוהו בביקור חוזר אם לא יאומתו שוב. 

לדוגמה, אדם ביקר באתר בשבוע שעבר, נכנס לחשבון המשתמש שלו באתר ודפדף בקטלוג המוצרים. בשבוע שלאחר מכן האדם חוזר ומעיין במוצרים נוספים בלי להיכנס לחשבון. בעלי האתר המשתמש בתכונה **לא ידוע לידוע** יידע שאותו אדם חזר ומה הוא עשה באתר. הדבר מאפשר דיווח וניתוח מדויק יותר של הפעילויות באתר.

## <a name="enable-unknown-to-known"></a>הפוך את התכונה 'לא ידוע לידוע' לזמינה

עליך להיות [מנהל סביבת עבודה](user-roles.md) כדי להפוך תכונה זו לזמינה. 

1. בתובנות לגבי מעורבות, עבור אל **מנהל מערכת** > **סביבת עבודה**. 
2. בחר את הכרטיסיה **הגדרות**.
3. במקטע **לא ידוע לידוע**, הגדר את הלחצן הדו מצבי למצב **זמין**.

![הפוך את התכונה 'לא ידוע לידוע' לזמינה](media/U2Ktoggle.png "הפוך את התכונה 'לא ידוע לידוע' לזמינה")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>הוספת קוד JavaScript למקטע המעקב של האתר

אתר יכול ללכוד את ה- **authId של משתמש** עם ה- JavaScript לדוגמה הבא באמצעות [SDK לאינטרנט של תובנות לגבי מעורבות](advanced-SDK-implementation.md). כדי שהתכונה **ידוע ללא ידוע** תפעל, עליך ללכוד authId *וגם* להפעיל את userMapping:True במקטע JavaScript כמוצג בדוגמה למטה.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
